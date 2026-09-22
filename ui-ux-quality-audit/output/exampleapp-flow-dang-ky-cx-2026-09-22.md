# Báo cáo Đánh giá Chất lượng UI/UX & Flow Audit (Flow Quality Audit Report)

- **Sản phẩm:** ExampleApp (Ứng dụng mẫu)
- **Tên luồng (Flow Name):** Đăng ký tài khoản
- **Flow ID:** `FL-DK01`
- **Mục tiêu người dùng (User Goal):** Tạo tài khoản mới để bắt đầu sử dụng dịch vụ
- **Quy mô luồng (Flow Steps):** 5 bước (`S01` → `S02` → `S03` → `S04` → `S05`)
- **Nền tảng / Thiết bị:** Mobile App (iOS / Android Mockup)
- **Thời gian thực hiện:** 22/09/2026
- **Tiêu chuẩn tham chiếu:** VNPT Design System, WCAG 2.2 AA, ISO 9241-161 / ISO 9241-210, NN/g 10 Usability Heuristics, Apple HIG, Material Design 3

---

## 1. Executive Summary

Luồng **Đăng ký tài khoản (FL-DK01)** trên ứng dụng ExampleApp được thiết kế theo mô hình chia nhỏ bước (Chunking / Multi-step Form) gồm 5 màn hình: Bắt đầu từ Đăng nhập (`S01`), Nhập thông tin cá nhân (`S02`), Xác thực OTP điện thoại (`S03`), Thiết lập mật khẩu (`S04`), và Màn hình hoàn tất (`S05`). Giao diện mang phong cách phẳng hiện đại, tinh gọn với tông màu xanh dương chủ đạo, các trường nhập liệu rõ ràng và có hỗ trợ đăng nhập mạng xã hội.

Tuy nhiên, qua quá trình kiểm định chi tiết theo bộ tiêu chí **UI/UX Screen Audit** kết hợp **Flow Audit Integration**, luồng bộc lộ các điểm nghẽn nghiêm trọng về **trải nghiệm xuyên suốt (Cross-screen UX)** và **tính nhất quán điều hướng**:

1. **Thiếu hoàn toàn chỉ báo tiến trình (Missing Progress Stepper - FLI-02):** Toàn bộ 5 bước không có thanh tiến trình (Progress Bar hoặc số bước `1/4, 2/4...`). Người dùng tại bước Nhập thông tin không thể dự đoán được phía sau còn phải xác thực OTP và đặt mật khẩu, dễ gây tâm lý nản lòng (cognitive fatigue) dẫn đến tỷ lệ bỏ dở luồng (drop-off rate) cao.
2. **Hệ thống điều hướng tiến/lùi không nhất quán (Inconsistent Back Navigation - FLI-01):** Bước `S02` (Nhập thông tin) và `S04` (Tạo mật khẩu) hoàn toàn **không có nút Quay lại (Back)**, vô tình tạo thành "bẫy điều hướng" (Navigation Trap). Ngược lại, tại bước `S03` (OTP) lại xuất hiện liên kết `← Quay lại` đặt lơ lửng ngay trên nút bấm chính, vi phạm quy ước đặt nút điều hướng ở Top App Bar theo chuẩn Apple HIG / Material 3.
3. **Phản hồi trạng thái tĩnh sai lệch logic (False Validation Feedback - FLI-03 / ISS-08):** Tại bước `S04` (Tạo mật khẩu), khi hai ô nhập mật khẩu hoàn toàn trống, toàn bộ 4 tiêu chí bảo mật bên dưới đều đã hiển thị dấu tick xanh `✔` (Tối thiểu 8 ký tự, chữ hoa/thường, số, ký tự đặc biệt). Đây là lỗi hiển thị nghiêm trọng, báo hiệu sai trạng thái thành công trước khi người dùng thực hiện thao tác.
4. **Trùng lặp và thừa thãi điều hướng ở Header (Redundant Header Action):** Màn hình `S01` (Đăng nhập) hiển thị nút chữ *"Đăng nhập"* ngay trên góc phải Topbar; màn hình `S02` cũng có nút *"Đăng nhập"* nhưng thiếu nút hủy/quay lại màn hình chào mừng.
5. **Cơ chế phục hồi ngữ cảnh chưa tối ưu (Context Recovery):** Tại bước `S03` (OTP), hệ thống che số điện thoại (`*** *** 123`) nhưng không có nút *"Sửa số điện thoại"* trực tiếp; nếu người dùng nhập sai SĐT ở `S02`, họ buộc phải tìm cách quay lại mà không rõ thông tin đã nhập trước đó có bị xóa sạch hay không.

