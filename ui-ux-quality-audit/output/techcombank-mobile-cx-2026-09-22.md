# Báo cáo Đánh giá Chất lượng UI/UX (UI/UX Quality Audit Report)

- **Sản phẩm:** Techcombank Mobile - Ứng dụng Ngân hàng số Techcombank
- **Màn hình đánh giá:** Trang chủ (Home Screen)
- **Nền tảng / Thiết bị:** Mobile iOS (iPhone - Viewport 390x844 / 414x896)
- **Thời gian thực hiện:** 22/09/2026
- **Tiêu chuẩn tham chiếu:** Apple Human Interface Guidelines (HIG), WCAG 2.2 AA, ISO 9241-161 / ISO 9241-210, Material Design 3

---

## 1. Executive Summary

Màn hình **Trang chủ (Home Screen) Techcombank Mobile** mang phong cách thiết kế hiện đại với nhận diện thương hiệu đỏ rực rỡ đặc trưng của Techcombank, kết hợp họa tiết quả trám đa lớp và hệ thống thẻ bo góc mềm mại. Ứng dụng tích hợp đa dạng dịch vụ từ quản lý số dư, phím tắt thanh toán, tích điểm OneU đến gợi ý ưu đãi cá nhân hóa.

Tuy nhiên, qua quá trình kiểm định chi tiết theo bộ checklist chuẩn UI/UX và công thái học di động (Mobile Usability), màn hình bộc lộ một số bất cập lớn ảnh hưởng trực tiếp đến trải nghiệm thị giác và thao tác của người dùng:

1. **Lỗi che khuất giao diện ở đáy màn hình (Layout Clipping / Scrollview Overlap):** Nút kêu gọi hành động (CTA) *"Khám phá ngay"* trong khối *"Dành cho bạn"* bị thanh điều hướng đáy (Bottom Navigation Bar) đè lên và cắt mất một phần chiều cao (kèm một vạch đỏ ngang bất thường). Nguyên nhân do scroll container thiếu `padding-bottom` (content inset) tương ứng với chiều cao của bottom bar.
2. **Bố cục thẻ số dư bất cân xứng (Asymmetrical Balance Card):** Khối thẻ *"Số dư hiện có"* bị co cụm dồn hẳn sang 60% bên phải màn hình, để lại khoảng trống lớn bên trái chỉ có hình họa quả trám mờ và 2 đồng xu vàng, gây mất cân bằng thị giác nghiêm trọng.
3. **Quảng cáo chèn ép tính năng quản lý tài chính:** Khối upsell gói tiết kiệm (*"An tâm sinh lời, xây tương lai..."*) chiếm tới ~65% diện tích Thẻ số dư chính, làm phân tán và lấn át mục đích cốt lõi của người dùng khi truy cập app ngân hàng (tra cứu số dư và giao dịch nhanh).
4. **Biểu tượng không chuẩn ngành (Unconventional Metaphors):** Tính năng tài chính *"Sinh lời tự động"* sử dụng icon khuôn mặt cười đeo kính lúp xa lạ; tab *"Tổng quan tài sản"* ở thanh điều hướng sử dụng icon bóng đèn (thường là biểu tượng gợi ý/ý tưởng), gây khó hiểu cho người dùng mới.
5. **Thiếu dấu hiệu nhận biết trượt ngang (Missing Carousel Affordance):** Section *"Dành cho bạn"* là dạng danh sách trượt ngang (horizontal carousel) nhưng hiển thị vừa khít 100% bề rộng, không có phần lộ ra (peek) của thẻ tiếp theo và thiếu hoàn toàn thanh chỉ báo trang (pagination dots).

---

## 2. Tổng quan điểm số (Score Summary)

### Bảng 1 — Score Summary

