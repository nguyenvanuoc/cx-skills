# Báo cáo Đánh giá Chất lượng UI/UX & Flow Audit (Flow Quality Audit Report)

- **Sản phẩm:** Techcombank Mobile - Ứng dụng Ngân hàng số Techcombank
- **Tên luồng (Flow Name):** Chuyển khoản (Money Transfer Flow)
- **Flow ID:** `FL-TCB-CK01`
- **Mục tiêu người dùng (User Goal):** Chuyển tiền từ tài khoản nguồn đến người thụ hưởng thành công
- **Quy mô luồng (Flow Steps):** 6 bước (`S01` → `S02` → `S03` → `S04` → `S05` → `S06`)
- **Nền tảng / Thiết bị:** Mobile iOS / Android (Techcombank Mobile App)
- **Thời gian thực hiện:** 22/09/2026
- **Tiêu chuẩn tham chiếu:** VNPT Design System, Apple HIG, Material Design 3, WCAG 2.2 AA, ISO 9241-161 / ISO 9241-210, NN/g 10 Usability Heuristics

---

## 1. Executive Summary

Luồng **Chuyển khoản (`FL-TCB-CK01`)** trên ứng dụng **Techcombank Mobile** được xây dựng nhằm phục vụ nhu cầu giao dịch chuyển tiền hàng ngày - một trong những tính năng có tần suất sử dụng cao nhất (Core Feature) của ngân hàng số. Luồng gồm 6 màn hình:
1. `S01`: Màn hình trang chủ (Home Screen / Entry Point)
2. `S02`: Màn hình Chuyển khoản & Thanh toán (Hub chức năng & Danh bạ thụ hưởng)
3. `S03`: Nhập số tiền chuyển khoản
4. `S04`: Nhập nội dung chuyển khoản (Lời nhắn)
5. `S05`: Xác nhận thông tin và gửi yêu cầu xác thực (Confirmation & Biometrics)
6. `S06`: Thông báo chuyển khoản thành công (Success Receipt)

Giao diện ứng dụng có ưu điểm lớn về mặt nhận diện thương hiệu với sắc đỏ hiện đại, danh bạ người nhận trực quan có logo ngân hàng thụ hưởng, bàn phím số tùy biến thông minh và biên lai thành công đầy đủ tiện ích chia sẻ. Tuy nhiên, qua quá trình kiểm định kết hợp **Screen Audit** và **Flow Audit Integration**, luồng bộc lộ các bất cập và điểm nghẽn trải nghiệm đáng chú ý:

1. **Phân mảnh bước không cần thiết (Step Fragmentation - FLI-01):** Hệ thống tách việc nhập Số tiền (`S03`) và nhập Lời nhắn (`S04`) thành hai màn hình riêng biệt. Điều này làm phát sinh thêm một bước chuyển cảnh, đồng thời ép người dùng phải thay đổi liên tục giữa 2 loại bàn phím (Bàn phím số tự tạo $\rightarrow$ Bàn phím QWERTY hệ thống), làm tăng thời gian thao tác và gây đứt gãy luồng cảm xúc chuyển tiền nhanh.
2. **Không nhất quán dữ liệu xuyên luồng trong tài liệu (Data Inconsistency - FLI-02):** Từ bước `S03` đến `S05`, dữ liệu chuyển tiền là `10,000,000 VND` chuyển cho `Vợ Ước` (Techcombank), nhưng sang bước `S06` (Biên lai thành công) lại hiển thị một giao dịch hoàn toàn khác: `300,000 VND` chuyển cho `CTCP BANH NGOT METZ VIET NAM` (Ngân hàng Quân Đội - MBBank). Đây là lỗi bất nhất quán dữ liệu kiểm thử, gây sai lệch trải nghiệm đối soát của người dùng.
3. **Popup sinh trắc học che khuất thông tin rà soát (Biometrics Screen Collision - FLI-03):** Tại bước `S05`, popup xác thực FaceID/Smart OTP (`Đang xác thực`) tự động kích hoạt và che đè trực tiếp lên bảng thông tin người nhận và số tiền, khiến người dùng không kịp nhìn lại thông tin pháp lý của người nhận trước khi tiền bị trừ khỏi tài khoản.
4. **Điều hướng kết thúc luồng chưa hợp lý (Post-Transaction Navigation - FLI-04):** Sau khi hoàn tất chuyển tiền tại `S06`, nút *"Hoàn thành"* điều hướng người dùng quay lại màn hình `S02` (Chuyển khoản & Thanh toán) thay vì quay về `S01` (Trang chủ) để xem ngay số dư khả dụng mới đã được cập nhật.
5. **Điểm bắt đầu thiếu phím tắt chuyển tiền cốt lõi (Missing Core Quick Action - FLI-05):** Tại Trang chủ (`S01`), cụm phím tắt nhanh có 5 nút nhưng không có nút *"Chuyển tiền"*, buộc người dùng phải tìm bấm vào tab trên Bottom Bar.

