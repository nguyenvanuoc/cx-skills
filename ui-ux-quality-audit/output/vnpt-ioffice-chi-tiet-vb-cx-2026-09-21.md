# Báo cáo Đánh giá Chất lượng UI/UX (UI/UX Quality Audit Report)

- **Sản phẩm:** VNPT iOffice - Hệ thống Quản lý Văn bản và Điều hành
- **Màn hình đánh giá:** Chi tiết Văn bản đến ("Thông tin văn bản" - 108/QĐ-VNPTIT-SI)
- **Nền tảng / Thiết bị:** Web Desktop (1920x1080)
- **Thời gian thực hiện:** 21/09/2026
- **Tiêu chuẩn tham chiếu:** VNPT Design System, WCAG 2.2 AA, ISO 9241-161 / ISO 9241-210, Material Design 3, Apple HIG

---

## 1. Executive Summary

Màn hình **Chi tiết Văn bản đến ("Thông tin văn bản" - VNPT iOffice)** cung cấp cái nhìn toàn diện về một văn bản tiếp nhận, phân chia thành các khối thông tin logic (Thông tin chung, Thông tin lưu số, Tài liệu đính kèm, Ý kiến xử lý) và tích hợp nhiều tiện ích chuyên sâu (Tóm tắt VB bằng AI, Tham chiếu văn bản, Sơ đồ luồng, Log xử lý). Tuy nhiên, qua quá trình thẩm định UI/UX chuyên sâu, màn hình còn bộc lộ một số vấn đề về **tính nhất quán điều hướng**, **tải nhận thức** và **bố cục tương tác**:

1. **Breadcrumb bị cắt cụt vô lý (Premature Truncation):** Breadcrumb hiển thị `VB đến cá nhân chờ xử lý / Thông...` bị cắt cụt bằng dấu ba chấm (`...`) dù khoảng trống bên phải còn rất rộng.
2. **Xung đột điều khiển Đóng/Mở Card (Duplicate Accordion Controls):** Mỗi thẻ (Card) vừa có icon mũi tên thu gọn `^` ở góc trên bên phải, vừa có thêm nút `Mở rộng v` ở góc dưới bên phải, gây hoang mang cho người dùng về trạng thái thực của Card.
3. **Quá tải hành động & Thiếu phân cấp nút tác vụ (Toolbar Cognitive Overload):**
   - Thanh tác vụ đầu trang tập trung quá nhiều nút: `Chuyển xử lý`, `Kết thúc văn bản`, `Tạo việc`, `Đánh dấu đã đọc`, `Lưu hồ sơ công việc`, `In Phiếu trình`, `Khác`.
   - Nút *"Kết thúc văn bản"* (hành động đóng quy trình có tính chất quan trọng) dùng màu xanh đậm tương tự nút *"Chuyển xử lý"*, thiếu sự phân biệt rõ ràng về mức độ an toàn.
4. **Trùng lặp thông tin và nút bấm trong cùng ngữ cảnh (Redundancy):**
   - Badge `Thường` đặt đầu Card 1 bị trùng 100% với trường dữ liệu `Độ khẩn: Thường` ngay phía dưới.
   - Nút *"Xem toàn bộ log"* xuất hiện 2 lần liên tiếp trong khối *Tổng hợp ý kiến xử lý* (một nút ở Header card chính, một nút ở Header thanh đơn vị).
5. **Cắt cụt dữ liệu quan trọng (Data Truncation):** Trường `Đơn vị soạn thảo` và `Người ký` bị cắt chữ (`...`), làm che khuất số điện thoại liên hệ và tên đầy đủ của đơn vị ban hành.
6. **Mật độ hành động trên dòng tệp đính kèm quá cao:** Một dòng tệp PDF chứa cùng lúc 5 hành động (`Tóm tắt VB`, `Tham chiếu văn bản`, `Lấy VB liên quan`, `Lấy nội dung xử lý`, `⋮`), làm kéo dài dòng và dễ gây bấm nhầm.