| Chỉ số | Giá trị UI | Giá trị UX | Toàn hệ thống / Tổng hợp |
|---|---:|---:|---:|
| **Tổng checklist áp dụng** | 24 | 26 | 50 |
| **Checklist PASS** | 19 | 18 | 37 |
| **Checklist FAIL** | 5 | 8 | 13 |
| **Checklist N/A** | 52 | 252 | 304 |
| **Checklist NEEDS VALIDATION** | 5 | 8 | 13 |
| **Tổng số Issue phát hiện** | 5 | 8 | 13 |
| - Critical (Trọng số 5) | 0 | 0 | 0 |
| - Major (Trọng số 3) | 2 | 3 | 5 |
| - Minor (Trọng số 1) | 3 | 5 | 8 |
| **Issue Penalty** | 9 | 14 | 23 |
| **Checklist Compliance Score** | **79.2 / 100** | **69.2 / 100** | **74.0 / 100** |
| **Issue Score** | **92.5 / 100** | **89.2 / 100** | **90.8 / 100** |
| **UI Quality Score** (70% CL + 30% Issue) | **83.2 / 100** | — | — |
| **UX Quality Score** (70% CL + 30% Issue) | — | **75.2 / 100** | — |
| **Experience Quality Score** (40% UI + 60% UX) | — | — | **78.4 / 100** |

---

### Bảng 2 — Calculation Detail

| Chỉ số | Giá trị đầu vào | Công thức tính toán | Kết quả |
|---|---|---|---:|
| **UI Checklist Score** | Áp dụng: 24, FAIL: 5 | `(24 - 5) / 24 * 100` | **79.2** |
| **UI Issue Penalty** | Minor: 3, Major: 2, Critical: 0 | `3*1 + 2*3 + 0*5` | **9** |
| **UI Issue Score** | Áp dụng: 24, Penalty: 9 | `100 * (1 - 9 / (24 * 5))` | **92.5** |
| **UI Quality Score** | CL Score: 79.2, Issue Score: 92.5 | `79.2 * 70% + 92.5 * 30%` | **83.2** |
| **UX Checklist Score** | Áp dụng: 26, FAIL: 8 | `(26 - 8) / 26 * 100` | **69.2** |
| **UX Issue Penalty** | Minor: 5, Major: 3, Critical: 0 | `5*1 + 3*3 + 0*5` | **14** |
| **UX Issue Score** | Áp dụng: 26, Penalty: 14 | `100 * (1 - 14 / (26 * 5))` | **89.2** |
| **UX Quality Score** | CL Score: 69.2, Issue Score: 89.2 | `69.2 * 70% + 89.2 * 30%` | **75.2** |
| **Experience Quality Score** | UI: 83.2, UX: 75.2 | `83.2 * 40% + 75.2 * 60%` | **78.4 / 100** |

---

### Bảng 3 — Severity Summary

| Severity | Weight | Số issue UI | Số issue UX | Tổng Issue | Penalty UI | Penalty UX | Tổng Penalty |
|---|---:|---:|---:|---:|---:|---:|---:|
| **Critical** | 5 | 0 | 0 | 0 | 0 | 0 | 0 |
| **Major** | 3 | 2 | 3 | 5 | 6 | 9 | 15 |
| **Minor** | 1 | 3 | 5 | 8 | 3 | 5 | 8 |
| **Tổng cộng** | | **5** | **8** | **13** | **9** | **14** | **23** |

---

### Bảng 4 — Mandatory Gate