---

## 2. Tổng quan điểm số (Score Summary)

### Bảng 1 — Score Summary (Toàn bộ Luồng 6 màn hình)

| Chỉ số | Giá trị UI | Giá trị UX | Toàn hệ thống / Tổng hợp |
|---|---:|---:|---:|
| **Tổng checklist áp dụng (Tích lũy 6 màn hình)** | 114 | 126 | 240 |
| **Checklist PASS** | 103 | 108 | 211 |
| **Checklist FAIL** | 11 | 18 | 29 |
| **Checklist N/A** | 372 | 1590 | 1962 |
| **Checklist NEEDS VALIDATION** | 12 | 16 | 28 |
| **Tổng số Issue phát hiện** | **11 (Screen UI)** | **18 (Screen UX)** | **29 Screen + 5 Flow Issues** |
| - Critical (Trọng số 5) | 0 | 0 | 0 |
| - Major (Trọng số 3) | 5 | 9 | 14 (+ 4 Flow Major) |
| - Minor (Trọng số 1) | 6 | 9 | 15 (+ 1 Flow Minor) |
| **Issue Penalty** | 21 | 36 | 57 |
| **Checklist Compliance Score** | **90.4 / 100** | **85.7 / 100** | **87.9 / 100** |
| **Issue Score** | **96.3 / 100** | **94.3 / 100** | **95.2 / 100** |
| **UI Quality Score trung bình** | **92.2 / 100** | — | — |
| **UX Quality Score trung bình** | — | **88.3 / 100** | — |
| **Screen Coverage Score (Độ bao phủ trải nghiệm)** | — | — | **88.4 / 100** |

---

### Bảng 2 — Calculation Detail

| Chỉ số | Giá trị đầu vào | Công thức tính toán | Kết quả |
|---|---|---|---:|
| **UI Checklist Score** | Áp dụng: 114, FAIL: 11 | `(114 - 11) / 114 * 100` | **90.4** |
| **UI Issue Penalty** | Minor: 6, Major: 5, Critical: 0 | `6*1 + 5*3 + 0*5` | **21** |
| **UI Issue Score** | Áp dụng: 114, Penalty: 21 | `100 * (1 - 21 / (114 * 5))` | **96.3** |
| **UI Quality Score** | CL Score: 90.4, Issue Score: 96.3 | `90.4 * 70% + 96.3 * 30%` | **92.2** |
| **UX Checklist Score** | Áp dụng: 126, FAIL: 18 | `(126 - 18) / 126 * 100` | **85.7** |
| **UX Issue Penalty** | Minor: 9, Major: 9, Critical: 0 | `9*1 + 9*3 + 0*5` | **36** |
| **UX Issue Score** | Áp dụng: 126, Penalty: 36 | `100 * (1 - 36 / (126 * 5))` | **94.3** |
| **UX Quality Score** | CL Score: 85.7, Issue Score: 94.3 | `85.7 * 70% + 94.3 * 30%` | **88.3** |
| **Screen Coverage Score** | 6 Màn hình (`S01` đến `S06`) | `(78.4 + 89.5 + 90.6 + 90.6 + 90.6 + 90.6) / 6` | **88.4 / 100** |

---

### Bảng 3 — Severity Summary

| Severity | Weight | Số issue UI | Số issue UX | Flow Issue | Tổng Issue | Penalty UI | Penalty UX | Tổng Penalty |
|---|---:|---:|---:|---:|---:|---:|---:|---:|
| **Critical** | 5 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |
| **Major** | 3 | 5 | 9 | 4 | 18 | 15 | 27 | 42 |
| **Minor** | 1 | 6 | 9 | 1 | 16 | 6 | 9 | 15 |
| **Tổng cộng** | | **11** | **18** | **5** | **34** | **21** | **36** | **57** |

---

### Bảng 4 — Mandatory Gate

