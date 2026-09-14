# Báo cáo Phân tích Chiến lược & Đề xuất Ý tưởng Sản phẩm (Product Discovery) - VNPT SmartCollect AI (Hệ thống Trợ lý AI nhắc nợ cước & Tự động hóa thanh toán)

- **Tên ý tưởng sản phẩm:** VNPT SmartCollect AI (AI-powered Debt Collection Assistant)
- **Mục tiêu:** Tự động hóa quy trình gọi điện nhắc nợ cước dịch vụ viễn thông (Internet, MyTV, Di động trả sau), tương tác đối thoại tự nhiên bằng giọng nói AI (Voice Bot), tự động gửi link QR code thanh toán cá nhân hóa qua SMS/Zalo và đối soát trạng thái thanh toán thời gian thực.
- **Ngày thực hiện:** 24/06/2026
- **Chuyên gia thực hiện:** Senior Product Designer, Product Manager & UX Strategist (.agent)
- **Dựa trên quy trình:** [idea.md](file:///Volumes/CHAOS/VNPT/AI/CX/.agent/skills/idea.md)

---

## BƯỚC 1. PHÂN TÍCH SẢN PHẨM (PRODUCT OVERVIEW)

| Nội dung | Phân tích chi tiết ý tưởng |
| :--- | :--- |
| **Sản phẩm đề xuất** | **VNPT SmartCollect AI** - Nền tảng Trợ lý ảo Voice Bot chuyên biệt cho nghiệp vụ nhắc nợ cước và hỗ trợ thanh toán tự động tích hợp đa kênh (Call, SMS, Zalo, App). |
| **Bài toán cần giải quyết** | 1. **Chi phí nhân sự nhắc nợ quá lớn:** Các chi nhánh VNPT tỉnh/thành phải duy trì đội ngũ điện thoại viên nhắc nợ cước khổng lồ mỗi kỳ khóa cước (thường từ ngày 15 - 25 hàng tháng), tốn kém chi phí nhân công và cước gọi thoại.<br>2. **Tỷ lệ bỏ qua tin nhắn cao:** Gửi SMS nhắc nợ tự động thường bị khách hàng bỏ qua hoặc coi là tin nhắn rác (Spam), tỷ lệ chuyển đổi thanh toán dưới 15%.<br>3. **Trải nghiệm khách hàng tiêu cực:** Các cuộc gọi nhắc nợ từ con người đôi khi thiếu thân thiện, gây cảm giác bị đòi nợ thô bạo, ảnh hưởng đến hình ảnh thương hiệu.<br>4. **Quy trình thanh toán rời rạc:** Nhắc nợ qua điện thoại nhưng khách hàng không biết thanh toán ở đâu, phải tự tìm số tài khoản hoặc ra cửa hàng giao dịch, dẫn đến việc tiếp tục trễ hạn đóng cước. |
| **Mục tiêu người dùng** | 1. **Khách hàng nợ cước:** Được nhắc nhở lịch sự, nhận được phương thức thanh toán nhanh nhất (quét mã QR) mà không cần tự nhập thông tin tài khoản.<br>2. **Chuyên viên Đối soát / Kế toán cước:** Quản lý và giám sát chiến dịch gọi nhắc nợ tự động, theo dõi dòng tiền cước thu hồi theo thời gian thực.<br>3. **Quản trị viên hệ thống (Admin):** Thiết kế kịch bản gọi đối thoại (Voice Flow) và cấu hình phân phối cuộc gọi thông minh theo nhóm đối tượng nợ. |
| **Mục tiêu doanh nghiệp** | 1. Giảm 80% chi phí nhân sự và cước phí viễn thông cho hoạt động nhắc nợ cước.<br>2. Rút ngắn số ngày nợ cước quá hạn trung bình (DSO - Days Sales Outstanding) từ 15 ngày xuống còn dưới 5 ngày.<br>3. Tăng tỷ lệ thu hồi nợ cước đúng hạn lên trên 90% trước khi thực hiện khóa chiều dịch vụ.<br>4. Tự động hóa đối soát dòng tiền thu nợ từ cổng ngân hàng/ví điện tử sang hệ thống Billing của VNPT. |
| **Giá trị cốt lõi** | **"Gentle Reminder, Instant Payment."** (Nhắc nhở tinh tế, thanh toán tức thì). |

---

## BƯỚC 2. XÁC ĐỊNH NHU CẦU NGƯỜI DÙNG

| Nhóm đối tượng | Functional Needs (Hành vi/Chức năng) | Emotional Needs (Cảm xúc) | Social Needs (Vị thế/Xã hội) |
| :--- | :--- | :--- | :--- |
| **Khách hàng cá nhân (Subscriber)** | - Cần biết chính xác số tiền cước nợ và hạn thanh toán.<br>- Cần nhận được link thanh toán nhanh (QR code) chứa sẵn số tiền và nội dung chuyển khoản.<br>- Cần đăng ký hẹn ngày thanh toán nếu chưa có tiền ngay. | - Không muốn cảm thấy bị làm phiền hoặc xấu hổ vì bị đòi nợ.<br>- Muốn cảm thấy được tôn trọng và hỗ trợ nhiệt tình. | - Tránh việc bị khóa dịch vụ làm ảnh hưởng đến công việc và sinh hoạt hàng ngày của gia đình. |
| **Nhân viên đối soát cước (Billing Accountant)** | - Cần tạo và quản lý các chiến dịch gọi nhắc nợ tự động theo khu vực.<br>- Cần theo dõi tỷ lệ cuộc gọi thành công và số tiền đã thu hồi được theo thời gian thực.<br>- Cần đối soát tự động giữa hệ thống Billing và tài khoản ngân hàng. | - Giảm bớt áp lực doanh số thu hồi nợ cước vào cuối tháng.<br>- Cảm thấy tự tin vào tính chính xác của dữ liệu tài chính. | - Hoàn thành xuất sắc KPI thu hồi công nợ của chi nhánh mà không tốn nhiều công sức. |
| **Trưởng ban quản lý dịch vụ khách hàng** | - Cần kiểm soát chất lượng giọng nói AI và kịch bản đối thoại.<br>- Cần báo cáo thống kê hiệu quả chiến dịch để tối ưu hóa.<br>- Cần phân tích lý do khách hàng chậm thanh toán. | - Yên tâm rằng hình ảnh thương hiệu VNPT luôn được giữ vững ở mọi cuộc gọi.<br>- Cảm thấy kiểm soát toàn diện hoạt động thu cước. | - Khẳng định năng lực đổi mới sáng tạo, chuyển đổi số quy trình nghiệp vụ tài chính của đơn vị. |

---

## BƯỚC 3. XÂY DỰNG USER PERSONA

### Persona 1: Anh Quốc Minh (32 tuổi) - Khách hàng sử dụng gói Internet Home Mesh tại Hà Nội
*   **Mục tiêu:** Thanh toán tiền cước Internet hàng tháng nhanh chóng để tránh bị cắt mạng làm ảnh hưởng đến công việc làm tự do (Freelancer) tại nhà.
*   **Nhu cầu:** Cần một lời nhắc nhở lịch sự vào buổi tối (khi đã đi làm về) kèm theo mã QR thanh toán nhanh để quét qua ứng dụng ngân hàng di động.
*   **Pain Point:** Rất bận rộn và hay quên ngày đóng cước (ngày 20 hàng tháng). Nhận được tin nhắn SMS nhắc nợ nhưng thường trôi mất hoặc không có thời gian đọc. Ngại ra cửa hàng giao dịch để nộp tiền mặt.
*   **Hành vi với SmartCollect AI:** Nhận cuộc gọi từ số thương hiệu VNPT vào lúc 19h. AI Voice Bot chào hỏi và báo số tiền nợ cước 220.000đ. Anh đồng ý thanh toán, AI lập tức gửi một tin nhắn Zalo kèm mã VietQR chứa sẵn thông tin hóa đơn. Anh Minh mở Zalo, quét mã thanh toán thành công trong 1 phút.

### Persona 2: Chị Thu Hồng (29 tuổi) - Kế toán Công nợ tại VNPT Chi nhánh TP.HCM
*   **Mục tiêu:** Quản lý việc nhắc nợ cước cho hơn 50.000 thuê bao internet quá hạn thanh toán trên địa bàn quận.
*   **Nhu cầu:** Cần một công cụ để tải danh sách thuê bao nợ cước từ hệ thống Billing lên, phân loại đối tượng (nợ 1 tháng, nợ 2 tháng) và lập lịch gọi tự động phù hợp.
*   **Pain Point:** Việc gọi điện nhắc nợ thủ công của nhóm cộng tác viên rất chậm, tốn nhiều chi phí điện thoại và khó kiểm soát chất lượng cuộc gọi. Báo cáo đối soát công nợ từ ngân hàng trả về trễ, dẫn đến việc gọi nhắc nhầm cho khách hàng đã thanh toán.
*   **Hành vi với SmartCollect AI:** Đăng nhập trang quản trị Web, tải file excel danh sách nợ cước lên hệ thống, chọn kịch bản "Nhắc cước lần 1", thiết lập khung giờ gọi từ 9h-11h và 14h-17h, nhấn "Bắt đầu chiến dịch". Hệ thống tự động gọi đồng thời hàng nghìn cuộc gọi và cập nhật số tiền thu hồi trực tiếp lên dashboard của chị.

---

## BƯỚC 4. PHÂN TÍCH ĐỐI THỦ CẠNH TRANH

| Sản phẩm | Điểm mạnh | Điểm yếu | Điều nên học hỏi |
| :--- | :--- | :--- | :--- |
| **Giải pháp Voice Bot Call Center thông thường** (Các nhà mạng cung cấp hạ tầng) | - Tự động gọi điện theo danh sách có sẵn.<br>- Chi phí thoại rẻ. | - Cuộc gọi mang tính một chiều (chỉ đọc kịch bản thu âm sẵn - IVR), không có khả năng đối thoại tương tác ngữ nghĩa.<br>- Không tích hợp luồng thanh toán QR code tự động sau cuộc gọi. | Khả năng xử lý hàng nghìn cuộc gọi đồng thời (Concurrency) ổn định trên hạ tầng viễn thông. |
| **Mô hình Call Center đòi nợ thuê** (Các công ty tài chính tiêu dùng) | - Nhân viên gọi điện trực tiếp thuyết phục, thương lượng linh hoạt. | - Chi phí nhân sự và vận hành cực kỳ cao.<br>- Rất dễ xảy ra vi phạm chuẩn mực đạo đức, đe dọa khách hàng gây scandal thương hiệu. | Các kỹ năng xử lý từ chối và kịch bản thương lượng hẹn ngày thanh toán của điện thoại viên. |
| **Các ứng dụng Ví điện tử / App Ngân hàng** (Nhắc nợ tự động) | - Tự động thông báo nợ cước qua thông báo đẩy (Push Notification) trên ứng dụng. | - Chỉ tiếp cận được nhóm khách hàng đã cài app và liên kết dịch vụ.<br>- Tỷ lệ đọc và bấm vào thông báo đẩy rất thấp do bị trôi tin. | Trải nghiệm thanh toán 1-click tích hợp sẵn nguồn tiền (ví, tài khoản ngân hàng). |

---

## BƯỚC 5. SO SÁNH TÍNH NĂNG (FEATURE COMPARISON MATRIX)

| Tính năng cốt lõi | IVR nhắc nợ tự động | Nhân viên gọi điện | App ngân hàng | VNPT SmartCollect AI (Đề xuất) |
| :--- | :---: | :---: | :---: | :---: |
| **Đối thoại tự nhiên bằng giọng nói AI** | Không | **Có** | Không | **Có (Voice Bot hiểu ngữ nghĩa tiếng Việt)** |
| **Tự động gửi VietQR cá nhân hóa tức thì** | Không | Không | Không | **Có (Tạo link thanh toán động qua SMS/Zalo)** |
| **Ghi nhận lịch hẹn thanh toán của khách** | Không | **Có** | Không | **Có (AI ghi nhận và lên lịch gọi lại tự động)** |
| **Đối soát cước tự động thời gian thực (Real-time)**| Không | Không | Có | **Có (API kết nối trực tiếp Billing & Bank)** |
| **Tự động dừng gọi khi đã thanh toán** | Không | Trễ 1 ngày | Có | **Có (Dừng cuộc gọi ngay khi nhận cổng báo có)** |
| **Báo cáo phân tích lý do chậm trả cước** | Không | Hạn chế | Không | **Có (AI phân loại lý do: Quên, Bận, Kế toán...)** |

---

## BƯỚC 6. PHÁT HIỆN KHOẢNG TRỐNG THỊ TRƯỜNG & CƠ HỘI NỘI BỘ

| Cơ hội cạnh tranh | Giá trị mang lại cho VNPT |
| :--- | :--- |
| **Kết hợp Voice Bot đàm thoại và SMS/Zalo VietQR động** | Chưa có giải pháp đòi nợ nào trên thị trường liên kết trực tiếp cuộc gọi thoại của AI với việc sinh mã thanh toán VietQR động cá nhân hóa gửi ngay qua SMS/Zalo trong thời gian thực. Việc này rút ngắn khoảng cách từ "nhận thức nợ cước" đến "hành động thanh toán" chỉ còn dưới 30 giây, loại bỏ hoàn toàn ma sát nhập liệu số tài khoản. |
| **Hệ thống tự động ngắt chiến dịch thông minh (Auto-Suppress)** | Khách hàng rất ức chế khi đã đóng tiền cước nhưng vẫn nhận được cuộc gọi đòi nợ do dữ liệu cập nhật chậm. Kết nối API thời gian thực với hệ thống Billing của VNPT và cổng thanh toán để tự động loại bỏ số thuê bao ra khỏi danh sách gọi ngay lập tức khi phát sinh giao dịch báo có, giúp bảo vệ trải nghiệm khách hàng tối đa. |

---

## BƯỚC 7. ĐỀ XUẤT Ý TƯỞNG THIẾT KẾ (PRODUCT CONCEPT)

*   **Product Concept:** **VNPT SmartCollect AI** là một giải pháp tự động hóa công nợ thông minh. Hệ thống quét dữ liệu nợ cước hàng ngày từ Billing, lập lịch gọi tối ưu bằng Voice Bot AI sử dụng giọng đọc tự nhiên (TTS) kết hợp nhận diện giọng nói (ASR) tiếng Việt. Khi khách hàng đồng ý thanh toán, hệ thống tự động sinh một đường link VietQR chứa chính xác mã hóa đơn và số tiền nợ, gửi ngay qua kênh Zalo OA hoặc SMS. Hệ thống tự động kiểm tra cổng ngân hàng và cập nhật gạch nợ trên Billing.
*   **UX Vision:** **"Frictionless Debt Resolution"** (Giải quyết công nợ không ma sát) - Trải nghiệm đòi nợ không gây cảm giác khó chịu. AI nói chuyện lịch sự, thấu cảm và cung cấp giải pháp thanh toán dễ dàng nhất (quét QR).
*   **UI Direction:** **Professional, Trustworthy & Action-Oriented (Navy Blue & Mint Green Theme)**.
    *   *Màu sắc:* Màu xanh dương đậm (Navy) thể hiện sự uy tín và bảo mật tài chính. Màu xanh bạc hà (Mint Green) đại diện cho dòng tiền lưu thông và trạng thái thanh toán thành công.
    *   *Bố cục:* Bảng điều khiển quản trị (Admin Dashboard) hiển thị các chỉ số tài chính trực quan: Tỷ lệ tiếp cận cuộc gọi, Tỷ lệ thu hồi nợ (Recovery Rate), Biểu đồ dòng tiền cước thu hồi theo ngày.
*   **Interaction Model:** **Conversation Flow Builder** - Trình thiết kế kịch bản cuộc gọi bằng giao diện kéo thả khối logic trực quan (Visual IVR Node Editor) giúp nhân viên vận hành dễ dàng điều chỉnh kịch bản nói chuyện của AI theo thực tế.

---

## BƯỚC 8. XÂY DỰNG USER JOURNEY (HÀNH TRÌNH TRẢI NGHIỆM)

| Giai đoạn | Hành động người dùng | Cảm xúc | Cơ hội cải thiện trải nghiệm (UX Opportunity) |
| :--- | :--- | :--- | :--- |
| **1. Awareness** | Khách hàng nhận cuộc gọi từ số định danh thương hiệu (Brandname) của VNPT báo nợ cước. | Hơi e dè, đề phòng cuộc gọi lừa đảo. | Hiển thị đúng tên định danh thương hiệu (Ví dụ: `VNPT_cskh`) trên màn hình điện thoại thay vì số lạ. |
| **2. Discovery** | Trò chuyện với AI, nghe AI báo số tiền nợ cước và thời hạn cần đóng tiền. | Bất ngờ vì giọng nói AI tự nhiên, lịch sự như người thật. | Sử dụng công nghệ giọng nói AI tự nhiên nhất (có ngắt nghỉ, lấy hơi) để tránh cảm giác máy móc robot. |
| **3. Onboarding** | Khách hàng xác nhận đồng ý đóng tiền và yêu cầu nhận hướng dẫn thanh toán. | Thuận tiện, sẵn sàng thực hiện. | AI phản hồi ngay: *"Dạ em vừa gửi mã QR thanh toán nhanh qua tin nhắn Zalo/SMS cho anh Nam rồi ạ"*. |
| **4. First Use** | Mở tin nhắn Zalo, click vào link ảnh QR, chụp màn hình hoặc lưu ảnh để quét trên app ngân hàng. | Dễ dàng, không cần nhập tay. | Sinh mã VietQR đạt chuẩn NAPAS 247 để mọi ứng dụng ngân hàng và ví điện tử Việt Nam đều quét được ngay. |
| **5. Regular Use** | Nhận được thông báo gạch nợ thành công trên điện thoại chỉ sau 5 giây chuyển khoản. | Cực kỳ an tâm, hài lòng. | Gửi tin nhắn cảm ơn tự động: *"VNPT đã nhận được thanh toán cước của quý khách. Cảm ơn quý khách đã tin dùng dịch vụ"*. |
| **6. Goal Completion**| Đường truyền internet của khách hàng không bị gián đoạn, công nợ được xóa bỏ trên hệ thống Billing. | Nhẹ nhõm, thoải mái. | Lưu trữ thói quen thanh toán để kỳ sau tự động gửi thông tin QR trước khi gọi điện nhắc cước. |
| **7. Retention** | Khách hàng đăng ký hình thức thanh toán tự động (Auto-debit) qua ví VNPT Money để không cần nhận cuộc gọi nhắc nợ kỳ sau. | Hoàn toàn gắn bó, trung thành. | Đề xuất đăng ký Auto-debit ngay trong tin nhắn cảm ơn thanh toán thành công. |

---

## BƯỚC 9. INFORMATION ARCHITECTURE (CẤU TRÚC THÔNG TIN)

```
VNPT SmartCollect AI Admin Portal
├── Dashboard (Tỷ lệ thu hồi nợ, doanh thu thu hồi, trạng thái cuộc gọi trực tiếp)
├── Campaign Manager (Quản lý các chiến dịch gọi nhắc nợ)
│   ├── Campaign Creator (Tạo chiến dịch mới, tải danh sách Excel nợ cước)
│   └── Campaign Schedule (Lập lịch gọi: ngày gọi, khung giờ vàng, tần suất gọi lại)
├── Voice Scenario Studio (Thiết kế kịch bản đàm thoại của AI)
│   ├── Scenario Canvas (Trình kéo thả kịch bản đối thoại Voice Bot)
│   └── TTS & Voice Library (Quản lý thư viện giọng đọc AI vùng miền)
├── Transactions & Billing (Quản lý giao dịch và đối soát)
│   ├── Payment Tracking (Theo dõi lịch sử thanh toán qua link QR)
│   └── Auto-Decline Register (Danh sách ngắt gọi tự động cho các số đã trả cước)
└── Call Logs & Audio Analytics (Nhật ký cuộc gọi và ghi âm đối thoại)
    ├── Call Transcript Viewer (Đọc nội dung và phân tích lý do khất nợ)
    └── Call Quality Auditing (Đánh giá mức độ hiểu câu hỏi của AI)
```

---

## BƯỚC 10. THIẾT KẾ SITEMAP

```
/ (Dashboard - Tổng quan công nợ & Hiệu quả thu hồi)
├── /campaigns (Quản lý chiến dịch gọi)
│   ├── /campaigns/create (Tạo chiến dịch nhắc nợ mới)
│   └── /campaigns/[id] (Chi tiết trạng thái chiến dịch đang chạy)
├── /scenarios (Trình biên tập kịch bản Voice Bot)
│   ├── /scenarios/editor (Không gian kéo thả sơ đồ kịch bản nói)
│   └── /scenarios/voices (Quản lý cài đặt giọng đọc AI)
├── /transactions (Theo dõi thanh toán hóa đơn)
│   └── /transactions/reconciliation (Đối soát giao dịch ngân hàng & Billing)
├── /call-logs (Lịch sử cuộc gọi)
│   └── /call-logs/[id] (Chi tiết đoạn ghi âm cuộc gọi + Transcript)
└── /settings (Cấu hình kết nối tổng đài SIP, cổng thanh toán, Billing API)
```

---

## BƯỚC 11. DANH SÁCH MÀN HÌNH CHÍNH

| Màn hình | Mục tiêu trải nghiệm | Thành phần chính |
| :--- | :--- | :--- |
| **1. Executive Billing Dashboard** | Giúp bộ phận kế toán cước nắm bắt ngay tiến độ thu cước và lượng dòng tiền thu hồi trong ngày. | - Biểu đồ phễu cuộc gọi (Tổng số -> Đã nghe -> Đồng ý thanh toán -> Đã quét QR -> Đã gạch nợ).<br>- Chỉ số tỷ lệ thu hồi nợ (Recovery Rate %).<br>- Biểu đồ nhiệt cuộc gọi thành công theo khung giờ trong ngày.<br>- Thống kê số lượng cuộc gọi bị lỗi kết nối hoặc khách hàng dập máy. |
| **2. Scenario Studio (Voice Flow Builder)** | Cho phép chuyên viên nghiệp vụ thiết kế luồng nói chuyện của AI dạng sơ đồ cây quyết định trực quan. | - Central Canvas để kéo thả các khối logic: `[Khối Bắt đầu]` -> `[Khối Chào hỏi]` -> `[Nhánh rẽ ý định: Đồng ý / Khất nợ / Từ chối]` -> `[Khối gửi SMS QR]`.<br>- Bảng cấu hình chi tiết cho từng khối bên phải (Nhập text để AI đọc, thiết lập các câu trả lời mẫu của khách hàng để AI nhận diện). |
| **3. Campaign Detail & Live Tracker** | Giám sát trạng thái thực thi của một chiến dịch gọi nhắc nợ đang diễn ra thời gian thực. | - Trạng thái cuộc gọi trực tiếp (Đang gọi, Đang đối thoại, Đã kết thúc).<br>- Danh sách chi tiết các thuê bao trong chiến dịch (Họ tên, Số tiền nợ, Trạng thái cuộc gọi, Trạng thái thanh toán: Đã gửi VietQR / Đã thanh toán).<br>- Nút tạm dừng (Pause) hoặc hủy chiến dịch khẩn cấp. |
| **4. Call Transcript & Audio Player** | Kiểm tra chi tiết lịch sử đàm thoại giữa AI và khách hàng để tinh chỉnh kịch bản. | - Trình phát âm thanh ghi âm cuộc gọi.<br>- Transcript hội thoại phân tích ý định (Intent Classification): Ví dụ AI nhận diện khách nói *"Mai tôi đóng"* thuộc intent `Hẹn thanh toán` và tự động cập nhật lịch hẹn đóng tiền lên CRM. |

---

## BƯỚC 12. USER FLOW (LUỒNG NGƯỜI DÙNG CHÍNH)

### Main Flow: AI Voice Bot gọi nhắc cước và gửi VietQR thanh toán
```
[Bắt đầu] Hệ thống tự động kích hoạt chiến dịch nhắc cước -> Quay số đến thuê bao
  │
  ▼
[Kết nối thành công] AI Voice Bot phát câu chào: "Dạ em chào anh Nam, em là Trợ lý thanh toán tự động của VNPT..."
  │
  ▼
[Thông báo cước] AI báo cước nợ: "...Em xin phép nhắc mình cước internet tháng này là 180.000đ hiện đã quá hạn đóng..."
  │
  ▼
[Đối thoại ý định] AI hỏi: "...Anh Nam có thể thanh toán hóa đơn này ngay hôm nay được không ạ?"
  │
  ▼
[Khách trả lời] Khách nói: "Được em, gửi thông tin tài khoản qua tin nhắn cho anh đi"
  │
  ▼
[AI nhận diện Intent] AI phân tích ý định thành công (Khách đồng ý thanh toán)
  │
  ▼
[Phản hồi cuộc thoại] AI nói: "Dạ vâng, em đã gửi mã QR thanh toán nhanh qua Zalo/SMS cho anh rồi ạ. Cảm ơn anh Nam." -> Cúp máy
  │
  ▼
[Gửi SMS/Zalo] Hệ thống tự động sinh link VietQR chứa sẵn số hóa đơn + Số tiền -> Gửi ngay đến số điện thoại khách hàng
  │
  ▼
[Khách thanh toán] Khách quét mã VietQR trên app Ngân hàng -> Giao dịch chuyển khoản thành công
  │
  ▼
[Đối soát Billing] Ngân hàng báo có -> API gạch nợ trên Billing -> Hệ thống tự động gửi tin nhắn xác nhận thanh toán thành công
```

### Alternative Flow: Khách hàng xin hẹn ngày đóng tiền (Khất nợ)
```
[Bắt đầu] AI gọi điện và thông báo số tiền nợ cước
  │
  ▼
[Khách phản hồi] Khách nói: "Anh đang đi công tác, cuối tuần này anh về anh đóng nhé"
  │
  ▼
[AI nhận diện Intent] AI phân tích và phân loại intent thuộc nhóm: [Hẹn thanh toán]
  │
  ▼
[Xác nhận ngày hẹn] AI nói: "Dạ em ghi nhận anh Nam hẹn thanh toán trước ngày Chủ nhật tuần này ạ. Hệ thống sẽ tạm thời giữ kết nối mạng cho anh đến hết ngày hẹn nhé."
  │
  ▼
[Cập nhật CRM] Hệ thống tự động lưu lịch hẹn (28/06/2026) lên hệ thống CRM/Billing của VNPT
  │
  ▼
[Kiểm soát chiến dịch] Số điện thoại của anh Nam được tự động chuyển vào danh sách "Tạm hoãn gọi nhắc nợ" đến hết ngày 28/06.
  │
  ▼
[Quá hạn hẹn] Nếu đến ngày 29/06 hệ thống vẫn chưa ghi nhận thanh toán -> Tự động đưa số anh Nam trở lại hàng đợi gọi nhắc cước lần 2.
```

---

## BƯỚC 13. ĐỀ XUẤT WIREFRAME CẤP CAO (MÀN HÌNH SCENARIO STUDIO)

*   **Header Bar:**
    *   Left: Tên kịch bản (`Nhắc cước Internet lần 1 - Khách cá nhân`), trạng thái kịch bản (`Đang hoạt động`).
    *   Center: Nút `Chạy thử nghiệm (Simulate Flow)` và nút `Lưu kịch bản`.
    *   Right: Nút `Xuất JSON` và cấu hình tham số mô hình ngôn ngữ (Độ nhạy nhận diện giọng nói).
*   **Left Tool Palette (Thư viện các khối kéo thả):**
    *   `Khối thoại (Speech Block):` AI nói văn bản (TTS).
    *   `Khối nhận diện (Collect Input):` Chờ nghe khách nói và phân loại ý định (Intent).
    *   `Khối logic (Logic Decision):` Kiểm tra số tiền nợ, kiểm tra số ngày quá hạn để rẽ nhánh kịch bản.
    *   `Khối hành động (Action Block):` Gửi SMS, Gửi Zalo VietQR, Gạch nợ Billing, Tạo lịch hẹn gọi lại.
*   **Central Canvas (Khu vực vẽ sơ đồ):**
    *   Không gian làm việc vô cực (Infinity Canvas), cho phép dùng chuột kéo thả các khối, kết nối các đầu nút của khối bằng đường vẽ mũi tên định hướng.
    *   Ví dụ: Mũi tên từ đầu ra `Đồng ý` của Khối nhận diện nối sang Khối hành động `Gửi Zalo VietQR`. Mũi tên từ đầu ra `Bận/Gọi lại` nối sang Khối hành động `Đặt lịch gọi lại sau 2 giờ`.
*   **Right Inspector Panel (Cấu hình thuộc tính khối đang chọn):**
    *   Khi click vào một khối trên Canvas, bảng bên phải sẽ hiển thị cấu hình:
    *   Ví dụ click Khối thoại: Khung nhập văn bản soạn nội dung nói (hỗ trợ chèn biến động như `{Ten_Khach_Hang}`, `{So_Tien_No}`). Tùy chọn giọng đọc (`Giọng miền Bắc - Nam`).

---

## BƯỚC 14. ĐÁNH GIÁ UX THEO HEURISTIC (10 NGUYÊN TẮC NIELSEN)

1.  **Visibility of System Status (Trạng thái hệ thống rõ ràng):**
    *   *Mức độ đáp ứng:* Cao. Dashboard hiển thị thời gian thực số lượng cuộc gọi đang được AI xử lý đồng thời, giúp quản trị viên biết hệ thống có bị quá tải hay không.
2.  **Match Between System and Real World (Gần gũi thực tế):**
    *   *Mức độ đáp ứng:* Cao. Sử dụng các thuật ngữ tài chính hành chính quen thuộc của kế toán cước: Công nợ, Hóa đơn quá hạn, Gạch nợ cước, Cổng thanh toán, Đối soát dòng tiền.
3.  **User Control and Freedom (Quyền kiểm soát của người dùng):**
    *   *Mức độ đáp ứng:* Rất cao.
    *   *Đối với khách hàng:* Cho phép dập máy bất cứ lúc nào để từ chối cuộc gọi của AI.
    *   *Đối với nhân viên:* Nút Tạm dừng chiến dịch (Pause Campaign) khẩn cấp cho phép dừng ngay lập tức hàng nghìn cuộc gọi đang xếp hàng nếu phát hiện lỗi kịch bản.
4.  **Consistency and Standards (Nhất quán & Tiêu chuẩn):**
    *   *Mức độ đáp ứng:* Cao. Các ký hiệu trạng thái cuộc gọi được đồng bộ hóa màu sắc tiêu chuẩn viễn thông: Xanh lá - Đang đàm thoại, Xám - Đợi gọi, Đỏ - Thuê bao bận/không liên lạc được.
5.  **Error Prevention (Phòng tránh lỗi):**
    *   *Mức độ đáp ứng:* Cực kỳ cao.
    *   *Rủi ro:* Hệ thống gọi điện nhắc nợ cho khách hàng đã đóng tiền cước trước đó vài phút do dữ liệu đối soát chậm, gây trải nghiệm cực kỳ tiêu cực.
    *   *Giải pháp phòng lỗi:* Thiết kế module **Auto-Suppress** quét liên tục cổng thanh toán ngân hàng 24/7. Trước khi bấm số gọi cho bất kỳ thuê bao nào, hệ thống kiểm tra trạng thái cước trên Billing lại một lần nữa ở mili-giây cuối cùng. Nếu ghi nhận đã đóng cước, hệ thống lập tức hủy cuộc gọi.
6.  **Recognition Rather Than Recall (Nhận diện thay vì ghi nhớ):**
    *   *Mức độ đáp ứng:* Cao. Khi khách hàng nhận được tin nhắn VietQR, nội dung tin nhắn hiển thị đầy đủ thông tin hóa đơn, giúp khách hàng nhận biết ngay mà không cần nhớ số tài khoản thanh toán của VNPT.
7.  **Flexibility and Efficiency of Use (Linh hoạt & Hiệu quả):**
    *   *Mức độ đáp ứng:* Cao. Trình thiết kế kịch bản kéo thả cho phép nhân viên kế toán tự tinh chỉnh câu từ nói chuyện của AI rất nhanh chóng khi có chương trình khuyến mãi mới mà không cần nhờ lập trình viên can thiệp.
8.  **Aesthetic and Minimalist Design (Thẩm mỹ & Tối giản):**
    *   *Mức độ đáp ứng:* Cao. Bố cục bảng điều khiển gọn gàng, hiển thị nổi bật các chỉ số dòng tiền quan trọng nhất bằng biểu đồ trực quan, ẩn bớt các logs log cuộc gọi kỹ thuật sâu.
9.  **Help Users Recover From Errors (Hỗ trợ sửa lỗi):**
    *   *Mức độ đáp ứng:* Khá. Nếu file danh sách excel tải lên bị sai định dạng cột, hệ thống chỉ ra chính xác dòng bị lỗi và cung cấp file mẫu chuẩn để tải về chỉnh sửa.
10. **Help and Documentation (Trợ giúp):**
    *   *Mức độ đáp ứng:* Khá. Tích hợp các tooltip hướng dẫn nhanh cách sử dụng bên cạnh các khối kéo thả của Scenario Studio.

---

## BƯỚC 15. ĐÁNH GIÁ KHẢ NĂNG SỬ DỤNG (USABILITY ASSESSMENT)

*   **Learnability (Khả năng học hỏi):** **8.5/10** (Nhân viên vận hành mất khoảng 2 tiếng đào tạo để nắm vững cách tạo chiến dịch và cấu hình kịch bản đàm thoại).
*   **Efficiency (Hiệu suất sử dụng):** **9.9/10** (Năng suất nhắc nợ tăng gấp 50 lần so với đội ngũ con người gọi thủ công, thực hiện hàng chục nghìn cuộc gọi đồng thời chỉ trong 1 giờ).
*   **Accessibility (Khả năng tiếp cận):** **8.5/10** (Tin nhắn chứa mã VietQR gửi qua Zalo/SMS được tối ưu hiển thị rõ ràng trên mọi loại thiết bị di động từ smartphone đến điện thoại phổ thông).
*   **Satisfaction (Mức độ hài lòng):** **9.0/10** (Khách hàng hài lòng vì nhận được phương thức đóng cước nhanh gọn bằng mã QR, giảm bớt ma sát nộp cước rườm rà).

---

## BƯỚC 16. PHÂN TÍCH RỦI RO UX & GIẢI PHÁP ĐỀ XUẤT

| Rủi ro trải nghiệm | Mức độ | Giải pháp đề xuất |
| :--- | :---: | :--- |
| **"Over-calling" (Gọi làm phiền quá nhiều):** Hệ thống AI gọi điện lặp đi lặp lại nhiều lần cho một thuê bao khi họ không nhấc máy, gây ức chế cực độ cho khách hàng. | **Cao** | Cài đặt giới hạn tần suất gọi nghiêm ngặt: *Tối đa gọi 2 lần/ngày và không quá 3 lần/tuần* cho một thuê bao. Không gọi vào các khung giờ nghỉ ngơi (trước 8h sáng, từ 12h-13h30 trưa, và sau 20h tối). |
| **Rủi ro nghi ngờ lừa đảo tài chính:** Khách hàng lo ngại cuộc gọi Voice Bot và link QR gửi qua SMS là giả mạo để chiếm đoạt tiền. | **Cao** | 1. Bắt buộc hiển thị tên định danh thương hiệu (Brandname) của VNPT khi gọi điện thoại (Voice Brandname).<br>2. Gửi mã QR qua tài khoản Zalo Official Account (Zalo OA) đã được tích xác minh chính chủ của VNPT. |
| **Khách hàng lớn tuổi không biết quét mã QR:** Gây khó khăn cho đối tượng người lớn tuổi không sử dụng mobile banking. | **Medium** | Thiết kế kịch bản AI thông minh: Nếu khách hàng phản hồi không biết quét mã QR, AI sẽ tự động đề xuất: *"Dạ, anh/chị có thể ra cửa hàng VNPT gần nhất hoặc các điểm thu hộ như WinMart, Thế Giới Di Động đọc số điện thoại để nộp tiền cước ạ"*. |

---

## BƯỚC 17. ƯU TIÊN PHÁT TRIỂN MVP (MOSCOW)

### Must Have (Bắt buộc phải có)
*   Mô hình Voice Bot AI hội thoại tiếng Việt (chào hỏi, báo nợ cước, nhận diện ý định đồng ý/khất nợ).
*   Hệ thống quản lý chiến dịch (Campaign Manager) cho phép tải danh sách excel nợ cước lên và lập lịch gọi tự động.
*   Trình tự động sinh và gửi link ảnh VietQR động cá nhân hóa qua SMS/Zalo.
*   Cơ chế Auto-Suppress: Tự động ngắt cuộc gọi ngay khi khách hàng hoàn tất thanh toán cước trên Billing.

### Should Have (Nên có)
*   Scenario Studio: Trình thiết kế kịch bản kéo thả trực quan No-code Node Editor.
*   Nhận diện và xử lý kịch bản xin hẹn ngày thanh toán (Khất nợ) và tự động đồng bộ ngày hẹn lên CRM.
*   Tích hợp Zalo OA chính chủ để gửi tin nhắn ảnh mã QR trực tiếp thay vì link text qua SMS.

### Could Have (Có thể có sau)
*   Phân tích giọng điệu phản hồi để dự đoán khả năng bùng nợ (Churn/Bad debt prediction).
*   Tính năng đề xuất và đăng ký thanh toán tự động Auto-debit trực tiếp trong luồng thanh toán hóa đơn.

---

## BƯỚC 18. ROADMAP PHÁT TRIỂN

*   **Phase 1 (Tháng 1-3) - Chạy PoC & Thử nghiệm hiệu quả thu hồi (MVP):**
    *   Hoàn thiện mô hình Voice Bot đối thoại nhắc cước cơ bản và tích hợp cổng VietQR.
    *   Chạy thử nghiệm giới hạn trên danh sách 10.000 khách hàng quá hạn cước Internet tại một quận ở Hà Nội.
    *   Đo lường các chỉ số: Tỷ lệ nhấc máy, Tỷ lệ chuyển đổi quét mã thanh toán, Tỷ lệ giảm chi phí nhân sự gọi nợ.
*   **Phase 2 (Tháng 4-6) - Tinh chỉnh kịch bản & Mở rộng quy mô:**
    *   Phát triển giao diện kéo thả kịch bản Scenario Studio.
    *   Tích hợp hệ thống quản lý lịch hẹn (Khất nợ) đồng bộ thời gian thực với CRM.
    *   Mở rộng triển khai cho toàn bộ khách hàng cước cá nhân Internet/MyTV trên địa bàn Hà Nội và TP.HCM.
*   **Phase 3 (Tháng 7-12) - Nhân rộng toàn quốc & Thương mại hóa B2B:**
    *   Triển khai toàn diện cho 63 tỉnh/thành phố trên cả nước cho cả dịch vụ di động trả sau VinaPhone.
    *   Đóng gói giải pháp dưới dạng sản phẩm SaaS thương mại để bán cho các doanh nghiệp cung cấp dịch vụ tiện ích khác (Điện, Nước, Phí chung cư, Trả góp tài chính).

---

## BƯỚC 19. UX SCORECARD (ĐÁNH GIÁ CHẤT LƯỢNG)

| Tiêu chí | Điểm số (Thang 10) | Nhận xét chi tiết |
| :--- | :---: | :--- |
| **User Value** (Giá trị cho người dùng) | 9.0/10 | Giúp khách hàng thanh toán cước nhanh nhất bằng QR code, tránh bị cắt dịch vụ một cách tinh tế, lịch sự. |
| **Business Value** (Giá trị kinh doanh) | 10.0/10 | Cắt giảm tới 80% chi phí gọi nhắc nợ cước thủ công và đẩy nhanh tốc độ thu hồi dòng tiền cước hàng tháng. |
| **Usability** (Khả năng sử dụng) | 8.5/10 | Trình thiết kế kịch bản kéo thả giúp chuyên viên kế toán vận hành cực kỳ dễ dàng. |
| **Accessibility** (Khả năng tiếp cận) | 9.0/10 | Phương thức quét VietQR cực kỳ phổ biến, dễ dàng sử dụng trên mọi ứng dụng ngân hàng tại Việt Nam. |
| **Scalability** (Khả năng mở rộng) | 9.5/10 | Hệ thống dễ dàng xử lý hàng triệu cuộc gọi nhắc cước mỗi ngày vào các đợt cao điểm khóa cước. |
| **Innovation** (Tính đổi mới sáng tạo) | 9.0/10 | Khép kín chuỗi quy trình từ "Cuộc gọi nhắc nhở AI" sang "Thanh toán QR di động" tức thì. |
| **Competitive Advantage** (Lợi thế cạnh tranh) | 9.5/10 | Việc tích hợp sâu thời gian thực với cổng Billing nội bộ của VNPT là rào cản độc quyền đối với các nhà cung cấp ngoài. |

**TỔNG ĐIỂM UX SCORE: 9.2/10**

---

## BƯỚC 20. KẾT LUẬN CHUYÊN GIA

*   **Mức độ khả thi về mặt kỹ thuật:** **RẤT CAO**. Công nghệ Voice Bot hội thoại và sinh mã thanh toán VietQR động đều là những công nghệ đã được chứng minh hiệu quả và hoàn toàn làm chủ được tại Việt Nam. Điểm mấu chốt nằm ở việc tích hợp API thời gian thực với Billing để gạch nợ tức thì và ngắt cuộc gọi tự động (Auto-suppress) để tránh làm phiền khách hàng.
*   **Mức độ cạnh tranh trên thị trường:** **TRUNG BÌNH**. Có một số đơn vị cung cấp Voice Bot trên thị trường nhưng hầu hết chỉ bán hạ tầng tổng đài đài thoại (SIP Trunk/API), chưa có bên nào xây dựng một giải pháp quản lý công nợ khép kín tích hợp VietQR động dành riêng cho nghiệp vụ thu cước dịch vụ định kỳ.
*   **Khuyến nghị đầu tư:** **ĐẶC BIỆT KHUYẾN NGHỊ TRIỂN KHAI NGAY**. Đây là bài toán thực tế nhất, giải quyết trực tiếp bài toán tài chính công nợ và dòng tiền của các đơn vị thành viên VNPT (VNPT-Net, VNPT-Media, VNPT-VinaPhone) và có thể mang lại hiệu quả tiết kiệm hàng tỷ đồng chi phí vận hành ngay trong tháng đầu tiên áp dụng.
