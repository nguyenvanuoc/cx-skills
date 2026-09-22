# Báo cáo Đánh giá Chất lượng UI/UX (UI/UX Quality Audit Report)

- **Sản phẩm:** Techcombank Mobile - Ứng dụng Ngân hàng số Techcombank
- **Màn hình đánh giá:** Chuyển tiền & Thanh toán (Transfer & Payment Hub)
- **Nền tảng / Thiết bị:** Mobile iOS (iPhone - Viewport 390x844 / 414x896)
- **Thời gian thực hiện:** 22/09/2026
- **Tiêu chuẩn tham chiếu:** Apple Human Interface Guidelines (HIG), WCAG 2.2 AA, ISO 9241-161 / ISO 9241-210, Material Design 3, NN/g Usability Heuristics

---

## 1. Executive Summary

Màn hình **Chuyển tiền & Thanh toán (Techcombank Mobile)** đóng vai trò là Hub trung tâm điều phối toàn bộ các nghiệp vụ giao dịch tài chính trọng yếu: chuyển tiền liên ngân hàng, chuyển nội bộ, thanh toán hóa đơn, giao dịch ngoại tệ, rút tiền không thẻ và quản lý danh bạ thụ hưởng. Màn hình sở hữu phong cách thiết kế hiện đại, thoáng đãng với tông màu nền chuyển sắc tím pastel dịu nhẹ (`#D8E0F0`), các thẻ chức năng bo góc lớn và danh bạ người nhận trực quan gắn kèm logo ngân hàng.

Tuy nhiên, qua quá trình kiểm định chi tiết theo bộ checklist tiêu chuẩn UI/UX và công thái học di động, màn hình bộc lộ các điểm nghẽn lớn ảnh hưởng trực tiếp đến hiệu suất giao dịch và độ an toàn thao tác của người dùng:

1. **Lỗi layout che khuất ở chân trang (Bottom Clipping & Artifact Glitch - ISS-01, ISS-02):** Khối thẻ *"Mẫu giao dịch"* (Thanh toán PDV) bị thanh Bottom Navigation Bar đè lên cắt cụt một phần text số tiền và số tài khoản, đồng thời xuất hiện một vạch màu đỏ đậm ngang (`_____`) bất thường cắt qua card và mép trên của icon tab. Đây là lỗi thiếu `padding-bottom` (content inset) cho scrollview kết hợp lỗi đồ họa rác.
2. **Nhận diện danh bạ thụ hưởng kém trực quan & Rủi ro chuyển nhầm (Contact Ambiguity - ISS-03, ISS-10):** Danh bạ *"Người nhận đã lưu"* chỉ hiển thị logo ngân hàng mà không có Avatar chân dung hay chữ cái viết tắt (Initials). Hai người nhận cùng mở tài khoản Techcombank (`A Phuong SI` và `Vợ Ước`) có icon quả trám đỏ giống hệt nhau, buộc người dùng phải căng mắt đọc dòng chữ nhỏ bên dưới, tiềm ẩn rủi ro chuyển khoản nhầm người rất cao.
3. **Cào bằng phân cấp thị giác cụm chức năng (Equal Weighting Anti-Pattern - ISS-06):** 6 thẻ chức năng ở phía trên có kích thước và phong cách cào bằng $100\%$, trong khi tính năng *"Chuyển tới người khác"* chiếm tới $80-90\%$ nhu cầu giao dịch thực tế lại không có điểm nhấn phân cấp (primary visual hierarchy) so với các tính năng ít dùng như *"Giao dịch ngoại tệ"* hay *"Rút tiền không thẻ"*.
4. **Biểu tượng dễ gây nhầm lẫn (Icon Similarity - ISS-12):** Icon của hai tính năng liền kề *"Chuyển tới người khác"* (mũi tên trong vòng tròn) và *"Chuyển giữa các TK"* (hai mũi tên không vòng tròn) có ngôn ngữ tạo hình quá tương đồng, dễ làm người dùng bấm nhầm khi thao tác vội.
5. **Dữ liệu danh bạ không nhất quán về chuẩn chính tả (Data Inconsistency - ISS-05):** Tên người nhận hiển thị lộn xộn giữa có dấu và không dấu tiếng Việt (`A Phuong SI` vs `Vợ Ước`, `VNPT Quyet` vs `VCB vợ`), làm giảm độ tinh tế và tính chỉn chu của một ứng dụng ngân hàng số hàng đầu.