---

## 2. Tổng quan điểm số (Score Summary)

### Bảng 1 — Score Summary (Toàn bộ Luồng & Màn hình)

| Chỉ số | Giá trị UI | Giá trị UX | Toàn hệ thống / Tổng hợp |
|---|---:|---:|---:|
| **Tổng checklist áp dụng (Tích lũy 5 màn hình)** | 88 | 84 | 172 |
| **Checklist PASS** | 81 | 74 | 155 |
| **Checklist FAIL** | 7 | 10 | 17 |
| **Checklist N/A** | 317 | 1346 | 1663 |
| **Checklist NEEDS VALIDATION** | 10 | 14 | 24 |
| **Tổng số Issue phát hiện** | **7 (Screen UI)** | **10 (Screen UX)** | **17 Screen + 5 Flow Issues** |
| - Critical (Trọng số 5) | 0 | 0 | 0 |
| - Major (Trọng số 3) | 3 | 5 | 8 (+ 3 Flow Major) |
| - Minor (Trọng số 1) | 4 | 5 | 9 (+ 2 Flow Minor) |
| **Issue Penalty** | 13 | 20 | 33 |
| **Checklist Compliance Score** | **92.0 / 100** | **88.1 / 100** | **90.1 / 100** |
| **Issue Score** | **97.0 / 100** | **95.2 / 100** | **96.2 / 100** |
| **UI Quality Score trung bình** | **93.5 / 100** | — | — |
| **UX Quality Score trung bình** | — | **90.2 / 100** | — |
| **Screen Coverage Score (Độ bao phủ trải nghiệm)** | — | — | **91.5 / 100** |

---

### Bảng 2 — Calculation Detail

| Chỉ số | Giá trị đầu vào | Công thức tính toán | Kết quả |
|---|---|---|---:|
| **UI Checklist Score** | Áp dụng: 88, FAIL: 7 | `(88 - 7) / 88 * 100` | **92.0** |
| **UI Issue Penalty** | Minor: 4, Major: 3, Critical: 0 | `4*1 + 3*3 + 0*5` | **13** |
| **UI Issue Score** | Áp dụng: 88, Penalty: 13 | `100 * (1 - 13 / (88 * 5))` | **97.0** |
| **UI Quality Score** | CL Score: 92.0, Issue Score: 97.0 | `92.0 * 70% + 97.0 * 30%` | **93.5** |
| **UX Checklist Score** | Áp dụng: 84, FAIL: 10 | `(84 - 10) / 84 * 100` | **88.1** |
| **UX Issue Penalty** | Minor: 5, Major: 5, Critical: 0 | `5*1 + 5*3 + 0*5` | **20** |
| **UX Issue Score** | Áp dụng: 84, Penalty: 20 | `100 * (1 - 20 / (84 * 5))` | **95.2** |
| **UX Quality Score** | CL Score: 88.1, Issue Score: 95.2 | `88.1 * 70% + 95.2 * 30%` | **90.2** |
| **Screen Coverage Score** | UI: 93.5, UX: 90.2 | `93.5 * 40% + 90.2 * 60%` | **91.5 / 100** |

---

### Bảng 3 — Severity Summary

| Severity | Weight | Số issue UI | Số issue UX | Flow Issue | Tổng Issue | Penalty UI | Penalty UX | Tổng Penalty |
|---|---:|---:|---:|---:|---:|---:|---:|---:|
| **Critical** | 5 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |
| **Major** | 3 | 3 | 5 | 3 | 11 | 9 | 15 | 24 |
| **Minor** | 1 | 4 | 5 | 2 | 11 | 4 | 5 | 9 |
| **Tổng cộng** | | **7** | **10** | **5** | **22** | **13** | **20** | **33** |

---

### Bảng 4 — Mandatory Gate

