# Báo cáo Đánh giá Trải nghiệm Người dùng (UX Audit) - VNPT SmartCA

- **Sản phẩm:** VNPT SmartCA (Màn hình Khai báo thông tin chứng thư số)
- **Ngày đánh giá:** 14/06/2026
- **Phương pháp:** Heuristic Evaluation (Nielsen's 10 Heuristics) & UX/UI Review

---

## 1. Tổng quan đánh giá
Màn hình "Khai báo thông tin" này thực hiện việc thu thập thông tin định danh và liên hệ của người sở hữu chứng thư số để kích hoạt dịch vụ. Giao diện được cấu trúc theo dạng danh sách cuộn dọc đơn giản. Tuy nhiên, luồng điền form còn khá thủ công, thiếu tính tối ưu hóa trong nhập liệu và chưa đáp ứng tốt tiêu chuẩn về khả năng tiếp cận (Accessibility).

---

## 2. Điểm UX tổng thể

| Hạng mục | Điểm | Nhận xét nhanh |
| :--- | :--- | :--- |
| **Usability** (Khả năng sử dụng) | 6.5/10 | Bố cục biểu mẫu rõ ràng nhưng thiếu hướng dẫn nhập liệu động trực quan. |
| **Accessibility** (Khả năng tiếp cận) | 5.5/10 | Độ tương phản của nút "Tiếp tục" và các hộp cảnh báo thấp. Thiết kế ô nhập liệu dạng Underline có diện tích chạm phản hồi nhỏ. |
| **Navigation** (Điều hướng) | 8.0/10 | Nút Back và Close thiết kế tốt ở header. Nút hành động chính cố định giúp định hướng bước tiếp theo rõ ràng. |
| **Visual Design** (Thiết kế trực quan) | 6.0/10 | Màu sắc thương hiệu chưa hài hòa (phối màu xanh dương và vàng cam chưa tối ưu). Định dạng ký tự bắt buộc không nhất quán. |
| **Customer Experience** (Trải nghiệm khách hàng) | 6.0/10 | Bắt buộc nhập tay quá nhiều thông tin giấy tờ, làm tăng thời gian hoàn thành và rủi ro nhập sai thông tin. |

**Tổng điểm UX: 6.4/10**

---

## 3. Điểm mạnh
- **Phân tách phân mục hợp lý:** Chia rõ ràng giữa thông tin cá nhân sở hữu chứng thư và thông tin liên hệ nhận mã kích hoạt.
- **Có hộp thông tin chỉ dẫn:** Đưa ra các lưu ý quan trọng để người dùng kiểm tra độ chính xác của thông tin trước khi tiếp tục.
- **Điều hướng cơ bản tốt:** Header hiển thị đầy đủ nút quay lại (Back) và đóng (Close).

---

## 4. Vấn đề phát hiện

| Hạng mục | Vấn đề | Severity | Priority | Heuristic | Root Cause | Impact |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **Accessibility** | Độ tương phản của nút **"Tiếp tục"** rất thấp (chữ trắng trên nền vàng cam nhạt) không đạt chuẩn WCAG AA. | **High** | **P1** | Aesthetic and Minimalist Design | Design | Người dùng khó đọc chữ trên nút bấm, đặc biệt khi dùng ngoài trời hoặc đối với người lớn tuổi. |
| **Usability & Efficiency** | Phải nhập tay thủ công toàn bộ thông tin giấy tờ (Họ tên, Số CCCD, Ngày cấp, Nơi cấp) thay vì hỗ trợ OCR quét ảnh CCCD. | **High** | **P2** | Flexibility and Efficiency of Use | Technology | Tăng đáng kể thời gian điền form, tăng tỷ lệ sai sót thông tin và tỷ lệ thoát luồng. |
| **Design Affordance** | Ô nhập liệu dạng đường kẻ dưới (Underline) có diện tích phản hồi chạm nhỏ và ranh giới không rõ ràng. | **Medium** | **P2** | Aesthetic and Minimalist Design | Design | Người dùng di động dễ bấm hụt hoặc bấm nhầm giữa các dòng nhập liệu sát nhau. |
| **Design Affordance** | Thiếu chỉ dẫn loại tương tác ở các trường đặc thù (như icon lịch chọn "Ngày cấp", icon dropdown cho "Nơi cấp"). | **Medium** | **P2** | Match Between System and Real World / Recognition Rather Than Recall | Design | Người dùng bối rối không biết trường nào phải gõ chữ, trường nào được chọn từ danh sách hoặc lịch biểu. |
| **Visual Design** | Hộp thông báo màu xám nhạt dễ bị lướt qua (Banner Blindness) do trông giống trạng thái bị vô hiệu hóa (disabled). | **Medium** | **P2** | Help and Documentation / Visibility of System Status | Design | Người dùng dễ bỏ qua lưu ý quan trọng dẫn đến nhập sai định dạng hoặc sai số điện thoại nhận mã. |
| **Consistency** | Hiển thị ký hiệu bắt buộc (`*`) không nhất quán (chỗ viết sát nhãn như `Họ tên*`, chỗ có khoảng trắng như `Ngày cấp *`). | **Low** | **P3** | Consistency and Standards | Content / Design | Gây cảm giác thiếu chỉn chu và thiếu chuyên nghiệp trong thiết kế giao diện. |

---

## 5. Đề xuất cải tiến

| Giải pháp | Impact | Effort | Priority |
| :--- | :--- | :--- | :--- |
| **Tăng tương phản nút bấm:** Thay đổi màu chữ của nút "Tiếp tục" sang màu sẫm hơn hoặc chỉnh tông màu nền nút để tăng độ tương phản đạt chuẩn WCAG AA. | **High** | **Low** | **P1** |
| **Thiết kế lại trường nhập liệu:** Chuyển đổi từ dạng đường kẻ dưới (Underline) sang dạng hộp đóng (Outlined/Filled Text Field) theo chuẩn Material Design/iOS để tối ưu vùng chạm. | **High** | **Low** | **P1** |
| **Tích hợp quét ảnh OCR:** Bổ sung tính năng quét CCCD để tự động điền (auto-populate) biểu mẫu nhằm tối ưu hóa thời gian nhập liệu. | **High** | **Medium** | **P2** |
| **Thêm icon chỉ dẫn tương tác:** Bổ sung icon lịch chọn ngày cho "Ngày cấp" và icon dropdown cho "Nơi cấp" và các trường danh sách. | **Medium** | **Low** | **P2** |
| **Thiết kế lại hộp cảnh báo:** Sử dụng màu nền ngữ nghĩa (như xanh dương nhạt cho thông tin) kèm icon biểu thị (ℹ️) để tăng khả năng chú ý. | **Medium** | **Low** | **P2** |
| **Chuẩn hóa nhãn bắt buộc:** Định dạng nhất quán tất cả ký tự `*` viết sát nhãn, hoặc loại bỏ `*` và dùng ghi chú chung: *"Mọi thông tin dưới đây là bắt buộc nhập"*. | **Low** | **Low** | **P3** |

---

## 6. Kết quả mong đợi
- **Tăng Task Success Rate:** Người dùng hoàn thành biểu mẫu đăng ký dịch vụ ngay từ lần đầu tiên.
- **Giảm Drop-off Rate:** Hạn chế tỷ lệ thoát luồng nhờ rút ngắn thời gian nhập liệu (nhờ OCR) và thao tác chạm chính xác hơn.
- **Đạt chuẩn tiếp cận:** Đảm bảo toàn bộ người dùng có thể dễ dàng nhận dạng nút bấm và các lưu ý quan trọng.

---

## 7. Roadmap

### P1: Triển khai ngay
- Tối ưu màu sắc nút bấm chính để đạt độ tương phản chuẩn WCAG.
- Chuyển đổi các ô nhập liệu sang dạng hộp đóng (Outlined Text Fields) giúp tăng diện tích tương tác.

### P2: Ngắn hạn (Sprint tiếp theo)
- Bổ sung icon lịch biểu chọn ngày và icon dropdown cho các trường dữ liệu danh mục.
- Làm nổi bật và thiết kế lại màu sắc các hộp cảnh báo quan trọng bằng màu chỉ dẫn (Info/Warning).

### P3: Dài hạn
- Tích hợp công nghệ OCR tự động nhận diện thông tin từ ảnh chụp CCCD.
- Rà soát tính nhất quán về nội dung (content consistency) của toàn bộ các nhãn biểu mẫu.
