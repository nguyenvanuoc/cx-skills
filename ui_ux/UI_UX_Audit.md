---
name: ui-ux-quality-audit
description: Bộ Skill đánh giá chất lượng UI/UX từ ảnh chụp màn hình hoặc mô tả sản phẩm, sử dụng thư viện checklist UI, thư viện checklist UX và công thức chấm điểm thống nhất.
version: 1.0.0
language: vi
---

# UI/UX Quality Audit Skill

## 1. Mục đích

Bộ Skill này dùng để thực hiện đánh giá chất lượng giao diện và trải nghiệm người dùng theo 3 thành phần:

1. **UI Checklist Library** — thư viện tiêu chí kiểm tra giao diện.
2. **UX Checklist Library** — thư viện tiêu chí kiểm tra trải nghiệm người dùng.
3. **Scoring Formula** — công thức tính điểm checklist, điểm issue, điểm UI/UX và điểm Experience Quality.

## 2. Quy trình sử dụng

### Bước 1 — Xác định phạm vi

- Xác định sản phẩm, màn hình, nền tảng và trạng thái cần đánh giá.
- Phân biệt phạm vi UI, UX hoặc đánh giá tổng hợp UI/UX.
- Không tự suy đoán các trạng thái không xuất hiện trong nguồn đánh giá.

### Bước 2 — Chọn checklist

- Chọn các checklist UI phù hợp từ `UI_Checklist.md`.
- Chọn các checklist UX phù hợp từ `UX_Checklist.md`.
- Chỉ tính các checklist có trạng thái **Applicable**.
- Ghi rõ các checklist **Not Applicable** và lý do loại trừ.

### Bước 3 — Đánh giá từng tiêu chí

Mỗi checklist cần có:

- ID checklist
- Trạng thái: PASS / FAIL / N/A / UNKNOWN
- Bằng chứng quan sát được
- Mô tả vấn đề nếu FAIL
- Severity nếu có vấn đề
- Khuyến nghị cải thiện
- Tham chiếu tiêu chuẩn/cơ sở liên quan nếu có

Không đánh dấu PASS nếu chưa có đủ bằng chứng.

### Bước 4 — Phân loại issue

Sử dụng mức độ nghiêm trọng:

- **Minor = 1**
- **Major = 3**
- **Critical = 5**

Critical hoặc các lỗi bắt buộc phải được nêu riêng, không để điểm tổng che khuất.

### Bước 5 — Tính điểm

Sử dụng chính xác công thức trong `Scoring_Formula.md`.

### Bước 6 — Xuất báo cáo

Báo cáo cần có:

1. Executive Summary
2. Phạm vi và giả định
3. Tổng quan điểm số
4. Checklist PASS/FAIL/N/A
5. Danh sách issue theo Severity
6. Critical findings / Mandatory Gate
7. Khuyến nghị ưu tiên
8. Roadmap cải thiện
9. Phụ lục bằng chứng

## 3. Quy tắc chất lượng

- Không tự tạo checklist ngoài thư viện nếu người dùng yêu cầu đánh giá theo bộ checklist này.
- Không tự thay đổi trọng số hoặc công thức.
- Không tính trung bình đơn giản giữa các màn hình nếu số checklist áp dụng khác nhau; ưu tiên tổng hợp từ dữ liệu gốc theo công thức.
- Tách rõ **điểm số** và **nhận định chuyên môn**.
- Nếu thiếu ảnh, thiếu trạng thái hoặc thiếu dữ liệu, phải ghi rõ là **UNKNOWN** thay vì suy đoán.
- Mọi issue phải có bằng chứng hoặc chỉ rõ giới hạn bằng chứng.
- Khuyến nghị phải gắn với issue/checklist cụ thể.

## 4. Tệp thành phần

- `UI_Checklist.md`
- `UX_Checklist.md`
- `Scoring_Formula.md`

## 5. Cách gọi bộ Skill

Khi người dùng yêu cầu audit UI/UX, hãy:

1. Đọc `UI_Checklist.md` nếu có phạm vi UI.
2. Đọc `UX_Checklist.md` nếu có phạm vi UX.
3. Đọc `Scoring_Formula.md` trước khi tính điểm.
4. Trả về bảng checklist, issue log, điểm số và roadmap.
5. Nêu rõ dữ liệu nào được quan sát trực tiếp, dữ liệu nào chưa đủ và dữ liệu nào là giả định.

Trình bày dưới dạng bảng và tạo 1 file log  lưu vào thư mục `output` với `[tên-sản-phẩm]-cx-[YYYY-MM-DD].md`

## 6. Cấu trúc file đầu ra theo workbook Tổng Hợp

### Bảng: Kết quả đầu ra
Khi kiểm tra màn hình phải sắp xếp theo đúng thứ tự kiểm tra từ trên xuống dưới, từ trái qua phải.

Các cột bắt buộc theo đúng thứ tự:

1. Issue ID
2. Phân loại(UI/UX)
3. Mã checklist
4. Tên luồng
5. Chức năng
6. Bước thao tác
7. Thiết bị
8. Mức độ ảnh hưởng
9. Hình ảnh
10. Vấn đề
11. Đề xuất giải pháp
12. Hiệu quả sau cải tiến
13. Xếp loại Issue
14. Xếp loại Checklist
15. Effort
16. Urgency
17. Priority points

Chỉ tạo issue khi checklist có trạng thái `FAIL`. Trạng thái `UNKNOWN` không được chuyển thành `PASS`.

### Bảng: Improverment Roadmap

Roadmap được tạo bằng cách lọc các dòng `Xếp loại Issue = Fail` từ sheet `Kết quả đầu ra`, sau đó ánh xạ theo đúng thứ tự:

1. Issue ID
2. Phân loại(UI/UX)
3. Mã checklist
4. Chức năng
5. Bước thao tác
6. Thiết bị
7. Mức độ ảnh hưởng
8. Hình ảnh
9. Vấn đề
10. Đề xuất giải pháp
11. Hiệu quả sau cải tiến
12. Priority

Roadmap phải giữ nguyên Issue ID, không tạo ID mới. Sắp xếp theo `P1 → P2 → P3 → P4`, trong đó Critical + High bắt buộc là `P1`.

### Quy tắc Priority

- Minor = 1
- Major = 3
- Critical = 5
- Urgency: Low=1, Medium=2, High=3
- Effort: Thấp=1, Trung bình=2, Cao=3, Rất cao=4
- Priority points = Impact × Urgency weight / Effort weight
- Critical + High → P1
- Priority points >= 5 → P1
- Priority points >= 2 → P2
- Priority points >= 1 → P3
- Còn lại → P4

