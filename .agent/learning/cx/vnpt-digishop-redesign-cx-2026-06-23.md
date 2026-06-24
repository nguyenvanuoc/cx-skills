# Báo cáo Đánh giá Trải nghiệm Người dùng (UX Audit) - VNPT Digishop Redesign

- **Sản phẩm:** Giao diện thiết kế mới (Redesign) của Portal VNPT Digishop (Desktop)
- **Ngày đánh giá:** 23/06/2026
- **Phương pháp:** Heuristic Evaluation (Nielsen's 10 Heuristics), UX/UI Review & CRO (Conversion Rate Optimization) Principles

---

## 1. Tổng quan đánh giá
Bản thiết kế mới (Redesign) của VNPT Digishop thể hiện một bước tiến vượt bậc về mặt thẩm mỹ và tư duy tối ưu hóa chuyển đổi (CRO) so với phiên bản cũ. Giao diện sử dụng ngôn ngữ thiết kế hiện đại với các đường bo góc mềm mại, đổ bóng nhẹ tạo chiều sâu và phân bổ màu sắc thương hiệu (xanh dương - cam) rất hài hòa. 

Bằng cách loại bỏ form đăng ký lắp đặt thô sơ ở giữa trang, tích hợp các bộ lọc tab động và carousel, trang web đã giải quyết triệt để lỗi quá tải thông tin và giảm chiều dài cuộn trang (Scrolling Fatigue). Tuy nhiên, để đạt tới mức độ hoàn thiện tối đa, bản thiết kế cần tinh chỉnh thêm về tính nhất quán của các nút hành động (CTA), độ tương phản của một số nhãn ưu đãi và tối ưu hóa khả năng tương tác của các nút điều hướng carousel.

---

## 2. Điểm UX tổng thể

| Hạng mục | Điểm | Nhận xét nhanh |
| :--- | :--- | :--- |
| **Usability** (Khả năng sử dụng) | 8.5/10 | Cải tiến rõ rệt nhờ cơ chế lọc theo đối tượng và lọc theo dịch vụ giúp người dùng nhanh chóng tìm thấy sản phẩm phù hợp. |
| **Accessibility** (Khả năng tiếp cận) | 7.5/10 | Độ tương phản chung tốt hơn nhiều. Tuy nhiên, một số nhãn giảm giá màu trắng trên nền cam sáng vẫn cần được kiểm chứng độ tương phản chuẩn WCAG. |
| **Navigation** (Điều hướng) | 8.5/10 | Header tối giản và các nhóm quick links (SIM, Internet, Combo, Nạp tiền) đặt ở đầu trang giúp định hướng người dùng cực tốt. |
| **Visual Design** (Thiết kế trực quan) | 9.0/10 | Giao diện hiện đại, sạch sẽ, phân cấp thị giác rõ ràng và chuyên nghiệp. Thẻ sản phẩm nổi bật (gói cước ở giữa) thu hút sự chú ý tốt. |
| **Customer Experience** (Trải nghiệm khách hàng) | 8.5/10 | Tích hợp thành công các yếu tố tâm lý thúc đẩy mua hàng (Đồng hồ đếm ngược Ưu đãi hôm nay, Social Proof ở footer) giúp nâng cao trải nghiệm mua sắm số. |

**Tổng điểm UX: 8.4/10** (Tăng đáng kể so với phiên bản cũ là 6.4/10)

---

## 3. Điểm mạnh
- **Áp dụng hiệu quả các nguyên lý CRO:**
  - **Urgency (Cảm giác cấp bách):** Khung "Ưu đãi hôm nay" kèm đồng hồ đếm ngược đếm giây tạo động lực kích thích khách hàng click mua ngay.
  - **Decoy & Center Stage Effect:** Gói cước di động chủ lực (50GB/ngày) được thiết kế to hơn, có viền cam nổi bật giúp định hướng lựa chọn của khách hàng một cách tự nhiên.
  - **Social Proof (Bằng chứng xã hội):** Footer hiển thị các con số ấn tượng (2M+ khách hàng, 63 tỉnh thành...) củng cố mức độ tin cậy của thương hiệu.
- **Tối ưu hóa không gian (Space Efficiency):** Sử dụng các tab lọc đối tượng (`Cá nhân`, `Gia đình`, `Sinh viên`...) và tab lọc dịch vụ (`Internet`, `Truyền hình`...) giúp thu gọn thông tin hiển thị, tránh làm người dùng ngợp.
- **Tính năng tìm kiếm SIM số đẹp trực quan:** Thanh tìm kiếm kết hợp bộ lọc phân loại nhanh (Lộc phát, Tam hoa, Tứ quý...) giúp tăng trải nghiệm tìm kiếm (Findability).
- **Hỗ trợ đa kênh tiện lợi:** Nút gọi hỗ trợ và chat Zalo/Messenger dạng floating luôn hiển thị ở mép phải màn hình giúp người dùng tiếp cận hỗ trợ nhanh nhất.

---

## 4. Vấn đề phát hiện

| Hạng mục | Vấn đề | Severity | Priority | Heuristic | Root Cause | Impact |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **Consistency** | Nhãn văn bản trên các nút hành động chính (CTA) chưa đồng nhất: chỗ ghi "Mua ngay", chỗ ghi "Đăng ký ngay", chỗ lại ghi "Đăng ký". | **Medium** | **P2** | Consistency and Standards | Content | Làm giảm tính nhất quán của hệ thống và có thể gây bối rối cho người dùng về hành vi tiếp theo (thanh toán ngay hay chỉ để lại thông tin tư vấn). |
| **Usability & Affordance** | Các nút mũi tên điều hướng carousel (`<` và `>`) có kích thước khá nhỏ và đặt sát viền ngoài. | **Medium** | **P2** | Visibility of System Status / Flexibility and Efficiency of Use | Design | Người dùng sử dụng thiết bị màn hình cảm ứng (Tablet, Mobile) dễ bấm hụt hoặc gặp khó khăn khi thao tác cuộn trang. |
| **Accessibility** | Một số nhãn giảm giá (như `-50%`, `-30%` chữ trắng trên nền cam/đỏ sáng) và chữ số của đồng hồ đếm ngược có thể không đạt độ tương phản tối thiểu 4.5:1 (WCAG AA). | **Low** | **P3** | Aesthetic and Minimalist Design | Design | Người dùng có thị lực kém hoặc sử dụng thiết bị dưới ánh sáng mạnh khó đọc được thông tin ưu đãi. |
| **Usability** | Ở bảng kết quả tìm kiếm SIM, cột "Gói cước ưu đãi" hiển thị văn bản mô tả khá dài dưới dạng text thuần túy không có điểm nhấn. | **Low** | **P3** | Aesthetic and Minimalist Design / Recognition Rather Than Recall | Design / Content | Người dùng khó đọc lướt nhanh để so sánh ưu đãi đi kèm giữa các số điện thoại khác nhau. |

---

## 5. Đề xuất cải tiến

| Giải pháp | Impact | Effort | Priority |
| :--- | :--- | :--- | :--- |
| **Chuẩn hóa nhãn nút CTA theo loại sản phẩm:**<br>- Sử dụng **"Mua ngay"** cho các sản phẩm mua đứt bán đoạn hoặc thanh toán tức thì (SIM số đẹp, Nạp tiền điện thoại, gói cước di động thanh toán ngay).<br>- Sử dụng **"Đăng ký ngay"** cho các dịch vụ cần khảo sát hạ tầng lắp đặt (Internet cáp quang, Combo Internet + Truyền hình). | **High** | **Low** | **P2** |
| **Tối ưu hóa các nút điều hướng Carousel:**<br>- Tăng kích thước nút mũi tên điều hướng lên tối thiểu 40x40px, thêm hiệu ứng hover rõ ràng.<br>- Trên môi trường di động, ẩn các nút mũi tên này và kích hoạt hoàn toàn cử chỉ vuốt chạm **(Swipe gesture)** kèm theo thanh chấm phân trang (pagination dots) nhỏ ở dưới. | **High** | **Medium** | **P2** |
| **Cân chỉnh màu sắc tăng độ tương phản (WCAG AA):** Tinh chỉnh tông màu nền cam/đỏ của các tag giảm giá sẫm màu hơn một chút, hoặc sử dụng viền ngoài/chữ màu tối để đảm bảo thông tin khuyến mãi rõ ràng. | **Medium** | **Low** | **P3** |
| **Trực quan hóa gói cước đi kèm SIM:** Chuyển đổi văn bản mô tả gói cước đi kèm SIM thành các tag biểu thị ngắn gọn (ví dụ sử dụng tag: `[120GB/tháng]` `[Free Call]`) thay vì ghi chuỗi text dài dòng. | **Medium** | **Low** | **P3** |

---

## 6. Kết quả mong đợi
- **Tối ưu hóa phễu mua sắm (Sales Funnel):** Việc chuẩn hóa nhãn CTA giúp định hình đúng kỳ vọng của người dùng ở bước tiếp theo, làm giảm tỷ lệ hủy đơn giữa chừng.
- **Nâng cao khả năng tương tác (Engagement):** Các nút điều hướng carousel trực quan giúp tăng lượt tương tác của người dùng với các sản phẩm khác trong danh sách slide.
- **Trải nghiệm tìm kiếm SIM nhanh hơn:** Nhờ trực quan hóa thông tin ưu đãi đi kèm SIM bằng các thẻ tag dễ đọc lướt.

---

## 7. Roadmap

### P1: Triển khai ngay (Sprint hiện tại)
- Kiểm tra lại độ tương phản màu sắc của toàn bộ nhãn ưu đãi giảm giá và đồng hồ đếm ngược.
- Thực hiện chuẩn hóa hệ thống nhãn nút bấm CTA ("Mua ngay" vs "Đăng ký ngay") trên toàn bộ trang.

### P2: Ngắn hạn (Sprint tiếp theo)
- Thiết kế lại nút điều hướng Carousel (mũi tên to hơn, tối ưu cử chỉ swipe trên Mobile/Tablet).
- Cải tiến giao diện hiển thị ưu đãi gói cước đi kèm trong danh sách SIM số đẹp bằng cách dùng các tag ngắn gọn.

### P3: Dài hạn (Các sprint sau)
- Triển khai đo lường bản đồ nhiệt (Heatmap) và bản đồ click (Clickmap) trên các khu vực Carousel để phân tích hành vi tương tác thực tế của khách hàng.