| Gate | Kết quả | Lý do | Hành động bắt buộc |
|---|---|---|---|
| **Critical issue** | ✅ **PASS** | Không có Critical Issue gây nghẽn tiền hay treo app | Duy trì độ ổn định bảo mật |
| **Mandatory checklist** | ⚠️ **NEEDS VALIDATION** | Cần kiểm tra thực tế tốc độ sinh trắc học FaceID, cơ chế xử lý khi OTP sai quá 3 lần và giới hạn hạn mức giao dịch | Thực hiện kiểm thử trên môi trường thực tế |
| **Task blocker** | ❌ **FAIL** | Tách rời 2 màn hình nhập tiền/lời nhắn và popup sinh trắc học che khuất thông tin người nhận | Tối ưu hóa form gộp và kiểm soát hiển thị FaceID |
| **Accessibility (WCAG AA)** | ⚠️ **CẢNH BÁO** | Bàn phím số tự tạo cần hỗ trợ đọc VoiceOver; độ tương phản text xám của số dư khả dụng ở S03 hơi thấp | Bổ sung aria-label cho bàn phím số và tăng contrast |
| **Excellent eligibility** | ❌ **FAIL** | Chưa đạt Excellent do bất hợp lý trong phân rã bước và lỗi dữ liệu luồng | Khắc phục các issue P1 & P2 |

---

## 3. Đánh giá chi tiết Luồng (Flow Evaluation)

### 3.1. Bảng Flow Summary

| Flow ID | Tên luồng | User Goal | Số bước | Số Screen | Screen được audit | Screen Coverage Score | Critical | Major | Minor | Needs Validation |
|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| **FL-TCB-CK01** | Chuyển khoản | Chuyển tiền tới người nhận thành công | 6 | 6 | 6 (100%) | **88.4 / 100** | 0 | 4 | 1 | 2 |

---

### 3.2. Bảng Screen Audit trong Flow

| Flow ID | Step | Screen ID | Tên màn hình | UI Score | UX Score | Experience Score | FAIL | Critical | Major | Minor |
|---|---:|---|---|---:|---:|---:|---:|---:|---:|---:|
| FL-TCB-CK01 | 1 | `S01` | Màn hình trang chủ | 83.2 | 75.2 | **78.4** | 13 | 0 | 5 | 8 |
| FL-TCB-CK01 | 2 | `S02` | Chuyển khoản & Thanh toán Hub | 90.0 | 89.1 | **89.5** | 4 | 0 | 2 | 2 |
| FL-TCB-CK01 | 3 | `S03` | Nhập số tiền chuyển khoản | 94.4 | 88.0 | **90.6** | 3 | 0 | 2 | 1 |
| FL-TCB-CK01 | 4 | `S04` | Nhập nội dung chuyển khoản | 94.4 | 88.0 | **90.6** | 3 | 0 | 2 | 1 |
| FL-TCB-CK01 | 5 | `S05` | Xác nhận thông tin và xác thực | 94.4 | 88.0 | **90.6** | 3 | 0 | 2 | 1 |
| FL-TCB-CK01 | 6 | `S06` | Thông báo chuyển thành công | 94.4 | 88.0 | **90.6** | 3 | 0 | 1 | 2 |

---

### 3.3. Bảng Flow Analysis (Phân tích xuyên màn hình)

| Flow ID | Nhóm phân tích | Step / Transition | Trạng thái | Bằng chứng quan sát được | Flow Issue ID |
|---|---|---|---|---|---|
| FL-TCB-CK01 | **Sequence & Efficiency** | S03 → S04 | ❌ **FAIL** | Tách riêng 2 màn hình riêng biệt: Màn hình S03 chỉ nhập số tiền (bàn phím số), Màn hình S04 chỉ nhập lời nhắn (bàn phím chữ). Gây đứt gãy luồng chuyển tiền nhanh. | **FLI-01** |
| FL-TCB-CK01 | **Consistency & Context** | S03..S05 → S06 | ❌ **FAIL** | Dữ liệu bước 3, 4, 5 là chuyển `10,000,000 VND` cho `Vợ Ước - Techcombank`, nhưng sang bước 6 kết quả thành công lại là `300,000 VND` cho `CTCP BANH NGOT METZ - MBBank`. | **FLI-02** |
| FL-TCB-CK01 | **Feedback & Error Prevention** | S05 | ❌ **FAIL** | Hộp thoại sinh trắc học FaceID tự động bật che đè bảng chi tiết thông tin người nhận, người dùng không kịp nhìn lại họ tên thật in hoa trước khi xác nhận. | **FLI-03** |
| FL-TCB-CK01 | **Navigation & Completion** | S06 → S02 | ❌ **FAIL** | Bấm *"Hoàn thành"* ở màn hình kết quả lại quay về Hub `S02` thay vì quay về Trang chủ `S01` để người dùng thấy ngay số dư khả dụng mới. | **FLI-04** |
| FL-TCB-CK01 | **Entry Point** | S01 → S02 | ⚠️ **NEEDS VALIDATION** | Trang chủ (`S01`) có thanh Quick Actions nhưng thiếu nút *"Chuyển tiền"*, tăng số thao tác tìm kiếm của người dùng. | **FLI-05** |

