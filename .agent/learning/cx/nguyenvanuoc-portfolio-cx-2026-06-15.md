# Báo cáo Đánh giá Trải nghiệm Người dùng (UX Audit) - NguyenVanUoc Portfolio

- **Sản phẩm:** Trang web Portfolio cá nhân (https://nguyenvanuoc.github.io/)
- **Ngày đánh giá:** 15/06/2026
- **Phương pháp:** Heuristic Evaluation & UX/UI Review

---

## 1. Tổng quan đánh giá
Trang web portfolio cá nhân của tác giả **Uoc Nguyen** (Frontend, UI/UX Designer) hiện đang sử dụng một template blog tĩnh (như Jekyll). Hiện tại, trang web đang ở trạng thái **chưa hoàn thiện (template mặc định)** với rất nhiều nội dung giả lập (lorem ipsum), liên kết bị hỏng và thông tin không nhất quán. Đối với một portfolio của chuyên gia thiết kế UI/UX, trạng thái này ảnh hưởng nghiêm trọng đến uy tín thương hiệu cá nhân và trải nghiệm của nhà tuyển dụng/khách hàng.

---

## 2. Điểm UX tổng thể

| Hạng mục | Điểm | Nhận xét nhanh |
| :--- | :--- | :--- |
| **Usability** (Khả năng sử dụng) | 4.0/10 | Menu điều hướng đơn giản nhưng chứa các liên kết lỗi (404) và nội dung giả lập gây bối rối. |
| **Accessibility** (Khả năng tiếp cận) | 6.0/10 | Font chữ Roboto dễ đọc, độ tương phản cơ bản tốt nhưng cấu trúc tiêu đề (Headings) chưa chuẩn. |
| **Navigation** (Điều hướng) | 5.0/10 | Các liên kết mạng xã hội và một số menu tag dẫn đến trang trống hoặc trang lỗi. |
| **Visual Design** (Thiết kế trực quan) | 6.5/10 | Bố cục dạng lưới (Grid) tối giản, sạch sẽ (thừa hưởng từ theme gốc) nhưng thiếu cá tính cá nhân của chủ sở hữu. |
| **Customer Experience** (Trải nghiệm khách hàng) | 3.0/10 | Trải nghiệm kém vì khách hàng không tìm thấy thông tin thực tế về dự án, năng lực hay cách thức liên hệ của tác giả. |

**Tổng điểm UX: 4.9/10**

---

## 3. Điểm mạnh
- **Giao diện tối giản, sạch sẽ:** Layout thừa hưởng từ template có thiết kế gọn gàng, sử dụng font Roboto dễ đọc và khoảng trắng (white space) hợp lý.
- **Tốc độ tải trang nhanh:** Nhờ sử dụng trang tĩnh (GitHub Pages) không có các mã JavaScript nặng hay database phức tạp.
- **Có đầy đủ các trang chức năng cốt lõi:** Home, About, Blog, Contact (mặc dù nội dung chưa hoàn thiện).

---

## 4. Vấn đề phát hiện

| Hạng mục | Vấn đề | Severity | Priority | Heuristic | Root Cause | Impact |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **Content & Trust** | Trang **About** và **Style Guide** chứa toàn bộ văn bản giả lập (Lorem Ipsum Hipster: *"Copper mug fam food truck..."*). | **Critical** | **P1** | Match Between System and Real World / Help & Documentation | Content | Làm giảm hoàn toàn sự tin cậy của website. Khách hàng/Nhà tuyển dụng không có thông tin thực tế về tác giả. |
| **Consistency** | Không nhất quán danh tính: Tên trang là **Uoc Nguyen** nhưng nội dung giới thiệu ở trang About lại là **Alex Rodriguez**. | **Critical** | **P1** | Consistency and Standards | Content | Gây hoang mang về mặt nhận diện thương hiệu cá nhân, tạo cảm giác thiếu chuyên nghiệp. |
| **Navigation** | Liên kết **"Resources"** trên menu dẫn đến trang lỗi 404 (do sai định dạng đường dẫn `/blog/tag/Resources` viết hoa). | **High** | **P1** | Error Prevention / User Control & Freedom | Design / Technology | Gây đứt gãy trải nghiệm điều hướng của người dùng, tạo ấn tượng sản phẩm bị lỗi kỹ thuật. |
| **System Status** | Thông tin lỗi thời: Các bài viết blog từ năm 2018, bản quyền footer ghi năm **2021/2022** trong khi hiện tại là năm **2026**. | **High** | **P1** | Visibility of System Status | Content | Tạo cảm giác website đã ngừng hoạt động hoặc bị bỏ hoang từ lâu. |
| **Navigation** | Các icon mạng xã hội ở footer trỏ về các liên kết rác hoặc placeholder mặc định của theme (`{url}`). | **High** | **P2** | Match Between System and Real World | Design | Không thể kết nối với tác giả qua các kênh mạng xã hội, mất cơ hội chuyển đổi (Conversion). |
| **SEO & Meta** | Thẻ meta description và cấu trúc SEO vẫn giữ cấu hình mặc định của theme, chưa tối ưu từ khóa cá nhân. | **Medium** | **P2** | Help and Documentation | Content | Trang web khó xuất hiện trên kết quả tìm kiếm khi tìm kiếm tên của tác giả. |

---

## 5. Đề xuất cải tiến

| Giải pháp | Impact | Effort | Priority |
| :--- | :--- | :--- | :--- |
| **Thay thế toàn bộ nội dung giả:** Cập nhật thông tin giới thiệu chính xác của tác giả Uoc Nguyen (vị trí, kinh nghiệm, kỹ năng) thay thế cho Alex Rodriguez. | **Critical** | **Low** | **P1** |
| **Sửa link hỏng (404):** Điều chỉnh liên kết "Resources" trên menu trỏ đúng đường dẫn viết thường `/blog/tag/resources` hoặc ẩn đi nếu chưa có bài viết. | **High** | **Low** | **P1** |
| **Cập nhật năm bản quyền và bài viết:** Sửa footer thành `Copyright © 2026` và cập nhật tối thiểu 1-2 bài viết hoặc dự án mới nhất. | **High** | **Low** | **P1** |
| **Cập nhật liên kết mạng xã hội:** Điền link thật của các tài khoản Twitter, Dribbble, LinkedIn, Facebook của tác giả vào phần cấu hình theme. | **High** | **Low** | **P2** |
| **Ẩn trang Style Guide:** Nếu không cần thiết giới thiệu bộ quy chuẩn giao diện, nên ẩn trang này khỏi menu chính để tránh gây nhiễu thông tin. | **Medium** | **Low** | **P2** |
| **Tối ưu SEO cá nhân:** Cấu hình lại file `_config.yml` để cập nhật mô tả chính xác về năng lực, từ khóa tìm kiếm (SEO title, description). | **Medium** | **Low** | **P2** |

---

## 6. Kết quả mong đợi
- **Tăng tính chuyên nghiệp:** Khách hàng và nhà tuyển dụng có góc nhìn tích cực, tin cậy về năng lực chuyên môn của một Frontend & UI/UX Designer.
- **Trải nghiệm mượt mà:** Không còn các trang lỗi 404 hay liên kết rác hướng người dùng ra ngoài hệ thống một cách vô nghĩa.
- **Tối ưu hóa chuyển đổi:** Giúp người xem dễ dàng liên hệ hoặc xem các dự án thực tế thông qua các kênh liên kết chuẩn xác.

---

## 7. Roadmap

### P1: Triển khai ngay (Trong vòng 1-2 ngày)
- Thay đổi thông tin cá nhân trên trang About (thay thế văn bản placeholder).
- Sửa lỗi đường dẫn 404 của mục "Resources" và cập nhật năm bản quyền ở Footer.

### P2: Ngắn hạn (Trong vòng 1 tuần)
- Cập nhật đúng các liên kết mạng xã hội cá nhân.
- Ẩn hoặc tối ưu hóa trang Style Guide để chỉ hiển thị các thành phần thiết kế thực sự của tác giả.
- Tối ưu hóa file cấu hình SEO (`_config.yml`).

### P3: Dài hạn (Cải tiến liên tục)
- Cập nhật các bài viết blog chuyên ngành và các dự án thiết kế/lập trình thực tế đã thực hiện.