| Gate | Kết quả | Lý do | Hành động bắt buộc |
|---|---|---|---|
| **Critical issue** | ✅ **PASS** | Không có Critical Issue chặn đứng luồng đăng ký | Duy trì luồng logic |
| **Mandatory checklist** | ⚠️ **NEEDS VALIDATION** | Cần kiểm tra thực tế bàn phím số bật tự động ở OTP (`keyboardType="number-pad"`), cơ chế autofocus và paste mã OTP | Thực hiện kiểm thử trên thiết bị thật |
| **Task blocker** | ❌ **FAIL** | Bước S04 bẫy điều hướng không có nút quay lại; S04 tick xanh sẵn dù chưa nhập mật khẩu | Bổ sung nút Back và sửa logic validation mật khẩu |
| **Accessibility (WCAG AA)** | ⚠️ **CẢNH BÁO** | Bước OTP các ô vuông cần có thẻ input ẩn hỗ trợ Screen Reader; nhãn điều khoản cần checkbox rõ ràng | Bổ sung aria-label và tối ưu checkbox đồng ý xử lý dữ liệu |
| **Excellent eligibility** | ❌ **FAIL** | Chưa đủ điều kiện xếp loại Excellent do thiếu Stepper xuyên suốt và lỗi điều hướng | Khắc phục các issue P1 & P2 |

---

## 3. Đánh giá chi tiết Luồng (Flow Evaluation)

### 3.1. Bảng Flow Summary

| Flow ID | Tên luồng | User Goal | Số bước | Số Screen | Screen được audit | Screen Coverage Score | Critical | Major | Minor | Needs Validation |
|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| **FL-DK01** | Đăng ký tài khoản | Tạo tài khoản cá nhân mới | 5 | 5 | 5 (100%) | **91.5 / 100** | 0 | 3 | 2 | 2 |

---

### 3.2. Bảng Screen Audit trong Flow

| Flow ID | Step | Screen ID | Tên màn hình | UI Score | UX Score | Experience Score | FAIL | Critical | Major | Minor |
|---|---:|---|---|---:|---:|---:|---:|---:|---:|---:|
| FL-DK01 | 1 | `S01` | Đăng nhập (Entry Point) | 94.2 | 91.5 | **92.6** | 2 | 0 | 0 | 2 |
| FL-DK01 | 2 | `S02` | Nhập thông tin cá nhân | 91.0 | 87.8 | **89.1** | 4 | 0 | 2 | 2 |
| FL-DK01 | 3 | `S03` | Xác thực số điện thoại (OTP) | 90.5 | 86.4 | **88.0** | 4 | 0 | 2 | 2 |
| FL-DK01 | 4 | `S04` | Tạo mật khẩu mới | 89.2 | 85.0 | **86.7** | 4 | 0 | 2 | 2 |
| FL-DK01 | 5 | `S05` | Đăng ký thành công (Hoàn tất)| 98.0 | 95.5 | **96.5** | 3 | 0 | 0 | 1 |

---

### 3.3. Bảng Flow Analysis (Phân tích xuyên màn hình)

| Flow ID | Nhóm phân tích | Step / Transition | Trạng thái | Bằng chứng quan sát được | Flow Issue ID |
|---|---|---|---|---|---|
| FL-DK01 | **Sequence & Progress** | S02 → S03 → S04 | ❌ **FAIL** | Người dùng trải qua 3 màn hình nhập liệu liên tiếp nhưng không có thanh tiến trình (Stepper / Progress Bar) báo hiệu số bước còn lại. | **FLI-02** |
| FL-DK01 | **Navigation** | S01 → S02 → S03 → S04 | ❌ **FAIL** | S02 và S04 không có nút Back; S03 nút `← Quay lại` đặt ngay trên nút `Xác nhận`. Không nhất quán vị trí điều hướng lùi. | **FLI-01** |
| FL-DK01 | **Feedback & State** | S04 | ❌ **FAIL** | Ô mật khẩu trống nhưng các điều kiện mật khẩu đều hiển thị tick xanh `✔`, báo hiệu sai trạng thái hoàn thành. | **FLI-03** |
| FL-DK01 | **Context & Recovery** | S03 → S02 | ⚠️ **NEEDS VALIDATION** | Không có nút "Sửa số điện thoại" tại màn hình OTP; nếu bấm `← Quay lại` chưa rõ dữ liệu S02 có được bảo lưu hay không. | **FLI-04** |
| FL-DK01 | **Completion & Next Step** | S05 | ⚠️ **NEEDS VALIDATION** | Màn hình thành công có 2 nút "Đi tới trang chủ" và "Khám phá tính năng", nhưng không nêu rõ người dùng đã được tự động đăng nhập chưa. | **FLI-05** |