---

## 2. Tổng quan điểm số (Score Summary)

### Bảng 1 — Score Summary

| Chỉ số | Giá trị UI | Giá trị UX | Toàn hệ thống / Tổng hợp |
|---|---:|---:|---:|
| **Tổng checklist áp dụng** | 28 | 32 | 60 |
| **Checklist PASS** | 23 | 25 | 48 |
| **Checklist FAIL** | 5 | 7 | 12 |
| **Checklist N/A** | 48 | 246 | 294 |
| **Checklist NEEDS VALIDATION** | 5 | 8 | 13 |
| **Tổng số Issue phát hiện** | 5 | 7 | 12 |
| - Critical (Trọng số 5) | 0 | 0 | 0 |
| - Major (Trọng số 3) | 2 | 4 | 6 |
| - Minor (Trọng số 1) | 3 | 3 | 6 |
| **Issue Penalty** | 9 | 15 | 24 |
| **Checklist Compliance Score** | **82.1 / 100** | **78.1 / 100** | **80.0 / 100** |
| **Issue Score** | **93.6 / 100** | **90.6 / 100** | **92.0 / 100** |
| **UI Quality Score** (70% CL + 30% Issue) | **85.6 / 100** | — | — |
| **UX Quality Score** (70% CL + 30% Issue) | — | **81.9 / 100** | — |
| **Experience Quality Score** (40% UI + 60% UX) | — | — | **83.4 / 100** |

---

### Bảng 2 — Calculation Detail

| Chỉ số | Giá trị đầu vào | Công thức tính toán | Kết quả |
|---|---|---|---:|
| **UI Checklist Score** | Áp dụng: 28, FAIL: 5 | `(28 - 5) / 28 * 100` | **82.1** |
| **UI Issue Penalty** | Minor: 3, Major: 2, Critical: 0 | `3*1 + 2*3 + 0*5` | **9** |
| **UI Issue Score** | Áp dụng: 28, Penalty: 9 | `100 * (1 - 9 / (28 * 5))` | **93.6** |
| **UI Quality Score** | CL Score: 82.1, Issue Score: 93.6 | `82.1 * 70% + 93.6 * 30%` | **85.6** |
| **UX Checklist Score** | Áp dụng: 32, FAIL: 7 | `(32 - 7) / 32 * 100` | **78.1** |
| **UX Issue Penalty** | Minor: 3, Major: 4, Critical: 0 | `3*1 + 4*3 + 0*5` | **15** |
| **UX Issue Score** | Áp dụng: 32, Penalty: 15 | `100 * (1 - 15 / (32 * 5))` | **90.6** |
| **UX Quality Score** | CL Score: 78.1, Issue Score: 90.6 | `78.1 * 70% + 90.6 * 30%` | **81.9** |
| **Experience Quality Score** | UI: 85.6, UX: 81.9 | `85.6 * 40% + 81.9 * 60%` | **83.4 / 100** |

---

### Bảng 3 — Severity Summary

| Severity | Weight | Số issue UI | Số issue UX | Tổng Issue | Penalty UI | Penalty UX | Tổng Penalty |
|---|---:|---:|---:|---:|---:|---:|---:|
| **Critical** | 5 | 0 | 0 | 0 | 0 | 0 | 0 |
| **Major** | 3 | 2 | 4 | 6 | 6 | 12 | 18 |
| **Minor** | 1 | 3 | 3 | 6 | 3 | 3 | 6 |
| **Tổng cộng** | | **5** | **7** | **12** | **9** | **15** | **24** |

---

### Bảng 4 — Mandatory Gate

