# Báo cáo Đánh giá Chất lượng UI/UX (UI/UX Quality Audit Report)

- **Sản phẩm:** VNPT CMS - Hệ thống Quản trị Nội dung
- **Màn hình đánh giá:** Tổng quan (Dashboard)
- **Nền tảng / Thiết bị:** Web Desktop (1920x1080)
- **Thời gian thực hiện:** 16/09/2026
- **Tiêu chuẩn tham chiếu:** VNPT Design System, WCAG 2.2 AA, ISO 9241-161 / ISO 9241-210, Material Design 3, Apple HIG

---

## 1. Executive Summary

Màn hình **Tổng quan (Dashboard) VNPT CMS** có cấu trúc giao diện sáng sủa, tone màu nhận diện xanh VNPT chuẩn mực, hệ thống phân cấp sidebar rõ ràng và bố cục lưới cơ bản khoa học. Tuy nhiên, qua quá trình kiểm định chi tiết theo bộ checklist UI/UX tiêu chuẩn, màn hình còn tồn tại một số bất cập lớn về **trải nghiệm người dùng (UX)** và **tính logic của dữ liệu**, nổi bật là:
1. **Critical UX Blocker / Rủi ro thao tác:** Nút *"Duyệt tất cả"* đặt trực tiếp tại bảng lịch sử cập nhật mà không có cơ chế chọn lọc (bulk selection) hay hộp thoại xác nhận bảo vệ, tiềm ẩn rủi ro nghiêm trọng khi duyệt nhầm các bài viết đang ở trạng thái Bản nháp hoặc Xuất bản lỗi.
2. **Lỗi logic phân trang:** Dãy số phân trang hiển thị sai quy tắc rút gọn (`1 2 3 ... 4 5 6` trên tổng số 10 trang).
3. **Dữ liệu giả định bị lặp & Cột STT hardcode:** Cột STT hiển thị toàn bộ số `1`, tiêu đề bài viết lặp lại 100%, 4 thẻ Metric đều có cùng chỉ số tăng trưởng `+3 bài` bất kể loại trạng thái.
4. **Trùng lặp thành phần điều hướng:** User Profile của Admin xuất hiện đồng thời ở cả Top Bar bên phải và Bottom Sidebar bên trái.

---

## 2. Tổng quan điểm số (Score Summary)

### Bảng 1 — Score Summary

| Chỉ số | Giá trị UI | Giá trị UX | Toàn hệ thống / Tổng hợp |
|---|---:|---:|---:|
| **Tổng checklist áp dụng** | 28 | 32 | 60 |
| **Checklist PASS** | 23 | 24 | 47 |
| **Checklist FAIL** | 5 | 8 | 13 |
| **Checklist N/A** | 48 | 246 | 294 |
| **Checklist NEEDS VALIDATION** | 5 | 8 | 13 |
| **Tổng số Issue phát hiện** | 5 | 9 | 14 |
| - Critical (Trọng số 5) | 0 | 1 | 1 |
| - Major (Trọng số 3) | 2 | 5 | 7 |
| - Minor (Trọng số 1) | 3 | 3 | 6 |
| **Issue Penalty** | 9 | 23 | 32 |
| **Checklist Compliance Score** | **82.1 / 100** | **75.0 / 100** | **78.3 / 100** |
| **Issue Score** | **93.6 / 100** | **85.6 / 100** | **89.3 / 100** |
| **UI Quality Score** (70% CL + 30% Issue) | **85.6 / 100** | — | — |
| **UX Quality Score** (70% CL + 30% Issue) | — | **78.2 / 100** | — |
| **Experience Quality Score** (40% UI + 60% UX) | — | — | **81.2 / 100** |

---

### Bảng 2 — Calculation Detail