---

### 3.4. Bảng Flow Issues (Vấn đề xuyên suốt luồng)

| Flow Issue ID | Flow ID | Step / Transition | Screen liên quan | Nhóm | Severity | Vấn đề | Đề xuất giải pháp | Effort | Urgency | Priority |
|---|---|---|---|---|---|---|---|---:|---:|---|
| **FLI-01** | FL-DK01 | S01 → S04 | S02, S03, S04 | **Navigation** | **Major** | Điều hướng quay lại không nhất quán: S02 và S04 thiếu nút Back, trong khi S03 có nút Back đặt lệch chuẩn ở giữa màn hình | Bổ sung nút mũi tên quay lại (`←`) cố định tại góc trên bên trái của Top App Bar ở các bước S02, S03, S04 | 1 | 3 | **P1** |
| **FLI-02** | FL-DK01 | S02 → S04 | S02, S03, S04 | **Sequence** | **Major** | Thiếu thanh tiến trình (Progress Stepper) cho người dùng biết họ đang ở bước nào trong quy trình 4 bước tạo tài khoản | Bổ sung Stepper nhỏ gọn trên Header (VD: `Bước 1/3: Thông tin` → `Bước 2/3: Xác thực` → `Bước 3/3: Mật khẩu`) | 2 | 3 | **P1** |
| **FLI-03** | FL-DK01 | S04 | S04 | **Feedback** | **Major** | Trạng thái hiển thị tĩnh gây hiểu nhầm: Tick xanh `✔` xuất hiện sẵn cho toàn bộ 4 tiêu chí mật khẩu khi chưa nhập ký tự nào | Đổi icon mặc định thành dấu chấm xám `○` hoặc gạch ngang `-`; chỉ chuyển thành tick xanh `✔` khi ký tự người dùng gõ đáp ứng tiêu chuẩn | 1 | 3 | **P1** |
| **FLI-04** | FL-DK01 | S03 → S02 | S02, S03 | **Context** | **Minor** | Không có nút sửa nhanh số điện thoại trên màn hình OTP; phụ thuộc vào nút quay lại và tiềm ẩn mất dữ liệu S02 | Thêm liên kết *"Thay đổi số điện thoại"* ngay cạnh số SĐT hiển thị, click sẽ back về S02 và giữ nguyên các trường đã nhập | 1 | 2 | **P2** |
| **FLI-05** | FL-DK01 | S05 | S05 | **Completion** | **Minor** | Thông điệp hoàn tất chưa nêu rõ trạng thái đăng nhập (đã lưu phiên làm việc hay cần nhập lại tài khoản ở trang chủ) | Ghi rõ: *"Tài khoản đã được đăng nhập tự động. Bấm 'Đi tới trang chủ' để bắt đầu trải nghiệm"* | 1 | 1 | **P3** |

---

## 4. Bảng Kết quả đầu ra (Issue Log chi tiết theo từng Screen)

*Quy tắc sắp xếp: Từ bước 1 đến bước 5, từ trên xuống dưới, từ trái qua phải theo cấu trúc thị giác.*