| Gate | Kết quả | Lý do | Hành động bắt buộc |
|---|---|---|---|
| **Critical issue** | ✅ **PASS** | Không có lỗi nghiêm trọng gây treo luồng hoặc mất dữ liệu | Tiếp tục duy trì chất lượng kỹ thuật |
| **Mandatory checklist** | ⚠️ **NEEDS VALIDATION** | Cần kiểm tra hoạt động của modal "Chuyển xử lý", "Kết thúc văn bản", tương tác phím và responsive | Kiểm thử tương tác động trên môi trường thật |
| **Task blocker** | ✅ **PASS** | Luồng nghiệp vụ cơ bản vẫn thông suốt | Tối ưu hóa trải nghiệm thao tác |
| **Accessibility (WCAG AA)** | ⚠️ **CẢNH BÁO** | Text breadcrumb bị cắt cụt (`Thông...`), các nút phụ trên dòng file PDF có kích thước hit-target nhỏ | Sửa độ rộng hiển thị breadcrumb và tăng padding cho action |
| **Excellent eligibility** | ❌ **FAIL** | Điểm toàn diện đạt 83.4/100, còn tồn tại 6 issue Major | Khắc phục các issue P1 & P2 để nâng hạng lên Excellent |

---

## 3. Bảng Kết quả đầu ra (Issue Log & Chi tiết kiểm định)

*Quy tắc sắp xếp: Từ trên xuống dưới, từ trái qua phải theo cấu trúc thị giác của giao diện.*