| Chỉ số | Giá trị đầu vào | Công thức tính toán | Kết quả |
|---|---|---|---:|
| **UI Checklist Score** | Áp dụng: 28, FAIL: 5 | `(28 - 5) / 28 * 100` | **82.1** |
| **UI Issue Penalty** | Minor: 3, Major: 2, Critical: 0 | `3*1 + 2*3 + 0*5` | **9** |
| **UI Issue Score** | Áp dụng: 28, Penalty: 9 | `100 * (1 - 9 / (28 * 5))` | **93.6** |
| **UI Quality Score** | CL Score: 82.1, Issue Score: 93.6 | `82.1 * 70% + 93.6 * 30%` | **85.6** |
| **UX Checklist Score** | Áp dụng: 32, FAIL: 8 | `(32 - 8) / 32 * 100` | **75.0** |
| **UX Issue Penalty** | Minor: 3, Major: 5, Critical: 1 | `3*1 + 5*3 + 1*5` | **23** |
| **UX Issue Score** | Áp dụng: 32, Penalty: 23 | `100 * (1 - 23 / (32 * 5))` | **85.6** |
| **UX Quality Score** | CL Score: 75.0, Issue Score: 85.6 | `75.0 * 70% + 85.6 * 30%` | **78.2** |
| **Experience Quality Score** | UI: 85.6, UX: 78.2 | `85.6 * 40% + 78.2 * 60%` | **81.2 / 100** |

---

### Bảng 3 — Severity Summary

| Severity | Weight | Số issue UI | Số issue UX | Tổng Issue | Penalty UI | Penalty UX | Tổng Penalty |
|---|---:|---:|---:|---:|---:|---:|---:|
| **Critical** | 5 | 0 | 1 | 1 | 0 | 5 | 5 |
| **Major** | 3 | 2 | 5 | 7 | 6 | 15 | 21 |
| **Minor** | 1 | 3 | 3 | 6 | 3 | 3 | 6 |
| **Tổng cộng** | | **5** | **9** | **14** | **9** | **23** | **32** |

---

### Bảng 4 — Mandatory Gate