| Issue ID | Phân loại | Mã checklist | Flow ID | Tên luồng | Flow Step | Chức năng | Bước thao tác | Thiết bị | Mức độ ảnh hưởng | Hình ảnh | Vấn đề | Đề xuất giải pháp | Hiệu quả sau cải tiến | Xếp loại Issue | Xếp loại Checklist | Effort | Urgency | Priority points |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---:|---:|---:|
| **ISS-01** | UI | `UI-ME01` | FL-DK01 | Đăng ký | Step 1 | Top Header | Xem màn hình đăng nhập | Mobile | Minor | S01 - Top right | Màn hình Đăng nhập nhưng góc trên bên phải vẫn có link *"Đăng nhập"* gây thừa thãi và khó hiểu | Ẩn link "Đăng nhập" ở S01 hoặc đổi thành nút "Hỗ trợ" / "Ngôn ngữ" | Tránh dư thừa thành phần điều hướng | Minor | FAIL | 1 | 1 | 1.0 (P3) |
| **ISS-02** | UI | `UI-BU04` | FL-DK01 | Đăng ký | Step 1 | Social Login | Chọn kênh đăng nhập khác | Mobile | Minor | S01 - Cụm icon social | 3 nút Social Login (Google, Apple, Facebook) chỉ có icon đơn lẻ, khoảng cách giữa các nút hơi thưa và thiếu nhãn tiếp cận | Bổ sung `aria-label` cho từng nút và đồng nhất kích thước container tròn/vuông bo góc | Đạt chuẩn tiếp cận và thao tác bấm nhạy hơn | Minor | FAIL | 1 | 1 | 1.0 (P3) |
| **ISS-03** | UI | `UI-TE01` | FL-DK01 | Đăng ký | Step 2 | Form đăng ký | Nhập ngày sinh & SĐT | Mobile | Major | S02 - Ô Ngày sinh & SĐT | Các ô nhập liệu thiếu placeholder hướng dẫn định dạng chuẩn (VD: `DD/MM/YYYY`, `09xx xxx xxx`) | Bổ sung placeholder định dạng mờ và tự động format mask khi người dùng gõ | Giảm thiểu lỗi sai cú pháp nhập liệu | Major | FAIL | 1 | 3 | 9.0 (P1) |
| **ISS-04** | UX | `UX-NV01` | FL-DK01 | Đăng ký | Step 2 | Điều hướng | Muốn quay lại màn hình trước | Mobile | Major | S02 - Header | Không có nút Back (`←`) quay lại màn hình Login; chỉ có link "Đăng nhập" nhỏ ở góc phải | Thêm nút mũi tên `←` ở góc trên bên trái Header để quay lại S01 | Giúp người dùng dễ dàng hủy bỏ hoặc quay lại | Major | FAIL | 1 | 3 | 9.0 (P1) |
| **ISS-05** | UX | `UX-TC18` | FL-DK01 | Đăng ký | Step 2 | Điều khoản | Đồng ý điều khoản | Mobile | Minor | S02 - Chân trang | Điều khoản sử dụng và chính sách bảo mật để dạng ngầm định (implicit agreement) | Cân nhắc bổ sung checkbox đồng ý rõ ràng để tuân thủ Nghị định 13/2023/NĐ-CP về bảo vệ dữ liệu cá nhân | Minh bạch pháp lý và bảo vệ quyền riêng tư người dùng | Minor | FAIL | 1 | 2 | 2.0 (P2) |
| **ISS-06** | UI | `UI-BU02` | FL-DK01 | Đăng ký | Step 3 | Bàn phím & Action | Xem màn hình OTP | Mobile | Major | S03 - Trên nút Xác nhận | Nút `← Quay lại` đặt lơ lửng ngay phía trên nút chính `Xác nhận` ở giữa màn hình | Di chuyển nút Back lên góc trên bên trái Header theo chuẩn di động | Bố cục chuẩn mực, tránh che khuất khi bàn phím số bật lên | Major | FAIL | 1 | 3 | 9.0 (P1) |
| **ISS-07** | UX | `UX-EC01` | FL-DK01 | Đăng ký | Step 3 | Nhập mã OTP | Nhận và điền OTP | Mobile | Major | S03 - Ô OTP 6 số | Thiếu tùy chọn phương thức nhận OTP dự phòng (Zalo, Gọi thoại tự động) khi SMS bị nghẽn | Bổ sung link: *"Nhận mã qua cuộc gọi"* sau khi hết thời gian đếm ngược 45s | Đảm bảo tỷ lệ chuyển đổi khi mạng viễn thông chậm SMS | Major | FAIL | 2 | 2 | 3.0 (P2) |
| **ISS-08** | UI | `UI-CH03` | FL-DK01 | Đăng ký | Step 4 | Tạo mật khẩu | Kiểm tra quy tắc mật khẩu | Mobile | Major | S04 - Checklist quy tắc | 4 tiêu chí mật khẩu hiển thị tick xanh `✔` mặc định khi ô nhập còn trống | Chuyển trạng thái mặc định sang icon màu xám mờ; chỉ đổi màu xanh và tick `✔` khi điều kiện thỏa mãn trong lúc gõ | Phản ánh chính xác tính xác thực của mật khẩu | Major | FAIL | 1 | 3 | 9.0 (P1) |
| **ISS-09** | UX | `UX-NV01` | FL-DK01 | Đăng ký | Step 4 | Tạo mật khẩu | Muốn kiểm tra lại thông tin | Mobile | Major | S04 - Header | Bước tạo mật khẩu không có nút Quay lại (`←`), biến bước này thành bẫy điều hướng bắt buộc phải hoàn tất | Thêm nút Back góc trên trái cho phép quay lại bước OTP hoặc thông tin cá nhân | Đảm bảo quyền kiểm soát và tự do của người dùng (NN/g #3) | Major | FAIL | 1 | 3 | 9.0 (P1) |
| **ISS-10** | UX | `UX-ND01` | FL-DK01 | Đăng ký | Step 5 | Hoàn tất | Bấm chuyển tiếp | Mobile | Minor | S05 - Hai nút điều hướng | Có 2 nút cùng cấp *"Đi tới trang chủ"* và *"Khám phá tính năng"* nhưng không rõ sự khác biệt về điểm đến | Giữ nút chính *"Bắt đầu sử dụng"* (vào Dashboard chính) và nút phụ *"Xem hướng dẫn"* | Đơn giản hóa quyết định hành động tiếp theo của người dùng | Minor | FAIL | 1 | 1 | 1.0 (P3) |

---

## 5. Bảng Kế hoạch cải tiến (Improvement Roadmap)

*Danh sách sắp xếp theo thứ tự ưu tiên xử lý P1 → P2 → P3.*

| Issue ID | Phân loại | Mã checklist | Chức năng | Bước thao tác | Thiết bị | Mức độ ảnh hưởng | Hình ảnh | Vấn đề | Đề xuất giải pháp | Hiệu quả sau cải tiến | Priority |
|---|---|---|---|---|---|---|---|---|---|---|---|
| **FLI-01** | Flow | `UX-NV01` | Toàn bộ luồng | Điều hướng tiến lùi | Mobile | **Major** | S02, S03, S04 | Nút Back bị thiếu ở S02, S04 và đặt sai vị trí ở S03 | Bổ sung nút mũi tên `←` chuẩn mực tại góc trên bên trái Header ở mọi bước | Thao tác quay lại liền mạch, không còn bẫy điều hướng | **P1** |
| **FLI-02** | Flow | `UX-TC01` | Toàn bộ luồng | Tiến trình các bước | Mobile | **Major** | S02 → S04 | Không có thanh tiến trình báo hiệu số bước còn lại | Bổ sung Stepper trực quan (`Bước 1/3` → `Bước 2/3` → `Bước 3/3`) | Giảm tỷ lệ bỏ dở luồng, định hướng tâm lý tốt cho người dùng | **P1** |
| **FLI-03** | Flow | `UI-CH03` | Tạo mật khẩu | Xem tiêu chí | Mobile | **Major** | S04 | Toàn bộ tiêu chí mật khẩu tick xanh sẵn khi chưa nhập liệu | Đổi trạng thái mặc định sang xám mờ; kích hoạt tick xanh theo thời gian thực | Phản hồi trung thực, giúp người dùng đặt mật khẩu đúng chuẩn | **P1** |
| **ISS-03** | UI | `UI-TE01` | Nhập thông tin | Điền ngày sinh & SĐT | Mobile | **Major** | S02 | Thiếu gợi ý định dạng ngày sinh và số điện thoại | Thêm placeholder mờ và mặt nạ định dạng tự động | Giảm thiểu lỗi nhập sai cú pháp ngay từ đầu | **P1** |
| **ISS-06** | UI | `UI-BU02` | Xác thực OTP | Thao tác nút | Mobile | **Major** | S03 | Nút `← Quay lại` đặt đè trên nút `Xác nhận` dễ bấm nhầm và bị bàn phím che | Đưa nút Back lên Top Bar, để không gian cho nút Xác nhận nổi bật | Tránh bấm nhầm và tránh xung đột với bàn phím số | **P1** |
| **ISS-08** | UI | `UI-CH03` | Tạo mật khẩu | Đặt mật khẩu | Mobile | **Major** | S04 | Icon tick xanh xuất hiện khi ô mật khẩu còn trống | Cập nhật logic render trạng thái validation động | Đảm bảo đúng chuẩn phản hồi giao diện | **P1** |
| **ISS-09** | UX | `UX-NV01` | Tạo mật khẩu | Thoát hoặc lùi bước | Mobile | **Major** | S04 | Thiếu nút quay lại ở bước tạo mật khẩu | Bổ sung nút Back ở Top Header | Tránh cảm giác bị giam cầm trong bước tạo mật khẩu | **P1** |
| **FLI-04** | Flow | `UX-EC01` | Xác thực OTP | Sửa số điện thoại | Mobile | Minor | S03 | Không sửa nhanh được SĐT khi nhập sai ở bước trước | Thêm nút *"Thay đổi số điện thoại"* kế bên số masked SĐT | Người dùng sửa nhanh SĐT mà không cần lùi lại từ đầu | **P2** |
| **ISS-05** | UX | `UX-TC18` | Nhập thông tin | Đồng ý điều khoản | Mobile | Minor | S02 | Điều khoản ngầm định chưa tối ưu theo luật dữ liệu cá nhân | Thêm checkbox đồng ý xử lý dữ liệu cá nhân rõ ràng | Tăng tính tuân thủ pháp lý và tạo sự an tâm | **P2** |
| **ISS-07** | UX | `UX-EC01` | Xác thực OTP | Nhận mã OTP | Mobile | Minor | S03 | Thiếu phương án nhận mã dự phòng khi SMS bị trễ | Thêm tùy chọn nhận mã OTP qua cuộc gọi thoại sau 45s | Đảm bảo tỷ lệ xác thực thành công ngay cả khi SMS nghẽn mạng | **P2** |
| **FLI-05** | Flow | `UX-ND01` | Hoàn tất | Đăng nhập hệ thống | Mobile | Minor | S05 | Chưa làm rõ trạng thái đã tự động đăng nhập hay chưa | Thêm thông báo *"Tài khoản đã đăng nhập tự động"* | Giúp người dùng yên tâm tiếp tục | **P3** |
| **ISS-01** | UI | `UI-ME01` | Đăng nhập | Xem Header | Mobile | Minor | S01 | Link "Đăng nhập" ở góc phải màn hình Đăng nhập bị thừa | Ẩn link này để Topbar gọn gàng | Tránh gây nhiễu thị giác | **P3** |
| **ISS-02** | UI | `UI-BU04` | Đăng nhập | Chọn mạng xã hội | Mobile | Minor | S01 | 3 nút Social Login thiếu nhãn trợ năng | Thêm `aria-label` cho các nút Google, Apple, Facebook | Tối ưu trợ năng cho người dùng khiếm thị | **P3** |
| **ISS-10** | UX | `UX-ND01` | Hoàn tất | Chọn hành động tiếp | Mobile | Minor | S05 | Hai nút điều hướng ở màn hình thành công cạnh tranh nhau | Tinh giản thành 1 nút chính *"Bắt đầu sử dụng"* | Dẫn dắt người dùng thẳng vào trải nghiệm sản phẩm | **P3** |

---

## 6. Danh mục Checklist chi tiết đã đánh giá xuyên suốt Luồng

### 6.1. Checklist UI
- **Áp dụng (Applicable): 88 lượt tiêu chí**
  - **PASS (81):** Hệ lưới căn gióng `UI-LA01`, `UI-LA02`, phân cấp thị giác `UI-LA03`, khoảng cách đệm `UI-LA04`, `UI-LA05`, độ tương phản màu sắc `UI-LA06`, nhận diện Logo `UI-LO01`, font chữ đồng nhất `UI-TY01`, kích thước chữ dễ đọc trên di động `UI-TY05`, căn lề trái chuẩn `UI-TY08`, độ tương phản text `UI-TY10`, hình học icon `UI-IC01`, căn giữa icon trong input `UI-IC03`, kiểu dáng nút bấm chính `UI-BU01`, trạng thái input `UI-TE01`, v.v.
  - **FAIL (7):** `UI-ME01` (Link Đăng nhập thừa ở S01), `UI-BU04` (Khoảng cách nút mạng xã hội S01), `UI-TE01` (Thiếu placeholder định dạng S02), `UI-BU02` (Vị trí nút Back ở S03), `UI-CH03` (Tick xanh mặc định sai trạng thái S04), `UI-ME01` (Thiếu nút Back ở S04).
  - **NEEDS VALIDATION (10):** Khả năng co giãn khi người dùng bật cỡ chữ lớn (Dynamic Type) `UI-LA08`, trạng thái pressed khi chạm nút `UI-BU05`, hiệu ứng chuyển cảnh mượt mà giữa các bước `UI-AL02`.
- **Không áp dụng (N/A): 317 lượt tiêu chí** (Bao gồm Data Table, Breadcrumbs, Chart, Switch, Multi-tab, Pagination phức tạp...).

### 6.2. Checklist UX
- **Áp dụng (Applicable): 84 lượt tiêu chí**
  - **PASS (74):** Thứ tự tiếp nhận thông tin hợp lý `UX-TC01`, màu sắc định hướng hành vi `UX-TC02`, icon có nghĩa trực quan `UX-TC06`, thao tác 1 chạm `UX-TC16`, vùng bấm bao phủ nút `UX-TC17`, định dạng SĐT ẩn bảo mật `UX-HI06`, thời gian đếm ngược rõ ràng `UX-TT02`, thông điệp thành công tích cực `UX-TT03`, v.v.
  - **FAIL (10):** `UX-NV01` (Thiếu nút Back ở S02, S04), `UX-TC18` (Điều khoản ngầm định S02), `UX-EC01` (Thiếu phương thức sửa SĐT nhanh S03), `UX-EC02` (Thiếu phương án dự phòng gửi OTP S03), `UX-TC08` (Phản hồi điều kiện mật khẩu chưa đúng thực tế S04), `UX-ND01` (Chưa rõ ràng trạng thái đăng nhập ở S05).
  - **NEEDS VALIDATION (14):** Tự động bật bàn phím số ở bước OTP, khả năng đọc của Screen Reader (VoiceOver / TalkBack) với từng ô OTP, thời gian chờ API tạo tài khoản.
- **Không áp dụng (N/A): 1346 lượt tiêu chí** (Bao gồm luồng mua hàng, giỏ hàng, thanh toán hóa đơn, xem video, upload tài liệu...).

---

## 7. Kết luận và Khuyến nghị

1. **Khắc phục ngay trong Sprint hiện tại (P1):**
   - **Đồng bộ hóa thanh điều hướng Top Bar:** Thêm nút mũi tên quay lại (`←`) ở góc trên bên trái cho các màn hình `S02`, `S03`, `S04`. Chuyển nút `← Quay lại` ở `S03` từ thân màn hình lên Top Bar.
   - **Bổ sung Progress Stepper:** Thêm thanh tiến trình 3 bước trực quan (`Thông tin` → `Xác thực` → `Mật khẩu`) trên đầu các màn hình từ `S02` đến `S04` để người dùng kiểm soát được tiến độ.
   - **Sửa logic hiển thị checklist mật khẩu (`S04`):** Thiết lập trạng thái mặc định của các tiêu chí là xám mờ (`○`); chỉ chuyển sang màu xanh lá và tick `✔` khi chuỗi người dùng gõ thực sự thỏa mãn tiêu chí đó.
   - **Bổ sung placeholder định dạng tại `S02`:** Hiển thị mờ `DD/MM/YYYY` cho ngày sinh và định dạng tự động thêm dấu cách cho số điện thoại.
2. **Nâng cao trải nghiệm & Tối ưu chuyển đổi (P2):**
   - **Tối ưu bước OTP:** Bổ sung nút liên kết *"Đổi số điện thoại"* ngay cạnh số masked SĐT; sau 45s đếm ngược, bổ sung nút *"Nhận mã qua cuộc gọi"* để giải quyết rủi ro nghẽn tin nhắn SMS.
   - **Tuân thủ quy định bảo vệ dữ liệu:** Đưa điều khoản sử dụng và chính sách bảo mật thành checkbox chủ động tích chọn.
3. **Tinh chỉnh thẩm mỹ & Trợ năng (P3):**
   - Xóa bỏ nút link *"Đăng nhập"* thừa trên Topbar của màn hình `S01`.
   - Rút gọn 2 nút hành động ở màn hình `S05` thành 1 nút CTA duy nhất: *"Bắt đầu sử dụng"*, kèm thông báo xác nhận tài khoản đã được tự động đăng nhập.