| Issue ID | Phân loại | Mã checklist | Tên luồng | Chức năng | Bước thao tác | Thiết bị | Mức độ ảnh hưởng | Hình ảnh | Vấn đề | Đề xuất giải pháp | Hiệu quả sau cải tiến | Xếp loại Issue | Xếp loại Checklist | Effort | Urgency | Priority points |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---:|---:|---:|
| **ISS-01** | UI | `UI-BR01` | Điều hướng | Breadcrumb | Xem vị trí | Desktop | Minor | Góc trên bên trái | Breadcrumb bị cắt cụt vô lý: *"VB đến cá nhân chờ xử lý / Thông..."* dù khoảng trống bên phải còn rất lớn | Hiển thị đầy đủ: *"VB đến cá nhân chờ xử lý / Chi tiết văn bản 108/QĐ-VNPTIT-SI"* | Giúp người dùng nắm bắt ngữ cảnh và số hiệu văn bản tức thì | Minor | FAIL | 1 | 2 | 2.0 (P2) |
| **ISS-02** | UI | `UI-BU02` | Tác vụ | Action Toolbar | Thực hiện tác vụ | Desktop | Major | Toolbar góc trên bên phải | Quá nhiều nút ngang hàng (`Chuyển xử lý`, `Kết thúc văn bản`, `Tạo việc`, `Đánh dấu đã đọc`, `Lưu hồ sơ`, `In Phiếu trình`) làm loãng phân cấp thị giác | Giữ lại 1 nút Primary nổi bật nhất (`Chuyển xử lý`), gom các hành động phụ vào menu dropdown `Khác` hoặc dạng Secondary/Ghost button | Tập trung sự chú ý vào hành động nghiệp vụ quan trọng nhất | Major | FAIL | 1 | 3 | 9.0 (P1) |
| **ISS-03** | UX | `UX-EC01` | Tác vụ | Kết thúc văn bản | Bấm nút kết thúc | Desktop | Major | Nút "Kết thúc văn bản" | Nút "Kết thúc văn bản" là hành động đóng văn bản quan trọng nhưng dùng style tương tự nút Chuyển xử lý và cần đảm bảo luôn có modal xác nhận lý do | Chuyển style sang Secondary/Outline kèm icon cảnh báo, bắt buộc mở Dialog xác nhận trước khi hoàn tất | Tránh bấm nhầm kết thúc văn bản khi chưa xử lý xong | Major | FAIL | 2 | 3 | 4.5 (P2) |
| **ISS-04** | UI | `UI-CA01` | Trình bày | Thẻ Thông tin chung & Lưu số | Xem & Thu gọn | Desktop | Major | Góc trên phải và góc dưới phải các Card | Thẻ vừa có icon thu gọn `^` ở Header, vừa có nút `Mở rộng v` ở chân Card gây dư thừa và mâu thuẫn trạng thái | Loại bỏ nút `Mở rộng v` ở chân card, chỉ giữ lại icon đóng/mở chuẩn ở Header của Card | Giao diện gọn gàng, tương tác chuẩn mực | Major | FAIL | 1 | 3 | 9.0 (P1) |
| **ISS-05** | UX | `UX-ND01` | Trình bày | Thẻ Thông tin chung | Đọc độ khẩn | Desktop | Minor | Thẻ Thông tin chung | Badge `Thường` ở đầu tiêu đề bị trùng lặp với trường `Độ khẩn: Thường` ở bên dưới | Tinh gọn: nếu đã có Badge nổi bật ở tiêu đề thì có thể ẩn hoặc gộp trường Độ khẩn trong bảng chi tiết | Giảm thông tin rác, tăng không gian thoáng đãng | Minor | FAIL | 1 | 1 | 1.0 (P3) |
| **ISS-06** | UI | `UI-TY14` | Hiển thị dữ liệu | Thẻ Thông tin chung & Lưu số | Đọc thông tin | Desktop | Minor | Cột Đơn vị soạn thảo & Người ký | Dữ liệu `Đơn vị soạn thảo` và `Người ký` bị cắt chữ (`...`) che mất tên đầy đủ và số điện thoại | Cho phép text tự động xuống dòng (wrap text) hoặc hiển thị tooltip khi hover | Đọc trọn vẹn thông tin liên hệ và đơn vị ban hành | Minor | FAIL | 1 | 2 | 2.0 (P2) |
| **ISS-07** | UX | `UX-RC01` | Hiển thị dữ liệu | Các trường thông tin | Đọc chi tiết | Desktop | Minor | Các trường Lĩnh vực, Ghi chú, Hạn xử lý, Số trang... | Quá nhiều trường hiển thị giá trị `--` làm tăng chiều dài form một cách không cần thiết | Ẩn bớt các trường rỗng ở chế độ xem mặc định, chỉ hiển thị khi bấm "Xem thêm thông tin" | Tăng tính súc tích, người dùng chỉ tập trung vào dữ liệu có thật | Minor | FAIL | 2 | 2 | 1.0 (P3) |
| **ISS-08** | UX | `UX-CS01` | Tài liệu đính kèm | Dòng tệp tin | Thao tác tệp | Desktop | Major | Dòng file `108QD-VNPTIT-SI...pdf` | Dòng tệp chứa quá nhiều nút hành động (`Tóm tắt VB`, `Tham chiếu văn bản`, `Lấy VB liên quan`, `Lấy nội dung xử lý`, `⋮`) gây rối mắt | Gom các tính năng AI/Nâng cao vào menu `⋮` hoặc popover tác vụ thông minh khi click vào tệp | Danh sách tệp đính kèm thoáng, dễ đọc | Major | FAIL | 2 | 3 | 4.5 (P2) |
| **ISS-09** | UI | `UI-TY02` | Tài liệu đính kèm | Tên file PDF | Đọc tên file | Desktop | Minor | Tên file PDF đính kèm | Tên file bị cắt cụt ở giữa (`108QD-VNPTIT-SI...0260630.pdf`) làm mất thông tin ngày tháng đầy đủ của file | Điều chỉnh độ rộng cột tên file và hiển thị tooltip đầy đủ tên tệp gốc khi rê chuột | Nhận diện chính xác tên tệp văn bản đính kèm | Minor | FAIL | 1 | 2 | 2.0 (P2) |
| **ISS-10** | UX | `UX-ND02` | Ý kiến xử lý | Khối Ý kiến | Đọc luồng xử lý | Desktop | Major | Header Card Ý kiến & Header Đơn vị | Nút *"Xem toàn bộ log"* xuất hiện 2 lần liên tiếp (ở Header Card chính và Header thanh đơn vị màu xanh) | Bỏ nút lặp ở Header Card chính, chỉ giữ nút log gắn liền với đơn vị xử lý cụ thể | Loại bỏ sự dư thừa nút bấm, làm sạch giao diện | Major | FAIL | 1 | 3 | 9.0 (P1) |
| **ISS-11** | UX | `UX-TC02` | Ý kiến xử lý | Chi tiết phân công | Đọc vai trò | Desktop | Minor | Cột Nội dung ý kiến xử lý | Các vai trò `Xử lý chính`, `Phối hợp xử lý`, `Xem để biết` dùng các màu sắc khác nhau (xanh lá, xanh dương, cam) nhưng thiếu badge nhận diện rõ ràng | Sử dụng Tag/Badge có nền nhẹ bao quanh tên nhân sự tương ứng với từng vai trò | Phân biệt vai trò xử lý trực quan và chuyên nghiệp hơn | Minor | FAIL | 1 | 2 | 2.0 (P2) |
| **ISS-12** | UI | `UI-LA01` | Thanh công cụ nổi | Right Dock Icons | Thao tác tiện ích | Desktop | Minor | Dãy icon dọc bên phải màn hình | Dãy 4 icon tròn nổi bên mép phải chiếm không gian thị giác và dễ gây phân tâm | Thiết kế dock thu gọn thông minh hoặc đồng bộ vào hệ thống drawer panel bên phải | Màn hình xem chi tiết tập trung tối đa vào văn bản | Minor | FAIL | 2 | 2 | 1.0 (P3) |

