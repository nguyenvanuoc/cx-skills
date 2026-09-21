# Báo cáo Đánh giá Chất lượng UI/UX (UI/UX Quality Audit Report)

- **Sản phẩm:** VNPT iOffice - Hệ thống Quản lý Văn bản và Điều hành
- **Màn hình đánh giá:** Tra cứu Văn bản / Danh sách Văn bản đến
- **Nền tảng / Thiết bị:** Web Desktop (1920x1080)
- **Thời gian thực hiện:** 21/09/2026
- **Tiêu chuẩn tham chiếu:** VNPT Design System, WCAG 2.2 AA, ISO 9241-161 / ISO 9241-210, Material Design 3, Apple HIG

---

## 1. Executive Summary

Màn hình **Tra cứu văn bản (VNPT iOffice)** được thiết kế theo phong cách giao diện cổng thông tin tác nghiệp doanh nghiệp (Enterprise Portal) với tông màu xanh dương nhận diện VNPT, bố cục bảng dữ liệu nhiều cột (data-heavy table), thanh công cụ tra cứu tích hợp và hệ thống phân trang rõ ràng. Tuy nhiên, qua quá trình kiểm định chi tiết theo bộ checklist tiêu chuẩn UI/UX và khả năng tiếp cận (Accessibility), màn hình bộc lộ nhiều điểm nghẽn nghiêm trọng ảnh hưởng trực tiếp đến hiệu suất tác nghiệp văn thư và trải nghiệm người dùng:

1. **Lệch pha điều hướng (Navigation State Mismatch):** Menu bên trái (Sidebar) đang active ở mục *"VB đến cá nhân chờ xử lý"* (badge đỏ 99+), nhưng Breadcrumb và nội dung chính lại hiển thị *"Tra cứu VB"*, gây xung đột nhận thức về vị trí và ngữ cảnh làm việc hiện tại của người dùng.
2. **Cắt cụt thông tin cốt lõi (Severe Text Truncation):** Cột Số ký hiệu văn bản (định danh pháp lý quan trọng nhất) bị truncate thành dấu ba chấm (`...`) ở hàng loạt dòng (ví dụ `108/QĐ-VNPTIT...`, `3834/VNPT VNP...`, `952/QĐ-VNPT IT...`). Tương tự, tên người dùng trên Topbar (`Nguyễn Văn Ư...`), trích yếu và nơi nhận cũng bị cắt cụt dù không gian màn hình còn nhiều chỗ trống.
3. **Widget nổi che khuất dữ liệu (Floating AI Widget Collision):** Icon chatbot / trợ lý AI dạng floating cố định ở mép phải đè trực tiếp lên cột dữ liệu *"Nơi nhận"*, gây cản trở đọc thông tin và thao tác dòng.
4. **Nút Sắp xếp (Sort `⇅`) đặt sát cạnh nhau gây bấm nhầm:** Cột *"Đơn vị ban hành / Ngày đến ⇅ - Số đến đi ⇅"* và các cột gộp 2 tầng nhồi nhét tới 2 icon sort `⇅` sát sàn sạt nhau trên cùng một ô/dòng text, vi phạm nghiêm trọng vùng bấm tối thiểu (WCAG SC 2.5.8), dễ gây click nhầm và làm rối loạn phản hồi trạng thái dữ liệu.
5. **Dữ liệu rỗng hiển thị sơ sài (Poor Empty State Formatting):** Các trường chưa có dữ liệu hiển thị dạng placeholder thô `🏢 _ _`, `📅 _ _`, `📄 _ _` hoặc `--` lặp lại dày đặc, tạo cảm giác hệ thống bị lỗi tải dữ liệu (broken UI) thay vì xử lý khuyết thiếu tinh tế.
6. **Thiếu giải nghĩa mã viết tắt & Màu sắc gây hiểu nhầm (Ambiguous Badges & Color Coding):** Các tag tiền tố `[CN]`, `[XLC]`, `[PH]` không có tooltip/chú thích giải nghĩa; màu chữ Số ký hiệu (đỏ, xanh lá, đen) không đồng bộ và không được giải thích trong thanh Chú thích trạng thái bên dưới; badge `[PH]` có độ tương phản chữ trắng trên nền vàng/cam nhạt dưới ngưỡng WCAG AA.
7. **Thông tin liên hệ chân trang không chuẩn doanh nghiệp:** Phần Footer hiển thị email cá nhân (`nguyenkhacthanh@vnpt.vn`) và số di động thay vì kênh Tổng đài Hỗ trợ Kỹ thuật / Service Desk chính thức.