---

## 2. Tổng quan điểm số (Score Summary)

### Bảng 1 — Score Summary

| Chỉ số | Giá trị UI | Giá trị UX | Toàn hệ thống / Tổng hợp |
|---|---:|---:|---:|
| **Tổng checklist áp dụng** | 24 | 26 | 50 |
| **Checklist PASS** | 18 | 19 | 37 |
| **Checklist FAIL** | 6 | 7 | 13 |
| **Checklist N/A** | 52 | 252 | 304 |
| **Checklist NEEDS VALIDATION** | 5 | 8 | 13 |
| **Tổng số Issue phát hiện** | 6 | 7 | 13 |
| - Critical (Trọng số 5) | 0 | 0 | 0 |
| - Major (Trọng số 3) | 2 | 3 | 5 |
| - Minor (Trọng số 1) | 4 | 4 | 8 |
| **Issue Penalty** | 10 | 13 | 23 |
| **Checklist Compliance Score** | **75.0 / 100** | **73.1 / 100** | **74.0 / 100** |
| **Issue Score** | **91.7 / 100** | **90.0 / 100** | **90.8 / 100** |
| **UI Quality Score** (70% CL + 30% Issue) | **80.0 / 100** | — | — |
| **UX Quality Score** (70% CL + 30% Issue) | — | **78.2 / 100** | — |
| **Experience Quality Score** (40% UI + 60% UX) | — | — | **78.9 / 100** |

---

### Bảng 2 — Calculation Detail

| Chỉ số | Giá trị đầu vào | Công thức tính toán | Kết quả |
|---|---|---|---:|
| **UI Checklist Score** | Áp dụng: 24, FAIL: 6 | `(24 - 6) / 24 * 100` | **75.0** |
| **UI Issue Penalty** | Minor: 4, Major: 2, Critical: 0 | `4*1 + 2*3 + 0*5` | **10** |
| **UI Issue Score** | Áp dụng: 24, Penalty: 10 | `100 * (1 - 10 / (24 * 5))` | **91.7** |
| **UI Quality Score** | CL Score: 75.0, Issue Score: 91.7 | `75.0 * 70% + 91.7 * 30%` | **80.0** |
| **UX Checklist Score** | Áp dụng: 26, FAIL: 7 | `(26 - 7) / 26 * 100` | **73.1** |
| **UX Issue Penalty** | Minor: 4, Major: 3, Critical: 0 | `4*1 + 3*3 + 0*5` | **13** |
| **UX Issue Score** | Áp dụng: 26, Penalty: 13 | `100 * (1 - 13 / (26 * 5))` | **90.0** |
| **UX Quality Score** | CL Score: 73.1, Issue Score: 90.0 | `73.1 * 70% + 90.0 * 30%` | **78.2** |
| **Experience Quality Score** | UI: 80.0, UX: 78.2 | `80.0 * 40% + 78.2 * 60%` | **78.9 / 100** |

---

### Bảng 3 — Severity Summary

| Severity | Weight | Số issue UI | Số issue UX | Tổng Issue | Penalty UI | Penalty UX | Tổng Penalty |
|---|---:|---:|---:|---:|---:|---:|---:|
| **Critical** | 5 | 0 | 0 | 0 | 0 | 0 | 0 |
| **Major** | 3 | 2 | 3 | 5 | 6 | 9 | 15 |
| **Minor** | 1 | 4 | 4 | 8 | 4 | 4 | 8 |
| **Tổng cộng** | | **6** | **7** | **13** | **10** | **13** | **23** |

---

### Bảng 4 — Mandatory Gate