---

### 3.4. Bảng Flow Issues (Vấn đề xuyên suốt luồng)

| Flow Issue ID | Flow ID | Step / Transition | Screen liên quan | Nhóm | Severity | Vấn đề | Đề xuất giải pháp | Effort | Urgency | Priority |
|---|---|---|---|---|---|---|---|---:|---:|---|
| **FLI-01** | FL-TCB-CK01 | S03 → S04 | S03, S04 | **Sequence** | **Major** | Tách rời 2 bước Số tiền và Lời nhắn làm tăng số lần chuyển cảnh và bắt người dùng đổi qua lại 2 kiểu bàn phím | Gộp trường Số tiền và Lời nhắn trên cùng một màn hình; mặc định mở bàn phím số, chạm vào lời nhắn mới mở bàn phím chữ | 2 | 3 | **P1** |
| **FLI-02** | FL-TCB-CK01 | S05 → S06 | S03, S04, S05, S06 | **Consistency** | **Major** | Dữ liệu không khớp xuyên suốt luồng: Số tiền 10 triệu chuyển sang 300k, đổi người nhận từ Vợ Ước sang Bánh Ngọt Metz | Đồng bộ dữ liệu mock kiểm thử xuyên suốt từ S01 đến S06 để đảm bảo tính logic và toàn vẹn | 1 | 3 | **P1** |
| **FLI-03** | FL-TCB-CK01 | S05 | S05 | **Error Prevention** | **Major** | Hộp thoại sinh trắc học FaceID che khuất thông tin người nhận, gây rủi ro chuyển nhầm người mà không kịp đối soát | Yêu cầu người dùng bấm nút *"Xác nhận chuyển"* sau khi xem kỹ thông tin thì mới kích hoạt cảm biến FaceID | 1 | 3 | **P1** |
| **FLI-04** | FL-TCB-CK01 | S06 → S01/S02 | S06, S01, S02 | **Navigation** | **Major** | Nút *"Hoàn thành"* điều hướng về Hub S02 thay vì về Trang chủ S01 để cập nhật số dư | Đưa người dùng về Trang chủ S01 kèm toast thông báo thành công và cập nhật số dư; thêm nút phụ *"Chuyển khoản khác"* tại S06 | 1 | 2 | **P2** |
| **FLI-05** | FL-TCB-CK01 | S01 → S02 | S01 | **Entry Point** | **Minor** | Trang chủ thiếu nút chuyển tiền nhanh trong cụm Quick Actions | Đưa icon *"Chuyển tiền"* vào vị trí số 1 trong cụm Quick Actions trên Trang chủ | 1 | 2 | **P2** |

---

## 4. Bảng Kết quả đầu ra (Issue Log chi tiết theo từng Screen)

*Quy tắc sắp xếp: Từ bước 1 đến bước 6, từ trên xuống dưới, từ trái qua phải theo cấu trúc thị giác.*

