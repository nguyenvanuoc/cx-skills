# Báo cáo Đánh giá Chất lượng UI/UX (UI/UX Quality Audit Report)

- **Sản phẩm**: VNPT CMS / Portal Management System
- **Màn hình đánh giá**: Màn hình **Tổng quan (Dashboard)**
- **Ngày thực hiện**: 2026-09-15
- **Tài liệu tham chiếu**: [UI_UX_Audit.md](file:///Volumes/CHAOS/VNPT/AI/CX/ui_ux/UI_UX_Audit.md), [UI_Checklist.md](file:///Volumes/CHAOS/VNPT/AI/CX/.agent/skills/ui_ux/UI_Checklist.md), [UX_Checklist.md](file:///Volumes/CHAOS/VNPT/AI/CX/.agent/skills/ui_ux/UX_Checklist.md), [Scoring_Formula.md](file:///Volumes/CHAOS/VNPT/AI/CX/.agent/skills/ui_ux/Scoring_Formula.md)

---

## 1. Tổng quan điểm số (Score Summary)

$$\text{Checklist Score} = \frac{\text{Tổng áp dụng} - \text{FAIL}}{\text{Tổng áp dụng}} \times 100$$
$$\text{Issue Penalty} = (\text{Minor} \times 1) + (\text{Major} \times 3) + (\text{Critical} \times 5)$$
$$\text{Issue Score} = \max\left(0, 100 \times \left(1 - \frac{\text{Issue Penalty}}{\text{Tổng áp dụng} \times 5}\right)\right)$$
$$\text{UI/UX Score} = (\text{Checklist Score} \times 70\%) + (\text{Issue Score} \times 30\%)$$
$$\text{Experience Quality Score} = (\text{UI Score} \times 40\%) + (\text{UX Score} \times 60\%)$$

| Chỉ số | UI (Giao diện) | UX (Trải nghiệm) | Toàn diện (Experience Quality) |
|:---|---:|---:|---:|
| **Tổng checklist áp dụng** | 20 | 15 | 35 |
| **Checklist PASS** | 14 | 8 | 22 |
| **Checklist FAIL** | 6 | 7 | 13 |
| **N/A** | 61 | 271 | 332 |
| **NEEDS VALIDATION** | 0 | 0 | 0 |
| **Tổng số Issue** | **5** *(1 Critical, 2 Major, 2 Minor)* | **6** *(2 Critical, 2 Major, 2 Minor)* | **11 Issues** |
| - *Critical (Weight = 5)* | 1 | 2 | 3 |
| - *Major (Weight = 3)* | 2 | 2 | 4 |
| - *Minor (Weight = 1)* | 2 | 2 | 4 |
| **Issue Penalty** | **13** | **18** | **31** |
| **Checklist Score** | **70.0%** | **53.3%** | — |
| **Issue Score** | **87.0 / 100** | **76.0 / 100** | — |
| **UI Quality Score** | **75.1 / 100** | — | — |
| **UX Quality Score** | — | **60.1 / 100** | — |
| **Experience Quality Score** | — | — | **66.1 / 100 (Cần cải thiện)** |

---

## 2. Bảng: Kết quả đầu ra

| Issue ID | Tên luồng | Chức năng | Bước thao tác | Thiết bị | Mức độ ảnh hưởng | Vấn đề | Hình ảnh | Tác động | Đề xuất giải pháp | Hiệu quả sau cải tiến | Điểm tác động | Xếp loại Issue | Xếp loại Checklist | Effort | Urgency | Priority points |
|:---|:---|:---|:---|:---|:---|:---|:---|:---|:---|:---|:---:|:---:|:---:|:---:|:---:|:---:|
| `ISSUE-01` | Quản trị nội dung | Phân trang bài viết | Xem thanh điều hướng phân trang ở chân bảng | Desktop | Critical | Dãy phân trang sai logic toán học: `1 2 3 ... 4 5 6` trên tổng số 10 trang (dấu `...` chen giữa số 3 và 4, cụm cuối không có trang 10). | Pagination footer | Người dùng không thể chuyển trang chính xác, mất phương hướng điều hướng và không nhảy được đến trang cuối. | Sửa thuật toán phân trang chuẩn `[1] 2 3 4 5 ... 10` và hiển thị dấu `...` đúng vị trí khi có khoảng cách số. | Điều hướng mượt mà, đúng logic chuẩn ngành. | 5 | Fail | Fail | 1 (Thấp) | 3 (High) | 15.0 |
| `ISSUE-02` | Quản trị nội dung | Phê duyệt bài viết | Bấm nút "Duyệt tất cả" trên bảng lịch sử | Desktop | Critical | Nút "Duyệt tất cả" đặt cạnh tiêu đề bảng nhưng bảng không có Checkbox để chọn dòng, trong khi bảng chứa cả bài Đã xuất bản, Bản nháp, Từ chối và Chờ duyệt. | Nút `✓ Duyệt tất cả` | Dễ dẫn đến hành động sai lầm nghiêm trọng (duyệt nhầm toàn bộ bài chưa hoàn thiện, bài nháp hoặc bài bị từ chối). | Bổ sung checkbox từng dòng; chỉ kích hoạt action duyệt khi có bài được tick chọn; hoặc chuyển nút vào màn hình "Duyệt bài" chuyên biệt. | Tránh duyệt nhầm dữ liệu, đảm bảo quy trình kiểm duyệt an toàn. | 5 | Fail | Fail | 2 (Trung bình) | 3 (High) | 7.5 |
| `ISSUE-03` | Quản trị nội dung | Hiển thị bảng dữ liệu | Xem cột STT trong bảng lịch sử | Desktop | Critical | Cột STT của tất cả 10 hàng đều hiển thị số `1`, tên bài viết và ngày tháng trùng lặp 100%. | Cột STT & Tên bài viết | Gây nhầm lẫn dữ liệu, người dùng không thể phân biệt và đếm số lượng bản ghi hiển thị. | Sửa công thức STT tự tăng theo index dòng: $(\text{Page} - 1) \times \text{PageSize} + \text{Index}$. | Dữ liệu bảng chuẩn xác, dễ tra cứu. | 5 | Fail | Fail | 1 (Thấp) | 3 (High) | 15.0 |
| `ISSUE-04` | Quản trị nội dung | Tìm kiếm, lọc & sắp xếp | Tìm kiếm bài viết cũ trong bảng | Desktop | Major | Bảng dữ liệu có 10 trang bài viết nhưng thiếu thanh công cụ Tìm kiếm (Search), Bộ lọc (Filter) và Sắp xếp cột (Sort arrows) vi phạm quy tắc thiết kế hệ thống quản trị. | Toolbar trên bảng | Người dùng mất nhiều thời gian lật từng trang để tìm bài viết, giảm hiệu suất làm việc. | Bổ sung ô Search theo tên, Dropdown lọc theo Trạng thái / Chuyên mục và icon sort trên header các cột. | Tăng tốc độ tra cứu và quản lý dữ liệu lớn. | 3 | Fail | Fail | 2 (Trung bình) | 3 (High) | 4.5 |
| `ISSUE-05` | Quản trị nội dung | Thao tác duyệt bài nhanh | Duyệt bài viết ở trạng thái "Chờ duyệt" tại dòng bảng | Desktop | Major | Dòng có trạng thái "Chờ duyệt" chỉ có thao tác Xem/Sửa/Xóa, thiếu nút duyệt nhanh hoặc từ chối trực tiếp. | Cột Thao tác dòng Chờ duyệt | Quản trị viên phải mở chi tiết/sửa bài mới duyệt được, làm chậm luồng công việc phê duyệt. | Bổ sung nút Duyệt (`✓`) và Từ chối (`✕`) theo ngữ cảnh trạng thái dòng. | Giảm 60% số lần click khi duyệt bài. | 3 | Fail | Fail | 2 (Trung bình) | 2 (Medium) | 3.0 |
| `ISSUE-06` | Hệ thống chung | Nhận diện trạng thái | Đối chiếu số liệu thẻ thống kê và trạng thái trong bảng | Desktop | Major | Không nhất quán thuật ngữ trạng thái: Thẻ thống kê ghi "Đã xuất bản" $\leftrightarrow$ Bảng ghi "Thành công"; Thẻ ghi "Xuất bản lỗi" $\leftrightarrow$ Bảng ghi "Từ chối". | Thẻ Stat Cards & Cột Trạng thái | Gây nhầm lẫn khái niệm trạng thái bài viết cho người dùng. | Thống nhất dùng chung bộ enum trạng thái: `Bản nháp`, `Chờ duyệt`, `Đã xuất bản`, `Từ chối`. | Tính nhất quán cao, giảm nhầm lẫn nhận thức. | 3 | Fail | Fail | 1 (Thấp) | 2 (Medium) | 6.0 |
| `ISSUE-07` | Điều hướng hệ thống | Thông tin tài khoản người dùng | Quan sát khu vực tài khoản trên giao diện | Desktop | Major | Khối thông tin Admin (Avatar, tên, email) bị hiển thị lặp lại ở cả Top Header và Bottom Sidebar. | Top Header & Chân Sidebar | Gây dư thừa giao diện, chiếm dụng không gian sidebar không cần thiết. | Loại bỏ khối profile ở Sidebar, gom toàn bộ menu tài khoản về Top Header Dropdown. | Giao diện gọn gàng, đúng chuẩn dashboard hiện đại. | 3 | Fail | Fail | 1 (Thấp) | 2 (Medium) | 6.0 |
| `ISSUE-08` | Bản địa hóa (i18n) | Ngôn ngữ phân trang | Xem thông tin phân trang chân bảng | Desktop | Minor | Khối phân trang còn sót text tiếng Anh: `Page 1 of 10`, `Rows per page` trong giao diện tiếng Việt. | Pagination footer | Giảm tính chuyên nghiệp, không đồng bộ ngôn ngữ. | Bản địa hóa sang tiếng Việt: `Trang 1 / 10`, `Số dòng/trang`. | Giao diện đồng nhất 100% tiếng Việt. | 1 | Fail | Fail | 1 (Thấp) | 2 (Medium) | 2.0 |
| `ISSUE-09` | Khả năng tiếp cận | Độ tương phản tiêu đề bảng | Đọc tiêu đề các cột trong bảng | Desktop | Minor | Chữ tiêu đề cột bảng (`STT`, `Tên bài viết`...) màu xám nhạt (`#9CA3AF`), tương phản thấp < 4.5:1 so với nền. | Table Header | Khó đọc đối với người dùng trong điều kiện ánh sáng mạnh hoặc thị lực kém. | Tăng độ đậm màu chữ header lên `#4B5563` hoặc `#374151` đạt chuẩn WCAG AA. | Đạt chuẩn Accessibility WCAG AA, dễ đọc. | 1 | Fail | Fail | 1 (Thấp) | 1 (Low) | 1.0 |
| `ISSUE-10` | Trực quan hóa số liệu | Thẻ thống kê (Stat Cards) | Xem các badge tăng trưởng trên thẻ thống kê | Desktop | Minor | Tất cả 4 thẻ thống kê đều mang badge text `+3 bài`; Thẻ lỗi mang badge màu đỏ nhưng ghi `+3 bài` gây hiểu nhầm về logic tăng trưởng. | Badge Stat Cards | Dữ liệu thống kê thiếu ý nghĩa thực tế, gây hiểu sai. | Hiển thị biến động thực tế hoặc % so với kỳ trước; Card lỗi thể hiện `-X bài` hoặc text cảnh báo. | Số liệu thống kê trực quan, phản ánh chính xác hiệu suất. | 1 | Fail | Fail | 1 (Thấp) | 1 (Low) | 1.0 |
| `ISSUE-11` | Tương tác hành động | Nút Xóa bài viết tại dòng | Rê chuột hoặc nhìn vào nút Xóa `🗑` | Desktop | Minor | Nút Xem và Sửa có nhãn chữ kèm icon (`👁 Xem`, `✏ Sửa`), trong khi nút Xóa chỉ có icon thùng rác `🗑` màu đỏ không nhãn và thiếu tooltip. | Cột Thao tác từng dòng | Không đồng nhất về kiểu nút, thiếu nhãn hỗ trợ screen reader / tooltip tiếp cận. | Bổ sung nhãn chữ `Xóa` hoặc tooltip `Xóa bài viết` và `aria-label="Xóa bài viết"`. | Đồng bộ visual, hỗ trợ tốt cho Accessibility. | 1 | Fail | Fail | 1 (Thấp) | 1 (Low) | 1.0 |

---

## 3. Bảng: Improverment Roadmap

*Sắp xếp theo thứ tự ưu tiên: **P1 $\rightarrow$ P2 $\rightarrow$ P3 $\rightarrow$ P4** (Critical + High hoặc Priority points $\ge 5 \rightarrow$ P1; Priority points $\ge 2 \rightarrow$ P2; Priority points $\ge 1 \rightarrow$ P3).*

| Issue ID | Chức năng | Bước thao tác | Thiết bị | Mức độ ảnh hưởng | Vấn đề | Hình ảnh | Tác động | Đề xuất giải pháp | Hiệu quả sau cải tiến | Priority |
|:---|:---|:---|:---|:---|:---|:---|:---|:---|:---|:---:|
| `ISSUE-01` | Phân trang bài viết | Xem thanh điều hướng phân trang ở chân bảng | Desktop | Critical | Dãy phân trang sai logic toán học: `1 2 3 ... 4 5 6` trên tổng số 10 trang (dấu `...` chen giữa số 3 và 4, cụm cuối không có trang 10). | Pagination footer | Người dùng không thể chuyển trang chính xác, mất phương hướng điều hướng và không nhảy được đến trang cuối. | Sửa thuật toán phân trang chuẩn `[1] 2 3 4 5 ... 10` và hiển thị dấu `...` đúng vị trí khi có khoảng cách số. | Điều hướng mượt mà, đúng logic chuẩn ngành. | **P1** |
| `ISSUE-02` | Phê duyệt bài viết | Bấm nút "Duyệt tất cả" trên bảng lịch sử | Desktop | Critical | Nút "Duyệt tất cả" đặt cạnh tiêu đề bảng nhưng bảng không có Checkbox để chọn dòng, trong khi bảng chứa cả bài Đã xuất bản, Bản nháp, Từ chối và Chờ duyệt. | Nút `✓ Duyệt tất cả` | Dễ dẫn đến hành động sai lầm nghiêm trọng (duyệt nhầm toàn bộ bài chưa hoàn thiện, bài nháp hoặc bài bị từ chối). | Bổ sung checkbox từng dòng; chỉ kích hoạt action duyệt khi có bài được tick chọn; hoặc chuyển nút vào màn hình "Duyệt bài" chuyên biệt. | Tránh duyệt nhầm dữ liệu, đảm bảo quy trình kiểm duyệt an toàn. | **P1** |
| `ISSUE-03` | Hiển thị bảng dữ liệu | Xem cột STT trong bảng lịch sử | Desktop | Critical | Cột STT của tất cả 10 hàng đều hiển thị số `1`, tên bài viết và ngày tháng trùng lặp 100%. | Cột STT & Tên bài viết | Gây nhầm lẫn dữ liệu, người dùng không thể phân biệt và đếm số lượng bản ghi hiển thị. | Sửa công thức STT tự tăng theo index dòng: $(\text{Page} - 1) \times \text{PageSize} + \text{Index}$. | Dữ liệu bảng chuẩn xác, dễ tra cứu. | **P1** |
| `ISSUE-06` | Nhận diện trạng thái | Đối chiếu số liệu thẻ thống kê và trạng thái trong bảng | Desktop | Major | Không nhất quán thuật ngữ trạng thái: Thẻ thống kê ghi "Đã xuất bản" $\leftrightarrow$ Bảng ghi "Thành công"; Thẻ ghi "Xuất bản lỗi" $\leftrightarrow$ Bảng ghi "Từ chối". | Thẻ Stat Cards & Cột Trạng thái | Gây nhầm lẫn khái niệm trạng thái bài viết cho người dùng. | Thống nhất dùng chung bộ enum trạng thái: `Bản nháp`, `Chờ duyệt`, `Đã xuất bản`, `Từ chối`. | Tính nhất quán cao, giảm nhầm lẫn nhận thức. | **P1** |
| `ISSUE-07` | Thông tin tài khoản người dùng | Quan sát khu vực tài khoản trên giao diện | Desktop | Major | Khối thông tin Admin (Avatar, tên, email) bị hiển thị lặp lại ở cả Top Header và Bottom Sidebar. | Top Header & Chân Sidebar | Gây dư thừa giao diện, chiếm dụng không gian sidebar không cần thiết. | Loại bỏ khối profile ở Sidebar, gom toàn bộ menu tài khoản về Top Header Dropdown. | Giao diện gọn gàng, đúng chuẩn dashboard hiện đại. | **P1** |
| `ISSUE-04` | Tìm kiếm, lọc & sắp xếp | Tìm kiếm bài viết cũ trong bảng | Desktop | Major | Bảng dữ liệu có 10 trang bài viết nhưng thiếu thanh công cụ Tìm kiếm (Search), Bộ lọc (Filter) và Sắp xếp cột (Sort arrows) vi phạm quy tắc thiết kế hệ thống quản trị. | Toolbar trên bảng | Người dùng mất nhiều thời gian lật từng trang để tìm bài viết, giảm hiệu suất làm việc. | Bổ sung ô Search theo tên, Dropdown lọc theo Trạng thái / Chuyên mục và icon sort trên header các cột. | Tăng tốc độ tra cứu và quản lý dữ liệu lớn. | **P2** |
| `ISSUE-05` | Thao tác duyệt bài nhanh | Duyệt bài viết ở trạng thái "Chờ duyệt" tại dòng bảng | Desktop | Major | Dòng có trạng thái "Chờ duyệt" chỉ có thao tác Xem/Sửa/Xóa, thiếu nút duyệt nhanh hoặc từ chối trực tiếp. | Cột Thao tác dòng Chờ duyệt | Quản trị viên phải mở chi tiết/sửa bài mới duyệt được, làm chậm luồng công việc phê duyệt. | Bổ sung nút Duyệt (`✓`) và Từ chối (`✕`) theo ngữ cảnh trạng thái dòng. | Giảm 60% số lần click khi duyệt bài. | **P2** |
| `ISSUE-08` | Ngôn ngữ phân trang | Xem thông tin phân trang chân bảng | Desktop | Minor | Khối phân trang còn sót text tiếng Anh: `Page 1 of 10`, `Rows per page` trong giao diện tiếng Việt. | Pagination footer | Giảm tính chuyên nghiệp, không đồng bộ ngôn ngữ. | Bản địa hóa sang tiếng Việt: `Trang 1 / 10`, `Số dòng/trang`. | Giao diện đồng nhất 100% tiếng Việt. | **P2** |
| `ISSUE-09` | Độ tương phản tiêu đề bảng | Đọc tiêu đề các cột trong bảng | Desktop | Minor | Chữ tiêu đề cột bảng (`STT`, `Tên bài viết`...) màu xám nhạt (`#9CA3AF`), tương phản thấp < 4.5:1 so với nền. | Table Header | Khó đọc đối với người dùng trong điều kiện ánh sáng mạnh hoặc thị lực kém. | Tăng độ đậm màu chữ header lên `#4B5563` hoặc `#374151` đạt chuẩn WCAG AA. | Đạt chuẩn Accessibility WCAG AA, dễ đọc. | **P3** |
| `ISSUE-10` | Thẻ thống kê (Stat Cards) | Xem các badge tăng trưởng trên thẻ thống kê | Desktop | Minor | Tất cả 4 thẻ thống kê đều mang badge text `+3 bài`; Thẻ lỗi mang badge màu đỏ nhưng ghi `+3 bài` gây hiểu nhầm về logic tăng trưởng. | Badge Stat Cards | Dữ liệu thống kê thiếu ý nghĩa thực tế, gây hiểu sai. | Hiển thị biến động thực tế hoặc % so với kỳ trước; Card lỗi thể hiện `-X bài` hoặc text cảnh báo. | Số liệu thống kê trực quan, phản ánh chính xác hiệu suất. | **P3** |
| `ISSUE-11` | Nút Xóa bài viết tại dòng | Rê chuột hoặc nhìn vào nút Xóa `🗑` | Desktop | Minor | Nút Xem và Sửa có nhãn chữ kèm icon (`👁 Xem`, `✏ Sửa`), trong khi nút Xóa chỉ có icon thùng rác `🗑` màu đỏ không nhãn và thiếu tooltip. | Cột Thao tác từng dòng | Không đồng nhất về kiểu nút, thiếu nhãn hỗ trợ screen reader / tooltip tiếp cận. | Bổ sung nhãn chữ `Xóa` hoặc tooltip `Xóa bài viết` và `aria-label="Xóa bài viết"`. | Đồng bộ visual, hỗ trợ tốt cho Accessibility. | **P3** |

---

## 4. Bảng Đánh giá Checklist Chi tiết

### 4.1. UI Checklist (20 tiêu chí áp dụng)

| ID | Phần tử | Tiêu chí | Kết quả | Bằng chứng quan sát |
|:---|:---|:---|:---:|:---|
| `UI-LA01` | Layout | Lưới & Bố cục thống nhất | **PASS** | 4 thẻ thống kê chia đều 4 cột, bảng dữ liệu bám sát chiều rộng content. |
| `UI-LA02` | Layout | Căn gióng các khối | **PASS** | Mép trái các khối thẳng hàng, phân trang căn đều 2 bên chân bảng. |
| `UI-LA03` | Layout | Phân cấp thị giác | **PASS** | Header $\rightarrow$ Stat Cards $\rightarrow$ Action bar $\rightarrow$ Data Table rõ ràng. |
| `UI-LA04` | Layout | Khoảng cách & Gom nhóm | **PASS** | Card padding và table row padding đạt chuẩn spacing. |
| `UI-LA06` | Layout | Màu sắc & Tương phản | **FAIL** | Tiêu đề cột của bảng (STT, Tên bài viết...) có màu quá mờ (`#9CA3AF`), contrast < 4.5:1. |
| `UI-SI01` | Sidebar | Phân biệt mục hiện tại | **PASS** | Mục "Tổng quan" có nền xanh `#0052CC` nổi bật, text trắng rõ ràng. |
| `UI-LO01` | Logo | Đúng chuẩn nhận diện | **PASS** | Logo VNPT hiển thị sắc nét, đúng tỷ lệ ở góc trên sidebar. |
| `UI-TY01` | Typography | Font family đồng nhất | **PASS** | Font Sans-serif hiện đại, hiển thị tốt tiếng Việt có dấu. |
| `UI-TY04` | Typography | Phân cấp chữ số | **PASS** | Số liệu thống kê (24, 12, 1,482) kích thước lớn (28px - 32px), nổi bật so với nhãn phụ. |
| `UI-TY10` | Typography | Tương phản chữ | **FAIL** | Table header và subtitle dưới số liệu có màu xám nhạt khó đọc. |
| `UI-TY12` | Typography | Tính nhất quán text | **FAIL** | Không khớp danh xưng: Stat card ghi *"Đã xuất bản"* nhưng bảng ghi *"Thành công"*; Card ghi *"Xuất bản lỗi"* nhưng bảng ghi *"Từ chối"*. |
| `UI-IC01` | Icon | Đồng bộ ngôn ngữ icon | **PASS** | Icon nét đơn (outline) đồng bộ cho Xem `👁`, Sửa `✏`, Xóa `🗑`. |
| `UI-BU01` | Button | Đúng variant | **PASS** | Nút `+ Tạo mới` và `✓ Duyệt tất cả` dùng đúng primary solid blue button. |
| `UI-DA01` | Table | Cột và hàng dùng lưới rõ ràng | **PASS** | Đường kẻ phân cách hàng mảnh, sạch sẽ, khoảng cách dòng dễ đọc. |
| `UI-DA02` | Table | Căn gióng dữ liệu theo loại | **PASS** | Text căn trái, STT căn giữa/trái, Thao tác căn phải. |
| `UI-DA03` | Table | Trạng thái bảng | **FAIL** | Thiếu công cụ sắp xếp (Sort arrows trên header), không có bộ lọc trạng thái. |
| `UI-PA01` | Pagination | Vùng tương tác & hiển thị | **FAIL** | Dãy số phân trang bị vỡ logic: `1 2 3 ... 4 5 6` trên tổng số 10 trang. |
| `UI-ME01` | Navigation | Giữ nguyên nhận diện menu | **FAIL** | Trùng lặp thông tin Admin profile ở cả Header góc trên phải và Sidebar chân trang. |
| `UI-AL01` | Badge/Tag | Thể hiện semantic nhất quán | **FAIL** | Cả 4 card đều mang badge `+3 bài`; Card *"Xuất bản lỗi"* mang badge màu đỏ nhưng ghi `+3 bài` gây hiểu nhầm về chỉ số tăng trưởng. |
| `UI-BU04` | Button | Spacing và padding button | **PASS** | Khoảng cách icon và text trong button `+ Tạo mới` cân đối. |

---

### 4.2. UX Checklist (15 tiêu chí áp dụng)

| ID | Tiêu chí | Nội dung kiểm tra | Kết quả | Bằng chứng quan sát |
|:---|:---|:---|:---:|:---|
| `UX-TC01` | Tiếp cận | Thứ tự trình bày hợp lý | **PASS** | Luồng nhận thức từ Tổng quan số liệu $\rightarrow$ Hành động tạo mới $\rightarrow$ Chi tiết lịch sử. |
| `UX-TC02` | Tiếp cận | Màu sắc mang tính định hướng | **FAIL** | Badge `+3 bài` màu đỏ trên card lỗi gây nhầm lẫn; Màu sắc trạng thái giữa Card và Table chưa đồng nhất. |
| `UX-TC04` | Tiếp cận | Đúng ngữ nghĩa văn bản | **FAIL** | Toàn bộ 10 dòng STT đều là `1`; Phân trang `1 2 3 ... 4 5 6` sai logic. |
| `UX-TC37` | Điều hướng | Nhận biết vị trí hiện tại | **PASS** | Sidebar active mục "Tổng quan", tiêu đề trang là "Tổng quan". |
| `UX-TC57` | Dữ liệu | Tìm kiếm & thu hẹp dữ liệu lớn | **FAIL** | Bảng có 10 trang (hàng trăm bài viết) nhưng không có ô tìm kiếm hoặc bộ lọc danh mục/trạng thái. |
| `UX-DH01` | Dễ hiểu | Hạn chế Jargon & Tiếng Anh sót | **FAIL** | Phần phân trang dùng tiếng Anh: `"Page 1 of 10"`, `"Rows per page"` trong giao diện tiếng Việt. |
| `UX-DH04` | Dễ hiểu | Không có lỗi logic/diễn đạt | **FAIL** | Dấu ba chấm `...` đặt giữa số 3 và 4 trong dãy số tự nhiên liên tiếp. |
| `UX-DX01` | Thao tác | Nút hành động an toàn & có kiểm soát | **FAIL** | Nút `Duyệt tất cả` không có cơ chế chọn lọc (Checkbox), dễ bấm nhầm duyệt toàn bộ bài không mong muốn. |
| `UX-DX02` | Thao tác | Hành động ngữ cảnh tại dòng | **FAIL** | Dòng có trạng thái *"Chờ duyệt"* chỉ có 3 nút `Xem`, `Sửa`, `Xóa` mà không có nút `Duyệt nhanh` hoặc `Từ chối`. |
| `UX-TC15` | Tương tác | Trạng thái button | **PASS** | Button có trạng thái rõ ràng. |
| `UX-TC16` | Tương tác | Thao tác 1-click | **PASS** | Các nút thao tác xem/sửa tại dòng có thể click trực tiếp. |
| `UX-TC36` | Điều hướng | Menu điều hướng phân khu | **PASS** | Cấu trúc phân nhóm sidebar rõ ràng (Menu chính, Nội dung, Biên tập & SEO, Hệ thống). |
| `UX-DH05` | Ngôn ngữ | Đồng nhất ngôn ngữ hiển thị | **FAIL** | Pha trộn tiếng Anh ở phân trang. |
| `UX-TC41` | Điều hướng | Truy cập trang chủ | **PASS** | Có thể click vào "Tổng quan" hoặc Logo để về trang chủ. |
| `UX-DX03` | Thao tác | Thao tác Xóa an toàn | **PASS** | Icon thùng rác có màu đỏ cảnh báo. |