| Gate | Kết quả | Lý do | Hành động bắt buộc |
|---|---|---|---|
| **Critical issue** | ✅ **PASS** | Không phát sinh lỗi Critical chặn hoàn toàn hệ thống | Duy trì chất lượng bảo mật và ổn định |
| **Mandatory checklist** | ⚠️ **NEEDS VALIDATION** | Cần kiểm tra động trên thiết bị thật (animation swipe carousel, mở ẩn số dư, chế độ Dark mode, độ nhạy cảm ứng) | Kiểm thử trực tiếp trên các dòng máy iOS / Android |
| **Task blocker** | ❌ **FAIL** | Nút CTA *"Khám phá ngay"* bị Bottom Bar che khuất một phần và có vạch đỏ rác đồ họa | Thêm content-inset bottom cho scrollview |
| **Accessibility (WCAG AA)** | ⚠️ **CẢNH BÁO** | Nhãn quick action chữ nhỏ xuống dòng dày đặc; icon con mắt ẩn số dư có hit target nhỏ | Mở rộng diện tích chạm $\ge 44\times44\text{pt}$ theo Apple HIG |
| **Excellent eligibility** | ❌ **FAIL** | Chưa đủ điều kiện xếp loại Excellent do còn tồn tại lỗi che khuất layout và các bất hợp lý về cấu trúc thẻ | Khắc phục các hạng mục P1 và P2 |

---

## 3. Bảng Kết quả đầu ra (Issue Log & Chi tiết kiểm định)

*Quy tắc sắp xếp: Từ trên xuống dưới, từ trái qua phải theo cấu trúc thị giác của giao diện.*