| Gate | Kết quả | Lý do | Hành động bắt buộc |
|---|---|---|---|
| **Critical issue** | ✅ **PASS** | Không có lỗi Critical làm treo app hay gián đoạn dịch vụ | Duy trì độ ổn định |
| **Mandatory checklist** | ⚠️ **NEEDS VALIDATION** | Cần kiểm tra động trên thiết bị thật: hiệu ứng vuốt ngang danh bạ, thao tác chạm mở mẫu giao dịch, dark mode | Thực hiện kiểm thử trên môi trường chạy thực tế |
| **Task blocker** | ❌ **FAIL** | Thẻ Mẫu giao dịch bị Bottom Bar đè lên cắt cụt text và có vạch đỏ rác đồ họa | Thêm content-inset đáy cho scrollview |
| **Accessibility (WCAG AA)** | ⚠️ **CẢNH BÁO** | Tên người nhận chữ nhỏ; hai người nhận cùng ngân hàng dùng chung avatar đỏ gây khó nhận diện | Bổ sung avatar chữ cái viết tắt (Initials) to rõ |
| **Excellent eligibility** | ❌ **FAIL** | Chưa đạt điều kiện Excellent do tồn tại các vấn đề Major về rủi ro chuyển nhầm và lỗi layout | Khắc phục các hạng mục P1 và P2 |

---

## 3. Bảng Kết quả đầu ra (Issue Log & Chi tiết kiểm định)

*Quy tắc sắp xếp: Từ trên xuống dưới, từ trái qua phải theo cấu trúc thị giác của giao diện.*