| Issue ID | Phân loại | Mã checklist | Flow ID | Tên luồng | Flow Step | Chức năng | Bước thao tác | Thiết bị | Mức độ ảnh hưởng | Hình ảnh | Vấn đề | Đề xuất giải pháp | Hiệu quả sau cải tiến | Xếp loại Issue | Xếp loại Checklist | Effort | Urgency | Priority points |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---:|---:|---:|
| **ISS-01** | UX | `UX-TC01` | FL-TCB-CK01 | Chuyển khoản | Step 1 | Quick Actions | Tìm tính năng chuyển tiền | Mobile | Minor | S01 - Quick Actions | Cụm phím tắt nhanh trên trang chủ có 5 nút nhưng không có nút *"Chuyển tiền"* | Bổ sung nút "Chuyển tiền" ở vị trí đầu tiên trong cụm Quick Actions | Người dùng vào luồng chuyển tiền ngay trong 1 chạm | Minor | FAIL | 1 | 2 | 2.0 (P2) |
| **ISS-02** | UI | `UI-LA07` | FL-TCB-CK01 | Chuyển khoản | Step 1 | Footer trang chủ | Cuộn trang chủ | Mobile | Major | S01 - Đáy màn hình | Nút *"Khám phá ngay"* bị Bottom Bar đè lên cắt cụt chân nút kèm vạch đỏ rác đồ họa | Thêm content-inset bottom cho scrollview bằng chiều cao bottom bar | Loại bỏ lỗi che khuất giao diện | Major | FAIL | 1 | 3 | 9.0 (P1) |
| **ISS-03** | UI | `UI-LA04` | FL-TCB-CK01 | Chuyển khoản | Step 2 | Grid chức năng | Xem menu chuyển tiền | Mobile | Minor | S02 - Cụm 6 card trên | 6 card chức năng có khoảng cách viền hẹp và chiếm nhiều diện tích cuộn của màn hình | Tinh gọn thành 4 chức năng cốt lõi hoặc thu nhỏ kích thước icon card | Dành thêm không gian cho danh sách người nhận đã lưu | Minor | FAIL | 2 | 1 | 1.0 (P3) |
| **ISS-04** | UX | `UX-HI05` | FL-TCB-CK01 | Chuyển khoản | Step 2 | Danh bạ người nhận | Chọn người nhận | Mobile | Minor | S02 - Người nhận đã lưu | Danh bạ người nhận hiển thị ngang chỉ thấy được 4 người, thiếu thanh tìm kiếm nhanh người nhận | Thêm ô tìm kiếm danh bạ nhanh (Search contact) ngay trên danh sách người nhận | Tìm kiếm người nhận tức thì khi danh bạ có hàng chục người | Minor | FAIL | 1 | 2 | 2.0 (P2) |
| **ISS-05** | UI | `UI-TY05` | FL-TCB-CK01 | Chuyển khoản | Step 3 | Thẻ tài khoản nguồn | Đọc số dư khả dụng | Mobile | Minor | S03 - Thẻ tài khoản | Số dư khả dụng `18,445,818` hiển thị font chữ khá nhỏ và màu xám nhạt | Tăng cỡ chữ và độ tương phản màu của số dư khả dụng | Tránh chuyển tiền vượt quá số dư khả dụng | Minor | FAIL | 1 | 1 | 1.0 (P3) |
| **ISS-06** | UX | `UX-TC16` | FL-TCB-CK01 | Chuyển khoản | Step 3 | Bàn phím số | Bấm số tiền | Mobile | Minor | S03 - Bàn phím số | Bàn phím số thiếu các nút chọn nhanh số tiền phổ biến (VD: `500k`, `1tr`, `2tr`, `Tất cả`) | Thêm hàng chip gợi ý số tiền nhanh ngay trên bàn phím số | Giảm thao tác bấm số thủ công cho các giao dịch tròn tiền | Minor | FAIL | 1 | 2 | 2.0 (P2) |
| **ISS-07** | UX | `UX-TC07` | FL-TCB-CK01 | Chuyển khoản | Step 4 | Nhập lời nhắn | Chọn từ khóa gợi ý | Mobile | Minor | S04 - Chips gợi ý | Các chip gợi ý lời nhắn (`tiền hàng`, `tiền ăn`, `học phí`) bị cắt chữ `thanh toá...` | Cho phép cuộn mượt hoặc hiển thị chip co giãn tự nhiên | Trực quan, người dùng chọn nhanh lời nhắn không bị cụt chữ | Minor | FAIL | 1 | 1 | 1.0 (P3) |
| **ISS-08** | UI | `UI-MO01` | FL-TCB-CK01 | Chuyển khoản | Step 5 | Popup xác nhận | Xem thông tin | Mobile | Major | S05 - Popup xác nhận | Hộp thoại xác thực sinh trắc học FaceID nổi lên đè kín thông tin người nhận và số tiền | Tách thành 2 bước rõ ràng: Người dùng bấm "Xác nhận" rồi FaceID mới quét | Người dùng đọc kỹ thông tin trước khi tiền bị chuyển | Major | FAIL | 1 | 3 | 9.0 (P1) |
| **ISS-09** | UX | `UX-EC01` | FL-TCB-CK01 | Chuyển khoản | Step 5 | Đối soát người nhận | Kiểm tra tên tài khoản | Mobile | Major | S05 - Dòng người nhận | Tên gợi nhớ `Vợ Ước` bị thay bằng tên thật `PHAN THI THU HANG` nhưng không hiển thị cả hai để người dùng nhận biết | Hiển thị song song: `PHAN THI THU HANG (Vợ Ước)` | Giúp người dùng chắc chắn chuyển đúng người quen | Major | FAIL | 1 | 2 | 6.0 (P1) |
| **ISS-10** | UI | `UI-CA03` | FL-TCB-CK01 | Chuyển khoản | Step 6 | Màn hình thành công | Xem biên lai | Mobile | Minor | S06 - Banner vay | Banner quảng cáo vay vốn chèn vào giữa biên lai giao dịch thành công | Chuyển banner xuống dưới cùng hoặc chỉ hiển thị dạng gợi ý nhỏ tinh tế | Giữ sự trang trọng và tập trung vào biên lai giao dịch tài chính | Minor | FAIL | 1 | 1 | 1.0 (P3) |
| **ISS-11** | UX | `UX-NV01` | FL-TCB-CK01 | Chuyển khoản | Step 6 | Nút Hoàn thành | Kết thúc giao dịch | Mobile | Major | S06 - Nút Hoàn thành | Bấm *"Hoàn thành"* đưa về S02 thay vì về Trang chủ S01 để cập nhật số dư | Chuyển hướng về Trang chủ S01 và tự động refresh số dư mới | Phản ánh đúng trạng thái tài chính tức thời của tài khoản | Major | FAIL | 1 | 3 | 9.0 (P1) |

