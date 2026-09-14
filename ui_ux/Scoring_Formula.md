---
name: ui-ux-scoring-formula
description: Skill tính điểm chất lượng UI/UX từ dữ liệu checklist và issue theo công thức trong UI_UX_Experience_Quality_Scorecard.docx. Dùng để tính Checklist Score, Issue Score, UI Quality Score, UX Quality Score, Experience Quality Score và System Score.
---

# UI/UX Scoring Formula Skill

## 1. Mục tiêu

Tính điểm chất lượng UI/UX dựa trên dữ liệu audit:

- Tổng checklist áp dụng.
- Số checklist FAIL.
- Số issue theo Severity.
- Issue Penalty.
- Điểm UI.
- Điểm UX.
- Điểm Experience tổng thể.
- Dữ liệu nhiều màn hình để tính System Score.

Nguồn công thức chuẩn:

`UI_UX_Experience_Quality_Scorecard.docx`

Không tự ý thay đổi công thức nếu người dùng chưa yêu cầu.

## 2. Quy tắc dữ liệu

### Checklist

Mỗi checklist có một trong các trạng thái:

- PASS
- FAIL
- N/A
- NEEDS VALIDATION

Quy tắc:

- Chỉ checklist áp dụng mới được tính vào mẫu số.
- N/A không tính vào mẫu số.
- Checklist FAIL được tính là một checklist FAIL, dù checklist có nhiều issue.
- Một checklist có nhiều issue vẫn chỉ tính một lần vào số checklist FAIL.
- NEEDS VALIDATION phải báo cáo riêng. Không tự động chuyển thành FAIL nếu chưa có bằng chứng.

### Issue

Mỗi issue có:

- Issue ID.
- Checklist ID.
- Type: UI hoặc UX.
- Severity: Minor / Major / Critical.
- Priority: P0 / P1 / P2 / P3.
- Vấn đề.
- Giải pháp đề xuất.

Một checklist có thể có nhiều issue.

## 3. Severity Weight

| Severity | Weight | Ý nghĩa |
|---|---:|---|
| Minor | 1 | Lỗi nhỏ, ảnh hưởng hạn chế đến visual, consistency hoặc polish |
| Major | 3 | Ảnh hưởng đáng kể đến UI/UX, thao tác hoặc hiệu quả thực hiện task |
| Critical | 5 | Lỗi nghiêm trọng, có thể chặn task, gây hiểu sai lớn hoặc vi phạm yêu cầu bắt buộc/accessibility |

Severity Weight là trọng số phạt, không phải điểm chất lượng.

## 4. Công thức Checklist Compliance Score

```text
Checklist Compliance Score =
(Tổng checklist áp dụng − Số checklist FAIL)
 / Tổng checklist áp dụng × 100
```

Trong đó:

```text
Tổng checklist áp dụng =
PASS + FAIL
```

Không đưa N/A vào mẫu số.

Ví dụ:

```text
Tổng checklist áp dụng = 20
Checklist FAIL = 4

Checklist Score =
(20 − 4) / 20 × 100
= 80
```

## 5. Công thức Issue Penalty

```text
Issue Penalty =
Σ(Số issue theo Severity × Severity Weight)
```

Chi tiết:

```text
Issue Penalty =
(Số Minor × 1)
+ (Số Major × 3)
+ (Số Critical × 5)
```

Ví dụ:

```text
Minor = 3
Major = 1
Critical = 1

Issue Penalty =
(3 × 1) + (1 × 3) + (1 × 5)
= 11
```

## 6. Công thức Issue Score

```text
Issue Score =
MAX(0, 100 ×
(1 − Issue Penalty /
(Tổng checklist áp dụng × 5)))
```

Số 5 là Severity Weight tối đa của Critical.

Ví dụ:

```text
Tổng checklist áp dụng = 20
Issue Penalty = 11

Issue Score =
MAX(0, 100 × (1 − 11 / (20 × 5)))
= 89
```

Luôn giới hạn điểm thấp nhất là 0.

## 7. Công thức UI/UX Quality Score

```text
UI/UX Quality Score =
Checklist Score × 70%
+ Issue Score × 30%
```

Tính riêng:

```text
UI Quality Score =
UI Checklist Score × 70%
+ UI Issue Score × 30%

UX Quality Score =
UX Checklist Score × 70%
+ UX Issue Score × 30%
```

Ví dụ UI:

```text
UI Checklist Score = 80
UI Issue Score = 89

UI Quality Score =
80 × 70% + 89 × 30%
= 82.7 / 100
```

Ví dụ UX:

```text
UX Checklist Score = 70
UX Issue Score = 86

UX Quality Score =
70 × 70% + 86 × 30%
= 74.8 / 100
```

## 8. Công thức Experience Quality Score

```text
Experience Quality Score =
UI Score × 40%
+ UX Score × 60%
```

Ví dụ:

```text
UI Score = 82.7
UX Score = 74.8

Experience Quality Score =
82.7 × 40% + 74.8 × 60%
= 78.0 / 100
```

UI có trọng số 40%, UX có trọng số 60%.

Nếu chỉ có UI hoặc chỉ có UX:

- Không tự tạo điểm Experience đầy đủ.
- Ghi `N/A — thiếu điểm UI hoặc UX`.
- Báo cáo phần còn thiếu.

## 9. System Score cho nhiều màn hình

Không chỉ lấy trung bình điểm màn hình khi số checklist áp dụng giữa các màn hình khác nhau.

### System Checklist Score

```text
System Checklist Score =
(Tổng checklist áp dụng − Tổng checklist FAIL)
 / Tổng checklist áp dụng × 100
```

### System Issue Score

```text
System Issue Score =
MAX(0, 100 ×
(1 − Tổng Issue Penalty /
(Tổng checklist áp dụng × 5)))
```