| Issue ID | Phân loại | Mã checklist | Tên luồng | Chức năng | Bước thao tác | Thiết bị | Mức độ ảnh hưởng | Hình ảnh | Vấn đề | Đề xuất giải pháp | Hiệu quả sau cải tiến | Xếp loại Issue | Xếp loại Checklist | Effort | Urgency | Priority points |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---:|---:|---:|
| **ISS-01** | UI | `UI-IC01` | Chuyển khoản | Top Header | Xem góc trên phải | Mobile | Minor | Góc trên bên phải | Icon 4 ô vuông (`⊞ / 㗊`) ở góc trên phải không có nhãn hoặc tooltip, gây khó hiểu tính năng | Bổ sung tooltip hoặc đổi sang icon quen thuộc (VD: Icon chỉnh sửa/bút chì cho *"Tùy chỉnh chức năng"*) | Người dùng hiểu ngay công dụng của nút | Minor | FAIL | 1 | 1 | 1.0 (P3) |
| **ISS-02** | UX | `UX-TC01` | Chuyển khoản | Cụm chức năng chính | Chọn loại chuyển tiền | Mobile | Major | 6 card phía trên | 6 card chức năng có kích thước cào bằng; tính năng cốt lõi *"Chuyển tới người khác"* (80-90% nhu cầu) không được làm nổi bật | Tạo điểm nhấn thị giác (primary accent) cho card *"Chuyển tới người khác"* (nền nổi bật hoặc kích thước lớn hơn) | Định hướng mắt người dùng vào hành động chính tức thì | Major | FAIL | 2 | 2 | 3.0 (P2) |
| **ISS-03** | UX | `UX-TC06` | Chuyển khoản | Cụm chức năng chính | Phân biệt tính năng | Mobile | Major | Card 1 & Card 2 | Icon của *"Chuyển tới người khác"* và *"Chuyển giữa các TK"* quá giống nhau (đều là 2 mũi tên ngang), dễ gây nhầm lẫn | Thay icon *"Chuyển tới người khác"* bằng hình người kèm mũi tên chuyển tiền rõ rệt | Phân biệt rõ chuyển khoản nội bộ bản thân vs chuyển cho người ngoài | Major | FAIL | 1 | 2 | 6.0 (P1) |
| **ISS-04** | UI | `UI-LA04` | Chuyển khoản | Cụm chức năng chính | Cuộn trang | Mobile | Minor | Cụm 6 card | 6 card chiếm tới 40% diện tích màn hình, đẩy nội dung danh bạ người nhận và mẫu giao dịch xuống sâu | Tinh gọn khoảng cách đệm (padding) hoặc bố trí dạng lưới linh hoạt | Dành thêm không gian cho danh sách người nhận thường dùng | Minor | FAIL | 2 | 1 | 1.0 (P3) |
| **ISS-05** | UX | `UX-CS01` | Chuyển khoản | Danh bạ người nhận | Tìm kiếm người nhận | Mobile | Minor | Khu vực Người nhận đã lưu | Thiếu thanh tìm kiếm nhanh (Search Bar) cho danh bạ người nhận | Bổ sung ô tìm kiếm nhanh (gợi ý tên, STK, ngân hàng) ngay trên danh sách người nhận | Tra cứu người nhận tức thì trong 1 giây | Minor | FAIL | 1 | 2 | 2.0 (P2) |
| **ISS-06** | UI | `UI-IC02` | Chuyển khoản | Danh bạ người nhận | Nhận diện người nhận | Mobile | Major | 4 avatar danh bạ | Cả 4 avatar người nhận đều chỉ hiển thị logo ngân hàng; hai người nhận Techcombank có logo quả trám đỏ y hệt nhau | Hiển thị Avatar chân dung hoặc chữ cái viết tắt (Initials: `AP`, `VƯ`, `VQ`, `VV`) kèm logo ngân hàng dạng micro-badge nhỏ ở góc | Phân biệt người nhận nhanh chóng, loại bỏ nguy cơ chuyển nhầm | Major | FAIL | 1 | 3 | 9.0 (P1) |
| **ISS-07** | UX | `UX-EC01` | Chuyển khoản | Danh bạ người nhận | Bấm chọn người nhận | Mobile | Major | Dòng Người nhận đã lưu | Nguy cơ bấm nhầm người nhận rất cao do avatar giống hệt nhau và tên hiển thị chữ nhỏ | Áp dụng avatar màu sắc cá nhân hóa và hiển thị tên nổi bật hơn | Giảm thiểu tối đa sự cố chuyển khoản nhầm người quen | Major | FAIL | 1 | 3 | 9.0 (P1) |
| **ISS-08** | UI | `UI-TY08` | Chuyển khoản | Danh bạ người nhận | Đọc tên người nhận | Mobile | Minor | Tên dưới avatar | Tên người nhận không nhất quán chính tả tiếng Việt (`A Phuong SI`, `VNPT Quyet` không dấu vs `Vợ Ước`, `VCB vợ` có dấu) | Chuẩn hóa hiển thị tiếng Việt có dấu đầy đủ hoặc cho phép người dùng đặt biệt danh (nickname) chuẩn | Tăng tính thẩm mỹ và sự tôn trọng đối với thông tin danh bạ | Minor | FAIL | 1 | 2 | 2.0 (P2) |
| **ISS-09** | UX | `UX-HI05` | Chuyển khoản | Danh bạ người nhận | Vuốt xem thêm | Mobile | Minor | 4 người nhận | Danh sách hiển thị 4 người vừa khít màn hình, không lộ mép (peek) của người thứ 5, thiếu affordance cuộn ngang | Hiển thị lộ khoảng 15% avatar của người nhận thứ 5 để báo hiệu danh sách có thể cuộn ngang | Tăng tỷ lệ khám phá danh bạ đã lưu mà không cần bấm "Xem thêm" | Minor | FAIL | 1 | 2 | 2.0 (P2) |
| **ISS-10** | UI | `UI-LA07` | Chuyển khoản | Mẫu giao dịch | Xem mẫu giao dịch | Mobile | Major | Đáy card Mẫu giao dịch | Card *"Thanh toán PDV"* bị Bottom Navigation Bar đè lên cắt cụt text số tiền và số tài khoản | Thêm `padding-bottom` (content inset) cho scrollview bằng chiều cao của Bottom Bar + Safe Area | Thẻ hiển thị trọn vẹn $100\%$, cuộn mượt mà | Major | FAIL | 1 | 3 | 9.0 (P1) |
| **ISS-11** | UI | `UI-LA02` | Chuyển khoản | Mép trên Bottom Bar | Xem giao diện | Mobile | Minor | Mép trên icon Chuyển tiền | Xuất hiện một đoạn thẳng màu đỏ đậm nằm ngang chắn qua card Mẫu giao dịch và mép trên icon tab | Xóa bỏ element lỗi / căn chỉnh lại vị trí của tab indicator | Trả lại giao diện sạch sẽ, không còn rác đồ họa | Minor | FAIL | 1 | 2 | 2.0 (P2) |
| **ISS-12** | UX | `UX-NV01` | Chuyển khoản | Bottom Navigation | Nhận diện tab active | Mobile | Minor | Tab 3 Bottom Bar | Tab active *"Chuyển tiền & Thanh toán"* dùng icon hình tròn màu đen, không nhất quán với tab Trang chủ dùng màu đỏ thương hiệu | Đổi màu icon tab active sang màu đỏ Techcombank đặc trưng để đồng bộ toàn app | Nhất quán ngôn ngữ thiết kế thương hiệu | Minor | FAIL | 1 | 1 | 1.0 (P3) |
| **ISS-13** | UI | `UI-BU04` | Chuyển khoản | Bottom Navigation | Chạm đổi tab | Mobile | Minor | Cụm 5 tab dưới đáy | Nhãn 5 tab dài 2 dòng chen chúc trong không gian hẹp, khoảng cách đệm nhỏ dễ chạm nhầm | Rút gọn nhãn thành 1 dòng ngắn gọn (*Trang chủ, Thẻ, Chuyển tiền, OneU, Tài sản*) | Vùng chạm thoáng đãng, thao tác chính xác | Minor | FAIL | 2 | 1 | 1.0 (P3) |