---

## 4. Bảng Kế hoạch cải tiến (Improvement Roadmap)

*Danh sách được lọc từ các Issue FAIL và sắp xếp theo thứ tự ưu tiên xử lý P1 → P2 → P3.*

| Issue ID | Phân loại | Mã checklist | Chức năng | Bước thao tác | Thiết bị | Mức độ ảnh hưởng | Hình ảnh | Vấn đề | Đề xuất giải pháp | Hiệu quả sau cải tiến | Priority |
|---|---|---|---|---|---|---|---|---|---|---|---|
| **ISS-02** | UI | `UI-BU02` | Tác vụ | Thực hiện tác vụ | Desktop | Major | Action Toolbar | Quá nhiều nút tác vụ dàn hàng ngang gây loãng phân cấp | Giữ 1 nút Primary chính, gom nút phụ vào menu dropdown `Khác` | Tinh gọn thanh công cụ, nhấn mạnh hành động chính | **P1** |
| **ISS-04** | UI | `UI-CA01` | Trình bày | Đóng/mở Card | Desktop | Major | Góc Card | Thẻ vừa có mũi tên thu gọn `^`, vừa có nút `Mở rộng v` gây mâu thuẫn | Bỏ nút `Mở rộng v` ở chân card, chỉ dùng icon đóng/mở ở Header | Thao tác đóng mở chuẩn mực, không gây nhầm lẫn | **P1** |
| **ISS-10** | UX | `UX-ND02` | Ý kiến xử lý | Đọc log xử lý | Desktop | Major | Khối Ý kiến | Nút *"Xem toàn bộ log"* bị lặp lại 2 lần liên tiếp | Bỏ nút ở Header ngoài, chỉ giữ 1 nút ở Header đơn vị | Giao diện gọn gàng, không trùng lặp | **P1** |
| **ISS-01** | UI | `UI-BR01` | Điều hướng | Xem vị trí | Desktop | Minor | Breadcrumb | Breadcrumb bị cắt chữ `Thông...` vô lý | Hiển thị đầy đủ tiêu đề và mã văn bản | Nắm bắt vị trí chính xác | **P2** |
| **ISS-03** | UX | `UX-EC01` | Tác vụ | Bấm Kết thúc | Desktop | Major | Nút Kết thúc | Nút Kết thúc văn bản cần phân biệt màu sắc và có modal xác nhận | Đổi sang Secondary button + Bắt buộc mở Modal xác nhận lý do | Ngăn ngừa rủi ro đóng nhầm văn bản | **P2** |
| **ISS-06** | UI | `UI-TY14` | Hiển thị dữ liệu | Đọc thông tin | Desktop | Minor | Trường Đơn vị / Người ký | Chữ bị cắt `...` làm mất tên đơn vị và số điện thoại | Cho phép xuống dòng hoặc thêm hover tooltip | Đọc trọn vẹn thông tin liên hệ | **P2** |
| **ISS-08** | UX | `UX-CS01` | Tệp đính kèm | Thao tác tệp | Desktop | Major | Dòng file PDF | 5 nút hành động trên 1 dòng file PDF gây quá tải | Gom các tác vụ AI/Phụ vào menu `⋮` | Danh sách tệp sạch sẽ, dễ thao tác | **P2** |
| **ISS-09** | UI | `UI-TY02` | Tệp đính kèm | Đọc tên tệp | Desktop | Minor | Tên file PDF | Tên tệp bị cắt cụt ở giữa | Mở rộng cột tên tệp và thêm tooltip tên file đầy đủ | Nhận diện đúng file đính kèm | **P2** |
| **ISS-11** | UX | `UX-TC02` | Ý kiến xử lý | Đọc phân công | Desktop | Minor | Cột Nội dung | Màu sắc phân vai chưa có badge bao bọc | Thêm badge nhẹ cho các vai trò Xử lý chính / Phối hợp | Tăng độ rõ ràng của cấu trúc nhân sự | **P2** |
| **ISS-05** | UX | `UX-ND01` | Trình bày | Đọc độ khẩn | Desktop | Minor | Card Thông tin chung | Badge `Thường` lặp lại trường `Độ khẩn: Thường` | Giữ badge nổi bật, tinh giản bớt trường trùng | Giao diện súc tích | **P3** |
| **ISS-07** | UX | `UX-RC01` | Hiển thị dữ liệu | Xem chi tiết | Desktop | Minor | Các trường rỗng | Quá nhiều trường `--` làm dài màn hình | Ẩn các trường không có dữ liệu vào mục xem thêm | Màn hình súc tích, hiện đại | **P3** |
| **ISS-12** | UI | `UI-LA01` | Thanh tiện ích | Xem màn hình | Desktop | Minor | Right Dock | Dãy icon dọc bên phải gây phân tâm thị giác | Tinh giản dock tiện ích thành drawer thu gọn | Không gian hiển thị tài liệu tập trung | **P3** |

