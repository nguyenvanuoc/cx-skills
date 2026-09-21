# Báo cáo Đánh giá Chất lượng UI/UX (UI/UX Quality Audit Report)

- **Sản phẩm:** VNPT iOffice - Hệ thống Quản lý Văn bản và Điều hành
- **Màn hình đánh giá:** Tra cứu Văn bản / Văn bản đến cá nhân chờ xử lý
- **Nền tảng / Thiết bị:** Web Desktop (1920x1080)
- **Thời gian thực hiện:** 21/09/2026
- **Tiêu chuẩn tham chiếu:** VNPT Design System, WCAG 2.2 AA, ISO 9241-161 / ISO 9241-210, Material Design 3, Apple HIG

---

## 1. Executive Summary

Màn hình **Tra cứu Văn bản (VNPT iOffice)** cung cấp khả năng hiển thị danh sách văn bản phong phú với hệ thống bảng dữ liệu đa cột, tích hợp bộ lọc, trạng thái xử lý và các tiện ích hỗ trợ người dùng. Tuy nhiên, qua quá trình rà soát và đối soát chi tiết theo bộ checklist chuẩn UI/UX và ISO/WCAG, hệ thống bộc lộ nhiều điểm bất cập cần khắc phục:

1. **Xung đột điều hướng & Nhận diện ngữ cảnh trang (Major UX/UI):** Mục đang active ở Sidebar bên trái là *"VB đến cá nhân chờ xử lý"* (badge 99+), nhưng tiêu đề trang và Breadcrumb lại hiển thị *"Tra cứu VB"*. Điều này gây mất phương hướng cho người dùng về ngữ cảnh làm việc hiện tại.
2. **Trùng lặp công cụ tìm kiếm (Search Redundancy):** Tồn tại đồng thời 2 thanh tìm kiếm lớn cạnh nhau (Thanh tìm kiếm toàn cục trên Header và Thanh tìm kiếm văn bản chi tiết trên thanh công cụ lọc), làm tăng tải nhận thức và gây lúng túng về phạm vi tìm kiếm.
3. **Ký hiệu viết tắt & Trạng thái thiếu trực quan (Accessibility & Cognitive Load):**
   - Các tag viết tắt `[CN]`, `[XLC]`, `[PH]` không có nhãn giải nghĩa hoặc tooltip chú thích.
   - Màu sắc số ký hiệu chuyển đỏ bất thường (không giải thích trong bảng chú thích).
   - Bảng chú thích trạng thái (Legend) bị đẩy xuống tận chân trang (dưới phân trang), tách rời khỏi bảng dữ liệu khiến người dùng phải cuộn trang liên tục để tra cứu.