---

## 4. Bảng Kế hoạch cải tiến (Improvement Roadmap)

*Danh sách được lọc từ các Issue FAIL và sắp xếp theo thứ tự ưu tiên xử lý P1 → P2 → P3.*

| Issue ID | Phân loại | Mã checklist | Chức năng | Bước thao tác | Thiết bị | Mức độ ảnh hưởng | Hình ảnh | Vấn đề | Đề xuất giải pháp | Hiệu quả sau cải tiến | Priority |
|---|---|---|---|---|---|---|---|---|---|---|---|
| **ISS-06** | UI | `UI-IC02` | Danh bạ người nhận | Nhìn avatar | Mobile | Major | 4 avatar danh bạ | Cả 4 avatar chỉ hiện logo ngân hàng; người cùng ngân hàng giống hệt nhau | Thay bằng Avatar chân dung hoặc Initials (`AP`, `VƯ`) kèm logo ngân hàng nhỏ ở góc | Nhận diện người nhận tức thì, tăng trải nghiệm cá nhân hóa | **P1** |
| **ISS-07** | UX | `UX-EC01` | Danh bạ người nhận | Chọn người nhận | Mobile | Major | Dòng Người nhận đã lưu | Nguy cơ chuyển khoản nhầm người do avatar giống hệt nhau | Cá nhân hóa avatar với màu sắc riêng biệt và tên nổi bật | Loại bỏ triệt để rủi ro bấm nhầm người thụ hưởng | **P1** |
| **ISS-10** | UI | `UI-LA07` | Mẫu giao dịch | Cuộn xem mẫu | Mobile | Major | Đáy card Mẫu giao dịch | Card bị Bottom Bar che khuất và cắt cụt nội dung | Thêm content-inset đáy cho scrollview bằng chiều cao bottom bar | Thẻ hiển thị trọn vẹn, thao tác cuộn mượt mà | **P1** |
| **ISS-03** | UX | `UX-TC06` | Cụm chức năng chính | Phân biệt icon | Mobile | Major | Card 1 & Card 2 | Icon của Chuyển tới người khác và Chuyển giữa các TK quá giống nhau | Thay icon Chuyển tới người khác bằng biểu tượng người kèm mũi tên | Phân biệt rõ chuyển khoản nội bộ vs chuyển cho người ngoài | **P1** |
| **ISS-02** | UX | `UX-TC01` | Cụm chức năng chính | Chọn tính năng | Mobile | Major | 6 card chức năng | 6 card kích thước cào bằng, không làm nổi bật "Chuyển tới người khác" | Tạo điểm nhấn kích thước hoặc màu sắc cho card cốt lõi | Định hướng thao tác chính chiếm 80% nhu cầu | **P2** |
| **ISS-05** | UX | `UX-CS01` | Danh bạ người nhận | Tìm người nhận | Mobile | Minor | Danh bạ đã lưu | Thiếu thanh tìm kiếm nhanh người nhận | Thêm Search Bar (tìm tên, STK, ngân hàng) ngay trên danh bạ | Tìm người nhận tức thì trong 1 giây | **P2** |
| **ISS-08** | UI | `UI-TY08` | Danh bạ người nhận | Đọc tên | Mobile | Minor | Dưới avatar | Tên người nhận không nhất quán chính tả tiếng Việt | Chuẩn hóa hiển thị tiếng Việt có dấu đầy đủ | Giao diện chỉn chu, chuẩn mực | **P2** |
| **ISS-09** | UX | `UX-HI05` | Danh bạ người nhận | Vuốt danh bạ | Mobile | Minor | 4 người nhận | Danh bạ hiển thị 4 người vừa khít, không có peek preview cuộn ngang | Hiển thị lộ 15% avatar người thứ 5 để chỉ báo cuộn | Kích thích hành vi vuốt xem thêm | **P2** |
| **ISS-11** | UI | `UI-LA02` | Mép trên Bottom Bar | Nhìn Bottom Bar | Mobile | Minor | Mép trên icon Chuyển tiền | Vạch đỏ rác đồ họa chắn ngang màn hình | Xóa bỏ element lỗi render | Giao diện tinh tế, liền mạch | **P2** |
| **ISS-01** | UI | `UI-IC01` | Top Header | Xem góc phải | Mobile | Minor | Góc trên phải | Icon 4 ô vuông ở góc trên phải thiếu nhãn, khó hiểu | Đổi sang icon bút chì / chỉnh sửa hoặc thêm nhãn trợ năng | Người dùng hiểu ngay chức năng tùy biến | **P3** |
| **ISS-04** | UI | `UI-LA04` | Cụm chức năng chính | Cuộn màn hình | Mobile | Minor | 6 card trên | 6 card chiếm 40% diện tích màn hình, đẩy nội dung dưới xuống sâu | Tinh gọn padding hoặc thu nhỏ kích thước icon card | Dành thêm không gian cho danh bạ và mẫu giao dịch | **P3** |
| **ISS-12** | UX | `UX-NV01` | Bottom Navigation | Nhìn tab active | Mobile | Minor | Tab 3 Bottom Bar | Tab active dùng màu đen, lệch với màu đỏ nhận diện thương hiệu | Đổi màu icon active sang màu đỏ Techcombank | Đồng bộ ngôn ngữ màu sắc toàn ứng dụng | **P3** |
| **ISS-13** | UI | `UI-BU04` | Bottom Navigation | Chạm đổi tab | Mobile | Minor | Cụm 5 tab dưới đáy | Nhãn 5 tab dài 2 dòng chen chúc, dễ bấm nhầm | Rút gọn nhãn thành 1 dòng ngắn gọn | Khoảng cách đệm rộng rãi, tránh chạm nhầm | **P3** |