### System UI/UX Score

```text
System UI/UX Score =
System Checklist Score × 70%
+ System Issue Score × 30%
```

### System Experience Quality Score

```text
Experience Quality Score =
System UI Score × 40%
+ System UX Score × 60%
```

## 10. Mandatory Gate

Critical issue và checklist bắt buộc không được bị che khuất bởi điểm tổng.

Bảng Gate:

| Gate | Kết quả | Chi tiết |
|---|---|---|
| Có Critical issue | PASS / FAIL | ... |
| Checklist bắt buộc đạt ngưỡng | PASS / FAIL / NEEDS VALIDATION | ... |
| Có issue chặn task | PASS / FAIL | ... |
| Có issue accessibility nghiêm trọng | PASS / FAIL | ... |
| Được xếp hạng Excellent | PASS / FAIL | ... |

Quy tắc:

- Nếu còn Critical issue, không xếp Excellent.
- Nếu checklist bắt buộc chưa đạt ngưỡng, không xếp Excellent.
- Nếu tài liệu chưa cung cấp ngưỡng cụ thể, ghi `Chưa cấu hình ngưỡng`.
- Không tự bịa ngưỡng xếp hạng.

## 11. Bảng output bắt buộc

### Bảng 1 — Score Summary

| Chỉ số | Giá trị |
|---|---:|
| Tổng checklist áp dụng | ... |
| Checklist PASS | ... |
| Checklist FAIL | ... |
| N/A | ... |
| NEEDS VALIDATION | ... |
| Tổng issue | ... |
| Critical | ... |
| Major | ... |
| Minor | ... |
| Issue Penalty | ... |
| Checklist Compliance Score | ... / 100 |
| Issue Score | ... / 100 |
| UI Quality Score | ... / 100 |
| UX Quality Score | ... / 100 |
| Experience Quality Score | ... / 100 |

### Bảng 2 — Calculation Detail

| Chỉ số | Giá trị đầu vào | Công thức | Kết quả |
|---|---|---|---:|
| Checklist Score | ... | ... | ... |
| Issue Penalty | ... | ... | ... |
| Issue Score | ... | ... | ... |
| UI Quality Score | ... | ... | ... |
| UX Quality Score | ... | ... | ... |
| Experience Quality Score | ... | ... | ... |

### Bảng 3 — Severity Summary

| Severity | Weight | Số issue | Penalty |
|---|---:|---:|---:|
| Critical | 5 | ... | ... |
| Major | 3 | ... | ... |
| Minor | 1 | ... | ... |
| Total | | ... | ... |

### Bảng 4 — Mandatory Gate

| Gate | Kết quả | Lý do | Hành động |
|---|---|---|---|
| Critical issue | ... | ... | ... |
| Mandatory checklist | ... | ... | ... |
| Task blocker | ... | ... | ... |
| Accessibility | ... | ... | ... |
| Excellent eligibility | ... | ... | ... |

## 12. Kiểm tra tính đúng đắn

Trước khi trả kết quả:

1. Kiểm tra tổng checklist áp dụng > 0.
2. Kiểm tra số checklist FAIL không lớn hơn tổng checklist áp dụng.
3. Kiểm tra Issue Penalty không âm.
4. Kiểm tra Severity chỉ gồm Minor, Major, Critical.
5. Kiểm tra Checklist Score nằm trong 0–100.
6. Kiểm tra Issue Score nằm trong 0–100.
7. Kiểm tra UI/UX Quality Score nằm trong 0–100.
8. Làm tròn hiển thị 1 chữ số thập phân hoặc 2 chữ số khi người dùng yêu cầu.
9. Không làm tròn các giá trị trung gian trước khi tính tổng.
10. Đối chiếu tổng số issue với bảng Severity Summary.
11. Đối chiếu tổng checklist FAIL với danh sách checklist FAIL.
12. Nếu dữ liệu thiếu, báo rõ dữ liệu cần bổ sung thay vì đoán.

## 13. Ví dụ đầy đủ

Input:

```text
UI:
- Tổng checklist áp dụng: 20
- Checklist FAIL: 4
- Minor: 3
- Major: 1
- Critical: 1

UX:
- Tổng checklist áp dụng: 10
- Checklist FAIL: 3
- Minor: 1
- Major: 2
- Critical: 0
```

Tính UI:

```text
UI Checklist Score = (20 − 4) / 20 × 100 = 80

UI Issue Penalty = 3×1 + 1×3 + 1×5 = 11

UI Issue Score =
100 × (1 − 11 / (20×5)) = 89

UI Quality Score =
80×70% + 89×30% = 82.7
```

Tính UX:

```text
UX Checklist Score = (10 − 3) / 10 × 100 = 70

UX Issue Penalty = 1×1 + 2×3 + 0×5 = 7

UX Issue Score =
100 × (1 − 7 / (10×5)) = 86

UX Quality Score =
70×70% + 86×30% = 74.8
```

Tính Experience:

```text
Experience Quality Score =
82.7×40% + 74.8×60%
= 78.0 / 100
```

## 14. Kết nối với các Skill khác

### UI Checklist Skill

Cung cấp checklist UI và trạng thái PASS / FAIL / N/A / NEEDS VALIDATION.

### UX Checklist Skill

Cung cấp checklist UX và trạng thái PASS / FAIL / N/A / NEEDS VALIDATION.

### UI/UX Audit Skill

Cung cấp issue, Severity, Priority, bằng chứng và giải pháp.

### UI/UX Scoring Formula Skill

Nhận các dữ liệu trên để tính điểm và xuất bảng Calculation.

### Improvement Roadmap

Sử dụng issue và Priority để tạo roadmap cải tiến. Roadmap không được làm thay đổi điểm số đã tính.