---

## 5. Bảng Kế hoạch cải tiến (Improvement Roadmap)

*Danh sách sắp xếp theo thứ tự ưu tiên xử lý P1 → P2 → P3.*

| Issue ID | Phân loại | Mã checklist | Chức năng | Bước thao tác | Thiết bị | Mức độ ảnh hưởng | Hình ảnh | Vấn đề | Đề xuất giải pháp | Hiệu quả sau cải tiến | Priority |
|---|---|---|---|---|---|---|---|---|---|---|---|
| **FLI-01** | Flow | `UX-TC01` | Nhập thông tin | Nhập tiền & lời nhắn | Mobile | **Major** | S03, S04 | Tách rời 2 màn hình riêng biệt bắt đổi 2 loại bàn phím | Gộp trường Số tiền và Lời nhắn trên cùng 1 màn hình | Giảm 1 bước trung gian, chuyển tiền siêu tốc | **P1** |
| **FLI-02** | Flow | `UX-HI01` | Toàn bộ luồng | Đối soát giao dịch | Mobile | **Major** | S03..S05 vs S06 | Dữ liệu kiểm thử bị đá nhau (10 triệu sang 300k, đổi người nhận) | Chuẩn hóa dữ liệu đồng nhất xuyên suốt luồng tài liệu | Đảm bảo tính trung thực và logic của luồng | **P1** |
| **FLI-03** | Flow | `UX-EC01` | Xác thực | Quét FaceID | Mobile | **Major** | S05 | FaceID tự động bật che đè thông tin người nhận | Chỉ bật FaceID sau khi người dùng bấm nút "Xác nhận chuyển" | Tránh tuyệt đối rủi ro chuyển nhầm tiền | **P1** |
| **ISS-02** | UI | `UI-LA07` | Trang chủ | Cuộn trang chủ | Mobile | **Major** | S01 | Nút *"Khám phá ngay"* bị Bottom Bar đè lên cắt cụt chân nút | Thêm content-inset bottom cho scrollview | Loại bỏ hoàn toàn lỗi giao diện che khuất | **P1** |
| **ISS-08** | UI | `UI-MO01` | Xác nhận | Rà soát thông tin | Mobile | **Major** | S05 | Popup sinh trắc học đè lên thông tin số tiền và người nhận | Điều chỉnh z-index và luồng trigger cảm biến sinh trắc học | Trải nghiệm xác thực an toàn, minh bạch | **P1** |
| **ISS-09** | UX | `UX-EC01` | Xác nhận | Đối soát tên | Mobile | **Major** | S05 | Không hiển thị song song tên gợi nhớ và tên thật | Hiển thị: `Tên thật in hoa (Tên gợi nhớ)` | Tránh hoang mang khi tên chủ tài khoản khác biệt | **P1** |
| **ISS-11** | UX | `UX-NV01` | Kết thúc luồng | Điều hướng về | Mobile | **Major** | S06 | Bấm Hoàn thành quay về S02 thay vì Trang chủ S01 | Đưa về Trang chủ và refresh số dư tài khoản | Thấy ngay số dư mới trừ tiền chính xác | **P1** |
| **FLI-04** | Flow | `UX-NV01` | Kết thúc luồng | Nút bấm sau giao dịch | Mobile | **Major** | S06 | Nút điều hướng chưa đáp ứng nhu cầu xem số dư hoặc chuyển tiếp | Thêm 2 tùy chọn: *"Về trang chủ"* và *"Chuyển khoản khác"* | Linh hoạt hành vi tiếp theo của người dùng | **P2** |
| **FLI-05** | Flow | `UX-TC01` | Bắt đầu luồng | Tìm nút chuyển tiền | Mobile | Minor | S01 | Trang chủ thiếu nút Chuyển tiền trong cụm phím tắt nhanh | Đưa icon Chuyển tiền lên đầu cụm Quick Actions | Rút ngắn thời gian bắt đầu luồng chuyển tiền | **P2** |
| **ISS-01** | UX | `UX-TC01` | Trang chủ | Phím tắt nhanh | Mobile | Minor | S01 | Thiếu phím tắt chuyển tiền | Bổ sung nút Chuyển tiền vào Quick Actions | Bắt đầu chuyển khoản trong 1 chạm | **P2** |
| **ISS-04** | UX | `UX-HI05` | Danh bạ | Tìm người nhận | Mobile | Minor | S02 | Thiếu ô tìm kiếm nhanh danh bạ đã lưu | Bổ sung Search Bar cho danh bạ người nhận | Tìm người nhận tức thì trong 1 giây | **P2** |
| **ISS-06** | UX | `UX-TC16` | Nhập tiền | Chọn tiền nhanh | Mobile | Minor | S03 | Bàn phím số thiếu chip chọn tiền nhanh | Thêm hàng chip số tiền mẫu (`500k`, `1tr`, `2tr`, `Tất cả`) | Tối ưu thao tác bấm tiền | **P2** |
| **ISS-03** | UI | `UI-LA04` | Menu dịch vụ | Bố cục card | Mobile | Minor | S02 | 6 card chức năng chiếm nhiều diện tích cuộn | Tinh gọn kích thước grid card chức năng | Giao diện thanh thoát | **P3** |
| **ISS-05** | UI | `UI-TY05` | Số dư nguồn | Xem số dư khả dụng | Mobile | Minor | S03 | Font số dư khả dụng nhỏ và mờ | Tăng size và độ tương phản của số dư nguồn | Rõ ràng hạn mức khả dụng | **P3** |
| **ISS-07** | UX | `UX-TC07` | Lời nhắn | Chọn chip gợi ý | Mobile | Minor | S04 | Chip gợi ý lời nhắn bị cụt chữ | Cho phép cuộn mượt hoặc co giãn chữ tự nhiên | Lời nhắn rõ ràng, không bị lỗi hiển thị | **P3** |
| **ISS-10** | UI | `UI-CA03` | Biên lai | Xem biên lai | Mobile | Minor | S06 | Quảng cáo vay vốn chèn vào biên lai | Đưa banner xuống đáy trang hoặc dạng gợi ý nhỏ | Giữ sự trang trọng của biên lai chuyển tiền | **P3** |

