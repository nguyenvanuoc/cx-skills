# Báo cáo Đánh giá Trải nghiệm Người dùng (UX Audit) - VNPT SmartCA: Cấp bù Chứng thư số

- **Sản phẩm:** VNPT SmartCA (Màn hình thông báo / Pop-up Cấp bù chứng thư số)
- **Ngày đánh giá:** 22/06/2026
- **Phương pháp:** Heuristic Evaluation (Nielsen's 10 Heuristics) & UX/UI Mobile Review
- **Dựa trên tài liệu gốc:** [cx.md](file:///Volumes/CHAOS/VNPT/AI/CX/.agent/skills/cx.md)

---

## 1. Tổng quan đánh giá
Màn hình "Cấp bù chứng thư số" xuất hiện dưới dạng một Pop-up/Bottom sheet trên ứng dụng di động VNPT SmartCA. Tác vụ này nhằm hỗ trợ người dùng cập nhật thời hạn hiệu lực của các chứng thư số cá nhân bị ảnh hưởng bởi việc thay đổi thời hạn chứng thư số gốc của nhà cung cấp dịch vụ CA (tuân thủ Nghị định số 23/2025/NĐ-CP). 

Đây là một tác vụ hành chính bắt buộc và có ảnh hưởng trực tiếp đến khả năng tiếp tục sử dụng dịch vụ ký số của khách hàng. Giao diện hiện tại đã cung cấp đầy đủ thông tin về tình trạng và các mốc thời gian. Tuy nhiên, luồng tương tác đa chứng thư số vẫn còn điểm mập mờ, cách trình bày dữ liệu kỹ thuật chưa được tối ưu hóa cho thiết bị di động và nội dung giải thích còn mang tính kỹ thuật/pháp lý khô khan đối với người dùng phổ thông.

---

## 2. Điểm UX tổng thể

| Hạng mục | Điểm | Nhận xét nhanh |
| :--- | :---: | :--- |
| **Usability** (Khả năng sử dụng) | 7.0/10 | Bố cục pop-up rõ ràng, các thông số đối chiếu đầy đủ. Tuy nhiên, phạm vi tác vụ của nút bấm chính chưa rõ ràng. |
| **Accessibility** (Khả năng tiếp cận) | 7.5/10 | Độ tương phản màu sắc tốt, đặc biệt ở các mốc ngày hết hạn mới (màu xanh đậm) và cảnh báo (màu đỏ). Tuy nhiên, nút điều hướng carousel có kích thước chạm nhỏ. |
| **Navigation** (Điều hướng) | 6.5/10 | Có hỗ trợ xem danh sách qua nút chuyển `< >`, nhưng thiếu chỉ báo tiến trình trực quan và việc thoát pop-up quá dễ dàng đối với một tác vụ quan trọng. |
| **Visual Design** (Thiết kế trực quan) | 7.0/10 | Giao diện sạch sẽ, gọn gàng, mang đậm nhận diện VNPT. Điểm trừ là hiển thị mã Serial dài bị rớt dòng tự do trông thiếu chỉn chu. |
| **Customer Experience** (Trải nghiệm khách hàng) | 6.8/10 | Có phần giải thích lý do để minh bạch hóa quy trình, nhưng ngôn từ quá nặng tính học thuật pháp lý, dễ gây bối rối và hoang mang về chi phí phát sinh. |

**Tổng điểm UX: 7.0/10** (Đạt mức Khá, cần tối ưu các chi tiết tương tác nhỏ để nâng cao trải nghiệm).

---

## 3. Điểm mạnh
- **Thông tin đối chiếu rõ ràng:** Việc hiển thị song song "Ngày hết hạn" hiện tại (18/11/2026) và "Ngày hết hạn mới" (02/01/2027) bằng định dạng in đậm màu xanh giúp người dùng nhanh chóng nhận thấy giá trị lợi ích của việc cấp bù (được gia hạn thêm thời gian sử dụng miễn phí).
- **Tạo tính cấp bách tốt (Urgency):** Dòng cảnh báo màu đỏ *"Vui lòng thực hiện cấp bù trước ngày 18/11/2026"* đặt ngay trên nút hành động thu hút sự chú ý tốt, thúc giục người dùng thực hiện ngay để tránh gián đoạn dịch vụ.
- **Có hộp thông tin chỉ dẫn (Transparency):** Phần "Lý do cấp bù" được thiết kế dưới dạng hộp màu xanh nhạt nổi bật giúp người dùng hiểu tại sao hệ thống lại yêu cầu họ thực hiện thao tác này.
- **Call-to-Action (CTA) rõ ràng:** Nút "Cấp bù ngay" dạng bo góc, kích thước lớn và màu xanh thương hiệu tạo sự nhận diện hành động rất rõ ràng.

---

## 4. Vấn đề phát hiện

| Hạng mục | Vấn đề | Severity | Priority | Heuristic | Root Cause | Impact |
| :--- | :--- | :---: | :---: | :--- | :--- | :--- |
| **Usability & User Control** | **Mơ hồ về phạm vi tác vụ:** Hệ thống báo có 3 chứng thư cần cấp bù và đang hiển thị "Chứng thư số 2". Người dùng không rõ khi click "Cấp bù ngay" thì hệ thống sẽ thực hiện cho riêng chứng thư số 2 hay cho cả 3 chứng thư cùng lúc. | **High** | **P1** | User Control and Freedom / Recognition Rather Than Recall | Design / Process | - Nếu chỉ cấp bù cho chứng thư số 2, người dùng phải lặp lại quy trình 3 lần (gây mệt mỏi).<br>- Nếu cấp bù cho cả 3, việc chỉ hiển thị thông tin của chứng thư số 2 làm người dùng bối rối.<br>- Người dùng có thể lầm tưởng bấm 1 lần là xong toàn bộ, dẫn đến bỏ sót các chứng thư khác. |
| **Usability & Interaction** | **Nút điều hướng Carousel khó tương tác:** Hai nút mũi tên trái `<` và phải `>` có diện tích bấm nhỏ (touch target < 48x48dp), nằm khá xa nhau và có màu xám mờ nhạt. | **Medium** | **P2** | Flexibility and Efficiency of Use | Design | Người dùng sử dụng thiết bị bằng một tay khó thao tác chuyển đổi qua lại giữa các chứng thư số, dễ bấm trượt. |
| **Content & Language** | **Nội dung lý do quá phức tạp:** Khối văn bản giải thích lý do sử dụng quá nhiều thuật ngữ chuyên môn hành chính (`Nghị định số 23/2025/NĐ-CP`, `Chứng thư số gốc của nhà Cung cấp dịch vụ CA`, `thực hiện cấp bù thời gian`). | **Medium** | **P2** | Match Between System and Real World | Content | Người dùng phổ thông không hiểu bản chất kỹ thuật, dễ hoang mang lo ngại bị phát sinh chi phí hoặc thủ tục phức tạp, dẫn đến thoát luồng. |
| **Error Prevention** | **Thiếu cơ chế xác nhận khi tắt pop-up:** Nút (X) đóng pop-up nằm ở góc trên bên phải rất dễ bấm nhầm, cho phép thoát ngay mà không đưa ra cảnh báo về hậu quả của việc không cấp bù. | **Medium** | **P2** | Error Prevention | Process | Người dùng dễ vô tình đóng pop-up và quên mất tác vụ, dẫn đến việc chứng thư số bị hết hạn sau này và không thể ký số tài liệu. |
| **Visual Design** | **Hiển thị Serial bị lỗi bẻ dòng:** Chuỗi Serial dài `54010101135423e20652ff93f110b37` bị rớt dòng tự do một cách cẩu thả thành 2 dòng làm mất thẩm mỹ. Ngoài ra, thiếu nút copy nhanh. | **Low** | **P3** | Aesthetic and Minimalist Design | Code / Design | Tạo cảm giác giao diện kém chỉn chu. Người dùng cũng không thể sao chép nhanh mã serial này khi cần đối chiếu hoặc nhờ nhân viên kỹ thuật hỗ trợ. |

---

## 5. Đề xuất cải tiến

| Giải pháp | Impact | Effort | Priority |
| :--- | :---: | :---: | :---: |
| **Tối ưu hóa quy trình đa chứng thư số:**<br>- Nếu hệ thống hỗ trợ: Hãy tự động gộp cả 3 chứng thư số để cấp bù trong 1 lần ký duy nhất, thay đổi nhãn nút thành *"Cấp bù cả 3 chứng thư số"*.<br>- Nếu bắt buộc ký từng chứng thư: Thay đổi nhãn nút rõ ràng theo ngữ cảnh *"Cấp bù Chứng thư số 2"*. Sau khi ký thành công chứng thư này, tự động chuyển sang chứng thư tiếp theo kèm thanh tiến trình dạng bước (ví dụ: *Bước 2/3* hoặc dấu tick xanh hoàn thành). | **High** | **Medium** | **P1** |
| **Đơn giản hóa nội dung giải thích:**<br>Chuyển ngôn từ kỹ thuật sang ngôn ngữ hướng người dùng. Ví dụ: *"VNPT đã cập nhật hệ thống Chứng thư số gốc để tăng cường tính bảo mật. VNPT sẽ tiến hành gia hạn bổ sung hoàn toàn **MIỄN PHÍ** thời gian sử dụng tương ứng với gói cước quý khách đã mua để tránh gián đoạn dịch vụ."* (Các thông tin pháp lý/Nghị định có thể ẩn dưới link *"Xem chi tiết"*). | **High** | **Low** | **P1** |
| **Thêm cảnh báo khi đóng pop-up (Error Prevention):**<br>Nếu người dùng nhấn nút (X) hoặc chạm ra ngoài để đóng pop-up khi chưa hoàn thành tác vụ cấp bù, hiển thị một hộp thoại xác nhận ngắn: *"Bạn có chắc chắn muốn bỏ qua? Nếu không cấp bù trước ngày 18/11/2026, chứng thư số của bạn sẽ không thể thực hiện ký số tài liệu."* với 2 nút: *"Để sau"* và *"Cấp bù ngay"*. | **High** | **Low** | **P2** |
| **Cải tiến Carousel điều hướng:**<br>Tăng kích thước vùng bấm (touch target) của nút `<` và `>` lên ít nhất 48x48dp. Đồng thời hỗ trợ thao tác vuốt ngang (horizontal swipe) trên vùng thông tin chứng thư số để người dùng dễ dàng chuyển đổi nhanh. | **Medium** | **Low** | **P2** |
| **Định dạng lại Serial & Thêm tính năng sao chép:**<br>Hiển thị rút gọn chuỗi Serial dài ở giữa (ví dụ: `540101...93f110b37`) hoặc chia nhóm ký tự để dễ đọc. Bổ sung một biểu tượng sao chép (copy icon) nhỏ ngay bên cạnh để người dùng có thể sao chép nhanh chuỗi serial khi cần. | **Medium** | **Low** | **P3** |

---

## 6. Kết quả mong đợi
- **Tăng tỷ lệ hoàn thành tác vụ (Task Success Rate):** Khách hàng chủ động cấp bù ngay nhờ hiểu rõ lợi ích (miễn phí, gia hạn thêm thời gian) và lý do đơn giản.
- **Giảm tỷ lệ bỏ sót chứng thư số:** Hạn chế tình trạng người dùng chỉ cấp bù 1 chứng thư mà bỏ quên các chứng thư còn lại trong danh sách cần xử lý.
- **Giảm tải cho bộ phận Chăm sóc khách hàng (Customer Support):** Hạn chế tối đa các ca hỗ trợ do chứng thư số bị hết hạn/khóa đột ngột sau ngày 18/11/2026 vì người dùng vô ý đóng pop-up và quên thực hiện.
- **Tăng trải nghiệm chỉn chu (Visual & Usability Satisfaction):** Giao diện chuyên nghiệp, các yếu tố điều hướng mượt mà nâng cao hình ảnh uy tín của một ứng dụng chứng thực chữ ký số quốc gia.

---

## 7. Lộ trình thực hiện (Roadmap)

### P1: Triển khai ngay (Sprint hiện tại)
- Đơn giản hóa văn bản "Lý do cấp bù", làm nổi bật cụm từ **MIỄN PHÍ** để loại bỏ e ngại của khách hàng.
- Điều chỉnh nhãn nút và luồng xử lý đa chứng thư số (hoặc cấp bù tất cả, hoặc hiển thị tiến độ 1/3, 2/3 rõ ràng).

### P2: Ngắn hạn (Sprint tiếp theo)
- Bổ sung hộp thoại cảnh báo xác nhận khi người dùng cố gắng tắt pop-up mà chưa thực hiện cấp bù.
- Cải tiến kích thước nút điều hướng Carousel và hỗ trợ cử chỉ vuốt ngang chuyển đổi nhanh.

### P3: Dài hạn (Cải tiến sản phẩm)
- Định dạng rút gọn mã Serial và tích hợp nút copy nhanh.
- Xem xét nghiên cứu luồng tự động cấp bù ngầm (silent renewal) từ phía máy chủ mà không cần sự can thiệp thủ công từ người dùng (nếu quy định pháp lý và cấu trúc khóa của VNPT SmartCA cho phép trong tương lai).