---

## 2. Tổng quan điểm số (Score Summary)

### Bảng 1 — Score Summary

| Chỉ số | Giá trị UI | Giá trị UX | Toàn hệ thống / Tổng hợp |
|---|---:|---:|---:|
| **Tổng checklist áp dụng** | 26 | 28 | 54 |
| **Checklist PASS** | 19 | 19 | 38 |
| **Checklist FAIL** | 7 | 9 | 16 |
| **Checklist N/A** | 50 | 250 | 300 |
| **Checklist NEEDS VALIDATION** | 5 | 8 | 13 |
| **Tổng số Issue phát hiện** | 7 | 9 | 16 |
| - Critical (Trọng số 5) | 0 | 1 | 1 |
| - Major (Trọng số 3) | 3 | 5 | 8 |
| - Minor (Trọng số 1) | 4 | 3 | 7 |
| **Issue Penalty** | 13 | 23 | 36 |
| **Checklist Compliance Score** | **73.1 / 100** | **67.9 / 100** | **70.4 / 100** |
| **Issue Score** | **90.0 / 100** | **83.6 / 100** | **86.7 / 100** |
| **UI Quality Score** (70% CL + 30% Issue) | **78.2 / 100** | — | — |
| **UX Quality Score** (70% CL + 30% Issue) | — | **72.6 / 100** | — |
| **Experience Quality Score** (40% UI + 60% UX) | — | — | **74.8 / 100** |

---

### Bảng 2 — Calculation Detail

| Chỉ số | Giá trị đầu vào | Công thức tính toán | Kết quả |
|---|---|---|---:|
| **UI Checklist Score** | Áp dụng: 26, FAIL: 7 | `(26 - 7) / 26 * 100` | **73.1** |
| **UI Issue Penalty** | Minor: 4, Major: 3, Critical: 0 | `4*1 + 3*3 + 0*5` | **13** |
| **UI Issue Score** | Áp dụng: 26, Penalty: 13 | `100 * (1 - 13 / (26 * 5))` | **90.0** |
| **UI Quality Score** | CL Score: 73.1, Issue Score: 90.0 | `73.1 * 70% + 90.0 * 30%` | **78.2** |
| **UX Checklist Score** | Áp dụng: 28, FAIL: 9 | `(28 - 9) / 28 * 100` | **67.9** |
| **UX Issue Penalty** | Minor: 3, Major: 5, Critical: 1 | `3*1 + 5*3 + 1*5` | **23** |
| **UX Issue Score** | Áp dụng: 28, Penalty: 23 | `100 * (1 - 23 / (28 * 5))` | **83.6** |
| **UX Quality Score** | CL Score: 67.9, Issue Score: 83.6 | `67.9 * 70% + 83.6 * 30%` | **72.6** |
| **Experience Quality Score** | UI: 78.2, UX: 72.6 | `78.2 * 40% + 72.6 * 60%` | **74.8 / 100** |

---

### Bảng 3 — Severity Summary

| Severity | Weight | Số issue UI | Số issue UX | Tổng Issue | Penalty UI | Penalty UX | Tổng Penalty |
|---|---:|---:|---:|---:|---:|---:|---:|
| **Critical** | 5 | 0 | 1 | 1 | 0 | 5 | 5 |
| **Major** | 3 | 3 | 5 | 8 | 9 | 15 | 24 |
| **Minor** | 1 | 4 | 3 | 7 | 4 | 3 | 7 |
| **Tổng cộng** | | **7** | **9** | **16** | **13** | **23** | **36** |

---

### Bảng 4 — Mandatory Gate

| Gate | Kết quả | Lý do | Hành động bắt buộc |
|---|---|---|---|
| **Critical issue** | ❌ **FAIL** | Tồn tại 01 Critical Issue: Widget Chatbot AI nổi che đè trực tiếp lên cột dữ liệu bảng "Nơi nhận" | Điều chỉnh z-index, vị trí floating hoặc thu nhỏ/docking vào cạnh phải |
| **Mandatory checklist** | ⚠️ **NEEDS VALIDATION** | Cần kiểm tra thực tế trạng thái tương tác động (hover row, tooltip trích yếu, modal chi tiết văn bản, phím tắt) | Thực hiện kiểm thử trực tiếp trên môi trường web chạy thật |
| **Task blocker** | ❌ **FAIL** | Cắt cụt số ký hiệu văn bản (`108/QĐ-VNPTIT...`) làm gián đoạn khả năng tra cứu và phân loại chính xác văn thư | Tối ưu độ rộng cột hoặc hiển thị wrap text 2 dòng |
| **Accessibility (WCAG AA)** | ⚠️ **CẢNH BÁO** | Badge `[PH]` màu vàng chữ trắng có độ tương phản dưới 4.5:1; dùng màu sắc chữ đỏ/xanh biểu thị trạng thái không có icon bổ trợ; 2 nút sort sát nhau vi phạm target size | Điều chỉnh màu nền/chữ và bổ sung tooltip/icon semantic; tách vùng nút sort |
| **Excellent eligibility** | ❌ **FAIL** | Chưa đủ điều kiện xếp loại Excellent do có Critical issue và checklist bắt buộc chưa hoàn tất | Khắc phục các issue P1 & P2 |