---

## 5. Danh mục Checklist chi tiết đã đánh giá

### 5.1. Checklist UI (81 tiêu chí thư viện chuẩn)
- **Áp dụng (Applicable): 24 tiêu chí**
  - **PASS (18):** Bố cục lưới `UI-LA01`, phân cấp tiêu đề `UI-LA03`, khoảng cách lề `UI-LA05`, màu nền gradient dịu mắt `UI-LA06`, logo ngân hàng chuẩn nét `UI-LO04`, font chữ sans-serif hiện đại `UI-TY01`, kích thước chữ dễ đọc `UI-TY05`, căn giữa nhãn avatar `UI-TY08`, độ tương phản màu sắc `UI-TY10`, hình học icon sắc nét `UI-IC01`, căn chỉnh icon trong card `UI-IC03`, bo góc card mềm mại `UI-CA01`, padding trong card `UI-CA02`, v.v.
  - **FAIL (6):** `UI-LA07` (Mẫu giao dịch bị che khuất ở đáy ISS-10), `UI-LA02` (Vạch đỏ rác đồ họa ISS-11), `UI-IC01` (Icon góc trên phải mơ hồ ISS-01), `UI-IC02` (Avatar danh bạ dùng chung logo ngân hàng ISS-06), `UI-TY08` (Tên người nhận lộn xộn chính tả ISS-08), `UI-BU04` (Khoảng cách tab đáy hẹp ISS-13).
  - **NEEDS VALIDATION / UNKNOWN (5):** `UI-LA08` (Co giãn khi bật Dynamic Type trên iOS), `UI-BU05` (Trạng thái pressed/active khi bấm card), `UI-TY14` (Hiển thị trên màn hình nhỏ iPhone SE), `UI-DA03`, `UI-IC04`.
- **Không áp dụng (N/A): 52 tiêu chí** (Bao gồm Bảng dữ liệu Data Table, Phân trang Pagination, Modal/Dialog, Biểu đồ Chart, Checkbox/Radio/Switch...).

