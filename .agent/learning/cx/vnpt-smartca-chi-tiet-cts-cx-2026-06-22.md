# Báo cáo Đánh giá Trải nghiệm Người dùng (UX Audit) - VNPT SmartCA: Chi tiết Chứng thư số

- **Sản phẩm:** VNPT SmartCA (Màn hình Chi tiết chứng thư số)
- **Ngày đánh giá:** 22/06/2026
- **Phương pháp:** Heuristic Evaluation (Nielsen's 10 Heuristics) & UX/UI Mobile Review
- **Dựa trên tài liệu gốc:** [cx.md](file:///Volumes/CHAOS/VNPT/AI/CX/.agent/skills/cx.md)

---

## 1. Tổng quan đánh giá
Màn hình "Chi tiết chứng thư số" hiển thị toàn bộ thông tin quản trị và vận hành của một chứng thư số cá nhân cụ thể (ở đây là chứng thư số tên gợi nhớ "Lê Đình Hào 01"). Màn hình này đóng vai trò là trung tâm kiểm soát chứng thư, cho phép người dùng theo dõi tình trạng, thông tin gói cước, số lượt ký, thiết bị kích hoạt và thực hiện các thay đổi cấu hình (như đổi PIN, đổi thiết bị, ẩn chứng thư).

Đặc biệt, giao diện đã tích hợp một banner màu xanh dương nhạt ở vị trí trung tâm để nhắc nhở tác vụ "Cấp bù chứng thư số" dành riêng cho chứng thư số này. Nhìn chung, giao diện đã có nhiều cải tiến rõ rệt về mặt thẩm mỹ và tính tiện dụng (như thêm icon copy nhanh cho mã Serial). Tuy nhiên, một số vấn đề về dồn ép nút chức năng, hiển thị thừa dữ liệu kỹ thuật và độ tương phản của nút chức năng phụ vẫn cần được tối ưu hóa để mang lại trải nghiệm hoàn hảo.

---

## 2. Điểm UX tổng thể

| Hạng mục | Điểm | Nhận xét nhanh |
| :--- | :---: | :--- |
| **Usability** (Khả năng sử dụng) | 7.5/10 | Bố cục thông tin mạch lạc, dễ tra cứu. Bổ sung nút sao chép nhanh số Serial rất hữu ích. Tuy nhiên việc gộp nhiều hành động vào một nút bấm ở cuối trang gây giảm khả năng sử dụng. |
| **Accessibility** (Khả năng tiếp cận) | 7.0/10 | Nút hành động phụ ở dưới cùng có độ tương phản chữ và nền kém. Checkbox có diện tích phản hồi chạm nhỏ. |
| **Navigation** (Điều hướng) | 8.0/10 | Nút quay lại rõ ràng. Nút kêu gọi hành động "Thực hiện cấp bù ngay ->" có mũi tên hướng đi giúp dẫn dắt luồng người dùng rất tốt. |
| **Visual Design** (Thiết kế trực quan) | 7.5/10 | Màu sắc nhất quán, căn lề và phân cấp typography tốt. Phần thông tin thiết bị chiếm nhiều không gian thị giác không cần thiết. |
| **Customer Experience** (Trải nghiệm khách hàng) | 7.5/10 | Trải nghiệm cá nhân hóa tốt (cho phép đặt tên gợi nhớ cho chứng thư số). Việc nhắc nhở cấp bù trực tiếp tại chi tiết chứng thư giúp tăng tính liên kết hành vi. |

**Tổng điểm UX: 7.5/10** (Mức Khá tốt, giao diện chỉn chu và tiện dụng hơn so với dạng Pop-up).

---

## 3. Điểm mạnh
- **Cải tiến tính năng sao chép (Copy icon):** Việc tích hợp icon copy bên cạnh chuỗi "Số seri" là một điểm cộng lớn, giúp người dùng dễ dàng sao chép chuỗi mã phức tạp này mà không cần bôi đen thủ công hay gõ tay, giải quyết triệt để lỗi rớt dòng của phiên bản cũ.
- **Cá nhân hóa chứng thư:** Cho phép "Đặt tên chứng thư số" (kèm biểu tượng bút chì để chỉnh sửa nhanh) giúp người dùng quản lý dễ dàng khi sở hữu nhiều chứng thư số khác nhau.
- **Banner cấp bù tích hợp khéo léo:** Đặt banner cấp bù ngay dưới phần thời hạn hiệu lực cũ, sử dụng màu nền dịu mắt nhưng vẫn đủ nổi bật. Thông tin ngày hết hạn mới (02/01/2027) được in đậm rõ ràng, tạo động lực thực hiện.
- **Thông tin trạng thái trực quan:** Nhãn trạng thái `Đang hoạt động` với màu xanh lá cây chuẩn giúp người dùng nhanh chóng xác nhận tình trạng của chứng thư mà không cần đọc nhiều.
- **Phân nhóm thông tin logic:** Sử dụng các đường kẻ ngang phân tách mảnh để chia dữ liệu thành các khối: Định danh -> Thời hạn & Cấp bù -> Trạng thái & Gói cước -> Kỹ thuật thiết bị -> Hành động nâng cao.

---

## 4. Vấn đề phát hiện

| Hạng mục | Vấn đề | Severity | Priority | Heuristic | Root Cause | Impact |
| :--- | :--- | :---: | :---: | :--- | :--- | :--- |
| **Usability & Interaction** | **Gộp quá nhiều hành động hành vi khác nhau vào một nút bấm:** Nút dưới cùng ghi `Đổi thiết bị/PIN/Kích hoạt lại chứng thư` gộp cả 3 tác vụ quản trị hệ trọng và khác biệt hoàn toàn về bản chất luồng đi. | **High** | **P2** | Consistency and Standards / Recognition Rather Than Recall | Design | Khiến người dùng bối rối không biết bấm vào sẽ dẫn đi đâu. Gây nguy cơ thao tác nhầm lẫn (ví dụ chỉ muốn đổi PIN nhưng lại đi vào luồng đổi thiết bị phức tạp). |
| **Aesthetic & Minimalist Design** | **Hiển thị thông tin kỹ thuật quá chi tiết (Visual Noise):** Khối "Thiết bị kích hoạt chứng thư" hiển thị các thông tin hệ thống thô (`Apple: iPhone`, `IOS: 17.2.1`, `Mã thiết bị: 4A37FJSNSF-...`) gây rối mắt người dùng phổ thông. | **Low** | **P3** | Aesthetic and Minimalist Design | Tech implementation / Design | Tăng độ dài cuộn trang không đáng có. Những thông tin này chỉ thực sự cần thiết khi xảy ra sự cố kỹ thuật cần debug. |
| **Accessibility (WCAG)** | **Độ tương phản thấp ở nút phụ:** Nút `Đổi thiết bị/PIN/Kích hoạt lại chứng thư` sử dụng chữ màu xanh dương trên nền xanh dương nhạt (`#EAF3FF` hoặc tương đương) có độ tương phản thấp. | **Medium** | **P2** | Aesthetic and Minimalist Design | Design | Người lớn tuổi hoặc người dùng ứng dụng dưới ánh sáng mặt trời mạnh sẽ rất khó đọc nội dung nút này. |
| **Error Prevention** | **Thiếu thông tin cảnh báo ở Checkbox ẩn chứng thư:** Checkbox `Ẩn chứng thư số khỏi màn hình danh sách` cho phép ẩn ngay lập tức chứng thư số mà không có dòng giải thích về hậu quả hoặc cách khôi phục lại hiển thị. | **Medium** | **P2** | Error Prevention / Help and Documentation | Content / Design | Người dùng vô tình tích chọn sẽ không thấy chứng thư số của mình ở danh sách ngoài, dẫn đến hoang mang tưởng chứng thư đã bị xóa và phải gọi tổng đài hỗ trợ. |
| **Consistency** | **Sự trùng lặp thông tin thời hạn gây tải nhận thức:** Dòng `Hiệu lực [i] 27/02/2024 - 18/11/2026` hiển thị ngay phía trên banner cấp bù (cũng chứa ngày hết hạn cũ `18/11/2026`). | **Low** | **P3** | Consistency and Standards | Design | Người dùng phải đọc lại thông tin ngày hết hạn cũ hai lần ở hai khối liền kề nhau, làm tăng tải nhận thức (cognitive load) không cần thiết. |

---

## 5. Đề xuất cải tiến

| Giải pháp | Impact | Effort | Priority |
| :--- | :---: | :---: | :---: |
| **Tách biệt các nút hành động quản trị:**<br>Thay vì dùng một nút gộp dài ở dưới cùng, hãy tách thành các liên kết hoặc nút nhỏ riêng biệt (hoặc đưa vào một menu cấu hình dạng bánh răng/dấu ba chấm ở góc trên cùng bên phải). Ví dụ tách thành: 1. *Đổi mã PIN*, 2. *Chuyển thiết bị ký số*, 3. *Kích hoạt lại*. | **High** | **Medium** | **P1** |
| **Thu gọn thông tin thiết bị (Mã thiết bị/HĐH):**<br>Mặc định ẩn các thông tin kỹ thuật sâu này dưới dạng một menu thả xuống (Dropdown/Collapse) tiêu đề *"Thông tin thiết bị"* hoặc chỉ hiển thị khi người dùng bấm vào biểu tượng trợ giúp/gỡ lỗi. Việc này giúp làm sạch giao diện và giảm chiều dài màn hình. | **Medium** | **Low** | **P2** |
| **Thêm cảnh báo xác nhận khi chọn "Ẩn chứng thư":**<br>Khi người dùng tích chọn checkbox ẩn, hiển thị một Pop-up thông báo: *"Chứng thư sẽ bị ẩn khỏi màn hình chính. Bạn có thể hiển thị lại bất kỳ lúc nào trong phần Cài đặt chứng thư. Bạn có muốn tiếp tục?"* để phòng tránh lỗi thao tác. | **High** | **Low** | **P2** |
| **Tăng độ tương phản màu sắc cho nút phụ:**<br>Điều chỉnh tông màu chữ của nút `Đổi thiết bị/PIN/Kích hoạt lại chứng thư` tối hơn hoặc chuyển nút này thành dạng văn bản liên kết (Text Link) có màu xanh đậm có gạch chân, hoặc nút viền (Outlined Button) để đạt chuẩn tương phản WCAG AA. | **Medium** | **Low** | **P2** |
| **Tối ưu hóa hiển thị ngày hiệu lực:**<br>Khi có sự kiện cấp bù, dòng hiệu lực chính `Hiệu lực [i]` có thể hiển thị một huy hiệu (Badge) nhỏ màu cam *"Sắp hết hạn - Cần cấp bù"* bên cạnh ngày hết hạn cũ để dẫn dắt trực tiếp sự chú ý của người dùng xuống banner cấp bù phía dưới. | **Medium** | **Low** | **P3** |

---

## 6. Kết quả mong đợi
- **Giảm tỷ lệ lỗi thao tác nhầm lẫn:** Việc tách các nút chức năng quản trị dưới cùng giúp khách hàng thực hiện đúng mục đích (đổi PIN hoặc đổi thiết bị) mà không bị lạc luồng hay cấu hình sai.
- **Tăng tính tự phục vụ (Self-service success):** Người dùng hiểu rõ hành động ẩn chứng thư và cách tìm lại, giảm bớt cuộc gọi thắc mắc đến tổng đài.
- **Giao diện tối giản, tập trung hơn:** Loại bỏ các thông tin rác (mã thiết bị dài) giúp mắt người dùng tập trung vào các khu vực trọng tâm như thông tin gói cước và nút hành động cấp bù.
- **Cải thiện tính tiếp cận (Accessibility):** Nút chức năng dễ đọc hơn đối với mọi phân khúc khách hàng, kể cả khách hàng lớn tuổi (đối tượng sử dụng SmartCA cá nhân để thực hiện dịch vụ công).

---

## 7. Lộ trình thực hiện (Roadmap)

### P1: Triển khai ngay (Sprint hiện tại)
- Tách nút gộp dưới cùng thành các tùy chọn riêng biệt hoặc chuyển vào menu phụ (Settings) để tránh nhầm lẫn.
- Cập nhật cảnh báo xác nhận (confirmation dialog) khi chọn checkbox "Ẩn chứng thư số".

### P2: Ngắn hạn (Sprint tiếp theo)
- Thiết kế lại phần hiển thị thông tin thiết bị dưới dạng khối thu gọn (collapsible).
- Tăng độ tương phản màu chữ/màu nền của nút chức năng phụ dưới cùng để đảm bảo khả năng tiếp cận tốt.

### P3: Dài hạn (Cải tiến sản phẩm)
- Đồng bộ hóa các cảnh báo về thời hạn hiệu lực và trạng thái chứng thư trên toàn bộ ứng dụng (đồng bộ định dạng ngày giờ, huy hiệu cảnh báo).