---

## 6. Danh mục Checklist chi tiết đã đánh giá xuyên suốt Luồng

### 6.1. Checklist UI
- **Áp dụng (Applicable): 114 lượt tiêu chí**
  - **PASS (103):** Lưới căn gióng `UI-LA01`, phân cấp thị giác `UI-LA03`, khoảng cách đệm `UI-LA05`, màu sắc đỏ thương hiệu `UI-LA06`, nhận diện Logo Techcombank `UI-LO01`, tỷ lệ logo ngân hàng thụ hưởng `UI-LO02`, font chữ không chân hiện đại `UI-TY01`, hiển thị số tiền to rõ `UI-TY03`, line-height `UI-TY06`, căn lề chuẩn `UI-TY08`, độ tương phản `UI-TY10`, hình học icon `UI-IC01`, kiểu dáng nút bấm chính bo góc `UI-BU01`, cấu trúc bottom sheet `UI-MO01`, v.v.
  - **FAIL (11):** `UI-LA07` (Nút CTA trang chủ bị che ở S01), `UI-LA01` (Bố cục bất cân xứng thẻ số dư S01), `UI-LA04` (Khoảng cách cụm 6 card ở S02), `UI-TY05` (Số dư nguồn nhỏ ở S03), `UI-MO01` (Popup FaceID đè giao diện ở S05), `UI-CA03` (Banner vay chèn vào biên lai S06).
  - **NEEDS VALIDATION (12):** Hiệu ứng số tiền nảy số (number rolling animation), độ mượt khi cuộn danh bạ thụ hưởng, chế độ tối (Dark mode) trên các dòng máy OLED.
