# Báo cáo Đánh giá Chất lượng UI/UX (UI/UX Quality Audit Report)

- **Sản phẩm**: VNPT eContract — Phân hệ Hợp đồng Lao động điện tử (Nghị định 337 & Nghị định 145)
- **Tên luồng đánh giá**: **Luồng Tạo mới, Thẩm định, Ký duyệt và Quản lý Hợp đồng Lao động (End-to-End Flow)**
- **Thứ tự kiểm tra**: Sắp xếp từ trên xuống dưới, từ trái qua phải theo từng bước trong luồng thao tác.
- **Ngày thực hiện**: 2026-09-15
- **Tài liệu tham chiếu**: [SKILL.md](file:///Volumes/CHAOS/VNPT/AI/CX/ui-ux-quality-audit/SKILL.md), [UI_Checklist.md](file:///Volumes/CHAOS/VNPT/AI/CX/.agent/skills/ui_ux/UI_Checklist.md), [UX_Checklist.md](file:///Volumes/CHAOS/VNPT/AI/CX/.agent/skills/ui_ux/UX_Checklist.md), [Scoring_Formula.md](file:///Volumes/CHAOS/VNPT/AI/CX/.agent/skills/ui_ux/Scoring_Formula.md)

---

## 1. Tổng quan điểm số (Score Summary)

$$\text{Checklist Score} = \frac{\text{Tổng áp dụng} - \text{FAIL}}{\text{Tổng áp dụng}} \times 100$$
$$\text{Issue Penalty} = (\text{Minor} \times 1) + (\text{Major} \times 3) + (\text{Critical} \times 5)$$
$$\text{Issue Score} = \max\left(0, 100 \times \left(1 - \frac{\text{Issue Penalty}}{\text{Tổng áp dụng} \times 5}\right)\right)$$
$$\text{UI/UX Score} = (\text{Checklist Score} \times 70\%) + (\text{Issue Score} \times 30\%)$$
$$\text{Experience Quality Score} = (\text{UI Score} \times 40\%) + (\text{UX Score} \times 60\%)$$

| Chỉ số | UI (Giao diện) | UX (Trải nghiệm) | Toàn diện (Experience Quality) |
|:---|---:|---:|---:|
| **Tổng checklist áp dụng** | 24 | 20 | 44 |
| **Checklist PASS** | 18 | 12 | 30 |
| **Checklist FAIL** | 6 | 8 | 14 |
| **N/A** | 57 | 266 | 323 |
| **NEEDS VALIDATION** | 0 | 0 | 0 |
| **Tổng số Issue** | **6** *(0 Critical, 3 Major, 3 Minor)* | **8** *(2 Critical, 4 Major, 2 Minor)* | **14 Issues** |
| - *Critical (Weight = 5)* | 0 | 2 | 2 |
| - *Major (Weight = 3)* | 3 | 4 | 7 |
| - *Minor (Weight = 1)* | 3 | 2 | 5 |
| **Issue Penalty** | **12** | **24** | **36** |
| **Checklist Score** | **75.0%** | **60.0%** | — |
| **Issue Score** | **90.0 / 100** | **76.0 / 100** | — |
| **UI Quality Score** | **79.5 / 100** | — | — |
| **UX Quality Score** | — | **64.8 / 100** | — |
| **Experience Quality Score** | — | — | **70.7 / 100 (Khá - Cần cải thiện)** |

---

## 2. Bảng: Kết quả đầu ra

*(Sắp xếp theo thứ tự kiểm tra từ trên xuống dưới, từ trái qua phải theo từng bước trong luồng)*

| Issue ID | Phân loại(UI/UX) | Mã checklist | Tên luồng | Chức năng | Bước thao tác | Thiết bị | Mức độ ảnh hưởng | Hình ảnh | Vấn đề | Đề xuất giải pháp | Hiệu quả sau cải tiến | Xếp loại Issue | Xếp loại Checklist | Effort | Urgency | Priority points |
|:---|:---|:---|:---|:---|:---|:---|:---|:---|:---|:---|:---|:---:|:---:|:---:|:---:|:---:|
| `ISSUE-01` | UX | `UX-DH01` | Tạo HĐLĐ | Nhập thông tin tài liệu | Nhập ô Tên hợp đồng lao động | Desktop | Minor | Trang 1 — Ô Tên HĐLĐ | Ô "Tên hợp đồng lao động" có placeholder ghi chữ "Text" thô sơ, thiếu tính hướng dẫn nghiệp vụ. | Sửa placeholder thành: "Nhập tên hợp đồng (VD: HĐLĐ - Nguyễn Văn A - 2026)". | Hướng dẫn rõ ràng, người dùng nhập đúng cú pháp ngay từ đầu. | Fail | Fail | 1 (Thấp) | 2 (Medium) | 2.0 |
| `ISSUE-02` | UI | `UI-TY12` | Tạo HĐLĐ | Cấu hình thời hạn | Chọn khoảng ngày hiệu lực HĐ | Desktop | Major | Trang 2 — Khối Hiệu lực HĐ | Checkbox "Không xác định thời hạn" chen ngang giữa 2 ô "Từ ngày" và "Đến ngày", làm đứt gãy căn gióng; placeholder ghi "Chọn ngày" thay vì định dạng ngày. | Gom checkbox "Không xác định thời hạn" xuống dưới ô "Đến ngày" hoặc đặt cạnh label; format ngày thành `DD/MM/YYYY`. | Bố cục liền mạch, thao tác chọn ngày giờ chuẩn xác. | Fail | Fail | 1 (Thấp) | 2 (Medium) | 6.0 |
| `ISSUE-03` | UI | `UI-LA06` | Tạo HĐLĐ | Cấu hình số HĐ | Nhập cấu hình số hợp đồng | Desktop | Minor | Trang 1, 2 — Ô Cấu hình số HĐ | Hiển thị 2 ô input rời rạc ngăn bằng dấu "-" nhưng không có tooltip hay nhãn phụ giải thích quy tắc sinh số tự động. | Bổ sung label "Tiền tố" / "Hậu tố" và preview số HĐ mẫu (VD: `HĐLĐ-001/2026`). | Tránh nhầm lẫn khi thiết lập dải số hợp đồng. | Fail | Fail | 1 (Thấp) | 1 (Low) | 1.0 |
| `ISSUE-04` | UX | `UX-TC02` | Tạo HĐLĐ | Cảnh báo thẩm quyền | Đọc cảnh báo người giao kết dưới form | Desktop | Minor | Trang 1, 2 — Chân form Tạo HĐ | Dòng chữ "Kiểm tra người có thẩm quyền giao kết..." dùng chữ màu đỏ cảnh báo lỗi khi người dùng chưa làm gì sai, gây tâm lý lo lắng. | Đổi sang màu xanh thông tin (Info Blue) hoặc màu xám trung tính kèm icon `ℹ` tooltip. | Tránh gây hoang mang, đúng nguyên tắc dùng màu trạng thái. | Fail | Fail | 1 (Thấp) | 1 (Low) | 1.0 |
| `ISSUE-05` | UX | `UX-DH02` | Báo cáo NĐ 337 | Khai báo dữ liệu báo cáo | Điền thông tin báo cáo Bộ LĐ-TB&XH | Desktop | Major | Trang 3, 4, 5 — Modal Báo cáo HĐLĐ | Form báo cáo có hơn 40 trường dữ liệu xếp dọc trong modal hẹp, người dùng phải cuộn chuột rất sâu, dễ sót thông tin. | Phân nhóm thành các Tab / Accordion: "1. Bên NSDLĐ", "2. Bên NLĐ", "3. Chế độ lương & BHXH" kèm thanh tiến độ. | Giảm tải nhận thức, dễ theo dõi tiến độ hoàn thiện hồ sơ. | Fail | Fail | 2 (Trung bình) | 3 (High) | 4.5 |
| `ISSUE-06` | UI | `UI-TY03` | Báo cáo NĐ 337 | Bảng thuộc tính báo cáo | Xem bảng ánh xạ dữ liệu | Desktop | Minor | Trang 3, 4 — Cột Loại dữ liệu | Cột "Loại dữ liệu" (String, Drop-down, Datetime) hiển thị thuật ngữ lập trình kỹ thuật không cần thiết cho nhân sự. | Ẩn cột "Loại dữ liệu" hoặc đổi thành nhãn trực quan (Chữ, Lựa chọn, Ngày tháng). | Giao diện thân thiện với người dùng phi kỹ thuật. | Fail | Fail | 1 (Thấp) | 1 (Low) | 1.0 |
| `ISSUE-07` | UX | `UX-DX01` | Báo cáo NĐ 337 | Xác thực dữ liệu báo cáo | Bấm nút Lưu khi chưa đủ thông tin | Desktop | Critical | Trang 5 — Modal Cảnh báo thiếu dữ liệu | Modal thông báo "Số lượng bắt buộc còn thiếu: 43" gây bế tắc vì không chỉ định trực tiếp trường nào bị thiếu và không có nút nhảy đến ô lỗi. | Highlight viền đỏ tại các ô bị thiếu và bổ sung nút "Đi đến trường thiếu đầu tiên". | Giúp người dùng hoàn thiện dữ liệu nhanh chóng thay vì dò tìm thủ công 43 trường. | Fail | Fail | 2 (Trung bình) | 3 (High) | 7.5 |
| `ISSUE-08` | UI | `UI-LA04` | Thẩm định HĐ | AI Review / Trợ lý pháp lý | Xem panel đánh giá tính pháp lý | Desktop | Major | Trang 5, 6 — Panel Đánh giá file | Panel đánh giá chiếm cố định nửa phải màn hình nhưng thiếu nút Thu gọn (Collapse) / Ghim nổi, che khuất giao diện chính. | Bổ sung nút thu gọn/mở rộng panel và cho phép kéo thả điều chỉnh kích thước chiều rộng. | Người dùng vừa đọc văn bản vừa đối chiếu nhận xét AI thuận tiện. | Fail | Fail | 2 (Trung bình) | 2 (Medium) | 3.0 |
| `ISSUE-09` | UX | `UX-TC34` | Thêm bên ký | Cấu hình luồng ký | Thiết lập danh sách người ký | Desktop | Major | Trang 7, 8 — Modal Thêm người ký | Quá nhiều checkbox tùy chọn đặt rải rác ("Ký tuần tự", "Áp dụng danh sách...", "Gắn dấu thời gian...") thiếu gom nhóm trực quan. | Gom các tùy chọn nâng cao vào khối "Cài đặt luồng ký" (Advanced Settings) với switch bật/tắt rõ ràng. | Quy trình thiết lập người ký mạch lạc, tránh nhầm lẫn. | Fail | Fail | 2 (Trung bình) | 2 (Medium) | 3.0 |
| `ISSUE-10` | UI | `UI-DA02` | Thêm bên ký | Bảng người tham gia ký | Xem bảng phân quyền ký | Desktop | Minor | Trang 7, 8 — Cột Thời gian xử lý | Cột "Thời gian xử lý" hiển thị số trơ trọi, thiếu đơn vị đo lường (giờ/ngày). | Bổ sung đơn vị rõ ràng: "24 giờ" hoặc "3 ngày". | Tránh hiểu nhầm về thời hạn cam kết xử lý hợp đồng. | Fail | Fail | 1 (Thấp) | 1 (Low) | 1.0 |
| `ISSUE-11` | UX | `UX-TC01` | Xem lại & Gửi | Kiểm tra tổng thể trước khi gửi | Xem màn hình Review & Send | Desktop | Major | Trang 8, 9 — Màn hình Xem lại và gửi | Màn hình xem lại hiển thị dạng bảng phẳng, thiếu nút "Sửa nhanh" (Quick Edit) từng phần, người dùng phải bấm "Quay lại" từ đầu nếu muốn chỉnh sửa. | Bổ sung nút "✏ Chỉnh sửa" tại từng khối thông tin để quay lại đúng bước cần sửa. | Tiết kiệm thao tác, tránh phải duyệt lại toàn bộ các bước trước. | Fail | Fail | 2 (Trung bình) | 3 (High) | 4.5 |
| `ISSUE-12` | UI | `UI-TA01` | Chi tiết HĐ | Điều hướng tab chi tiết | Chuyển đổi giữa các tab Thông tin, Chữ ký, Chứng thực | Desktop | Major | Trang 9, 10, 11, 12 — Tab bar chi tiết HĐ | Thanh Tab bên phải kích thước nhỏ, khoảng cách viền hẹp, trạng thái tab Active chưa đủ độ tương phản so với tab thường. | Tăng kích thước tab, thêm line active màu xanh đậm `#2563EB` và badge đếm số lượng (VD: Chữ ký (2)). | Người dùng dễ nhận biết tab đang chọn và chuyển đổi nhanh chóng. | Fail | Fail | 1 (Thấp) | 2 (Medium) | 6.0 |
| `ISSUE-13` | UX | `UX-DH01` | Chia sẻ HĐ | Tạo chia sẻ mới | Chọn loại tài khoản chia sẻ | Desktop | Major | Trang 11 — Form Tạo chia sẻ mới | Tùy chọn "Có tài khoản" / "Không có tài khoản" mơ hồ (không rõ là tài khoản VNPT hay tài khoản email bên ngoài). | Đổi nhãn thành: "Người dùng nội bộ VNPT" và "Đối tác / Cá nhân bên ngoài". | Người dùng chọn đúng đối tượng và phân quyền chính xác. | Fail | Fail | 1 (Thấp) | 2 (Medium) | 6.0 |
| `ISSUE-14` | UX | `UX-TC57` | Lịch sử HĐ | Tra cứu nhật ký hợp đồng | Tìm kiếm log hoạt động | Desktop | Critical | Trang 12, 13 — Tab Lịch sử & Modal Search | Tìm kiếm lịch sử phải mở thêm một Modal popup rời rạc, che khuất danh sách timeline bên dưới. | Tích hợp bộ lọc Từ ngày - Đến ngày và ô Search trực tiếp ngay phía trên dòng thời gian (Timeline Inline Filter). | Tra cứu lịch sử tức thì mà không bị che khuất ngữ cảnh màn hình. | Fail | Fail | 2 (Trung bình) | 3 (High) | 7.5 |

---

## 3. Bảng: Improverment Roadmap

*Sắp xếp theo thứ tự ưu tiên: **P1 $\rightarrow$ P2 $\rightarrow$ P3 $\rightarrow$ P4** (Critical + High hoặc Priority points $\ge 5 \rightarrow$ P1; Priority points $\ge 2 \rightarrow$ P2; Priority points $\ge 1 \rightarrow$ P3).*

| Issue ID | Phân loại(UI/UX) | Mã checklist | Chức năng | Bước thao tác | Thiết bị | Mức độ ảnh hưởng | Hình ảnh | Vấn đề | Đề xuất giải pháp | Hiệu quả sau cải tiến | Priority |
|:---|:---|:---|:---|:---|:---|:---|:---|:---|:---|:---|:---:|
| `ISSUE-07` | UX | `UX-DX01` | Xác thực dữ liệu báo cáo | Bấm nút Lưu khi chưa đủ thông tin | Desktop | Critical | Trang 5 — Modal Cảnh báo thiếu dữ liệu | Modal thông báo "Số lượng bắt buộc còn thiếu: 43" gây bế tắc vì không chỉ định trực tiếp trường nào bị thiếu và không có nút nhảy đến ô lỗi. | Highlight viền đỏ tại các ô bị thiếu và bổ sung nút "Đi đến trường thiếu đầu tiên". | Giúp người dùng hoàn thiện dữ liệu nhanh chóng thay vì dò tìm thủ công 43 trường. | **P1** |
| `ISSUE-14` | UX | `UX-TC57` | Tra cứu nhật ký hợp đồng | Tìm kiếm log hoạt động | Desktop | Critical | Trang 12, 13 — Tab Lịch sử & Modal Search | Tìm kiếm lịch sử phải mở thêm một Modal popup rời rạc, che khuất danh sách timeline bên dưới. | Tích hợp bộ lọc Từ ngày - Đến ngày và ô Search trực tiếp ngay phía trên dòng thời gian (Timeline Inline Filter). | Tra cứu lịch sử tức thì mà không bị che khuất ngữ cảnh màn hình. | **P1** |
| `ISSUE-02` | UI | `UI-TY12` | Cấu hình thời hạn | Chọn khoảng ngày hiệu lực HĐ | Desktop | Major | Trang 2 — Khối Hiệu lực HĐ | Checkbox "Không xác định thời hạn" chen ngang giữa 2 ô "Từ ngày" và "Đến ngày", làm đứt gãy căn gióng; placeholder ghi "Chọn ngày" thay vì định dạng ngày. | Gom checkbox "Không xác định thời hạn" xuống dưới ô "Đến ngày" hoặc đặt cạnh label; format ngày thành `DD/MM/YYYY`. | Bố cục liền mạch, thao tác chọn ngày giờ chuẩn xác. | **P1** |
| `ISSUE-12` | UI | `UI-TA01` | Điều hướng tab chi tiết | Chuyển đổi giữa các tab Thông tin, Chữ ký, Chứng thực | Desktop | Major | Trang 9, 10, 11, 12 — Tab bar chi tiết HĐ | Thanh Tab bên phải kích thước nhỏ, khoảng cách viền hẹp, trạng thái tab Active chưa đủ độ tương phản so với tab thường. | Tăng kích thước tab, thêm line active màu xanh đậm `#2563EB` và badge đếm số lượng (VD: Chữ ký (2)). | Người dùng dễ nhận biết tab đang chọn và chuyển đổi nhanh chóng. | **P1** |
| `ISSUE-13` | UX | `UX-DH01` | Tạo chia sẻ mới | Chọn loại tài khoản chia sẻ | Desktop | Major | Trang 11 — Form Tạo chia sẻ mới | Tùy chọn "Có tài khoản" / "Không có tài khoản" mơ hồ (không rõ là tài khoản VNPT hay tài khoản email bên ngoài). | Đổi nhãn thành: "Người dùng nội bộ VNPT" và "Đối tác / Cá nhân bên ngoài". | Người dùng chọn đúng đối tượng và phân quyền chính xác. | **P1** |
| `ISSUE-05` | UX | `UX-DH02` | Khai báo dữ liệu báo cáo | Điền thông tin báo cáo Bộ LĐ-TB&XH | Desktop | Major | Trang 3, 4, 5 — Modal Báo cáo HĐLĐ | Form báo cáo có hơn 40 trường dữ liệu xếp dọc trong modal hẹp, người dùng phải cuộn chuột rất sâu, dễ sót thông tin. | Phân nhóm thành các Tab / Accordion: "1. Bên NSDLĐ", "2. Bên NLĐ", "3. Chế độ lương & BHXH" kèm thanh tiến độ. | Giảm tải nhận thức, dễ theo dõi tiến độ hoàn thiện hồ sơ. | **P2** |
| `ISSUE-08` | UI | `UI-LA04` | AI Review / Trợ lý pháp lý | Xem panel đánh giá tính pháp lý | Desktop | Major | Trang 5, 6 — Panel Đánh giá file | Panel đánh giá chiếm cố định nửa phải màn hình nhưng thiếu nút Thu gọn (Collapse) / Ghim nổi, che khuất giao diện chính. | Bổ sung nút thu gọn/mở rộng panel và cho phép kéo thả điều chỉnh kích thước chiều rộng. | Người dùng vừa đọc văn bản vừa đối chiếu nhận xét AI thuận tiện. | **P2** |
| `ISSUE-09` | UX | `UX-TC34` | Cấu hình luồng ký | Thiết lập danh sách người ký | Desktop | Major | Trang 7, 8 — Modal Thêm người ký | Quá nhiều checkbox tùy chọn đặt rải rác ("Ký tuần tự", "Áp dụng danh sách...", "Gắn dấu thời gian...") thiếu gom nhóm trực quan. | Gom các tùy chọn nâng cao vào khối "Cài đặt luồng ký" (Advanced Settings) với switch bật/tắt rõ ràng. | Quy trình thiết lập người ký mạch lạc, tránh nhầm lẫn. | **P2** |
| `ISSUE-11` | UX | `UX-TC01` | Kiểm tra tổng thể trước khi gửi | Xem màn hình Review & Send | Desktop | Major | Trang 8, 9 — Màn hình Xem lại và gửi | Màn hình xem lại hiển thị dạng bảng phẳng, thiếu nút "Sửa nhanh" (Quick Edit) từng phần, người dùng phải bấm "Quay lại" từ đầu nếu muốn chỉnh sửa. | Bổ sung nút "✏ Chỉnh sửa" tại từng khối thông tin để quay lại đúng bước cần sửa. | Tiết kiệm thao tác, tránh phải duyệt lại toàn bộ các bước trước. | **P2** |
| `ISSUE-01` | UX | `UX-DH01` | Nhập thông tin tài liệu | Nhập ô Tên hợp đồng lao động | Desktop | Minor | Trang 1 — Ô Tên HĐLĐ | Ô "Tên hợp đồng lao động" có placeholder ghi chữ "Text" thô sơ, thiếu tính hướng dẫn nghiệp vụ. | Sửa placeholder thành: "Nhập tên hợp đồng (VD: HĐLĐ - Nguyễn Văn A - 2026)". | Hướng dẫn rõ ràng, người dùng nhập đúng cú pháp ngay từ đầu. | **P2** |
| `ISSUE-03` | UI | `UI-LA06` | Cấu hình số HĐ | Nhập cấu hình số hợp đồng | Desktop | Minor | Trang 1, 2 — Ô Cấu hình số HĐ | Hiển thị 2 ô input rời rạc ngăn bằng dấu "-" nhưng không có tooltip hay nhãn phụ giải thích quy tắc sinh số tự động. | Bổ sung label "Tiền tố" / "Hậu tố" và preview số HĐ mẫu (VD: `HĐLĐ-001/2026`). | Tránh nhầm lẫn khi thiết lập dải số hợp đồng. | **P3** |
| `ISSUE-04` | UX | `UX-TC02` | Cảnh báo thẩm quyền | Đọc cảnh báo người giao kết dưới form | Desktop | Minor | Trang 1, 2 — Chân form Tạo HĐ | Dòng chữ "Kiểm tra người có thẩm quyền giao kết..." dùng chữ màu đỏ cảnh báo lỗi khi người dùng chưa làm gì sai, gây tâm lý lo lắng. | Đổi sang màu xanh thông tin (Info Blue) hoặc màu xám trung tính kèm icon `ℹ` tooltip. | Tránh gây hoang mang, đúng nguyên tắc dùng màu trạng thái. | **P3** |
| `ISSUE-06` | UI | `UI-TY03` | Bảng thuộc tính báo cáo | Xem bảng ánh xạ dữ liệu | Desktop | Minor | Trang 3, 4 — Cột Loại dữ liệu | Cột "Loại dữ liệu" (String, Drop-down, Datetime) hiển thị thuật ngữ lập trình kỹ thuật không cần thiết cho nhân sự. | Ẩn cột "Loại dữ liệu" hoặc đổi thành nhãn trực quan (Chữ, Lựa chọn, Ngày tháng). | Giao diện thân thiện với người dùng phi kỹ thuật. | **P3** |
| `ISSUE-10` | UI | `UI-DA02` | Bảng người tham gia ký | Xem bảng phân quyền ký | Desktop | Minor | Trang 7, 8 — Cột Thời gian xử lý | Cột "Thời gian xử lý" hiển thị số trơ trọi, thiếu đơn vị đo lường (giờ/ngày). | Bổ sung đơn vị rõ ràng: "24 giờ" hoặc "3 ngày". | Tránh hiểu nhầm về thời hạn cam kết xử lý hợp đồng. | **P3** |

---

## 4. Bảng Đánh giá Checklist Chi tiết

### 4.1. UI Checklist (24 tiêu chí áp dụng)

| ID | Phần tử | Tiêu chí | Kết quả | Bằng chứng quan sát |
|:---|:---|:---|:---:|:---|
| `UI-LA01` | Layout | Lưới & Bố cục thống nhất | **PASS** | Giao diện chia 2 cột cân đối: Form nhập liệu bên trái, File đính kèm/Trợ lý AI bên phải. |
| `UI-LA02` | Layout | Căn gióng các khối | **PASS** | Trục lề trái của các trường thông tin thẳng hàng. |
| `UI-LA03` | Layout | Phân cấp thị giác | **PASS** | Stepper quy trình rõ ràng (Thông tin HĐ $\rightarrow$ Thêm bên ký $\rightarrow$ Xem lại và gửi). |
| `UI-LA04` | Layout | Khoảng cách & Gom nhóm | **FAIL** | Panel Đánh giá AI chiếm cố định nửa màn hình không thể thu gọn/điều chỉnh kích thước. |
| `UI-LA05` | Layout | Spacing scale | **PASS** | Margin/Padding đồng đều theo scale 8px/16px/24px. |
| `UI-LA06` | Layout | Màu sắc & Tương phản viền | **FAIL** | Ô cấu hình số HĐ và dải phân cách viền mờ nhạt, thiếu tooltip hướng dẫn. |
| `UI-TY01` | Typography | Font family đồng nhất | **PASS** | Font Sans-serif hiển thị rõ nét, không lỗi font tiếng Việt. |
| `UI-TY03` | Typography | Vai trò chữ có style riêng | **FAIL** | Cột "Loại dữ liệu" trong bảng báo cáo dùng thuật ngữ kỹ thuật (String, Drop-down, Datetime). |
| `UI-TY04` | Typography | Phân cấp chữ | **PASS** | Header modal, Section title và Label phân cấp rõ. |
| `UI-TY10` | Typography | Tương phản chữ | **PASS** | Độ tương phản text label so với nền đạt chuẩn WCAG AA. |
| `UI-TY12` | Typography | Tính nhất quán text & format | **FAIL** | Khối Hiệu lực HĐ bị đứt gãy do checkbox chen ngang giữa 2 ô ngày; placeholder "Chọn ngày" thiếu format `DD/MM/YYYY`. |
| `UI-IC01` | Icon | Đồng bộ ngôn ngữ icon | **PASS** | Icon Calendar, Upload, Delete, Checkmark nét vẽ đồng bộ. |
| `UI-BU01` | Button | Đúng variant | **PASS** | Primary button "Tiếp tục" / "Gửi hợp đồng", Secondary button "Quay lại" / "Lưu bản nháp". |
| `UI-BU04` | Button | Spacing & padding button | **PASS** | Padding bên trong các nút bấm cân đối. |
| `UI-TE01` | Input | Cấu trúc nhận diện rõ | **PASS** | Các input field có border bo góc và label đặt cố định phía trên. |
| `UI-TE02` | Input | Vị trí label thống nhất | **PASS** | 100% label đặt trên đầu ô nhập liệu. |
| `UI-DR01` | Dropdown | Hình dạng nhận diện Select | **PASS** | Có icon mũi tên dropdown `⌵` rõ ràng. |
| `UI-CH01` | Checkbox/Switch | Sử dụng đúng control | **PASS** | Checkbox dùng cho các tùy chọn nhiều mục (Ký tuần tự, Gắn dấu thời gian). |
| `UI-DA01` | Data table | Lưới bảng rõ ràng | **PASS** | Bảng danh sách người ký có divider phân cách hàng mảnh, sạch sẽ. |
| `UI-DA02` | Data table | Căn gióng & hiển thị dữ liệu | **FAIL** | Cột "Thời gian xử lý" hiển thị số trơ trọi thiếu đơn vị giờ/ngày. |
| `UI-MO01` | Modal/Dialog | Phân cấp lớp nền | **PASS** | Backdrop làm tối nền trang, modal nổi bật ở lớp trên. |
| `UI-MO02` | Modal/Dialog | Bố cục modal | **PASS** | Header, Body, Footer của các modal phân định rõ ràng. |
| `UI-TA01` | Tab bar | Phân biệt tab hiện tại | **FAIL** | Tab bar chi tiết HĐ bên phải (Thông tin, Chữ ký, Chứng thực...) kích thước nhỏ, active state chưa nổi bật. |
| `UI-AL01` | Toast/Alert | Thể hiện semantic nhất quán | **PASS** | Modal Thành công (icon xanh lá), Modal Warning (icon tam giác vàng). |

---

### 4.2. UX Checklist (20 tiêu chí áp dụng)

| ID | Tiêu chí | Nội dung kiểm tra | Kết quả | Bằng chứng quan sát |
|:---|:---|:---|:---:|:---|
| `UX-TC01` | Trình tự hợp lý | Luồng thao tác tự nhiên | **FAIL** | Trang Xem lại và gửi thiếu nút "Sửa nhanh" từng phần, bắt người dùng quay lại từ đầu nếu muốn sửa 1 trường. |
| `UX-TC02` | Màu sắc định hướng | Dùng màu đúng ngữ cảnh | **FAIL** | Dòng cảnh báo thẩm quyền người giao kết dùng chữ đỏ khi chưa có lỗi xảy ra. |
| `UX-TC03` | Từ ngữ quen thuộc | Hạn chế từ ngữ gây hoang mang | **FAIL** | Thông báo lỗi "Số lượng bắt buộc còn thiếu: 43" gây áp lực tâm lý cho người dùng. |
| `UX-TC04` | Đúng ngữ nghĩa | Dữ liệu và nhãn chính xác | **PASS** | Các thông tin pháp lý hợp đồng đúng chuẩn Bộ luật Lao động. |
| `UX-TC06` | Icon chuẩn ngành | Biểu tượng quen thuộc | **PASS** | Icon lịch cho ngày tháng, icon đám mây cho tải file. |
| `UX-TC15` | Button trạng thái | Đầy đủ visual feedback | **PASS** | Nút bấm có trạng thái rõ ràng. |
| `UX-TC16` | Thao tác 1-click | Thao tác đơn giản | **PASS** | Click tải file, chọn người ký trong 1-click. |
| `UX-TC26` | Label thường trực | Label ngoài ô nhập liệu | **PASS** | 100% trường nhập có label bên ngoài. |
| `UX-TC27` | Hướng dẫn định dạng | Format hiển thị sẵn | **FAIL** | Ô chọn ngày tháng không hiển thị gợi ý định dạng `DD/MM/YYYY`. |
| `UX-TC28` | Đánh dấu bắt buộc | Dấu hoa thị `*` rõ ràng | **PASS** | Các trường bắt buộc đều có dấu `*` đỏ cạnh label. |
| `UX-TC34` | Accordion/Gom nhóm | Gom nhóm form dài | **FAIL** | Bảng báo cáo NĐ 337 hơn 40 trường không gom nhóm theo accordion/tab, phải cuộn quá dài. |
| `UX-TC36` | Điều hướng luồng | Stepper tiến trình | **PASS** | Stepper 3 bước trên header giúp người dùng luôn biết mình đang ở bước nào. |
| `UX-TC37` | Vị trí hiện tại | Định vị ngữ cảnh | **PASS** | Tiêu đề và step active đồng bộ. |
| `UX-TC38` | Cơ chế quay lại | Nút Back / Hủy | **PASS** | Có nút "Quay lại", "Hủy", "Lưu bản nháp" ở mọi màn hình. |
| `UX-DH01` | Hạn chế Jargon | Ngôn ngữ dễ hiểu | **FAIL** | Placeholder ghi "Text"; Form chia sẻ ghi "Có tài khoản / Không có tài khoản" mơ hồ. |
| `UX-DH02` | Cung cấp action tiếp theo | Hướng dẫn xử lý lỗi | **FAIL** | Báo thiếu 43 trường nhưng không có nút "Đi đến trường lỗi đầu tiên". |
| `UX-DH04` | Không lỗi logic | Cấu trúc luồng logic | **PASS** | Luồng ký từ Soạn thảo $\rightarrow$ Thêm bên ký $\rightarrow$ Xem lại $\rightarrow$ Gửi hợp đồng logic. |
| `UX-DH05` | Ngôn ngữ đồng nhất | 100% tiếng Việt | **PASS** | Giao diện đã được Việt hóa đồng bộ. |
| `UX-DX01` | Xác thực dữ liệu | Validation thân thiện | **FAIL** | Thông báo lỗi dạng popup chặn (blocking alert) thay vì inline validation trực tiếp tại từng ô. |
| `UX-TC57` | Thu hẹp dữ liệu | Tìm kiếm & lọc thuận tiện | **FAIL** | Tìm kiếm nhật ký lịch sử tách riêng thành modal rời rạc thay vì filter inline. |