---

## 5. Danh mục Checklist chi tiết đã đánh giá

### 5.1. Checklist UI (81 tiêu chí thư viện chuẩn)
- **Áp dụng (Applicable): 28 tiêu chí**
  - **PASS (23):** `UI-LA02`, `UI-LA03`, `UI-LA04`, `UI-LA05`, `UI-LA06`, `UI-SI01`, `UI-LO01`, `UI-LO02`, `UI-LO03`, `UI-LO04`, `UI-TY01`, `UI-TY03`, `UI-TY04`, `UI-TY05`, `UI-TY06`, `UI-TY07`, `UI-TY08`, `UI-TY12`, `UI-IC01`, `UI-IC02`, `UI-IC03`, `UI-IC04`, `UI-DA01`.
  - **FAIL (5):** `UI-BR01` (Breadcrumb bị cắt cụt), `UI-BU02` (Quá nhiều nút chính ngang hàng), `UI-CA01` (Trùng lặp điều khiển đóng/mở card), `UI-TY14` (Cắt chữ đơn vị soạn thảo và người ký), `UI-TY02` (Tên file bị cắt cụt).
  - **NEEDS VALIDATION / UNKNOWN (5):** `UI-LA08` (Zoom 200%), `UI-BU05` (Trạng thái hover/focus/active button), `UI-DA03` (Trạng thái bảng ý kiến), `UI-DA04` (Responsive bảng ý kiến), `UI-MO04` (Modal xác nhận chuyển/kết thúc văn bản).
