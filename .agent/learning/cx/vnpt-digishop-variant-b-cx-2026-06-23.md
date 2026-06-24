# Báo cáo Đánh giá Trải nghiệm Người dùng (UX Audit) - VNPT Digishop (Biến thể B - Landing Page Tối ưu hóa Dịch vụ)

- **Sản phẩm:** Thiết kế biến thể B (Variant B) của VNPT Digishop - Tập trung giới thiệu 5G, SIM số đẹp và Gói cước gia đình
- **Ngày đánh giá:** 23/06/2026
- **Phương pháp:** Heuristic Evaluation (Nielsen's 10 Heuristics), UX/UI Review & CRO (Conversion Rate Optimization) Principles

---

## 1. Tổng quan đánh giá
Biến thể thiết kế B (Variant B) của VNPT Digishop tập trung vào việc tạo dựng các điểm nhấn thị giác cực mạnh (Visual Anchors) nhằm thu hút sự chú ý của khách hàng vào các gói cước chiến lược. Bố cục trang được làm thoáng đãng, hiện đại với các dải màu phân tách khu vực rõ ràng, sử dụng linh hoạt các card có màu nền tương phản cao và hiệu ứng nút bấm nổi bật.

Tuy nhiên, giao diện này vẫn còn một số điểm hạn chế về khả năng sử dụng (Usability) như: thiếu thanh tìm kiếm SIM nhanh tại chỗ, tính không nhất quán của màu sắc và nhãn nút bấm hành động (CTA), và các vấn đề về khả năng tiếp cận (Accessibility) đối với các tab bộ lọc ở trạng thái không hoạt động (inactive state).

---

## 2. Điểm UX tổng thể

| Hạng mục | Điểm | Nhận xét nhanh |
| :--- | :--- | :--- |
| **Usability** (Khả năng sử dụng) | 7.5/10 | Bố cục thoáng, dễ quét thông tin, nhưng việc loại bỏ hoàn toàn thanh tìm kiếm SIM nhanh ở trang chủ buộc người dùng phải chuyển trang để tìm kiếm. |
| **Accessibility** (Khả năng tiếp cận) | 7.0/10 | Độ tương phản của các tab chưa hoạt động (Inactive tabs) khá thấp. Cần kiểm chứng độ tương phản của chữ trắng trên nền nút hồng sen (Magenta). |
| **Navigation** (Điều hướng) | 8.5/10 | Header đầy đủ tính năng giỏ hàng và tìm kiếm. Thanh điều hướng neo nhanh và các nút "Xem tất cả" được bố trí hợp lý. |
| **Visual Design** (Thiết kế trực quan) | 9.0/10 | Rất xuất sắc trong việc tạo điểm nhấn thị giác (Visual Anchoring) ở thẻ trung tâm thông qua sự kết hợp màu sắc tương phản mạnh. |
| **Customer Experience** (Trải nghiệm khách hàng) | 8.0/10 | Giao diện mang tính định hướng cao, giúp khách hàng dễ dàng nhận biết đâu là gói cước bán chạy và được khuyên dùng nhất. |

**Tổng điểm UX: 8.0/10**

---

## 3. Điểm mạnh
- **Tạo điểm nhấn thị giác (Visual Anchoring) cực kỳ hiệu quả:** 
  - Thẻ SIM trung tâm (`0911.999.888`) và thẻ gói cước gia đình trung tâm (`Home Combo 2`) được thiết kế nổi bật với nền màu xanh dương đậm (Navy) và nút bấm màu hồng sen (Magenta) tương phản mạnh mẽ với các thẻ màu trắng xung quanh. Điều này giúp hướng người dùng tập trung vào sản phẩm biên lợi nhuận cao.
- **Phân tách khu vực tốt bằng màu nền (Visual Boundary):** Khu vực "Gói cước đang bán chạy" được đặt trên một dải nền màu xanh dương nhạt bo góc lớn giúp làm nổi bật chương trình Flash Sale mà không gây cảm giác lộn xộn.
- **Bố cục Hero Banner chất lượng cao:** Banner 5G sử dụng tông màu neon hiện đại, tạo cảm giác công nghệ cao và thu hút ngay từ cái nhìn đầu tiên.
- **Tiện ích nổi đa kênh (Floating Action Buttons):** Các icon Hotline và Chat được ghim cố định ở mép phải màn hình giúp khách hàng dễ dàng yêu cầu hỗ trợ bất kỳ lúc nào.

---

## 4. Vấn đề phát hiện

| Hạng mục | Vấn đề | Severity | Priority | Heuristic | Root Cause | Impact |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **Usability** | Thiếu thanh tìm kiếm nhanh SIM số đẹp tại chỗ. Khách hàng bắt buộc phải click chuyển trang "Xem toàn bộ sim số" mới tìm kiếm được số mong muốn. | **High** | **P2** | Flexibility and Efficiency of Use / Recognition Rather Than Recall | Design | Tăng số bước thao tác (Task Steps), gây bất tiện cho người dùng có nhu cầu tìm số cụ thể ngay tại trang chủ. |
| **Consistency** | Màu sắc và nhãn của nút bấm chính (CTA) không nhất quán: chỗ dùng nút xanh dương nhạt với chữ màu sậm, chỗ dùng nút hồng sen (Magenta), chỗ lại dùng nút xanh dương thương hiệu. Văn bản nút thay đổi liên tục: "Chọn số này", "Đăng ký", "Đăng ký ngay". | **Medium** | **P2** | Consistency and Standards | Design / Content | Làm giảm tính nhất quán trong trải nghiệm tương tác tổng thể và gây bối rối cho người dùng. |
| **Accessibility** | Các tab bộ lọc ở trạng thái chưa hoạt động (Inactive tabs) sử dụng chữ màu xám nhạt trên nền trắng, có độ tương phản rất thấp, không đạt chuẩn WCAG AA. | **Medium** | **P2** | Aesthetic and Minimalist Design | Design | Người dùng khó nhận diện các lựa chọn tab lọc khác, làm giảm hiệu quả khám phá sản phẩm (Findability). |
| **Interaction Design** | Thanh chỉ báo trượt (Carousel Indicators) dạng gạch ngang (`— —`) nằm ở dưới carousel bán chạy có kích thước quá mỏng và diện tích chạm (Tap Target) nhỏ. | **Low** | **P3** | Flexibility and Efficiency of Use | Design | Người dùng di động khó khăn khi muốn bấm trực tiếp vào chỉ báo để chuyển slide nhanh. |

---

## 5. Đề xuất cải tiến

| Giải pháp | Impact | Effort | Priority |
| :--- | :--- | :--- | :--- |
| **Tích hợp thanh tìm kiếm SIM thu nhỏ:** Bổ sung một ô tìm kiếm nhanh (gồm 1 input và 1 icon kính lúp) nằm ngay dưới tiêu đề phần SIM số đẹp để người dùng gõ nhanh số mong muốn. | **High** | **Medium** | **P2** |
| **Chuẩn hóa hệ thống nút bấm (CTA System):**<br>- Thống nhất màu sắc nút mặc định (ví dụ: nút màu xanh dương thương hiệu cho toàn trang).<br>- Giữ nút màu hồng sen (Magenta) **chỉ dành riêng** cho thẻ trung tâm được khuyên dùng để tạo điểm nhấn.<br>- Thống nhất nhãn nút: dùng "Mua ngay" cho SIM và "Đăng ký ngay" cho gói cước. | **High** | **Low** | **P2** |
| **Tăng độ tương phản cho trạng thái Inactive của Tab:** Thay đổi màu chữ của các tab chưa hoạt động sang màu xám đậm hơn (ví dụ: `#718096`) hoặc thêm đường viền mờ xung quanh tab để làm rõ ranh giới ô chọn. | **Medium** | **Low** | **P2** |
| **Cải tiến Carousel Indicators:** Thiết kế lại các dấu chỉ báo trượt dưới dạng các chấm tròn (Dots) có kích thước tối thiểu 8x8px và khoảng cách giữa các chấm rộng hơn để tối ưu vùng chạm trên Mobile. | **Low** | **Low** | **P3** |

---

## 6. Kết quả mong đợi
- **Tăng lượt đăng ký SIM số đẹp thành công:** Nhờ bổ sung thanh tìm kiếm nhanh giúp giảm ma sát (friction) trong luồng chọn số của khách hàng.
- **Tối ưu trải nghiệm sử dụng tab bộ lọc:** Giúp khách hàng dễ dàng nhận biết và click chuyển đổi giữa các nhóm dịch vụ khác nhau nhờ độ tương phản tab tốt hơn.
- **Trải nghiệm tương tác đồng bộ:** Nâng cao tính chuyên nghiệp của sản phẩm số nhờ chuẩn hóa thiết kế nút bấm.

---

## 7. Roadmap

### P1: Triển khai ngay (Sprint hiện tại)
- Tinh chỉnh màu chữ của các tab lọc ở trạng thái chưa hoạt động để đảm bảo độ tương phản dễ đọc.
- Đồng bộ hóa văn bản nhãn nút bấm chính trên toàn trang.
- Xác định quy chuẩn sử dụng màu sắc nút bấm (xanh thương hiệu cho nút thường, hồng sen cho nút đặc biệt cần làm nổi bật).

### P2: Ngắn hạn (Sprint tiếp theo)
- Bổ sung ô nhập liệu tìm kiếm nhanh SIM số đẹp ngay phía trên khu vực 3 thẻ SIM.
- Thiết kế lại các chấm chỉ báo chuyển slide (Carousel Indicators) để tăng diện tích tương tác chạm.

### P3: Dài hạn (Các sprint sau)
- Triển khai thử nghiệm A/B Testing giữa Biến thể A (có bảng danh sách SIM và form đăng ký nhanh) và Biến thể B (có 3 thẻ SIM lớn nổi bật và không có form đăng ký) để xem biến thể nào mang lại tỷ lệ chuyển đổi (Conversion Rate) cao hơn.