| Gate | Kết quả | Lý do | Hành động bắt buộc |
|---|---|---|---|
| **Critical issue** | ❌ **FAIL** | Tồn tại 01 Critical Issue: Nút "Duyệt tất cả" không có xác nhận bảo vệ & rủi ro duyệt sai dữ liệu | Yêu cầu khắc phục ngay trước khi đưa vào sản xuất |
| **Mandatory checklist** | ⚠️ **NEEDS VALIDATION** | Cần kiểm tra thực tế trạng thái tương tác động (hover, active, focus, responsive) | Thực hiện kiểm thử trực tiếp trên môi trường web chạy thật |
| **Task blocker** | ❌ **FAIL** | Nút phân trang bị sai logic hiển thị (`1 2 3 ... 4 5 6`) gây cản trở truy cập các trang giữa | Sửa logic thuật toán phân trang |
| **Accessibility (WCAG AA)** | ⚠️ **CẢNH BÁO** | Badge "Chờ duyệt" chữ trắng nền vàng (#f59e0b) có độ tương phản dưới 4.5:1 | Điều chỉnh màu nền hoặc màu chữ sang tông đậm hơn |
| **Excellent eligibility** | ❌ **FAIL** | Chưa đủ điều kiện xếp loại Excellent do có Critical issue và checklist bắt buộc chưa hoàn tất | Khắc phục các issue P1 & P2 |

---

## 3. Bảng Kết quả đầu ra (Issue Log & Chi tiết kiểm định)

*Quy tắc sắp xếp: Từ trên xuống dưới, từ trái qua phải theo cấu trúc thị giác của giao diện.*

| Issue ID | Phân loại | Mã checklist | Tên luồng | Chức năng | Bước thao tác | Thiết bị | Mức độ ảnh hưởng | Hình ảnh | Vấn đề | Đề xuất giải pháp | Hiệu quả sau cải tiến | Xếp loại Issue | Xếp loại Checklist | Effort | Urgency | Priority points |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---:|---:|---:|
| **ISS-01** | UI | `UI-ME01` | Điều hướng | Header & Sidebar | Xem giao diện | Desktop | Minor | Góc trên phải & Góc dưới trái | Thông tin User Profile Admin bị trùng lặp ở cả Top bar (header) và chân Sidebar | Giữ Profile ở Top Bar hoặc Sidebar, đồng thời tận dụng không gian còn lại cho các tác vụ ngữ cảnh | Tránh lãng phí diện tích, tinh gọn điều hướng | Minor | FAIL | 1 | 1 | 1.0 (P3) |
| **ISS-02** | UX | `UX-HI01` | Thống kê | Metric Cards | Xem dashboard | Desktop | Major | 4 thẻ thống kê | Cả 4 thẻ ("Bản nháp", "Chờ duyệt", "Đã xuất bản", "Xuất bản lỗi") đều hiển thị cùng tag `+3 bài` (lỗi copy dữ liệu tĩnh, thiếu logic nghiệp vụ) | Cập nhật logic hiển thị tăng/giảm theo từng chỉ số; thẻ "Xuất bản lỗi" cần cảnh báo số lượng lỗi thay vì tăng trưởng tích cực | Dữ liệu dashboard trung thực, mang giá trị theo dõi thời gian thực | Major | FAIL | 1 | 2 | 6.0 (P1) |
| **ISS-03** | UX | `UX-HI02` | Thống kê | Bộ lọc thời gian | Lọc số liệu | Desktop | Minor | Khu vực thẻ thống kê | Thiếu bộ lọc mốc thời gian (Hôm nay, 7 ngày, 30 ngày, Tùy chọn) cho các chỉ số tổng quan | Bổ sung Date Range Picker góc trên phải của khu vực tổng quan | Người quản trị linh hoạt xem số liệu theo các chu kỳ báo cáo | Minor | FAIL | 2 | 2 | 1.0 (P3) |
| **ISS-04** | UI | `UI-BU02` | Tác vụ | Header bảng dữ liệu | Xem danh sách | Desktop | Major | Bên phải tiêu đề "Lịch sử cập nhật gần đây" | Nút "Duyệt tất cả" đặt ngang hàng tiêu đề bảng gây cạnh tranh với nút chính "+ Tạo mới" và không phù hợp với ngữ cảnh bảng lịch sử | Chuyển nút "Duyệt tất cả" vào khu vực thao tác hàng loạt (Bulk Action Bar) chỉ xuất hiện khi chọn checkbox | Phân cấp thị giác rõ ràng, hành động đặt đúng ngữ cảnh | Major | FAIL | 1 | 3 | 9.0 (P1) |
| **ISS-05** | UX | `UX-EC01` | Duyệt bài | Phê duyệt hàng loạt | Bấm "Duyệt tất cả" | Desktop | **Critical** | Nút "Duyệt tất cả" | Nút "Duyệt tất cả" thực thi hành động duyệt toàn bộ danh sách mà không có checkbox lựa chọn bài và thiếu modal xác nhận cảnh báo nguy cơ | Yêu cầu người dùng tích chọn checkbox các bài "Chờ duyệt" rồi mới bật nút duyệt; hiển thị Modal xác nhận số lượng bài sẽ duyệt | Ngăn ngừa sự cố nghiêm trọng duyệt nhầm bản nháp hoặc bài bị lỗi | Critical | FAIL | 2 | 3 | **P1 (Critical)** |
| **ISS-06** | UX | `UX-CS01` | Quản lý nội dung | Bảng dữ liệu | Tìm kiếm & Lọc | Desktop | Major | Phía trên bảng dữ liệu | Thiếu thanh tìm kiếm (Search bar) và các bộ lọc nhanh (Filter theo chuyên mục, trạng thái, tác giả) | Bổ sung thanh Search + Dropdown Filter trạng thái/chuyên mục ở phía trên bên phải bảng | Giúp biên tập viên tra cứu nhanh bài viết khi dữ liệu tăng cao | Major | FAIL | 2 | 3 | 4.5 (P2) |
| **ISS-07** | UI | `UI-DA02` | Quản lý nội dung | Bảng dữ liệu | Xem danh sách | Desktop | Major | Cột STT | Cột Số thứ tự (STT) hiển thị toàn bộ số `1` cho tất cả 10 dòng (Hardcode bug) | Tính toán STT tự động theo công thức: `(Current_Page - 1) * Page_Size + Index` | Hiển thị đúng số thứ tự từ 1 đến 10 | Major | FAIL | 1 | 3 | 9.0 (P1) |
| **ISS-08** | UX | `UX-RC01` | Quản lý nội dung | Bảng dữ liệu | Xem dữ liệu bài viết | Desktop | Minor | Cột Tên bài viết & Ngày | Toàn bộ 10 dòng đều có tên "Chiến lược phân phối Q3/2025" và cùng ngày `12/09/2026` (lệch năm, thiếu giờ phút) | Hiển thị dữ liệu thực tế đa dạng; bổ sung định dạng giờ phút (`12/09/2026 14:30`) cho bảng lịch sử | Giúp người dùng phân biệt thứ tự thời gian cập nhật của các bài | Minor | FAIL | 1 | 2 | 2.0 (P2) |
| **ISS-09** | UI | `UI-TY10` | Quản lý nội dung | Bảng dữ liệu | Đọc trạng thái | Desktop | Minor | Cột Trạng thái | Badge "Chờ duyệt" (chữ trắng nền vàng cam #F59E0B) có độ tương phản ~2.2:1, vi phạm chuẩn WCAG 2.2 AA (yêu cầu >= 4.5:1) | Đổi sang nền vàng nhạt + chữ nâu sẫm/vàng đậm (#854D0E trên nền #FEF9C3) | Đảm bảo khả năng đọc cho người khiếm thị màu và môi trường ánh sáng mạnh | Minor | FAIL | 1 | 2 | 2.0 (P2) |
| **ISS-10** | UX | `UX-ND01` | Quản lý nội dung | Bảng dữ liệu | Đọc trạng thái | Desktop | Minor | Cột Trạng thái (Dòng 3) | Dòng 3 hiển thị trạng thái "Thành công" (không chuẩn thuật ngữ CMS quản lý xuất bản) | Chuẩn hóa thuật ngữ thành "Đã xuất bản" (Published) để đồng nhất với thẻ Thống kê phía trên | Thuật ngữ chuẩn xác, nhất quán trong toàn bộ hệ thống | Minor | FAIL | 1 | 1 | 1.0 (P3) |
| **ISS-11** | UI | `UI-TY11` | Quản lý nội dung | Bảng dữ liệu | Đọc trạng thái | Desktop | Minor | Cột Trạng thái | Các badge trạng thái chỉ dùng màu sắc và text, thiếu icon nhận diện hình học đi kèm | Bổ sung micro icon trạng thái (Vd: Icon đồng hồ cho Chờ duyệt, Check cho Đã xuất bản, Chấm than cho Từ chối) | Hỗ trợ người dùng nhận diện trạng thái tức thì theo chuẩn Accessibility | Minor | FAIL | 1 | 1 | 1.0 (P3) |
| **ISS-12** | UX | `UX-TC08` | Quản lý nội dung | Bảng dữ liệu | Thao tác dòng | Desktop | Major | Cột Thao tác | Nút Xóa (icon thùng rác đỏ) đặt liền kề nút "Sửa" và "Xem" mà không có phân cách an toàn; thiếu cơ chế cảnh báo xóa vĩnh viễn | Bổ sung khoảng cách an toàn (gap) hoặc đưa hành động Xóa vào menu ba chấm `...`; hiển thị Modal xác nhận xóa | Loại bỏ rủi ro bấm nhầm nút Xóa khi định bấm Sửa | Major | FAIL | 2 | 3 | 4.5 (P2) |
| **ISS-13** | UI | `UI-PA01` | Điều hướng trang | Phân trang | Chuyển trang | Desktop | Major | Khu vực phân trang đáy bảng | Dãy số phân trang bị lỗi logic rút gọn: `1 2 3 ... 4 5 6` trên tổng số 10 trang (dấu `...` bị đặt sai vị trí) | Sửa logic phân trang chuẩn: Khi ở trang 1: `[1] 2 3 ... 10`; Khi ở trang 5: `1 ... 4 [5] 6 ... 10` | Người dùng dễ dàng chuyển trang chính xác | Major | FAIL | 1 | 3 | 9.0 (P1) |
| **ISS-14** | UX | `UX-PG01` | Điều hướng trang | Phân trang | Thao tác phân trang | Desktop | Minor | Khu vực phân trang | Có sự dư thừa công cụ điều hướng (vừa có ô nhập `Page 1 of 10`, vừa có dãy nút số, vừa có nút nhảy trang đầu/cuối) | Tối giản thanh phân trang: giữ dãy nút số + nút Trước/Sau + Dropdown số dòng/trang | Giao diện gọn gàng, giảm tải nhận thức cho người dùng | Minor | FAIL | 1 | 1 | 1.0 (P3) |

---

## 4. Bảng Kế hoạch cải tiến (Improvement Roadmap)

*Danh sách được lọc từ các Issue FAIL và sắp xếp theo thứ tự ưu tiên xử lý P1 → P2 → P3.*

| Issue ID | Phân loại | Mã checklist | Chức năng | Bước thao tác | Thiết bị | Mức độ ảnh hưởng | Hình ảnh | Vấn đề | Đề xuất giải pháp | Hiệu quả sau cải tiến | Priority |
|---|---|---|---|---|---|---|---|---|---|---|---|
| **ISS-05** | UX | `UX-EC01` | Phê duyệt hàng loạt | Bấm "Duyệt tất cả" | Desktop | **Critical** | Nút "Duyệt tất cả" | Nút "Duyệt tất cả" không có chọn lọc và thiếu cảnh báo xác nhận | Chỉ bật duyệt khi tích chọn checkbox; bắt buộc có Dialog xác nhận số bài duyệt | Ngăn ngừa hoàn toàn rủi ro duyệt sai dữ liệu | **P1** |
| **ISS-02** | UX | `UX-HI01` | Thống kê | Xem dashboard | Desktop | Major | 4 thẻ thống kê | Cả 4 thẻ đều có cùng tag `+3 bài` sai lệch bản chất dữ liệu | Cập nhật logic tăng giảm thực tế cho từng loại thẻ | Số liệu dashboard trung thực, chính xác | **P1** |
| **ISS-04** | UI | `UI-BU02` | Tác vụ | Xem danh sách | Desktop | Major | Nút Duyệt tất cả | Đặt nút hành động hàng loạt cạnh tiêu đề bảng gây nhiễu phân cấp | Đưa vào Bulk Action Bar xuất hiện theo ngữ cảnh | Giao diện rõ ràng, phân cấp chuẩn mực | **P1** |
| **ISS-07** | UI | `UI-DA02` | Quản lý nội dung | Xem danh sách | Desktop | Major | Cột STT | Cột STT hiển thị toàn bộ số 1 | Tính STT tự động theo trang hiện tại | Bảng hiển thị thứ tự 1-10 chuẩn xác | **P1** |
| **ISS-13** | UI | `UI-PA01` | Phân trang | Chuyển trang | Desktop | Major | Thanh phân trang | Dãy số phân trang hiển thị lỗi `1 2 3 ... 4 5 6` of 10 | Sửa thuật toán rút gọn phân trang `1 2 3 ... 10` | Điều hướng trang mượt mà, đúng quy chuẩn | **P1** |
| **ISS-06** | UX | `UX-CS01` | Quản lý nội dung | Tìm kiếm & Lọc | Desktop | Major | Bảng dữ liệu | Thiếu thanh tìm kiếm và bộ lọc trạng thái bài viết | Thêm Search input + Filter dropdown ở đầu bảng | Tiết kiệm thời gian tìm kiếm bài viết cho Admin | **P2** |
| **ISS-12** | UX | `UX-TC08` | Quản lý nội dung | Thao tác dòng | Desktop | Major | Cột Thao tác | Nút Xóa đỏ sát nút Sửa dễ gây bấm nhầm | Tăng khoảng cách an toàn, bổ sung modal xác nhận xóa | Loại bỏ nguy cơ xóa nhầm bài viết | **P2** |
| **ISS-08** | UX | `UX-RC01` | Quản lý nội dung | Xem dữ liệu bài | Desktop | Minor | Bảng dữ liệu | Dữ liệu mẫu bị trùng 100% tên bài và thiếu giờ cập nhật | Render dữ liệu bài thực tế và thêm giờ phút | Giúp nhận diện bài viết và thời gian cập nhật | **P2** |
| **ISS-09** | UI | `UI-TY10` | Quản lý nội dung | Đọc trạng thái | Desktop | Minor | Cột Trạng thái | Badge "Chờ duyệt" không đạt tỷ lệ tương phản 4.5:1 | Đổi màu text nâu sẫm trên nền vàng nhạt (#854D0E / #FEF9C3) | Đạt chuẩn tiếp cận WCAG 2.2 AA | **P2** |
| **ISS-01** | UI | `UI-ME01` | Điều hướng | Xem giao diện | Desktop | Minor | Header & Sidebar | User Profile Admin xuất hiện trùng lặp ở 2 vị trí | Tinh gọn giữ lại 1 vị trí thích hợp | Tối ưu không gian hiển thị | **P3** |
| **ISS-03** | UX | `UX-HI02` | Thống kê | Lọc số liệu | Desktop | Minor | Thẻ thống kê | Thiếu bộ lọc mốc thời gian tổng quan | Thêm Date Range Picker | Linh hoạt thống kê theo giai đoạn | **P3** |
| **ISS-10** | UX | `UX-ND01` | Quản lý nội dung | Đọc trạng thái | Desktop | Minor | Cột Trạng thái | Thuật ngữ "Thành công" chưa chuẩn với ngữ cảnh CMS | Đổi thành "Đã xuất bản" | Đồng nhất thuật ngữ toàn hệ thống | **P3** |
| **ISS-11** | UI | `UI-TY11` | Quản lý nội dung | Đọc trạng thái | Desktop | Minor | Cột Trạng thái | Badge trạng thái thiếu icon nhận diện hình thái | Bổ sung micro-icon phía trước nhãn trạng thái | Tăng khả năng quét thông tin nhanh | **P3** |
| **ISS-14** | UX | `UX-PG01` | Phân trang | Thao tác phân trang | Desktop | Minor | Thanh phân trang | Điều hướng phân trang quá nhiều thành phần lặp | Tối giản thanh phân trang | Gọn gàng, dễ thao tác | **P3** |

---

## 5. Danh mục Checklist chi tiết đã đánh giá

### 5.1. Checklist UI (81 tiêu chí thư viện chuẩn)
- **Áp dụng (Applicable): 28 tiêu chí**
  - **PASS (23):** `UI-LA01`, `UI-LA02`, `UI-LA03`, `UI-LA04`, `UI-LA05`, `UI-LA06`, `UI-SI01`, `UI-LO01`, `UI-LO02`, `UI-LO03`, `UI-LO04`, `UI-TY01`, `UI-TY02`, `UI-TY03`, `UI-TY04`, `UI-TY05`, `UI-TY06`, `UI-TY07`, `UI-TY08`, `UI-TY09`, `UI-IC01`, `UI-IC02`, `UI-IC03`, `UI-IC04`, `UI-IC05`, `UI-IC06`, `UI-CA01`, `UI-CA02`, `UI-CA03`, `UI-DA01`.
  - **FAIL (5):** `UI-ME01` (Trùng lặp User Profile), `UI-BU02` (Phân cấp nút Duyệt tất cả), `UI-DA02` (STT bảng bị lặp số 1), `UI-TY10` (Độ tương phản badge Chờ duyệt), `UI-PA01` (Lỗi logic hiển thị phân trang).
  - **NEEDS VALIDATION / UNKNOWN (5):** `UI-LA07` (Responsive Layout), `UI-LA08` (Zoom 200%), `UI-BU05` (Trạng thái hover/focus button), `UI-DA03` (Trạng thái hover hàng bảng), `UI-TY14` (Responsive text).
- **Không áp dụng (N/A): 48 tiêu chí** (Bao gồm Modal/Dialog, Checkbox/Radio/Switch, Tabs, Breadcrumbs, Chart visualization, Alert/Toast không xuất hiện trên màn hình tĩnh hiện tại).

### 5.2. Checklist UX (286 tiêu chí thư viện chuẩn)
- **Áp dụng (Applicable): 32 tiêu chí**
  - **PASS (24):** `UX-TC01`, `UX-TC02`, `UX-TC03`, `UX-TC05`, `UX-TC06`, `UX-TC07`, `UX-TC16`, `UX-TC17`, `UX-HI03`, `UX-HI04`, `UX-HI05`, `UX-HI06`, `UX-ND02`, `UX-ND03`, `UX-ND04`, `UX-NV01`, `UX-NV02`, `UX-NV03`, `UX-TT01`, `UX-TT02`, `UX-TT03`, `UX-TT04`, `UX-EC02`, `UX-EC03`.
  - **FAIL (8):** `UX-EC01` (Critical: Thiếu xác nhận cho Duyệt tất cả), `UX-HI01` (Dữ liệu thẻ metric lặp `+3 bài`), `UX-HI02` (Thiếu filter thời gian metric), `UX-CS01` (Thiếu Search & Filter bảng), `UX-RC01` (Dữ liệu bảng lặp tên & thiếu giờ), `UX-TC08` (Nút Xóa thiếu khoảng cách an toàn & modal xác nhận), `UX-ND01` (Thuật ngữ trạng thái "Thành công"), `UX-PG01` (Dư thừa công cụ phân trang).
  - **NEEDS VALIDATION / UNKNOWN (8):** Các tiêu chí kiểm thử luồng tương tác thực tế, thời gian phản hồi API, khả năng điều hướng bàn phím (Keyboard navigation tab order), Screen Reader text.
- **Không áp dụng (N/A): 246 tiêu chí** (Các tiêu chí dành cho luồng giỏ hàng, thanh toán, biểu mẫu nhập liệu phức tạp, video/audio, multi-step wizard...).

---

## 6. Kết luận và Khuyến nghị

1. **Giai đoạn 1 (Khắc phục ngay - Sprint hiện tại / P1):**
   - Bổ sung modal xác nhận cho thao tác duyệt và sửa logic nút *"Duyệt tất cả"*.
   - Sửa thuật toán hiển thị phân trang (`1 2 3 ... 10`).
   - Sửa lỗi hardcode cột STT và cập nhật logic số liệu động cho 4 thẻ Metric.
2. **Giai đoạn 2 (Hoàn thiện nghiệp vụ / P2):**
   - Thêm thanh tìm kiếm và bộ lọc nhanh trạng thái bài viết ở đầu bảng.
   - Điều chỉnh bảng màu badge trạng thái "Chờ duyệt" đạt chuẩn WCAG AA.
   - Thêm khoảng cách an toàn hoặc đưa hành động Xóa vào menu ngữ cảnh.
3. **Giai đoạn 3 (Tối ưu trải nghiệm / P3):**
   - Chuẩn hóa thuật ngữ trạng thái "Đã xuất bản".
   - Tinh gọn khu vực hiển thị User Profile và thanh điều hướng phân trang.