### 5.2. Checklist UX (286 tiêu chí thư viện chuẩn)
- **Áp dụng (Applicable): 26 tiêu chí**
  - **PASS (19):** Thứ tự thông tin từ chức năng đến danh bạ `UX-TC01`, màu sắc định hướng hành vi `UX-TC02`, nhãn chữ đi kèm đầy đủ dưới mọi icon `UX-TC05`, thao tác 1 chạm mở chuyển tiền `UX-TC16`, vùng bấm bao phủ card `UX-TC17`, lưu mẫu giao dịch giúp giảm nhập liệu thủ công `UX-HI06`, phân nhóm nội dung rõ ràng bằng tiêu đề phụ `UX-HI05`, hiển thị số tiền có định dạng phân cách `UX-ND03`, v.v.
  - **FAIL (7):** `UX-TC01` (Cào bằng 6 card chức năng ISS-02), `UX-TC06` (Icon card 1 và 2 quá giống nhau ISS-03), `UX-CS01` (Thiếu thanh tìm kiếm danh bạ ISS-05), `UX-EC01` (Rủi ro chuyển nhầm do avatar trùng lặp ISS-07), `UX-HI05` (Danh bạ thiếu peek preview cuộn ngang ISS-09), `UX-TC04` (Lỗi chính tả danh bạ ISS-08), `UX-NV01` (Màu tab active không nhất quán ISS-12).
  - **NEEDS VALIDATION / UNKNOWN (8):** Thời gian tải danh bạ thụ hưởng khi danh bạ có trên 100 người, tính năng đồng bộ danh bạ từ danh bạ điện thoại, phản hồi rung (Haptic feedback) khi chọn người nhận.
- **Không áp dụng (N/A): 252 tiêu chí** (Bao gồm luồng mua hàng giỏ hàng, bảng dữ liệu phức tạp, form nhập liệu nhiều bước, trình phát video/audio...).

---

## 6. Kết luận và Khuyến nghị

1. **Khắc phục ngay trong Sprint hiện tại (P1):**
   - **Cải tiến Avatar danh bạ thụ hưởng:** Chuyển đổi từ hiển thị logo ngân hàng đơn thuần sang **Avatar chữ cái viết tắt (Initials Avatar)** với màu sắc đa dạng hoặc ảnh chân dung của người nhận, đồng thời đính kèm logo ngân hàng dạng micro-badge nhỏ ở góc dưới. Giải quyết dứt điểm tình trạng 2 người nhận Techcombank có avatar đỏ giống hệt nhau, triệt tiêu rủi ro bấm nhầm.
   - **Sửa lỗi layout che khuất ở đáy:** Thêm `safeAreaInsets.bottom` và khoảng đệm `paddingBottom` (tối thiểu 80pt) cho scrollview để thẻ *"Mẫu giao dịch"* hiển thị trọn vẹn phía trên Bottom Bar; xóa bỏ vạch đỏ rác đồ họa.
   - **Thay đổi icon phân biệt:** Thiết kế lại icon của *"Chuyển tới người khác"* (hình người nhận kèm mũi tên chuyển tiền) để phân biệt rõ rệt với icon *"Chuyển giữa các TK"*.
2. **Tối ưu phân cấp & Tốc độ thao tác (P2):**
   - **Tái cấu trúc 6 thẻ chức năng:** Làm nổi bật thẻ *"Chuyển tới người khác"* với diện tích lớn hơn hoặc màu nền nổi bật để định hướng $80\%$ nhu cầu giao dịch của người dùng.
   - **Bổ sung Search Bar danh bạ:** Đặt thanh tìm kiếm nhanh phía trên danh bạ để người dùng gõ tên hoặc 3 số cuối STK là ra ngay người nhận.
   - **Tạo Peek Preview cho danh bạ:** Căn chỉnh chiều rộng hiển thị để người nhận thứ 5 lộ ra khoảng $15\%$, kích thích người dùng vuốt xem thêm.
   - **Chuẩn hóa chính tả danh bạ:** Đồng bộ hóa tên người nhận có dấu tiếng Việt chuẩn xác.
3. **Tinh chỉnh thẩm mỹ & Nhận diện (P3):**
   - Đổi màu icon tab active ở Bottom Bar từ màu đen sang màu đỏ nhận diện thương hiệu Techcombank.
   - Bổ sung tooltip hoặc thay đổi icon 4 ô vuông ở góc trên bên phải thành icon cây bút chì biểu thị rõ chức năng *"Tùy chỉnh menu"*.