- **Không áp dụng (N/A): 48 tiêu chí** (Bao gồm Search/Filter phức tạp, Pagination, Data Grid nhiều trang, Switch, Tab navigation...).

### 5.2. Checklist UX (286 tiêu chí thư viện chuẩn)
- **Áp dụng (Applicable): 32 tiêu chí**
  - **PASS (25):** `UX-TC01`, `UX-TC04`, `UX-TC05`, `UX-TC06`, `UX-TC07`, `UX-TC15`, `UX-TC16`, `UX-TC17`, `UX-HI03`, `UX-HI04`, `UX-HI05`, `UX-NV01`, `UX-NV02`, `UX-NV03`, `UX-TT01`, `UX-TT02`, `UX-TT03`, `UX-TT04`, `UX-EC02`, `UX-EC03`, `UX-CS02`, `UX-CS03`, `UX-CS04`, `UX-PG02`, `UX-PG03`.
  - **FAIL (7):** `UX-EC01` (Nút Kết thúc văn bản cần modal bảo vệ), `UX-CS01` (Quá nhiều nút tác vụ trên dòng file PDF), `UX-ND01` (Trùng lặp badge Thường và trường Độ khẩn), `UX-ND02` (Nút Xem toàn bộ log lặp 2 lần), `UX-RC01` (Nhiều trường `--` gây loãng thông tin), `UX-TC02` (Vai trò phân công thiếu badge trực quan), `UX-NV01` (Dãy Right Dock gây phân tán sự chú ý).
  - **NEEDS VALIDATION / UNKNOWN (8):** Các tương tác mở tệp xem trước (PDF Previewer), luồng điều chuyển văn bản thực tế, Screen reader đọc cây phân cấp văn bản.
- **Không áp dụng (N/A): 246 tiêu chí** (Các tiêu chí cho giỏ hàng, thanh toán, biểu mẫu tạo mới nhiều bước, video/audio...).

---

## 6. Kết luận và Khuyến nghị

1. **Giai đoạn 1 (Khắc phục ngay - P1):**
   - Tinh gọn Action Toolbar đầu trang: Giữ `Chuyển xử lý` làm Primary Action, gom các nút phụ vào menu `Khác`.
   - Bỏ nút `Mở rộng v` thừa ở chân mỗi Card, chỉ giữ lại icon đóng/mở chuẩn ở Header.
   - Bỏ nút *"Xem toàn bộ log"* bị lặp ở Header chính khối Ý kiến xử lý.
2. **Giai đoạn 2 (Tối ưu giao diện & hiển thị - P2):**
   - Sửa lỗi Breadcrumb bị cắt cụt (`Thông...`).
   - Đổi style nút *"Kết thúc văn bản"* sang Secondary/Outline và đảm bảo có modal xác nhận lý do kết thúc.
   - Bật wrap-text hoặc tooltip cho các trường `Đơn vị soạn thảo`, `Người ký` và tên file PDF.
   - Gom các nút AI/tác vụ nâng cao trên dòng file PDF vào menu `⋮`.
3. **Giai đoạn 3 (Nâng cao trải nghiệm - P3):**
   - Tinh giản các trường rỗng (`--`) và loại bỏ thông tin trùng lặp (Badge Thường vs Độ khẩn).
   - Thiết kế badge nhận diện rõ ràng hơn cho các vai trò phân công xử lý.
   - Thu gọn dock tiện ích dọc bên phải thành dạng drawer có thể ẩn/hiện.