| Issue ID | Phân loại | Mã checklist | Tên luồng | Chức năng | Bước thao tác | Thiết bị | Mức độ ảnh hưởng | Hình ảnh | Vấn đề | Đề xuất giải pháp | Hiệu quả sau cải tiến | Xếp loại Issue | Xếp loại Checklist | Effort | Urgency | Priority points |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---:|---:|---:|
| **ISS-01** | UI | `UI-LA01` | Trang chủ | Thẻ số dư | Xem trang chủ | Mobile iOS | Major | Nửa trên màn hình | Thẻ *"Số dư hiện có"* bị đặt lệch sang phải, để trống nửa trái chỉ có hình trang trí quả trám, gây mất cân đối thị giác | Cân đối lại thẻ số dư tràn ngang (full-width card) hoặc chia đôi layout khoa học hơn | Bố cục cân đối, tận dụng tối ưu không gian hiển thị thông tin tài khoản | Major | FAIL | 2 | 2 | 3.0 (P2) |
| **ISS-02** | UX | `UX-TC01` | Trang chủ | Thẻ số dư | Xem số dư tài khoản | Mobile iOS | Major | Khối thẻ số dư | Khối quảng cáo tiết kiệm (*"An tâm sinh lời..."*) chiếm tới 65% diện tích Thẻ số dư, lấn át chức năng chính | Tách khối tiết kiệm thành banner phụ riêng biệt bên dưới, trả lại không gian cho các tiện ích số dư (sao kê, chi tiết tài khoản) | Người dùng tập trung kiểm tra tài chính nhanh mà không bị rối mắt bởi quảng cáo | Major | FAIL | 2 | 3 | 4.5 (P2) |
| **ISS-03** | UX | `UX-EC01` | Trang chủ | Thẻ số dư | Ẩn/Hiện số dư | Mobile iOS | Minor | Icon con mắt | Icon con mắt ẩn số dư có diện tích chạm (touch target) nhỏ, dễ bấm trượt vào thân thẻ | Mở rộng vùng bấm vô hình (min $44\times44\text{pt}$) hoặc cho phép chạm trực tiếp vào dòng dấu hoa thị để bật/tắt | Thao tác bật/mở số dư nhạy và chính xác hơn | Minor | FAIL | 1 | 1 | 1.0 (P3) |
| **ISS-04** | UX | `UX-TC07` | Trang chủ | Huy hiệu OneU | Khám phá ưu đãi | Mobile iOS | Minor | Huy hiệu góc trái | Huy hiệu *"Tích U-Point Săn deal chất"* đặt lơ lửng trên nền đỏ, không có affordance nút bấm rõ ràng | Bổ sung container mờ, viền nhẹ hoặc gắn thêm icon mũi tên `>` để chỉ thị đây là liên kết có thể bấm | Người dùng dễ dàng nhận diện và tương tác với chương trình ưu đãi | Minor | FAIL | 1 | 1 | 1.0 (P3) |
| **ISS-05** | UI | `UI-TY08` | Trang chủ | Phím tắt nhanh | Đọc nhãn tính năng | Mobile iOS | Minor | Khối Quick Actions | Cả 5 nhãn tính năng đều bị ngắt rớt xuống 2 dòng, khoảng cách chữ và dòng sít sao | Tinh giản từ ngữ (VD: *Tiết kiệm, Hóa đơn, Quét QR, Sinh lời, Thêm*) hoặc điều chỉnh font size/tracking | Nhãn chữ thoáng đãng, dễ quét mắt khi dùng một tay | Minor | FAIL | 1 | 2 | 2.0 (P2) |
| **ISS-06** | UX | `UX-TC01` | Trang chủ | Phím tắt nhanh | Quét mã thanh toán | Mobile iOS | Minor | Phím tắt Quét mã QR | Tính năng cốt lõi *"Quét mã QR"* bị xếp ngang hàng ở vị trí thứ 3 trong cụm icon nhỏ, thiếu điểm nhấn | Tạo viền highlight nổi bật hoặc đưa nút QR ra vị trí trung tâm nổi trên Bottom Bar | Người dùng mở và quét mã thanh toán tức thì trong 1 giây | Minor | FAIL | 1 | 2 | 2.0 (P2) |
| **ISS-07** | UX | `UX-TC06` | Trang chủ | Phím tắt nhanh | Nhận biết tính năng | Mobile iOS | Major | Icon Sinh lời tự động | Dùng icon "khuôn mặt cười đeo kính 1 mắt" cho tính năng *"Sinh lời tự động"*, vi phạm tính quen thuộc | Đổi sang biểu tượng chuẩn tài chính (Biểu đồ tăng trưởng, Cây tiền, Ký hiệu % sinh lời) | Trực quan, người dùng nhận biết ngay bản chất sinh lời tài chính | Major | FAIL | 1 | 3 | 9.0 (P1) |
| **ISS-08** | UX | `UX-TC04` | Ưu đãi | Khối Dành cho bạn | Đọc nội dung ưu đãi | Mobile iOS | Minor | Banner Dành cho bạn | Câu chữ thiếu tự nhiên và thiếu giới từ: *"nhiệm vụ dành riêng bạn"* | Biên tập lại ngữ pháp chuẩn xác: *"nhiệm vụ dành riêng cho bạn"* | Câu văn trau chuốt, nâng cao sự tin cậy của sản phẩm tài chính | Minor | FAIL | 1 | 1 | 1.0 (P3) |
| **ISS-09** | UX | `UX-NV02` | Ưu đãi | Khối Dành cho bạn | Khám phá ưu đãi | Mobile iOS | Major | Khối Dành cho bạn | Banner trượt ngang nhưng chiếm trọn chiều rộng, không lộ mép thẻ tiếp theo và không có pagination dots | Thiết kế dạng peek carousel (lộ 10-15% thẻ sau) và thêm hàng chấm tròn chỉ báo số lượng thẻ | Tăng tỷ lệ khám phá và tương tác với các chương trình ưu đãi khác | Major | FAIL | 1 | 3 | 9.0 (P1) |
| **ISS-10** | UI | `UI-LA07` | Trang chủ | Khối Dành cho bạn & Bottom Bar | Nhấn nút CTA | Mobile iOS | Major | Chân nút Khám phá ngay | Nút *"Khám phá ngay"* bị thanh Bottom Navigation Bar đè lên cắt cụt chân nút, có đường vạch đỏ rác đồ họa | Bổ sung `padding-bottom` (content inset) cho scrollview bằng chiều cao bottom bar + safe area | Nội dung cuộn mượt mà, nút CTA hiển thị trọn vẹn và bấm chính xác | Major | FAIL | 1 | 3 | 9.0 (P1) |
| **ISS-11** | UI | `UI-LA02` | Trang chủ | Mép trên Bottom Bar | Xem giao diện | Mobile iOS | Minor | Trên icon Trang chủ | Vạch màu đỏ đậm nằm ngang bất thường chắn trên mép icon Trang chủ | Kiểm tra và xóa thành phần đồ họa lỗi / đường phân cách bị render lệch | Loại bỏ visual glitch, trả lại sự liền mạch cho thanh điều hướng | Minor | FAIL | 1 | 2 | 2.0 (P2) |
| **ISS-12** | UX | `UX-TC06` | Điều hướng | Bottom Bar | Chọn tab Tài sản | Mobile iOS | Minor | Tab Tổng quan tài sản | Sử dụng icon bóng đèn (thường là ý tưởng/mẹo) đại diện cho *"Tổng quan tài sản"* | Thay bằng icon két sắt, ví tài sản hoặc biểu đồ phân bổ danh mục tài sản chuẩn | Thể hiện đúng bản chất quản lý danh mục tài sản | Minor | FAIL | 1 | 1 | 1.0 (P3) |
| **ISS-13** | UI | `UI-BU04` | Điều hướng | Bottom Bar | Chuyển đổi tab | Mobile iOS | Minor | Cụm 5 tab dưới đáy | 5 tab có nhãn dài 2 dòng nằm chen chúc, khoảng cách giữa các tab hẹp dễ chạm nhầm | Tối ưu nhãn ngắn gọn 1 dòng (VD: *Trang chủ, Thẻ & TK, Chuyển tiền, OneU, Tài sản*) | Tránh nhấn nhầm tab lân cận, giao diện thoáng đãng | Minor | FAIL | 2 | 2 | 1.0 (P3) |