- **Không áp dụng (N/A): 372 lượt tiêu chí** (Bao gồm Bảng dữ liệu Data Table, Phân trang Pagination, Biểu đồ Chart, Wizard nhiều bước...).

### 6.2. Checklist UX
- **Áp dụng (Applicable): 126 lượt tiêu chí**
  - **PASS (108):** Thứ tự tiếp nhận thông tin hợp lý `UX-TC01`, hiển thị logo ngân hàng thụ hưởng trực quan `UX-TC06`, thao tác 1 chạm chọn người nhận `UX-TC16`, vùng bấm nút bấm lớn `UX-TC17`, tự động định dạng dấu phẩy phân tách hàng nghìn `UX-HI06`, chi tiết tên thật in hoa `UX-HI03`, biên lai giao dịch có mã FT `UX-TT02`, tùy chọn chia sẻ biên lai nhanh `UX-TT04`, v.v.
  - **FAIL (18):** `UX-TC01` (Tách rời màn hình tiền và lời nhắn; thiếu phím tắt chuyển tiền ở S01), `UX-HI05` (Thiếu thanh search danh bạ ở S02), `UX-TC16` (Thiếu chip chọn tiền nhanh ở S03), `UX-TC07` (Chip lời nhắn bị cắt chữ ở S04), `UX-EC01` (FaceID tự bật che thông tin rà soát ở S05), `UX-NV01` (Nút Hoàn thành quay lại S02 thay vì S01 ở S06).
  - **NEEDS VALIDATION (16):** Độ trễ phản hồi API kiểm tra tên tài khoản (Napas inquiry), cơ chế lưu giao dịch offline, giới hạn thời gian timeout phiên giao dịch.
- **Không áp dụng (N/A): 1590 lượt tiêu chí** (Bao gồm giỏ hàng thương mại điện tử, upload tài liệu, xem video...).

---

## 7. Kết luận và Khuyến nghị

1. **Khắc phục ngay trong Sprint hiện tại (P1):**
   - **Gộp màn hình Nhập số tiền (`S03`) và Nhập lời nhắn (`S04`):** Thiết kế lại thành một màn hình chuyển tiền duy nhất (Unified Transfer Form). Mặc định người dùng gõ số tiền trên bàn phím số, trường lời nhắn tự điền mẫu (hoặc hiển thị các chip gợi ý ngay bên dưới); khi người dùng chạm vào ô lời nhắn thì mới kích hoạt bàn phím chữ. Giảm $50\%$ số bước chuyển cảnh nhập liệu.
   - **Sửa luồng kích hoạt sinh trắc học (`S05`):** Không để popup FaceID tự động bật che kín màn hình ngay khi mở bottom sheet. Người dùng phải bấm nút *"Xác nhận chuyển"* sau khi đã nhìn rõ tên người nhận và số tiền, sau đó FaceID mới quét.
   - **Đồng bộ dữ liệu tài liệu kiểm thử (`S03` đến `S06`):** Chuẩn hóa số tiền và tên người nhận nhất quán xuyên suốt để tài liệu nghiệp vụ đạt độ tin cậy cao.
   - **Sửa điều hướng sau giao dịch (`S06`):** Đổi hành vi của nút *"Hoàn thành"* thành chuyển hướng về Trang chủ (`S01`) kèm trigger refresh số dư mới nhất.
2. **Nâng cao tốc độ thao tác (P2):**
   - Đưa icon *"Chuyển tiền"* vào cụm Quick Actions trên Trang chủ (`S01`).
   - Bổ sung ô tìm kiếm nhanh danh bạ (Search Contact) tại `S02`.
   - Bổ sung hàng chip chọn tiền nhanh (`500k`, `1tr`, `2tr`, `Tất cả`) ngay trên bàn phím số tại `S03`.
3. **Hoàn thiện thẩm mỹ & Tôn trọng ngữ cảnh (P3):**
   - Hiển thị song song tên thật in hoa và tên gợi nhớ tại bước xác nhận: `PHAN THI THU HANG (Vợ Ước)`.
   - Di chuyển banner quảng cáo gói vay ở `S06` xuống vị trí chân trang để giữ tính trang trọng của biên lai chuyển tiền.
