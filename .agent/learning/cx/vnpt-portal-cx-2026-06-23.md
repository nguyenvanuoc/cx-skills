# Báo cáo Đánh giá Trải nghiệm Người dùng (UX Audit) - VNPT Portal (Đăng ký Dịch vụ Internet & Gói cước)

- **Sản phẩm:** VNPT Portal - Giao diện Đăng ký dịch vụ lắp đặt Internet & Gói cước di động
- **Ngày đánh giá:** 23/06/2026
- **Phương pháp:** Heuristic Evaluation (Nielsen's 10 Heuristics), UX/UI Review & Mobile UX Best Practices

---

## 1. Tổng quan đánh giá
Trang Portal đăng ký dịch vụ của VNPT là điểm chạm số quan trọng (Digital Touchpoint) giúp khách hàng cá nhân tiếp cận và đăng ký trực tuyến các sản phẩm cốt lõi như Internet cáp quang (Home Mesh), gói cước Combo (Internet + MyTV) và các gói di động VinaPhone. 

Qua đánh giá các phiên bản giao diện (Desktop & Mobile), trang web đã cấu trúc thông tin tương đối đầy đủ và rõ ràng. Tuy nhiên, trải nghiệm người dùng trên thiết bị di động (Mobile UX) vẫn gặp nhiều trở ngại lớn về: độ dài trang quá lớn gây mệt mỏi khi cuộn (Scrolling Fatigue), luồng điền form đăng ký lắp đặt nhanh thủ công gây tăng nỗ lực tương tác (Interaction Cost), độ tương phản của một số văn bản mô tả chưa đạt chuẩn và sự thiếu đồng bộ của các nút hành động (Call to Action - CTA).

---

## 2. Điểm UX tổng thể

| Hạng mục | Điểm | Nhận xét nhanh |
| :--- | :--- | :--- |
| **Usability** (Khả năng sử dụng) | 6.5/10 | Bố cục thẻ sản phẩm rõ ràng, nhưng biểu mẫu đăng ký lắp đặt nhanh còn thủ công và tốn nhiều bước thao tác của người dùng. |
| **Accessibility** (Khả năng tiếp cận) | 6.0/10 | Một số thông tin chi tiết gói cước có kích thước nhỏ và độ tương phản thấp (chữ xám trên nền trắng). Vùng chạm (Tap Target) của một số icon menu trên mobile chưa tối ưu. |
| **Navigation** (Điều hướng) | 7.0/10 | Cấu trúc menu phân loại tốt. Tuy nhiên, trang Mobile quá dài và thiếu tính năng neo điều hướng nhanh (Quick Anchor Links) đến từng nhóm gói cước. |
| **Visual Design** (Thiết kế trực quan) | 6.5/10 | Giao diện hiện đại, sử dụng đúng màu sắc nhận diện thương hiệu VNPT. Phân cấp thị giác (Visual Hierarchy) giữa giá tiền và đơn vị tính phí cần rõ ràng hơn. |
| **Customer Experience** (Trải nghiệm khách hàng) | 6.0/10 | Thiếu công cụ so sánh nhanh các gói cước tại khu vực hiển thị danh sách thẻ, khiến khách hàng phải ghi nhớ thông tin thủ công để đưa ra lựa chọn. |

**Tổng điểm UX: 6.4/10**

---

## 3. Điểm mạnh
- **Cấu trúc phân khu rõ ràng:** Trang web chia tách mạch lạc các phần: Banner khuyến mãi -> Gói cước khuyên dùng (Home Mesh) -> Form đăng ký lắp đặt nhanh -> Gói Combo -> Gói cước di động -> Footer.
- **Thẻ sản phẩm (Cards) thiết kế gọn gàng:** Các thẻ gói cước hiển thị đầy đủ thông số chính (Tên gói, tốc độ băng thông, thiết bị Mesh đi kèm, giá cước và nút hành động chính).
- **Banner chính nổi bật:** Banner "TỐC ĐỘ INTERNET X10" truyền tải thông điệp mạnh mẽ, trực quan hóa tốc độ bằng hình ảnh sống động và cung cấp các nút tiện ích nhanh tiện lợi.

---

## 4. Vấn đề phát hiện

| Hạng mục | Vấn đề | Severity | Priority | Heuristic | Root Cause | Impact |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **Usability & Efficiency** | Form "Đăng ký lắp đặt nhanh" trên Mobile quá dài và phức tạp, buộc người dùng chọn thủ công 3 cấp địa giới (Tỉnh/Thành -> Quận/Huyện -> Phường/Xã) bằng dropdown truyền thống, dễ gây bấm nhầm. | **High** | **P1** | Flexibility and Efficiency of Use | Design / Technology | Tăng đáng kể thời gian và nỗ lực điền form (Interaction Cost), làm tăng tỷ lệ bỏ cuộc (Drop-off Rate) ngay tại phễu đăng ký. |
| **Accessibility** | Văn bản mô tả chi tiết ưu đãi trong thẻ gói cước (ví dụ: *"Tốc độ 100Mbps + 1 Thiết bị Mesh..."*) sử dụng font chữ nhỏ và màu xám nhạt trên nền trắng, độ tương phản dưới 4.5:1, không đạt chuẩn WCAG AA. | **High** | **P1** | Aesthetic and Minimalist Design | Design | Người dùng lớn tuổi hoặc người có thị lực kém gặp khó khăn lớn khi đọc thông tin ưu đãi gói cước. |
| **Navigation & Mobile UX** | Trang Mobile xếp chồng toàn bộ danh sách gói cước và form đăng ký theo chiều dọc khiến trang cực kỳ dài (Long Scrolling), gây mệt mỏi khi cuộn trang. | **Medium** | **P2** | Flexibility and Efficiency of Use | Design | Người dùng dễ bỏ qua các nhóm gói cước ở phía dưới (như gói di động VinaPhone) do ngại cuộn tiếp (Scrolling Fatigue). |
| **Consistency** | Thiết kế nút bấm hành động "Đăng ký" không nhất quán giữa các nhóm gói cước (ví dụ: gói Home Mesh dùng nút xanh dương đậm, gói Home Combo dùng màu nền khác) và văn bản nhãn nút không đồng bộ (chỗ ghi "Đăng ký", chỗ ghi "Đăng ký ngay"). | **Medium** | **P2** | Consistency and Standards | Design / Content | Gây cảm giác giao diện chắp vá, thiếu đồng bộ về mặt hệ thống thiết kế (Design System) và làm giảm độ chuyên nghiệp. |
| **Visual Design** | Đơn vị tiền tệ và chu kỳ cước phí (`đ/tháng`) được thiết kế với kích thước chữ quá nhỏ và mờ so với con số giá tiền chính (ví dụ: `180.000`), làm giảm phân cấp thị giác. | **Low** | **P3** | Aesthetic and Minimalist Design | Design | Người dùng khó đọc nhanh chu kỳ cước phí hoặc dễ nhầm lẫn giá cước giữa các gói cước có chu kỳ đóng trước khác nhau. |
| **Customer Experience** | Thiếu tính năng so sánh nhanh các gói cước trực quan ngay tại khu vực danh sách, buộc người dùng phải tự đối chiếu thông số giữa các thẻ bằng trí nhớ. | **Medium** | **P2** | Recognition Rather Than Recall | Design / Technology | Kéo dài thời gian cân nhắc lựa chọn gói cước của khách hàng, ảnh hưởng tiêu cực đến tỷ lệ chuyển đổi (Conversion Rate). |

---

## 5. Đề xuất cải tiến

| Giải pháp | Impact | Effort | Priority |
| :--- | :--- | :--- | :--- |
| **Tối ưu hóa form đăng ký trên Mobile:**<br>- Bổ sung nút "Sử dụng vị trí hiện tại" để tự động điền Tỉnh/Thành, Quận/Huyện, Xã/Phường qua GPS.<br>- Thay thế 3 dropdown hành chính bằng tính năng tìm kiếm thông minh (Auto-complete Search) trong một ô nhập liệu duy nhất. | **High** | **Medium** | **P1** |
| **Tăng độ tương phản chữ:** Điều chỉnh màu văn bản chi tiết mô tả gói cước sang màu tối hơn (ví dụ: `#4A5568` hoặc `#2D3748`) để đảm bảo độ tương phản đạt chuẩn WCAG AA trên mọi kích thước màn hình. | **High** | **Low** | **P1** |
| **Chuẩn hóa nút hành động (CTA):** Thống nhất kiểu dáng nút bấm (Filled Button màu xanh thương hiệu) và nhãn văn bản duy nhất (ví dụ: "Đăng ký ngay") trên tất cả các thẻ gói cước để tạo sự đồng bộ. | **Medium** | **Low** | **P2** |
| **Thêm thanh điều hướng nhanh (Anchor Tabs) trên Mobile:** Bổ sung thanh tab cố định (Sticky Anchor Tabs) nằm ngay dưới banner chính gồm các nút: `[Home Mesh]` `[Home Combo]` `[Gói Di Động]` giúp người dùng nhảy nhanh đến khu vực mong muốn mà không cần cuộn trang. | **High** | **Low** | **P2** |
| **Bổ sung tính năng so sánh gói cước:** Thêm ô checkbox "So sánh" trên mỗi thẻ gói cước và hiển thị bảng so sánh thông số trực quan khi người dùng chọn từ 2 gói trở lên. | **High** | **Medium** | **P2** |
| **Cải thiện phân cấp thị giác giá tiền:** Tăng nhẹ kích thước font chữ và làm đậm ký hiệu `đ/tháng`, giữ khoảng cách hợp lý với con số giá cước để người dùng dễ đọc. | **Low** | **Low** | **P3** |

---

## 6. Kết quả mong đợi
- **Tăng tỷ lệ chuyển đổi đăng ký (Conversion Rate):** Việc rút ngắn các bước điền form và thêm tính năng so sánh trực quan sẽ giúp người dùng đưa ra quyết định nhanh hơn và ít bỏ cuộc giữa chừng hơn.
- **Cải thiện chỉ số hài lòng khách hàng (CSAT):** Giao diện đồng bộ, dễ đọc và dễ tiếp cận sẽ mang lại trải nghiệm chuyên nghiệp, tin cậy cho thương hiệu VNPT.
- **Giảm tỷ lệ thoát trang (Bounce Rate) trên di động:** Nhờ thanh điều hướng nhanh giúp giảm tải thao tác cuộn trang mệt mỏi của người dùng.

---

## 7. Roadmap

### P1: Triển khai ngay (Sprint hiện tại)
- Điều chỉnh màu sắc và độ tương phản của tất cả các đoạn văn bản mô tả ưu đãi gói cước.
- Đồng bộ hóa thiết kế và văn bản nhãn của tất cả các nút bấm "Đăng ký" thành một chuẩn duy nhất của VNPT Design System.
- Tinh chỉnh phân cấp thị giác phần hiển thị giá tiền và chu kỳ cước phí.

### P2: Ngắn hạn (Sprint tiếp theo)
- Triển khai thanh điều hướng nhanh dạng tab cố định (Sticky Anchor Tabs) trên phiên bản Mobile.
- Tối ưu hóa form đăng ký lắp đặt nhanh: Tích hợp tính năng định vị GPS tự động điền địa chỉ và chuyển đổi dropdown thành ô tìm kiếm thông minh auto-complete.
- Nghiên cứu và thiết kế luồng so sánh gói cước nhanh.

### P3: Dài hạn (Các sprint sau)
- Tích hợp sâu tính năng so sánh gói cước động trên cả Desktop và Mobile.
- Thực hiện A/B Testing trên form đăng ký lắp đặt để kiểm chứng hiệu quả giảm tỷ lệ bỏ cuộc (Drop-off Rate).