---

## 4. Bảng Kế hoạch cải tiến (Improvement Roadmap)

*Danh sách được lọc từ các Issue FAIL và sắp xếp theo thứ tự ưu tiên xử lý P1 → P2 → P3.*

| Issue ID | Phân loại | Mã checklist | Chức năng | Bước thao tác | Thiết bị | Mức độ ảnh hưởng | Hình ảnh | Vấn đề | Đề xuất giải pháp | Hiệu quả sau cải tiến | Priority |
|---|---|---|---|---|---|---|---|---|---|---|---|
| **ISS-07** | UX | `UX-TC06` | Nhận biết tính năng | Xem phím tắt | Mobile iOS | Major | Icon Sinh lời | Dùng icon mặt cười đeo kính xa lạ cho *"Sinh lời tự động"* | Đổi sang icon biểu đồ tài chính tăng trưởng hoặc ký hiệu % | Nhận diện đúng bản chất tính năng tài chính ngay từ cái nhìn đầu tiên | **P1** |
| **ISS-09** | UX | `UX-NV02` | Khám phá ưu đãi | Vuốt danh sách | Mobile iOS | Major | Khối Dành cho bạn | Carousel không có peek preview và thiếu pagination dots | Thiết kế lộ 10-15% thẻ sau kèm dãy chấm tròn chỉ số trang | Tăng tỷ lệ khám phá (discoverability) các ưu đãi cá nhân hóa | **P1** |
| **ISS-10** | UI | `UI-LA07` | Thao tác nút CTA | Cuộn & Nhấn nút | Mobile iOS | Major | Nút Khám phá ngay | Nút CTA bị Bottom Bar che khuất và có vạch đỏ rác đồ họa | Thêm content-inset đáy cho scrollview bằng chiều cao bottom bar | Loại bỏ lỗi che khuất, nút bấm hiển thị đầy đủ và dễ thao tác | **P1** |
| **ISS-01** | UI | `UI-LA01` | Xem thẻ số dư | Mở ứng dụng | Mobile iOS | Major | Thẻ số dư | Thẻ số dư bị dồn sang phải, bố cục bất cân xứng | Tái thiết kế thẻ số dư trải rộng cân đối toàn màn hình | Cấu trúc cân đối, tạo ấn tượng chuyên nghiệp | **P2** |
| **ISS-02** | UX | `UX-TC01` | Xem số dư tài khoản | Mở thẻ số dư | Mobile iOS | Major | Khối thẻ số dư | Quảng cáo tiết kiệm lấn át 65% diện tích thẻ số dư | Tách nội dung tiết kiệm thành banner phụ riêng biệt | Người dùng tập trung quản lý số dư nhanh chóng | **P2** |
| **ISS-05** | UI | `UI-TY08` | Đọc phím tắt | Quét mắt phím tắt | Mobile iOS | Minor | Cụm Quick Actions | Nhãn tính năng bị rớt 2 dòng chen chúc, chữ nhỏ | Rút gọn từ ngữ thành 1 dòng (*Tiết kiệm, Hóa đơn, Quét QR, Sinh lời, Khác*) | Nhãn thoáng đãng, dễ đọc nhanh | **P2** |
| **ISS-06** | UX | `UX-TC01` | Quét mã thanh toán | Chạm phím tắt | Mobile iOS | Minor | Icon Quét mã QR | Tính năng quét QR thanh toán cốt lõi bị chìm | Tạo viền màu nổi bật hoặc đặt vị trí trung tâm nổi trên Bottom Bar | Tối ưu tốc độ thanh toán ngoài đời thực | **P2** |
| **ISS-11** | UI | `UI-LA02` | Xem điều hướng | Nhìn Bottom Bar | Mobile iOS | Minor | Mép trên Bottom Bar | Xuất hiện vạch đỏ đồ họa rác chắn trên icon Trang chủ | Xóa bỏ element lỗi hoặc sửa vị trí đường phân cách | Giao diện tinh tế, không còn lỗi hiển thị | **P2** |
| **ISS-03** | UX | `UX-EC01` | Ẩn/Hiện số dư | Nhấn icon con mắt | Mobile iOS | Minor | Icon con mắt | Vùng chạm icon con mắt nhỏ, dễ chạm nhầm | Mở rộng vùng bấm $\ge 44\times44\text{pt}$ hoặc cho phép chạm trực tiếp dòng số dư | Thao tác bảo mật nhanh và mượt mà | **P3** |
| **ISS-04** | UX | `UX-TC07` | Khám phá OneU | Nhìn huy hiệu | Mobile iOS | Minor | Huy hiệu góc trái | Huy hiệu lơ lửng không rõ có phải nút bấm hay không | Thêm nền mờ, bo viền nhẹ và icon điều hướng `>` | Người dùng nhận biết ngay đây là nút bấm ưu đãi | **P3** |
| **ISS-08** | UX | `UX-TC04` | Đọc nội dung ưu đãi | Đọc banner | Mobile iOS | Minor | Banner Dành cho bạn | Câu chữ thiếu tự nhiên: *"nhiệm vụ dành riêng bạn"* | Sửa thành *"nhiệm vụ dành riêng cho bạn"* | Văn phong trau chuốt, tăng tính tin cậy | **P3** |
| **ISS-12** | UX | `UX-TC06` | Chọn tab Tài sản | Chạm tab Bottom Bar | Mobile iOS | Minor | Tab Tài sản | Icon bóng đèn chưa chuẩn ngữ cảnh *"Tổng quan tài sản"* | Thay bằng icon két sắt hoặc biểu đồ danh mục tài sản | Icon phản ánh chính xác nghiệp vụ | **P3** |
| **ISS-13** | UI | `UI-BU04` | Chuyển đổi tab | Chạm Bottom Bar | Mobile iOS | Minor | Thanh Bottom Bar | Nhãn 5 tab dài 2 dòng chen chúc, dễ bấm nhầm | Rút gọn nhãn thành 1 dòng ngắn gọn (*Trang chủ, Thẻ, Chuyển tiền, OneU, Tài sản*) | Vùng chạm rộng rãi, hạn chế bấm nhầm tab | **P3** |