---

## 3. Bảng Kết quả đầu ra (Issue Log & Chi tiết kiểm định)

*Quy tắc sắp xếp: Từ trên xuống dưới, từ trái qua phải theo cấu trúc thị giác của giao diện.*

| Issue ID | Phân loại | Mã checklist | Tên luồng | Chức năng | Bước thao tác | Thiết bị | Mức độ ảnh hưởng | Hình ảnh | Vấn đề | Đề xuất giải pháp | Hiệu quả sau cải tiến | Xếp loại Issue | Xếp loại Checklist | Effort | Urgency | Priority points |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---:|---:|---:|
| **ISS-01** | UI | `UI-TY02` | Người dùng | Topbar Header | Xem thông tin tài khoản | Desktop | Minor | Góc trên bên phải | Tên người dùng bị cắt cụt thành `Nguyễn Văn Ư...` dù thanh Topbar còn nhiều khoảng trống | Mở rộng vùng hiển thị tên hoặc cho phép tự co giãn theo độ dài tên thực tế | Hiển thị trọn vẹn họ tên người dùng, tăng tính cá nhân hóa | Minor | FAIL | 1 | 1 | 1.0 (P3) |
| **ISS-02** | UX | `UX-NV01` | Điều hướng | Sidebar & Breadcrumb | Điều hướng menu | Desktop | Major | Sidebar trái & Breadcrumb | Sidebar đang kích hoạt mục *"VB đến cá nhân chờ xử lý"* nhưng Breadcrumb và nội dung trang lại là *"Tra cứu VB"* | Đồng bộ trạng thái active của Sidebar khớp chính xác với URL và Breadcrumb trang hiện tại | Tránh gây bối rối về vị trí hiện tại của người dùng trong hệ thống | Major | FAIL | 1 | 3 | 9.0 (P1) |
| **ISS-03** | UI | `UI-TE01` | Tra cứu | Thanh tìm kiếm | Nhập từ khóa tìm kiếm | Desktop | Minor | Thanh tìm kiếm chính giữa | Placeholder quá dài và phức tạp, chứa nhiều câu văn hướng dẫn gộp chung | Đơn giản hóa placeholder: `Nhập số ký hiệu, trích yếu hoặc đơn vị ban hành...`; đưa mẹo ký tự `*` vào icon `(?)` tooltip | Giao diện gọn gàng, người dùng dễ nắm bắt cú pháp | Minor | FAIL | 1 | 1 | 1.0 (P3) |
| **ISS-04** | UX | `UX-TC03` | Tra cứu | Bảng văn bản | Đọc phân loại văn bản | Desktop | Major | Cột Trích yếu | Các badge tiền tố `[CN]`, `[XLC]`, `[PH]` viết tắt nội bộ gây khó hiểu cho nhân sự mới | Bổ sung tooltip giải nghĩa khi rê chuột (VD: `Chủ trì`, `Xử lý chính`, `Phối hợp`) hoặc hiển thị nhãn đầy đủ | Giúp người dùng hiểu rõ vai trò phân công tác nghiệp | Major | FAIL | 1 | 2 | 6.0 (P1) |
| **ISS-05** | UI | `UI-TY10` | Tra cứu | Bảng văn bản | Đọc badge phân loại | Desktop | Minor | Cột Trích yếu | Badge `[PH]` màu vàng chữ trắng không đạt độ tương phản chuẩn WCAG 2.2 AA (dưới 3:1) | Đổi sang phong cách nền vàng nhạt (#FEF9C3) chữ nâu đậm (#854D0E) | Đảm bảo tương phản đạt chuẩn, dễ đọc trong mọi điều kiện ánh sáng | Minor | FAIL | 1 | 2 | 2.0 (P2) |
| **ISS-06** | UI | `UI-TY05` | Tra cứu | Bảng văn bản | Đọc số ký hiệu | Desktop | Major | Cột Số ký hiệu | Cột Số ký hiệu bị cắt cụt (`108/QĐ-VNPTIT...`, `3834/VNPT VNP...`) khiến người dùng không đọc được đầy đủ định danh văn bản | Cho phép xuống dòng tự nhiên (text-wrap) hoặc mở rộng bề rộng tối thiểu (min-width) của cột Số ký hiệu | Đọc trọn vẹn số ký hiệu văn thư mà không cần mở chi tiết | Major | FAIL | 1 | 3 | 9.0 (P1) |
| **ISS-07** | UX | `UX-TC08` | Tra cứu | Bảng văn bản | Phân biệt tính chất văn bản | Desktop | Major | Cột Số ký hiệu & Icon sao | Chữ Số ký hiệu đổi màu đỏ/xanh lá/đen tùy ý; không giải thích màu sắc trong bảng chú thích trạng thái bên dưới | Đồng nhất màu text và dùng badge chuyên dụng (Khẩn, Hỏa tốc) có icon rõ ràng thay vì chỉ đổi màu text | Tuân thủ chuẩn tiếp cận WCAG, tránh hiểu nhầm về độ ưu tiên | Major | FAIL | 1 | 3 | 9.0 (P1) |
| **ISS-08** | UX | `UX-ND02` | Tra cứu | Bảng văn bản | Xem thông tin ngày tháng | Desktop | Minor | Cột Đơn vị ban hành & Ngày | Dữ liệu rỗng hiển thị placeholder thô sơ `🏢 _ _`, `📅 _ _`, `📄 _ _` xuất hiện tràn lan ở hầu hết các dòng | Ẩn các icon thừa khi không có dữ liệu hoặc hiển thị text mờ `Chưa cập nhật` / để trống lịch sự | Tránh cảm giác hệ thống bị lỗi dữ liệu, tăng tính hoàn thiện của UI | Minor | FAIL | 1 | 2 | 2.0 (P2) |
| **ISS-09** | UI | `UI-TY02` | Tra cứu | Bảng văn bản | Đọc trích yếu văn bản | Desktop | Minor | Cột Trích yếu (Dòng 5 & 6) | Nội dung trích yếu bị cắt cụt dở dang: `...sử...` mà không hiển thị hết câu hoặc thiếu nút xem thêm | Tăng chiều cao hàng cho phép hiển thị 2-3 dòng trích yếu kèm tooltip đầy đủ khi hover | Đảm bảo người dùng nắm trọn vẹn nội dung tóm tắt của văn bản | Minor | FAIL | 1 | 2 | 2.0 (P2) |
| **ISS-10** | UX | `UX-ND04` | Tra cứu | Bảng văn bản | Đọc nơi nhận | Desktop | Minor | Cột Nơi nhận | Dữ liệu Nơi nhận bị cắt cụt `Nghiên c...`, `P...` và hiển thị ký tự `--` thiếu nhất quán | Tối ưu hiển thị danh sách đơn vị nhận (dạng tag có tooltip + số lượng ẩn `+3 đơn vị`) | Dễ dàng quản lý và theo dõi nơi nhận văn bản | Minor | FAIL | 2 | 2 | 1.0 (P3) |
| **ISS-11** | UX | `UX-EC02` | Tương tác | Bảng văn bản | Đọc & Thao tác bảng | Desktop | **Critical** | Mép phải bảng dữ liệu | Floating Chatbot AI / Widget nổi đè trực tiếp lên cột "Nơi nhận" và mép phải của bảng | Đặt vị trí floating widget ra ngoài vùng nội dung bảng hoặc cung cấp nút thu nhỏ/docking thanh bên | Không che khuất dữ liệu quan trọng của văn bản | Critical | FAIL | 1 | 3 | **P1 (Critical)** |
| **ISS-12** | UX | `UX-TC08` | Tra cứu | Thanh chú thích trạng thái | Tra cứu ý nghĩa icon | Desktop | Minor | Thanh chú thích đáy bảng | Thanh chú thích trạng thái có biểu tượng sao nhưng thiếu đồng bộ với màu sắc thực tế trong bảng | Đồng bộ bảng chú thích với toàn bộ hệ thống icon và màu sắc đang hiển thị trên bảng | Giúp người dùng tra cứu nhanh ý nghĩa các ký hiệu nghiệp vụ | Minor | FAIL | 1 | 1 | 1.0 (P3) |
| **ISS-13** | UI | `UI-LA04` | Bố cục | Chú thích trạng thái | Xem toàn màn hình | Desktop | Minor | Phía trên Footer | Thanh chú thích trạng thái nằm cô lập như một dải phân cách giữa bảng và footer | Gộp thanh chú thích vào chân bảng (table footer) hoặc thanh công cụ trên đầu bảng | Tối ưu cấu trúc trang, giảm khoảng trống rời rạc | Minor | FAIL | 1 | 1 | 1.0 (P3) |
| **ISS-14** | UX | `UX-CS01` | Tra cứu | Nút Tải DS & Xem dạng lưới | Thao tác xuất & Chuyển chế độ | Desktop | Major | Bên phải số kết quả `286 kết quả` | Nút "Tải DS" không chỉ rõ định dạng xuất (Excel, PDF) và nút chế độ Grid View chưa thực sự hữu ích với dữ liệu bảng văn bản | Thêm menu chọn định dạng xuất `Excel / CSV / PDF` và tối ưu hóa chế độ hiển thị thẻ (Card view) | Nâng cao trải nghiệm xuất báo cáo và tùy biến giao diện làm việc | Major | FAIL | 2 | 2 | 3.0 (P2) |
| **ISS-15** | UX | `UX-TT01` | Chân trang | Footer hệ thống | Liên hệ hỗ trợ kỹ thuật | Desktop | Minor | Dòng thông tin liên hệ cuối cùng | Footer hiển thị email cá nhân `nguyenkhacthanh@vnpt.vn` và SĐT di động thay vì kênh hỗ trợ chính thức | Đổi sang email hỗ trợ doanh nghiệp (`hotro.ioffice@vnpt.vn`) và hotline tổng đài IT | Tăng tính chuyên nghiệp và đảm bảo kênh hỗ trợ vận hành liên tục | Minor | FAIL | 1 | 1 | 1.0 (P3) |
| **ISS-16** | UI | `UI-DA01` | Tra cứu | Bảng văn bản | Xem & Thao tác Header bảng | Desktop | Major | Header bảng dữ liệu | Header gộp 2 trường (`Ngày đến ⇅ - Số đến đi ⇅`) nhồi nhét 2 nút sort sát nhau vi phạm target size (< 24px), dễ bấm nhầm và không hiển thị rõ trường nào đang active sort | **Triển khai 1 trong 2 giải pháp chuẩn UI/UX:**<br>1. *(Khuyên dùng)* **Tách thành 2 cột riêng biệt**: Cột *Ngày đến* và cột *Số đến đi* độc lập, mỗi cột có 1 nút sort rõ ràng.<br>2. **Tái cấu trúc Compound Header**: Phân tách 2 vùng bấm bằng divider rõ nét, kích thước mỗi vùng tối thiểu $32\times32\text{px}$, chỉ cho phép 1 trường active sort tại một thời điểm, chỉ hiện icon sort khi hover/active | Loại bỏ $100\%$ rủi ro bấm nhầm, trạng thái sort minh bạch, header bảng thoáng đãng đạt chuẩn WCAG 2.5.8 | Major | FAIL | 2 | 2 | 3.0 (P2) |

---

## 4. Bảng Kế hoạch cải tiến (Improvement Roadmap)

*Danh sách được lọc từ các Issue FAIL và sắp xếp theo thứ tự ưu tiên xử lý P1 → P2 → P3.*

| Issue ID | Phân loại | Mã checklist | Chức năng | Bước thao tác | Thiết bị | Mức độ ảnh hưởng | Hình ảnh | Vấn đề | Đề xuất giải pháp | Hiệu quả sau cải tiến | Priority |
|---|---|---|---|---|---|---|---|---|---|---|---|
| **ISS-11** | UX | `UX-EC02` | Đọc & Thao tác bảng | Mép phải bảng dữ liệu | Desktop | **Critical** | Mép phải bảng | Floating Chatbot AI đè trực tiếp lên cột dữ liệu Nơi nhận | Đặt vị trí floating widget ra ngoài vùng nội dung bảng hoặc có cơ chế thu nhỏ | Loại bỏ nguy cơ che khuất dữ liệu quan trọng | **P1** |
| **ISS-02** | UX | `UX-NV01` | Sidebar & Breadcrumb | Điều hướng menu | Desktop | Major | Sidebar & Breadcrumb | Trạng thái active Sidebar và Breadcrumb không đồng bộ | Đồng bộ menu active chính xác theo URL/Breadcrumb trang hiện tại | Tránh gây bối rối về vị trí hiện tại | **P1** |
| **ISS-06** | UI | `UI-TY05` | Bảng văn bản | Đọc số ký hiệu | Desktop | Major | Cột Số ký hiệu | Cột Số ký hiệu bị cắt cụt (`...`) làm mất thông tin định danh | Mở rộng min-width cột hoặc cho phép wrap text 2 dòng | Đọc đầy đủ số ký hiệu văn thư quan trọng | **P1** |
| **ISS-07** | UX | `UX-TC08` | Bảng văn bản | Phân biệt tính chất văn bản | Desktop | Major | Cột Số ký hiệu & Icon sao | Dùng màu text tùy ý biểu đạt độ khẩn nhưng không giải thích trong legend | Chuẩn hóa badge mức độ Khẩn/Hỏa tốc có icon rõ ràng | Nhận diện tính khẩn cấp chuẩn xác, tiếp cận tốt | **P1** |
| **ISS-04** | UX | `UX-TC03` | Bảng văn bản | Đọc phân loại văn bản | Desktop | Major | Cột Trích yếu | Badge viết tắt `[CN]`, `[XLC]`, `[PH]` không có giải nghĩa | Bổ sung tooltip hoặc nhãn giải thích đầy đủ vai trò xử lý | Nhân sự mới dễ dàng hiểu và thực hiện đúng vai trò | **P2** |
| **ISS-05** | UI | `UI-TY10` | Bảng văn bản | Đọc badge phân loại | Desktop | Minor | Cột Trích yếu | Badge `[PH]` màu vàng chữ trắng không đạt độ tương phản WCAG | Chuyển sang nền vàng nhạt chữ nâu đậm đạt chuẩn tương phản | Dễ đọc, bảo vệ thị lực và đạt chuẩn tiếp cận | **P2** |
| **ISS-08** | UX | `UX-ND02` | Bảng văn bản | Xem thông tin ngày tháng | Desktop | Minor | Cột Đơn vị & Ngày | Placeholder rỗng `🏢 _ _`, `📅 _ _` hiển thị tràn lan | Ẩn placeholder thừa hoặc hiển thị text mờ tinh tế `Chưa cập nhật` | Giao diện chuyên nghiệp, không gây cảm giác lỗi dữ liệu | **P2** |
| **ISS-09** | UI | `UI-TY02` | Bảng văn bản | Đọc trích yếu | Desktop | Minor | Cột Trích yếu | Trích yếu bị cắt cụt dở dang `...sử...` | Cho phép hiển thị 2-3 dòng trích yếu kèm tooltip hover | Nắm bắt nhanh trích yếu văn bản | **P2** |
| **ISS-14** | UX | `UX-CS01` | Thao tác xuất & Chế độ xem | Xuất dữ liệu | Desktop | Major | Phía trên bảng | Nút Tải DS thiếu tùy chọn định dạng xuất | Bổ sung dropdown menu chọn định dạng `Excel / PDF / CSV` | Thuận tiện cho nghiệp vụ lưu trữ, in ấn | **P2** |
| **ISS-16** | UI | `UI-DA01` | Bảng văn bản | Đọc & Sort header bảng | Desktop | Major | Header bảng dữ liệu | 2 nút sort `⇅` đặt sát nhau trên cùng ô dễ gây bấm nhầm | **1.** Tách thành 2 cột riêng biệt có sort độc lập; hoặc **2.** Thiết kế Compound Header có phân vùng bấm rõ ràng $\ge 32\text{px}$, chỉ hiện icon khi hover | Dễ quét dữ liệu theo cột, loại bỏ hoàn toàn nguy cơ click nhầm, đạt chuẩn WCAG 2.5.8 | **P2** |
| **ISS-01** | UI | `UI-TY02` | Topbar Header | Xem thông tin tài khoản | Desktop | Minor | Góc trên phải | Tên người dùng bị cắt cụt `Nguyễn Văn Ư...` | Mở rộng vùng hiển thị tên người dùng | Tăng tính chuyên nghiệp và cá nhân hóa | **P3** |
| **ISS-03** | UI | `UI-TE01` | Thanh tìm kiếm | Nhập từ khóa | Desktop | Minor | Thanh tìm kiếm | Placeholder quá dài và phức tạp | Rút gọn placeholder và đưa gợi ý vào tooltip | Thanh tìm kiếm tinh gọn, thanh thoát | **P3** |
| **ISS-10** | UX | `UX-ND04` | Bảng văn bản | Đọc nơi nhận | Desktop | Minor | Cột Nơi nhận | Cột Nơi nhận bị cắt chữ và có ký tự `--` chưa nhất quán | Format dạng danh sách tag + badge số lượng ẩn | Hiển thị gọn gàng danh sách đơn vị nhận | **P3** |
| **ISS-12** | UX | `UX-TC08` | Chú thích trạng thái | Tra cứu ý nghĩa | Desktop | Minor | Thanh chú thích | Thiếu đồng bộ giữa thanh chú thích và màu sắc trong bảng | Cập nhật đầy đủ các trạng thái thực tế vào thanh chú thích | Bảng tra cứu chú thích chuẩn xác | **P3** |
| **ISS-13** | UI | `UI-LA04` | Chú thích trạng thái | Xem toàn màn hình | Desktop | Minor | Đáy bảng | Thanh chú thích nằm lơ lửng chia cắt bố cục | Tích hợp vào table footer hoặc toolbar | Bố cục liền mạch, gọn gàng | **P3** |
| **ISS-15** | UX | `UX-TT01` | Chân trang | Hỗ trợ kỹ thuật | Desktop | Minor | Footer hệ thống | Hiển thị email và SĐT cá nhân trong footer | Thay bằng email và hotline tổng đài hỗ trợ chính thức của đơn vị | Đảm bảo tính chuyên nghiệp và quy chuẩn doanh nghiệp | **P3** |

---

## 5. Danh mục Checklist chi tiết đã đánh giá

### 5.1. Checklist UI (81 tiêu chí thư viện chuẩn)
- **Áp dụng (Applicable): 26 tiêu chí**
  - **PASS (19):** `UI-LA01` (Hệ lưới Grid), `UI-LA02` (Căn gióng chung), `UI-LA03` (Phân cấp thị giác chính/phụ), `UI-LA05` (Khoảng cách spacing scale), `UI-LA06` (Màu sắc nền và nội dung), `UI-SI01` (Trạng thái Sidebar), `UI-LO01` (Logo chuẩn VNPT), `UI-LO02` (Tỷ lệ logo), `UI-LO03` (Vùng an toàn logo), `UI-LO04` (Độ nét logo), `UI-TY01` (Font chữ thương hiệu), `UI-TY03` (Phân cấp kiểu chữ), `UI-TY04` (Thứ bậc heading/body), `UI-TY06` (Line-height), `UI-TY07` (Paragraph spacing), `UI-TY08` (Căn lề trái văn bản), `UI-TY09` (Không lạm dụng viết hoa), `UI-IC01` (Ngôn ngữ hình học icon), `UI-PA01` (Phân trang chuẩn 29 trang).
  - **FAIL (7):** `UI-TY02` (Cắt cụt tên tài khoản ISS-01 & trích yếu ISS-09), `UI-TE01` (Cấu trúc placeholder input tìm kiếm ISS-03), `UI-TY10` (Độ tương phản badge PH ISS-05), `UI-TY05` (Cắt cụt Số ký hiệu văn bản ISS-06), `UI-LA04` (Khoảng cách thanh chú thích rời rạc ISS-13), `UI-DA01` (Cấu trúc header gộp 2 nút sort sát nhau rối mắt ISS-16), `UI-TY11` (Chỉ dùng màu chữ đỏ/xanh biểu thị tính chất văn bản ISS-07).
  - **NEEDS VALIDATION / UNKNOWN (5):** `UI-LA07` (Responsive ở các breakpoint), `UI-LA08` (Khả năng zoom 200%), `UI-BU05` (Trạng thái hover/active nút), `UI-DA03` (Trạng thái hover dòng dữ liệu), `UI-TY14` (Thích ứng độ dài dòng khi co giãn màn hình).
- **Không áp dụng (N/A): 50 tiêu chí** (Bao gồm Modal/Dialog, Radio/Switch, Card, Biểu đồ Chart, Alert/Toast không xuất hiện trên màn hình tĩnh hiện tại).

### 5.2. Checklist UX (286 tiêu chí thư viện chuẩn)
- **Áp dụng (Applicable): 28 tiêu chí**
  - **PASS (19):** `UX-TC01` (Thứ tự trình bày thông tin), `UX-TC02` (Màu sắc theo chuẩn tác nghiệp), `UX-TC05` (Icon có nhãn đi kèm trên các nút chính), `UX-TC06` (Icon chuẩn ngành: Kính lúp, Phễu lọc, Tải xuống), `UX-TC07` (Icon dễ nhận diện), `UX-TC16` (Nút bấm tương tác nhanh), `UX-TC17` (Vùng bấm bao phủ nút), `UX-TC20` (Checkbox chọn dòng dễ bấm), `UX-HI04` (Hiển thị số lượng kết quả tìm kiếm), `UX-HI05` (Phân nhóm danh mục văn bản), `UX-ND03` (Định dạng ngày tháng DD/MM/YYYY chuẩn Việt Nam), `UX-NV02` (Breadcrumb rõ ràng), `UX-NV03` (Cung cấp lối tắt về trang chủ), `UX-CS02` (Hỗ trợ lọc nâng cao), `UX-PG01` (Phân trang đầy đủ nút tới/lui và chọn số dòng/trang), `UX-TT02` (Thông tin địa chỉ trụ sở), `UX-TT03` (Tùy chọn ngôn ngữ & Giao diện sáng/tối), `UX-TT04` (Liên kết tải ứng dụng di động), `UX-EC03` (Xác nhận lựa chọn nhiều dòng).
  - **FAIL (9):** `UX-EC02` (Critical: Floating widget che khuất dữ liệu bảng ISS-11), `UX-NV01` (Lệch trạng thái active Sidebar và Breadcrumb ISS-02), `UX-TC03` (Thuật ngữ viết tắt `[CN]`, `[XLC]`, `[PH]` thiếu giải nghĩa ISS-04), `UX-TC08` (Thiếu đồng bộ icon/màu sắc với thanh chú thích ISS-07, ISS-12), `UX-ND02` (Placeholder rỗng `_ _` hiển thị sơ sài ISS-08), `UX-ND04` (Nơi nhận bị cắt chữ và hiển thị `--` ISS-10), `UX-CS01` (Nút Tải DS thiếu tùy chọn định dạng xuất ISS-14), `UX-TT01` (Email và SĐT liên hệ cá nhân ở Footer ISS-15), `UX-HI01` (Dữ liệu Số ký hiệu và trích yếu bị cắt ngắn cản trở nắm bắt thông tin ISS-06).
  - **NEEDS VALIDATION / UNKNOWN (8):** Khả năng điều hướng bằng bàn phím (Keyboard Tab order), Hỗ trợ Screen Reader (ARIA labels cho các icon-only button), Thời gian phản hồi API tra cứu, Cơ chế lưu trạng thái bộ lọc khi quay lại trang.
- **Không áp dụng (N/A): 250 tiêu chí** (Các tiêu chí dành cho luồng thanh toán, giỏ hàng, wizard biểu mẫu nhiều bước, video/audio streaming...).

---

## 6. Kết luận và Khuyến nghị

1. **Giai đoạn 1 (Khắc phục ngay - Sprint 1 / P1):**
   - Di chuyển hoặc cung cấp cơ chế thu nhỏ (minimizable) cho Floating Chatbot AI để giải phóng hoàn toàn vùng hiển thị dữ liệu cột *Nơi nhận*.
   - Sửa lỗi đồng bộ điều hướng: Đảm bảo khi người dùng đang ở trang *Tra cứu VB*, menu Sidebar kích hoạt đúng mục *Tra cứu văn bản*.
   - Xử lý dứt điểm tình trạng cắt cụt (truncation) ở cột *Số ký hiệu*: Mở rộng độ rộng tối thiểu hoặc hỗ trợ wrap text để hiển thị toàn vẹn số ký hiệu văn thư.
   - Chuẩn hóa hệ thống nhận diện mức độ khẩn (Thường / Khẩn / Hỏa tốc) bằng badge độc lập, loại bỏ việc tự ý đổi màu text số ký hiệu.
2. **Giai đoạn 2 (Hoàn thiện trải nghiệm tác nghiệp / P2):**
   - Tách các cột gộp hoặc chỉ cho phép sort theo 1 trường chính, loại bỏ việc đặt 2 nút sort `⇅` sát sàn sạt nhau.
   - Thêm tooltip giải nghĩa cho các badge tiền tố `[CN]`, `[XLC]`, `[PH]` và điều chỉnh màu badge `[PH]` đạt chuẩn WCAG AA.
   - Xử lý các ô trống dữ liệu tinh tế hơn (thay thế chuỗi `_ _` bằng text mờ nhẹ hoặc để trống ô).
   - Bổ sung menu chọn định dạng file khi bấm *Tải DS* (`Excel`, `PDF`, `CSV`).
3. **Giai đoạn 3 (Chuẩn hóa hệ thống & Footer / P3):**
   - Cập nhật thông tin Hotline Service Desk và email hỗ trợ kỹ thuật chính thức của VNPT tại Footer.
   - Rút gọn placeholder thanh tìm kiếm và hiển thị đầy đủ tên người dùng trên Topbar.
   - Tích hợp thanh chú thích trạng thái gọn gàng vào chân bảng dữ liệu.