4. **Cột số thứ tự (#) bị lẫn lộn biểu tượng trạng thái:** Cột `#` thay vì hiển thị STT tự nhiên (1, 2, 3...) lại dùng để chứa tổ hợp icon trạng thái (sao, mắt, tích xanh) khiến việc đếm và đối chiếu số lượng văn bản trên trang gặp khó khăn.
5. **Che khuất giao diện bởi Floating Widget:** Nút Chatbot/Hỗ trợ tròn dạng nổi (Floating Action) ở góc phải màn hình đè trực tiếp lên nội dung cột *"Nơi nhận"* của bảng dữ liệu.
6. **Không nhất quán Icon & Nhãn cài đặt:** Dropdown chọn bảng màu ở Footer hiển thị chữ *"Xanh dương"* nhưng icon phía trước là Cỏ 4 lá xanh lá cây (`☘️`).

---

## 2. Tổng quan điểm số (Score Summary)

### Bảng 1 — Score Summary

| Chỉ số | Giá trị UI | Giá trị UX | Toàn hệ thống / Tổng hợp |
|---|---:|---:|---:|
| **Tổng checklist áp dụng** | 30 | 34 | 64 |
| **Checklist PASS** | 24 | 26 | 50 |
| **Checklist FAIL** | 6 | 8 | 14 |
| **Checklist N/A** | 46 | 244 | 290 |
| **Checklist NEEDS VALIDATION** | 5 | 8 | 13 |
| **Tổng số Issue phát hiện** | 6 | 8 | 14 |
| - Critical (Trọng số 5) | 0 | 0 | 0 |
| - Major (Trọng số 3) | 3 | 5 | 8 |
| - Minor (Trọng số 1) | 3 | 3 | 6 |
| **Issue Penalty** | 12 | 18 | 30 |
| **Checklist Compliance Score** | **80.0 / 100** | **76.5 / 100** | **78.1 / 100** |
| **Issue Score** | **92.0 / 100** | **89.4 / 100** | **90.6 / 100** |
| **UI Quality Score** (70% CL + 30% Issue) | **83.6 / 100** | — | — |
| **UX Quality Score** (70% CL + 30% Issue) | — | **80.4 / 100** | — |
| **Experience Quality Score** (40% UI + 60% UX) | — | — | **81.7 / 100** |

---

### Bảng 2 — Calculation Detail

| Chỉ số | Giá trị đầu vào | Công thức tính toán | Kết quả |
|---|---|---|---:|
| **UI Checklist Score** | Áp dụng: 30, FAIL: 6 | `(30 - 6) / 30 * 100` | **80.0** |
| **UI Issue Penalty** | Minor: 3, Major: 3, Critical: 0 | `3*1 + 3*3 + 0*5` | **12** |
| **UI Issue Score** | Áp dụng: 30, Penalty: 12 | `100 * (1 - 12 / (30 * 5))` | **92.0** |
| **UI Quality Score** | CL Score: 80.0, Issue Score: 92.0 | `80.0 * 70% + 92.0 * 30%` | **83.6** |
| **UX Checklist Score** | Áp dụng: 34, FAIL: 8 | `(34 - 8) / 34 * 100` | **76.5** |
| **UX Issue Penalty** | Minor: 3, Major: 5, Critical: 0 | `3*1 + 5*3 + 0*5` | **18** |
| **UX Issue Score** | Áp dụng: 34, Penalty: 18 | `100 * (1 - 18 / (34 * 5))` | **89.4** |
| **UX Quality Score** | CL Score: 76.5, Issue Score: 89.4 | `76.5 * 70% + 89.4 * 30%` | **80.4** |
| **Experience Quality Score** | UI: 83.6, UX: 80.4 | `83.6 * 40% + 80.4 * 60%` | **81.7 / 100** |

---

### Bảng 3 — Severity Summary

| Severity | Weight | Số issue UI | Số issue UX | Tổng Issue | Penalty UI | Penalty UX | Tổng Penalty |
|---|---:|---:|---:|---:|---:|---:|---:|
| **Critical** | 5 | 0 | 0 | 0 | 0 | 0 | 0 |
| **Major** | 3 | 3 | 5 | 8 | 9 | 15 | 24 |
| **Minor** | 1 | 3 | 3 | 6 | 3 | 3 | 6 |
| **Tổng cộng** | | **6** | **8** | **14** | **12** | **18** | **30** |

---

### Bảng 4 — Mandatory Gate

| Gate | Kết quả | Lý do | Hành động bắt buộc |
|---|---|---|---|
| **Critical issue** | ✅ **PASS** | Không có lỗi tê liệt hệ thống hoặc rủi ro mất dữ liệu cấp Critical | Tiếp tục duy trì chất lượng kỹ thuật |
| **Mandatory checklist** | ⚠️ **NEEDS VALIDATION** | Cần kiểm tra tương tác bàn phím, phóng to 200% và cơ chế responsive trên các màn hình nhỏ | Thực hiện kiểm thử trên môi trường web tương tác |
| **Task blocker** | ⚠️ **CẢNH BÁO** | Xung đột vị trí menu Sidebar và tiêu đề trang làm gián đoạn luồng nhận diện tác vụ | Đồng bộ hóa active route với breadcrumb |
| **Accessibility (WCAG AA)** | ⚠️ **CẢNH BÁO** | Các thẻ viết tắt `[CN]`, `[XLC]`, `[PH]` thiếu Accessible name và giải nghĩa (WCAG 3.1.4) | Bổ sung tooltip chú thích và aria-label đầy đủ |
| **Excellent eligibility** | ❌ **FAIL** | Điểm tổng thể 81.7/100, còn tồn tại 8 lỗi Major | Khắc phục các issue P1 & P2 để đạt chuẩn Excellent (>= 90) |

---

## 3. Bảng Kết quả đầu ra (Issue Log & Chi tiết kiểm định)

*Quy tắc sắp xếp: Từ trên xuống dưới, từ trái qua phải theo cấu trúc thị giác của giao diện.*

| Issue ID | Phân loại | Mã checklist | Tên luồng | Chức năng | Bước thao tác | Thiết bị | Mức độ ảnh hưởng | Hình ảnh | Vấn đề | Đề xuất giải pháp | Hiệu quả sau cải tiến | Xếp loại Issue | Xếp loại Checklist | Effort | Urgency | Priority points |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---:|---:|---:|
| **ISS-01** | UX | `UX-NV01` | Điều hướng | Header & Toolbar | Tìm kiếm văn bản | Desktop | Major | Top Header & Thanh tìm kiếm chính | Trùng lặp 2 ô tìm kiếm (Global search trên Top Header và Document Search trên Toolbar) gây phân vân về phạm vi tìm kiếm | Quy định rõ Global search trên Header dùng để tìm nhanh mã/tên VB toàn hệ thống, hoặc ẩn Search header khi đã vào trang Tra cứu chuyên sâu | Tinh gọn giao diện, người dùng không bị bối rối | Major | FAIL | 2 | 3 | 4.5 (P2) |
| **ISS-02** | UX | `UX-NV02` | Điều hướng | Sidebar & Breadcrumb | Định vị trang | Desktop | Major | Sidebar trái & Breadcrumb | Sidebar đang active ở *"VB đến cá nhân chờ xử lý"*, nhưng Breadcrumb & Tiêu đề trang lại là *"Tra cứu VB"* | Đồng bộ chính xác trạng thái active ở Sidebar tương ứng với tiêu đề Breadcrumb của màn hình hiện tại | Người dùng luôn nhận biết chính xác vị trí và ngữ cảnh làm việc | Major | FAIL | 1 | 3 | 9.0 (P1) |
| **ISS-03** | UI | `UI-TY09` | Tìm kiếm | Ô nhập tìm kiếm | Xem gợi ý | Desktop | Minor | Ô input tìm kiếm chính | Placeholder quá dài (*"Nhập số tìm số văn bản. Nhập từ khóa tìm trích yếu, số ký hiệu (hỗ trợ ký tự *) và đơn vị ban hành."*) gây rối mắt và dễ bị cắt chữ trên màn hình nhỏ | Rút gọn placeholder thành: *"Tìm theo trích yếu, số ký hiệu, đơn vị ban hành..."*, chi tiết cú pháp hỗ trợ đưa vào icon tooltip trợ giúp `(?)` | Input gọn gàng, tăng tính thẩm mỹ | Minor | FAIL | 1 | 2 | 2.0 (P2) |
| **ISS-04** | UX | `UX-TC03` | Quản lý văn bản | Bảng dữ liệu | Đọc trích yếu | Desktop | Major | Cột Trích yếu (các tag màu) | Các thẻ viết tắt `[CN]`, `[XLC]`, `[PH]` không có chú giải ngữ nghĩa, người dùng mới không thể hiểu ngay ý nghĩa | Thêm tooltip khi hover vào tag (VD: `[XLC]` -> "Xử lý chính", `[PH]` -> "Phối hợp", `[CN]` -> "Cá nhân") và chuẩn hóa màu ngữ nghĩa | Dễ hiểu, thân thiện với mọi đối tượng người dùng | Major | FAIL | 1 | 3 | 9.0 (P1) |
| **ISS-05** | UI | `UI-DA02` | Quản lý văn bản | Bảng dữ liệu | Xem danh sách | Desktop | Major | Cột `#` trong bảng | Cột tiêu đề `#` không hiển thị số thứ tự (STT 1, 2, 3...) mà lại dùng để chứa các icon trạng thái (sao, tích xanh, mắt...) | Tách riêng cột STT rõ ràng (1, 2, 3...) và cột Trạng thái/Đánh dấu riêng biệt | Giúp người dùng dễ dàng theo dõi số lượng và thứ tự văn bản | Major | FAIL | 1 | 3 | 9.0 (P1) |
| **ISS-06** | UX | `UX-TC02` | Quản lý văn bản | Bảng dữ liệu | Đọc số ký hiệu | Desktop | Major | Cột Số ký hiệu | Số ký hiệu ở các dòng dưới chuyển sang màu đỏ (VD: `2482/VNPTIT-NS`, `4043/CT-CDS`...) mà không có quy ước rõ ràng trong bảng chú thích | Chuẩn hóa màu chữ số ký hiệu (chỉ dùng màu đỏ nếu văn bản Quá hạn/Hỏa tốc và phải ghi chú rõ ràng) | Tránh gây hoang mang hoặc hiểu nhầm về mức độ cảnh báo | Major | FAIL | 1 | 2 | 6.0 (P1) |
| **ISS-07** | UX | `UX-RC01` | Quản lý văn bản | Bảng dữ liệu | Xem chi tiết ngày & đơn vị | Desktop | Minor | Cột Đơn vị, Ngày đến, Ngày ban hành | Xuất hiện nhiều dữ liệu trống dạng `__` hoặc `--` thiếu nhất quán (VD: Đơn vị `__`, `Ngày 10/08/2026 - __`, Nơi nhận `--`) | Chuẩn hóa hiển thị khi dữ liệu rỗng (ví dụ để trống nhẹ nhàng hoặc dùng nhãn `-` mờ thống nhất) | Giao diện bảng chỉn chu, chuyên nghiệp | Minor | FAIL | 1 | 2 | 2.0 (P2) |
| **ISS-08** | UX | `UX-RC02` | Quản lý văn bản | Bảng dữ liệu | Đối soát dữ liệu | Desktop | Minor | Cột Ngày đến dòng 3 | Dòng 3 hiển thị ngày tương lai bất thường: *"01/07/2028 - 123"* trong khi ngày văn bản là *"30/06/2026"* (Lệch logic thời gian 2 năm) | Kiểm tra và ràng buộc dữ liệu ngày đến không được lớn hơn thời điểm hiện tại hoặc sai lệch bất thường | Đảm bảo tính toàn vẹn và độ tin cậy của dữ liệu | Minor | FAIL | 2 | 2 | 1.0 (P3) |
| **ISS-09** | UI | `UI-LA01` | Bố cục | Chân bảng dữ liệu | Tra cứu trạng thái | Desktop | Major | Bảng chú thích trạng thái (Legend) | Khu vực chú thích trạng thái đặt tách biệt ở đáy bảng (dưới cả thanh phân trang), gây khó quan sát khi bảng dài | Đưa thanh chú thích trạng thái lên góc trên bảng (hoặc vào popover hướng dẫn cạnh tiêu đề cột) | Người dùng dễ dàng tra cứu ký hiệu ngay khi nhìn bảng | Major | FAIL | 1 | 3 | 9.0 (P1) |
| **ISS-10** | UI | `UI-LA07` | Trải nghiệm tương tác | Bảng dữ liệu & Footer | Thao tác trên bảng | Desktop | Major | Nút Chatbot tròn góc dưới phải | Nút Chatbot/Hỗ trợ dạng floating cố định đè lên nội dung của cột *"Nơi nhận"* ở các dòng cuối bảng | Tạo khoảng đệm an toàn (safe-area/padding-right) cho bảng hoặc cho phép thu nhỏ/di chuyển nút widget | Đảm bảo không bị che khuất bất kỳ dòng dữ liệu nào | Major | FAIL | 1 | 3 | 9.0 (P1) |
| **ISS-11** | UI | `UI-IC05` | Cài đặt hệ thống | Footer | Chọn giao diện | Desktop | Minor | Dropdown Giao diện (Theme Color) | Dropdown ghi nhãn *"Xanh dương"* nhưng icon phía trước lại là Cỏ 4 lá màu xanh lá cây (`☘️`) gây lệch ngữ nghĩa | Đổi icon thành ô màu xanh dương chuẩn (VD: icon giọt nước xanh hoặc palette xanh) | Đồng nhất giữa hình ảnh biểu tượng và nhãn văn bản | Minor | FAIL | 1 | 1 | 1.0 (P3) |
| **ISS-12** | UI | `UI-BU04` | Thao tác | Thanh công cụ | Tìm kiếm & Lọc | Desktop | Minor | Cụm nút "Mặc định", "Tìm kiếm", "Bộ lọc" | Khoảng cách và độ cao các nút trên thanh tìm kiếm chưa đồng bộ nhịp nhàng với ô input | Chuẩn hóa padding, radius và chiều cao chuẩn (36px hoặc 40px) theo Design System | Cụm thanh công cụ hài hòa, cân đối | Minor | FAIL | 1 | 2 | 2.0 (P2) |
| **ISS-13** | UX | `UX-CS01` | Quản lý văn bản | Thanh tác vụ bảng | Tải danh sách | Desktop | Minor | Nút "Tải DS" | Nút "Tải DS" chỉ có 1 nút bấm đơn thuần, chưa hiển thị tùy chọn định dạng xuất (Excel, PDF) hoặc phạm vi tải (Tất cả / Đã chọn) | Tích hợp dropdown menu nhỏ cạnh nút Tải DS cho phép chọn *"Xuất Excel"*, *"Xuất PDF"*, *"Tải các mục đã chọn"* | Thao tác xuất dữ liệu linh hoạt, đúng nhu cầu | Minor | FAIL | 2 | 2 | 1.0 (P3) |
| **ISS-14** | UX | `UX-PG01` | Điều hướng trang | Phân trang | Chuyển trang | Desktop | Minor | Thanh phân trang | Nút chọn số dòng/trang (`10 / trang`) đặt cách xa dãy số trang nhưng thiếu hiển thị khoảng bản ghi hiện tại (VD: *"Hiển thị 1-10 trên 286 kết quả"*) | Bổ sung text tóm tắt *"Hiển thị 1 - 10 của 286 văn bản"* ở góc trái phân trang | Giúp người dùng nắm bắt tiến độ duyệt danh sách | Minor | FAIL | 1 | 2 | 2.0 (P2) |

---

## 4. Bảng Kế hoạch cải tiến (Improvement Roadmap)

*Danh sách được lọc từ các Issue FAIL và sắp xếp theo thứ tự ưu tiên xử lý P1 → P2 → P3.*

| Issue ID | Phân loại | Mã checklist | Chức năng | Bước thao tác | Thiết bị | Mức độ ảnh hưởng | Hình ảnh | Vấn đề | Đề xuất giải pháp | Hiệu quả sau cải tiến | Priority |
|---|---|---|---|---|---|---|---|---|---|---|---|
| **ISS-02** | UX | `UX-NV02` | Định vị trang | Xem sidebar | Desktop | Major | Sidebar & Breadcrumb | Sidebar active mục "VB đến cá nhân" nhưng breadcrumb ghi "Tra cứu VB" | Đồng bộ active route chính xác theo từng trang | Tránh nhầm lẫn ngữ cảnh làm việc | **P1** |
| **ISS-04** | UX | `UX-TC03` | Quản lý văn bản | Đọc trích yếu | Desktop | Major | Cột Trích yếu | Các tag `[CN]`, `[XLC]`, `[PH]` viết tắt không có giải nghĩa | Bổ sung tooltip giải nghĩa khi hover vào tag | Trực quan, người dùng mới hiểu ngay | **P1** |
| **ISS-05** | UI | `UI-DA02` | Quản lý văn bản | Xem danh sách | Desktop | Major | Cột `#` | Cột `#` bị gộp icon trạng thái, thiếu STT thực tế | Tách riêng cột STT (1, 2, 3...) và cột Trạng thái | Đếm và đối soát danh sách dễ dàng | **P1** |
| **ISS-06** | UX | `UX-TC02` | Quản lý văn bản | Đọc số ký hiệu | Desktop | Major | Cột Số ký hiệu | Số ký hiệu đổi màu đỏ không rõ nguyên nhân | Chuẩn hóa màu chữ và có ghi chú cảnh báo nếu quá hạn | Dữ liệu nhất quán, không gây hiểu lầm | **P1** |
| **ISS-09** | UI | `UI-LA01` | Bố cục | Tra cứu trạng thái | Desktop | Major | Legend chân trang | Bảng chú thích trạng thái bị đặt quá xa bảng dữ liệu | Chuyển Legend lên trên đầu bảng hoặc vào tooltip hỗ trợ | Tra cứu trạng thái tiện lợi ngay lập tức | **P1** |
| **ISS-10** | UI | `UI-LA07` | Bố cục | Thao tác trên bảng | Desktop | Major | Nút Chatbot nổi | Floating widget Chatbot che khuất nội dung cột Nơi nhận | Thêm padding-right an toàn hoặc cho phép thu gọn widget | Tránh che khuất dữ liệu quan trọng | **P1** |
| **ISS-01** | UX | `UX-NV01` | Tìm kiếm | Nhập từ khóa | Desktop | Major | Top Header & Toolbar | 2 ô tìm kiếm đặt gần nhau gây nhiễu | Phân định rõ chức năng Global Search và In-page Search | Tinh gọn thao tác tìm kiếm | **P2** |
| **ISS-03** | UI | `UI-TY09` | Tìm kiếm | Nhập tìm kiếm | Desktop | Minor | Ô input tìm kiếm | Placeholder quá dài gây rối mắt | Rút gọn placeholder súc tích và thêm icon trợ giúp | Giao diện thanh thoát, dễ đọc | **P2** |
| **ISS-07** | UX | `UX-RC01` | Quản lý văn bản | Xem dữ liệu | Desktop | Minor | Bảng dữ liệu | Ký tự trống `__`, `--` xuất hiện lộn xộn | Chuẩn hóa ký tự dữ liệu trống đồng nhất | Bảng dữ liệu chuyên nghiệp, sạch sẽ | **P2** |
| **ISS-12** | UI | `UI-BU04` | Thao tác | Bấm nút lọc | Desktop | Minor | Cụm nút tìm kiếm | Chiều cao và khoảng cách các nút chưa đồng đều | Đồng bộ size và khoảng cách theo Design System | Cân đối, thẩm mỹ cao | **P2** |
| **ISS-14** | UX | `UX-PG01` | Phân trang | Chuyển trang | Desktop | Minor | Thanh phân trang | Thiếu thông tin số dòng đang hiển thị (1-10 / 286) | Thêm text *"Hiển thị 1-10 của 286 văn bản"* | Giúp nắm bắt tiến độ xem trang | **P2** |
| **ISS-08** | UX | `UX-RC02` | Quản lý văn bản | Đối soát dữ liệu | Desktop | Minor | Cột Ngày đến | Ngày đến năm 2028 sai logic so với ngày ban hành 2026 | Ràng buộc kiểm tra tính hợp lệ của dữ liệu ngày tháng | Dữ liệu chính xác tuyệt đối | **P3** |
| **ISS-11** | UI | `UI-IC05` | Cài đặt | Chọn theme | Desktop | Minor | Footer Dropdown | Nhãn "Xanh dương" đi kèm icon Cỏ xanh | Đổi icon khớp với màu xanh dương | Đồng nhất biểu tượng và nhãn | **P3** |
| **ISS-13** | UX | `UX-CS01` | Tác vụ | Tải danh sách | Desktop | Minor | Nút "Tải DS" | Nút Tải DS chưa có tùy chọn loại tệp xuất | Thêm menu chọn xuất Excel / PDF | Tăng tính tiện dụng cho nghiệp vụ | **P3** |

---

## 5. Danh mục Checklist chi tiết đã đánh giá

### 5.1. Checklist UI (81 tiêu chí thư viện chuẩn)
- **Áp dụng (Applicable): 30 tiêu chí**
  - **PASS (24):** `UI-LA02`, `UI-LA03`, `UI-LA04`, `UI-LA05`, `UI-LA06`, `UI-SI01`, `UI-LO01`, `UI-LO02`, `UI-LO03`, `UI-LO04`, `UI-TY01`, `UI-TY02`, `UI-TY03`, `UI-TY04`, `UI-TY05`, `UI-TY06`, `UI-TY07`, `UI-TY08`, `UI-TY12`, `UI-IC01`, `UI-IC02`, `UI-IC03`, `UI-IC04`, `UI-DA01`.
  - **FAIL (6):** `UI-LA01` (Bố cục Legend bị đẩy xuống đáy), `UI-LA07` (Floating widget che khuất nội dung), `UI-TY09` (Placeholder quá dài), `UI-DA02` (Cột `#` thiếu STT thực tế), `UI-IC05` (Icon cỏ xanh đi kèm chữ Xanh dương), `UI-BU04` (Padding/Height nút Toolbar chưa tối ưu).
  - **NEEDS VALIDATION / UNKNOWN (5):** `UI-LA08` (Zoom 200%), `UI-BU05` (Hover/focus states trên web), `UI-DA03` (Trạng thái hover hàng bảng), `UI-DA04` (Responsive bảng dữ liệu), `UI-TY14` (Responsive text).
- **Không áp dụng (N/A): 46 tiêu chí** (Bao gồm Modal/Dialog, Switch, Breadcrumb đa cấp phức tạp, Card view, Tabs, Biểu đồ thống kê...).

### 5.2. Checklist UX (286 tiêu chí thư viện chuẩn)
- **Áp dụng (Applicable): 34 tiêu chí**
  - **PASS (26):** `UX-TC01`, `UX-TC04`, `UX-TC05`, `UX-TC06`, `UX-TC07`, `UX-TC15`, `UX-TC16`, `UX-TC17`, `UX-TC20`, `UX-TC21`, `UX-HI03`, `UX-HI04`, `UX-ND02`, `UX-ND03`, `UX-NV03`, `UX-TT01`, `UX-TT02`, `UX-TT03`, `UX-TT04`, `UX-EC02`, `UX-EC03`, `UX-CS02`, `UX-CS03`, `UX-CS04`, `UX-PG02`, `UX-PG03`.
  - **FAIL (8):** `UX-NV01` (Trùng lặp 2 ô tìm kiếm), `UX-NV02` (Mất đồng bộ giữa Sidebar và Breadcrumb), `UX-TC02` (Màu sắc số ký hiệu đổi đỏ không rõ lý do), `UX-TC03` (Các tag viết tắt CN/XLC/PH thiếu giải thích), `UX-RC01` (Hiển thị ký tự trống `__`/`--` lộn xộn), `UX-RC02` (Lệch logic thời gian 2028 vs 2026), `UX-CS01` (Nút Tải DS thiếu tùy chọn định dạng), `UX-PG01` (Thanh phân trang thiếu text tổng quan số lượng).
  - **NEEDS VALIDATION / UNKNOWN (8):** Khả năng điều hướng bằng bàn phím (Tab order), screen reader compatibility, tốc độ phản hồi khi search, debounce khi gõ phím.
- **Không áp dụng (N/A): 244 tiêu chí** (Các tiêu chí cho luồng thanh toán, form nhập liệu nhiều bước, video/audio...).

---

## 6. Kết luận và Khuyến nghị

1. **Giai đoạn 1 (Khắc phục ngay - P1):**
   - Đồng bộ trạng thái active của menu Sidebar với Breadcrumb để định vị chuẩn ngữ cảnh.
   - Thêm tooltip giải nghĩa cho các tag viết tắt `[CN]`, `[XLC]`, `[PH]`.
   - Tách biệt rõ ràng cột Số thứ tự (STT) và cột Biểu tượng trạng thái.
   - Đưa bảng chú thích trạng thái (Legend) lên khu vực dễ quan sát trên bảng.
   - Điều chỉnh vị trí của Floating Chatbot Widget để không che khuất dữ liệu dòng cuối.
2. **Giai đoạn 2 (Tối ưu nghiệp vụ & giao diện - P2):**
   - Tinh gọn cụm tìm kiếm, rút ngắn nội dung placeholder và phân định rõ phạm vi tìm kiếm.
   - Chuẩn hóa màu sắc số ký hiệu và cách hiển thị giá trị rỗng (`-`).
   - Bổ sung text chỉ số phân trang *"Hiển thị 1-10 của 286 văn bản"*.
3. **Giai đoạn 3 (Hoàn thiện trải nghiệm - P3):**
   - Thêm dropdown menu tùy chọn xuất tệp (Excel / PDF) cho nút Tải DS.
   - Điều chỉnh icon dropdown giao diện màu ở Footer cho đồng nhất với nhãn *"Xanh dương"*.