---

## 5. Danh mục Checklist chi tiết đã đánh giá

### 5.1. Checklist UI (81 tiêu chí thư viện chuẩn)
- **Áp dụng (Applicable): 24 tiêu chí**
  - **PASS (19):** `UI-LA03` (Phân cấp thị giác rõ ràng), `UI-LA04` (Gom nhóm nội dung bằng khoảng trắng), `UI-LA05` (Spacing scale nhất quán), `UI-LA06` (Màu sắc và độ tương phản nền đỏ chữ trắng), `UI-LO01` (Họa tiết nhận diện thương hiệu Techcombank), `UI-LO02` (Tỷ lệ icon biểu trưng), `UI-LO04` (Độ nét hình ảnh), `UI-TY01` (Font chữ hiện đại không chân), `UI-TY02` (Độ rõ ràng của văn bản), `UI-TY03` (Phân cấp kích thước chữ), `UI-TY04` (Thứ bậc heading - body), `UI-TY05` (Kích thước chữ đọc tốt trên mobile), `UI-TY06` (Line-height), `UI-TY07` (Khoảng cách đoạn), `UI-TY09` (Không lạm dụng viết hoa), `UI-TY10` (Độ tương phản chữ đạt WCAG), `UI-IC01` (Ngôn ngữ hình học icon thống nhất), `UI-IC02` (Kích thước icon cân đối), `UI-CA01` (Ngôn ngữ thẻ bo góc mềm mại).
  - **FAIL (5):** `UI-LA01` (Bố cục thẻ số dư mất cân bằng ISS-01), `UI-TY08` (Nhãn quick action rớt 2 dòng chen chúc ISS-05), `UI-LA07` (Nội dung và nút CTA bị bottom bar đè lên ISS-10), `UI-LA02` (Vạch đỏ rác đồ họa ISS-11), `UI-BU04` (Khoảng cách cụm 5 tab đáy hẹp ISS-13).
  - **NEEDS VALIDATION / UNKNOWN (5):** `UI-LA08` (Khả năng co giãn khi người dùng chỉnh Large Text trên iOS), `UI-BU05` (Trạng thái pressed/active khi nhấn nút), `UI-TY14` (Responsive trên các dòng màn hình iPhone hẹp/rộng), `UI-DA03`, `UI-IC04`.
- **Không áp dụng (N/A): 52 tiêu chí** (Bao gồm Data Table, Modal/Dialog, Checkbox/Radio/Switch, Breadcrumb, Pagination, Chart visualization...).

### 5.2. Checklist UX (286 tiêu chí thư viện chuẩn)
- **Áp dụng (Applicable): 26 tiêu chí**
  - **PASS (18):** `UX-TC02` (Màu sắc mang tính định hướng rõ ràng), `UX-TC05` (Nhãn chữ đi kèm đầy đủ dưới mọi icon), `UX-TC16` (Kích hoạt nhanh tính năng bằng 1 chạm), `UX-TC17` (Vùng bấm bao phủ nút bấm dạng pill), `UX-HI04` (Hiển thị số thông báo chưa đọc `9`), `UX-HI05` (Phân nhóm các khối tính năng tách biệt), `UX-HI06` (Bảo mật số dư bằng ký tự che), `UX-NV01` (Tab active Trang chủ thể hiện rõ ràng), `UX-NV03` (Luôn có nút truy cập nhanh tìm kiếm và thông báo ở header), `UX-CS01` (Tìm kiếm đặt ở góc trên dễ thấy), `UX-TT01` (Nhận diện thương hiệu OneU và Techcombank), `UX-TT02` (Dịch vụ đa dạng), `UX-TT03` (Thông điệp sản phẩm tích cực), `UX-TT04`, `UX-EC02`, `UX-EC03`, `UX-ND01`, `UX-ND02`.
  - **FAIL (8):** `UX-TC01` (Quảng cáo lấn át số dư ISS-02, phím tắt QR chưa nổi bật ISS-06), `UX-EC01` (Vùng bấm ẩn/hiện số dư nhỏ ISS-03), `UX-TC07` (Huy hiệu OneU thiếu affordance nút bấm ISS-04), `UX-TC06` (Icon mặt cười cho tính năng Sinh lời ISS-07, icon bóng đèn cho tài sản ISS-12), `UX-TC04` (Lỗi biên tập ngữ pháp thiếu từ nối ISS-08), `UX-NV02` (Thiếu peek preview và dots cho carousel ISS-09).
  - **NEEDS VALIDATION / UNKNOWN (8):** Thời gian phản hồi API khi chạm mở số dư, Luồng xác thực sinh trắc học FaceID, Trải nghiệm VoiceOver cho người khiếm thị, Phản hồi rung haptic feedback khi chạm nút.
- **Không áp dụng (N/A): 252 tiêu chí** (Bao gồm luồng thanh toán giỏ hàng, bảng dữ liệu phức tạp, form nhập liệu nhiều bước, trình phát video/audio...).

---

## 6. Kết luận và Khuyến nghị

1. **Giai đoạn 1 (Khắc phục ngay - Sprint 1 / P1):**
   - **Sửa lỗi layout che khuất ở đáy màn hình:** Thêm `safeAreaInsets.bottom` và khoảng đệm `paddingBottom` (tối thiểu 80-96pt) cho màn hình chính để đảm bảo toàn bộ nội dung scroll và nút CTA *"Khám phá ngay"* hiển thị trọn vẹn phía trên Bottom Bar; loại bỏ vạch đỏ rác đồ họa.
   - **Thay đổi icon tính năng "Sinh lời tự động":** Dùng biểu tượng tài chính chuẩn (Biểu đồ tăng trưởng tài sản hoặc Ký hiệu tiền sinh lời) thay cho khuôn mặt cười kỳ lạ.
   - **Bổ sung chỉ báo trượt cho khối "Dành cho bạn":** Thu nhỏ thẻ hiện tại xuống khoảng 88-90% chiều rộng màn hình để lộ mép thẻ tiếp theo (Peek preview), đồng thời bổ sung hàng chấm tròn chỉ báo trang (Pagination dots).
2. **Giai đoạn 2 (Tối ưu bố cục & Phân cấp chức năng / P2):**
   - **Cân đối lại Thẻ số dư:** Tái thiết kế thẻ số dư mở rộng đều toàn màn hình; tách riêng phần quảng cáo gói tiết kiệm thành một banner nhỏ phía dưới thẻ số dư để trả lại sự tập trung cho số dư và lịch sử giao dịch.
   - **Tối ưu nhãn Quick Actions:** Rút gọn text thành 1 dòng ngắn gọn để giao diện thoáng mắt và không bị rớt chữ.
   - **Nâng tầm tính năng Quét mã QR:** Bổ sung viền highlight nổi bật hoặc cân nhắc đưa nút Quét QR ra vị trí trung tâm của Bottom Bar để tối ưu thao tác thanh toán 1-chạm ngoài đời thực.
3. **Giai đoạn 3 (Hoàn thiện công thái học & Thẩm mỹ / P3):**
   - Mở rộng vùng bấm vô hình (Hit target) cho icon con mắt ẩn/hiện số dư đạt chuẩn $\ge 44\times44\text{pt}$.
   - Thêm viền và affordance nhận biết liên kết cho huy hiệu *"Tích U-Point Săn deal chất"*.
   - Sửa lỗi ngữ pháp câu chữ trong banner ưu đãi: *"dành riêng cho bạn"*.
   - Thay đổi icon tab *"Tổng quan tài sản"* sang biểu tượng két sắt hoặc biểu đồ danh mục tài sản.
