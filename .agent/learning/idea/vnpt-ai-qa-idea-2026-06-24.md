# Báo cáo Phân tích Chiến lược & Đề xuất Ý tưởng Sản phẩm (Product Discovery) - VNPT AI-QA (Hệ thống Giám sát & Phân tích Chất lượng Cuộc gọi Tổng đài Thông minh)

- **Tên ý tưởng sản phẩm:** VNPT AI-QA (AI-powered Call Quality Assurance & Speech Analytics)
- **Mục tiêu:** Tự động hóa 100% quy trình đánh giá chất lượng cuộc gọi của tổng đài viên CSKH/Sales, phát hiện lỗi nghiệp vụ, phân tích cảm xúc khách hàng thời gian thực và tự động chấm điểm theo tiêu chí doanh nghiệp.
- **Ngày thực hiện:** 24/06/2026
- **Chuyên gia thực hiện:** Senior Product Designer, Product Manager & UX Strategist (.agent)
- **Dựa trên quy trình:** [idea.md](file:///Volumes/CHAOS/VNPT/AI/CX/.agent/skills/idea.md)

---

## BƯỚC 1. PHÂN TÍCH SẢN PHẨM (PRODUCT OVERVIEW)

| Nội dung | Phân tích chi tiết ý tưởng |
| :--- | :--- |
| **Sản phẩm đề xuất** | **VNPT AI-QA** - Nền tảng phân tích âm thanh (Speech Analytics) và tự động hóa giám sát chất lượng (Quality Assurance) dành cho các trung tâm tổng đài (Contact Centers) quy mô lớn. |
| **Bài toán cần giải quyết** | 1. **Tỷ lệ kiểm thử quá thấp:** Bộ phận QA thủ công chỉ có thể nghe và chấm điểm tối đa **1 - 2%** tổng số cuộc gọi của điện thoại viên (Agents) do giới hạn nhân lực, bỏ sót 98% cuộc gọi còn lại.<br>2. **Báo cáo trễ (Time-to-Insight kéo dài):** Thời gian từ lúc cuộc gọi phát sinh lỗi đến khi QA phát hiện và đào tạo lại Agent thường trễ từ **1 - 2 tuần**, khiến trải nghiệm tiêu cực của khách hàng tiếp tục lặp lại.<br>3. **Đánh giá mang tính cảm tính:** Các QA chuyên viên chấm điểm thủ công dễ bị ảnh hưởng bởi cảm xúc cá nhân, dẫn đến sự thiếu công bằng giữa các Agents.<br>4. **Lãng phí dữ liệu thoại khổng lồ:** Hàng triệu cuộc gọi lưu trữ dưới dạng file ghi âm tĩnh `.wav` chỉ để lưu trữ mà không được khai thác thông tin phản hồi của thị trường. |
| **Mục tiêu người dùng** | 1. **QA Specialist:** Tự động hóa chấm điểm cuộc gọi, chỉ tập trung nghe các cuộc gọi bị AI cảnh báo lỗi nghiêm trọng.<br>2. **Agent:** Xem báo cáo chấm điểm chi tiết, hiểu rõ mình sai ở đâu (ví dụ: quên chào khách, tư vấn sai giá gói cước) để tự cải thiện.<br>3. **Manager:** Nắm bắt tổng quan hiệu suất tổng đài, phát hiện nhanh các cuộc gọi có rủi ro pháp lý/khiếu nại leo thang. |
| **Mục tiêu doanh nghiệp** | 1. Giám sát **100%** cuộc gọi khách hàng thay vì 2%.<br>2. Cắt giảm 70% chi phí nhân sự và thời gian vận hành bộ phận QA thủ công.<br>3. Nâng cao chỉ số hài lòng khách hàng (CSAT) và chỉ số đo lường lòng trung thành (NPS).<br>4. Phát hiện cơ hội kinh doanh (bán chéo/Upsell) bị bỏ lỡ trong cuộc hội thoại. |
| **Giá trị cốt lõi** | **"Evaluate 100% of Calls. Coach Agents in Real-Time."** (Đánh giá 100% cuộc gọi. Đào tạo điện thoại viên theo thời gian thực). |

---

## BƯỚC 2. XÁC ĐỊNH NHU CẦU NGƯỜI DÙNG

| Nhóm đối tượng | Functional Needs (Hành vi/Chức năng) | Emotional Needs (Cảm xúc) | Social Needs (Vị thế/Xã hội) |
| :--- | :--- | :--- | :--- |
| **Chuyên viên giám sát chất lượng (QA Specialist)** | - Cần bộ lọc thông minh để lọc nhanh các cuộc gọi có cảm xúc khách hàng tiêu cực (giận dữ, phàn nàn).<br>- Cần AI tự động điền bảng điểm đánh giá (Scorecard).<br>- Xuất báo cáo hiệu suất tổng đài nhanh chóng. | - Cảm thấy thoải mái khi giảm tải khối lượng nghe ghi âm tĩnh lặp đi lặp lại hàng ngày.<br>- Yên tâm vì kết quả chấm điểm khách quan. | - Khẳng định vai trò tư vấn chiến lược nâng cao chất lượng thay vì làm công việc nhập liệu thủ công. |
| **Điện thoại viên tổng đài (Call Center Agent)** | - Xem kết quả chấm điểm của từng cuộc gọi ngay trong ngày.<br>- Nghe lại chính xác đoạn hội thoại bị AI gắn cờ lỗi (flagged).<br>- Gửi phản hồi/khiếu nại nếu thấy điểm số chưa hợp lý. | - Cảm thấy công bằng và minh bạch trong việc đánh giá KPI.<br>- Giảm áp lực căng thẳng khi bị giám sát đột xuất. | - Được công nhận năng lực làm việc dựa trên kết quả toàn diện của 100% cuộc gọi. |
| **Giám đốc trung tâm CSKH (Contact Center Director)** | - Theo dõi xu hướng biến động chỉ số chất lượng dịch vụ (Service Level).<br>- Phát hiện các chủ đề (Topics) khách hàng đang phàn nàn nhiều nhất.<br>- Theo dõi hiệu quả của các chiến dịch bán hàng qua điện thoại. | - Kiểm soát tốt mọi rủi ro khủng hoảng truyền thông từ sớm.<br>- Cảm thấy tự tin trước Ban giám đốc về chất lượng phục vụ khách hàng. | - Nâng cao uy tín quản lý, đưa trung tâm chăm sóc khách hàng trở thành đơn vị đi đầu về chuyển đổi số. |

---

## BƯỚC 3. XÂY DỰNG USER PERSONA

### Persona 1: Chị Khánh Chi (28 tuổi) - QA Team Leader tại Trung tâm CSKH VNPT
*   **Mục tiêu:** Giám sát chất lượng cuộc gọi của nhóm 50 điện thoại viên, đảm bảo tính tuân thủ kịch bản bán hàng và thái độ phục vụ khách hàng.
*   **Nhu cầu:** Cần một công cụ tự động phát hiện các cuộc gọi có từ khóa nhạy cảm (như *"khiếu nại"*, *"chửi bậy"*, *"hủy dịch vụ"*) để vào nghe và xử lý can thiệp kịp thời.
*   **Pain Point:** Mỗi ngày nhóm của chị phát sinh hơn 5.000 cuộc gọi. Chị và 2 nhân viên QA chỉ có thể nghe ngẫu nhiên khoảng 50 cuộc gọi/ngày. Rất lo lắng vì có thể bỏ lọt các cuộc gọi tư vấn sai gói cước của nhân viên mới.
*   **Hành vi với VNPT AI-QA:** Đăng nhập hệ thống mỗi buổi sáng, xem danh sách cuộc gọi có điểm cảnh báo rủi ro cao (Risk Score > 80%) do AI gắn cờ, click nghe trực tiếp đoạn hội thoại vi phạm nghiệp vụ để gửi biên bản nhắc nhở điện thoại viên.

### Persona 2: Anh Đức Huy (22 tuổi) - Điện thoại viên Hỗ trợ Kỹ thuật ADSL/MyTV
*   **Mục tiêu:** Đạt KPI điểm chất lượng cuộc gọi trên 90 điểm để nhận đầy đủ lương hiệu quả công việc tháng.
*   **Nhu cầu:** Cần biết chính xác các cuộc gọi bị trừ điểm của mình vi phạm lỗi gì để rút kinh nghiệm lập tức, thay vì đợi đến cuối tháng họp tổng kết mới biết.
*   **Pain Point:** Thường xuyên bị trừ điểm QA vì lỗi "thiếu câu chào quy chuẩn" hoặc "ngắt lời khách hàng" nhưng không nhớ rõ cuộc gọi nào để đối chất.
*   **Hành vi với VNPT AI-QA:** Truy cập cổng thông tin cá nhân (Agent Portal), click vào các cuộc gọi bị AI đánh giá điểm thấp dưới 80, đọc đoạn text transcript được bôi đỏ lỗi nghiệp vụ và tự cải thiện trong các cuộc gọi tiếp theo.

---

## BƯỚC 4. PHÂN TÍCH ĐỐI THỦ CẠNH TRANH

| Sản phẩm | Điểm mạnh | Điểm yếu | Điều nên học hỏi |
| :--- | :--- | :--- | :--- |
| **CallMiner Eureka** (Best Practice quốc tế) | - Phân tích Speech-to-Text cực mạnh với hơn 20 ngôn ngữ.<br>- Bộ phân tích cảm xúc (Sentiment Analysis) dựa trên ngữ điệu và tốc độ nói.<br>- Công cụ thiết kế biểu mẫu chấm điểm (Scorecard Builder) rất linh hoạt. | - Chi phí đầu tư hạ tầng và bản quyền cực lớn.<br>- Xử lý tiếng Việt vùng miền (Bắc, Trung, Nam) và tiếng lóng bản địa còn nhiều sai sót.<br>- Triển khai cloud nước ngoài khó đáp ứng quy định bảo mật viễn thông Việt Nam. | Giao diện hiển thị sóng âm kết hợp văn bản dịch (Audio Waveform + Sync Transcript) giúp QA click vào text để nhảy đến file ghi âm. |
| **Nice Nexidia** | - Phân tích dữ liệu cuộc gọi quy mô cực lớn theo thời gian thực (Real-time Speech Analytics).<br>- Tích hợp tốt với các tổng đài Avaya, Cisco. | - Triển khai phức tạp, mất nhiều tháng để cài đặt cấu hình.<br>- Yêu cầu phần cứng máy chủ rất cao nếu chạy local. | Khả năng tự động phát hiện xu hướng (Topic Modeling) dựa trên các từ khóa nổi bật xuất hiện đột biến trong ngày. |
| **Giải pháp Speech-to-Text đơn lẻ** (Trong nước) | - Chuyển đổi giọng nói tiếng Việt chính xác cao.<br>- Giá thành rẻ, triển khai linh hoạt. | - Chỉ dừng lại ở việc chuyển giọng nói thành văn bản, không có nghiệp vụ giám sát QA (chấm điểm, thiết lập biểu mẫu, phân tích cảm xúc, quản lý tác vụ đào tạo). | Công nghệ nhận diện giọng nói tiếng Việt tối ưu cho các môi trường điện thoại băng thông hẹp (8kHz). |

---

## BƯỚC 5. SO SÁNH TÍNH NĂNG (FEATURE COMPARISON MATRIX)

| Tính năng cốt lõi | Công cụ STT đơn lẻ | Nice Nexidia | CallMiner | VNPT AI-QA (Đề xuất) |
| :--- | :---: | :---: | :---: | :---: |
| **Chuyển thoại thành văn bản tiếng Việt 8kHz** | **Có** | Hạn chế | Hạn chế | **Có (Chuyên sâu giọng vùng miền Việt Nam)** |
| **Tự động chấm điểm theo Scorecard tùy chỉnh** | Không | Có | **Có** | **Có (Trình thiết kế Scorecard kéo thả)** |
| **Đồng bộ hóa Audio Waveform & Text Transcript** | Hạn chế | Có | **Có** | **Có (Click chữ nhảy đến đoạn âm thanh)** |
| **Phân tích cảm xúc đa kênh (Sentiment Analysis)** | Không | **Có** | **Có** | **Có (Kết hợp từ khóa + âm vực giọng nói)** |
| **Cảnh báo cuộc gọi rủi ro thời gian thực (Real-time)**| Không | Có | Có | **Có (Hiển thị alert tức thì trên màn hình sếp)** |
| **Quản trị luồng công việc đào tạo (Coaching Workflow)**| Không | Hạn chế | Có | **Có (Tạo task đào tạo trực tiếp từ file lỗi)** |

---

## BƯỚC 6. PHÁT HIỆN KHOẢNG TRỐNG THỊ TRƯỜNG & CƠ HỘI NỘI BỘ

| Cơ hội cạnh tranh | Giá trị mang lại cho VNPT |
| :--- | :--- |
| **Speech-to-Text tiếng Việt chuyên sâu cho kênh điện thoại (8kHz)** | Chất lượng âm thanh cuộc gọi tổng đài thường bị nén rất sâu (tần số 8kHz) khiến các mô hình nhận diện giọng nói thông dụng quốc tế bị giảm độ chính xác xuống dưới 50%. Sở hữu mô hình AI nhận diện tiếng Việt tối ưu cho băng thông hẹp, phân biệt được giọng Bắc - Trung - Nam và nhận diện đúng các tên riêng sản phẩm dịch vụ VNPT sẽ tạo ra lợi thế cạnh tranh cốt lõi. |
| **Tích hợp quy trình đào tạo (Closed-loop Coaching)** | Hầu hết các công cụ quốc tế chỉ tập trung chỉ ra lỗi (Analytics) mà thiếu mô-đun quản lý hành động khắc phục (Coaching). Thiết kế một hệ thống khép kín: *Phát hiện lỗi -> Gắn cờ -> Tạo task đào tạo Agent -> Kiểm tra lại hiệu quả sau đào tạo* sẽ giúp doanh nghiệp tối ưu chất lượng dịch vụ triệt để. |

---

## BƯỚC 7. ĐỀ XUẤT Ý TƯỞNG THIẾT KẾ (PRODUCT CONCEPT)

*   **Product Concept:** **VNPT AI-QA** là hệ thống phân tích đàm thoại thông minh (Speech Analytics Platform) hoạt động trên nền tảng Web-app. Hệ thống kết nối trực tiếp với tổng đài (IP-PBX) để tự động thu thập file ghi âm cuộc gọi sau khi kết thúc, sử dụng AI chuyển đổi sang văn bản, chấm điểm tự động dựa trên bộ quy tắc (Scorecards) và phân phối các cuộc gọi lỗi về màn hình của kiểm soát viên chất lượng.
*   **UX Vision:** **"Fast-forward to the Friction"** (Bỏ qua đoạn thừa, đi thẳng tới điểm lỗi) - QA không cần nghe toàn bộ cuộc gọi kéo dài 10 phút. Giao diện hiển thị trực quan các điểm bất thường (khoảng lặng dài, ngắt lời nhau, cảm xúc tiêu cực, từ khóa nhạy cảm) dưới dạng các vạch màu trên dòng thời gian (Waveform Timeline), cho phép QA click để nghe đúng đoạn đó trong 3 giây.
*   **UI Direction:** **Modern Tech Dark & Vivid Status (Deep Slate Charcoal & Electric Accents)**.
    *   *Màu sắc:* Nền xám đen tối (Deep Slate) tạo cảm giác phòng điều hành công nghệ cao, giúp QA tập trung cao độ khi làm việc liên tục nhiều giờ. Các màu cảnh báo (Đỏ - Lỗi nặng, Vàng - Cảnh báo, Xanh lá - Đạt chuẩn) được hiển thị sắc nét để hướng sự chú ý.
    *   *Bố cục:* Split-screen ba phân vùng: Cột trái (Danh sách cuộc gọi cần duyệt), Cột giữa (Trình phát âm thanh đồng bộ text transcript), Cột phải (Bảng chấm điểm Scorecard chi tiết của AI).
*   **Interaction Model:** **Interact with Waveform** - Cho phép người dùng bôi đen một đoạn text trên transcript để tự động cắt nhỏ file âm thanh tạo thành tư liệu đào tạo (Coaching clip) gửi cho Agent.

---

## BƯỚC 8. XÂY DỰNG USER JOURNEY (HÀNH TRÌNH TRẢI NGHIỆM)

| Giai đoạn | Hành động người dùng | Cảm xúc | Cơ hội cải thiện trải nghiệm (UX Opportunity) |
| :--- | :--- | :--- | :--- |
| **1. Awareness** | QA Team Leader nghe giới thiệu về hệ thống AI tự động chấm điểm 100% cuộc gọi. | Hoài nghi về độ chính xác của AI. | Tổ chức chương trình đối chiếu: Để AI và QA người cùng chấm điểm 10 cuộc gọi, chứng minh độ tương đồng kết quả đạt > 90%. |
| **2. Discovery** | Trưởng bộ phận QA đăng nhập hệ thống, cấu trúc bộ quy tắc chấm điểm (Scorecard) đầu tiên. | Lo lắng vì sợ cấu hình phức tạp. | Cung cấp sẵn các mẫu Scorecard chuẩn ngành (Viễn thông, Ngân hàng, Bán hàng) để dùng ngay chỉ sau 3 cú click. |
| **3. Onboarding** | Chuyên viên QA lần đầu truy cập danh sách cuộc gọi cần xử lý. | Bất ngờ vì giao diện trực quan, hiển thị rõ cuộc gọi nào lỗi nặng cần nghe trước. | Thiết kế hệ thống nhãn cảnh báo (Tags) rõ ràng: `[Khách tức giận]` `[Tư vấn sai giá]` `[Agent nói tục]`. |
| **4. First Use** | QA mở một cuộc gọi bị AI cảnh báo lỗi, click vào dòng text bị bôi đỏ để nghe lại đoạn âm thanh. | Thích thú ("Wow") vì tìm đúng đoạn lỗi lập tức mà không cần nghe hết cả cuộc gọi. | Tối ưu hóa tính năng hiển thị tốc độ phát (Playback Speed) và tự động cuộn text theo nhịp nói (Auto-scroll). |
| **5. Regular Use** | Chấm điểm hàng trăm cuộc gọi mỗi ngày, tạo các ghi chú đào tạo gửi trực tiếp cho Agent. | Tự tin, làm chủ công việc tốt hơn. | Bổ sung tính năng phím tắt (Hotkeys) để chấm điểm nhanh không cần dùng chuột. |
| **6. Goal Completion**| Bộ phận hoàn thành đánh giá 100% cuộc gọi trong tháng, chỉ số lỗi vi phạm kịch bản giảm 40%. | Cực kỳ hài lòng và tự hào. | Xuất báo cáo đẹp mắt dạng PDF/PPTX chỉ bằng 1-click để QA Leader báo cáo trong cuộc họp Ban Giám đốc. |
| **7. Retention** | Đề xuất ban giám đốc nâng cấp thêm tính năng phân tích thời gian thực (Real-time Alerting) cho các cuộc gọi VIP. | Trung thành, gắn bó lâu dài. | Cung cấp tính năng gợi ý kịch bản phản hồi động (Real-time agent assist tips) cho các giai đoạn tiếp theo. |

---

## BƯỚC 9. INFORMATION ARCHITECTURE (CẤU TRÚC THÔNG TIN)

```
VNPT AI-QA Management Console
├── Executive Dashboard (Tổng quan chất lượng, xếp hạng Agent, phân tích Topic)
├── Call Center Analyser (Không gian phân tích cuộc gọi)
│   ├── Audit Workspace (Màn hình chấm điểm cuộc gọi chi tiết)
│   ├── Call Registry (Kho lưu trữ 100% cuộc gọi ghi âm và transcript)
│   └── Flagged Queue (Danh sách cuộc gọi có rủi ro cao đợi QA duyệt)
├── Scorecard Designer (Trình thiết kế tiêu chí chấm điểm tự động)
│   ├── Scorecard Templates (Thư viện mẫu tiêu chí)
│   └── Rule Engine (Thiết lập từ khóa, ngưỡng cảm xúc, quy tắc logic trừ điểm)
├── Agent Coaching Center (Trung tâm huấn luyện & Đào tạo điện thoại viên)
│   ├── Coaching Sessions (Lịch sử và tiến độ đào tạo các Agents)
│   └── Library of Good/Bad Cases (Thư viện các cuộc mẫu chuẩn và cuộc lỗi)
└── System Administration (Cấu hình tổng đài, phân quyền QA, quản trị API)
```

---

## BƯỚC 10. THIẾT KẾ SITEMAP

```
/ (Dashboard - Tổng quan chất lượng & Topic Analytics)
├── /calls (Kho lưu trữ & Phân tích cuộc gọi)
│   ├── /calls/all (Danh sách tất cả cuộc gọi)
│   ├── /calls/flagged (Danh sách cuộc gọi đợi duyệt)
│   └── /calls/[id] (Chi tiết phân tích & Chấm điểm 1 cuộc gọi)
├── /scorecards (Quản lý bộ tiêu chí chấm điểm)
│   ├── /scorecards/new (Tạo mới bộ quy tắc chấm điểm)
│   └── /scorecards/[id] (Chỉnh sửa bộ quy tắc hiện có)
├── /coaching (Không gian quản trị đào tạo điện thoại viên)
│   ├── /coaching/agents (Quản lý tiến độ đào tạo của từng điện thoại viên)
│   └── /coaching/lessons (Thư viện bài học thực tế từ cuộc gọi lỗi)
└── /settings (Liên kết tổng đài PBX, phân quyền truy cập, cài đặt AI)
```

---

## BƯỚC 11. DANH SÁCH MÀN HÌNH CHÍNH

| Màn hình | Mục tiêu trải nghiệm | Thành phần chính |
| :--- | :--- | :--- |
| **1. Executive Dashboard** | Giúp quản lý nắm bắt tức thì sức khỏe chất lượng của toàn trung tâm tổng đài trong ngày. | - Chỉ số chất lượng trung bình (Average Quality Score).<br>- Biểu đồ phân tích cảm xúc khách hàng (Tỷ lệ Vui vẻ / Bình thường / Tức giận).<br>- Biểu đồ đám mây từ khóa (Topic Cloud) thể hiện nội dung khách hàng phàn nàn nhiều nhất.<br>- Bảng xếp hạng các điện thoại viên xuất sắc và yếu kém. |
| **2. Audit Workspace (Split-Screen)** | Giúp QA Specialist thẩm định nhanh kết quả chấm điểm của AI và nghe lại lỗi. | - Cột trái: Danh sách cuộc gọi lỗi đang chờ thẩm định.<br>- Cột giữa: Audio Waveform hiển thị sóng âm 2 kênh (Agent & Customer) phân biệt màu sắc + Khung text transcript đồng bộ chữ chạy.<br>- Cột phải: Scorecard chấm điểm tự động do AI đề xuất. QA có thể tích chọn ghi đè (override) điểm số kèm lý do. |
| **3. Scorecard Builder (No-Code Rule Engine)**| Cho phép QA Team Leader tự xây dựng các tiêu chí chấm điểm tự động mà không cần biết lập trình. | - Canvas kéo thả các khối điều kiện.<br>- Khung thiết lập quy tắc từ khóa (ví dụ: *Nếu không xuất hiện cụm từ "xin chào" hoặc "VinaPhone xin nghe" trong 10 giây đầu -> Trừ 5 điểm*).<br>- Khung thiết lập quy tắc cảm xúc (ví dụ: *Nếu khách nói to hơn bình thường và có từ khóa "bực mình" -> Gắn cờ Khách hàng tức giận*). |
| **4. Agent Coaching Portal** | Giúp điện thoại viên tự xem lại lỗi và học tập trực quan từ các tình huống thực tế. | - Báo cáo điểm số chất lượng cá nhân theo tuần/tháng.<br>- Danh sách cuộc gọi bị gắn cờ lỗi kèm ghi chú hướng dẫn của QA.<br>- Thư viện âm thanh "Good Practices" (cuộc gọi mẫu đạt điểm tuyệt đối của đồng nghiệp để học hỏi). |

---

## BƯỚC 12. USER FLOW (LUỒNG NGƯỜI DÙNG CHÍNH)

### Main Flow: Thẩm định cuộc gọi bị AI cảnh báo lỗi
```
[Bắt đầu] QA đăng nhập hệ thống -> Truy cập màn hình Flagged Queue
  │
  ▼
[Chọn cuộc gọi] Click vào cuộc gọi có tag cảnh báo màu đỏ [Agent nói cắt lời khách hàng]
  │
  ▼
[Phân tích giao diện] Hệ thống mở Audit Workspace -> Hiển thị Waveform sóng âm
  │
  ▼
[Định vị điểm lỗi] QA nhìn thấy vạch màu đỏ đánh dấu lỗi trên Waveform -> Click trực tiếp vào vạch đỏ đó
  │
  ▼
[Nghe âm thanh] Hệ thống tự động tua ghi âm đến giây thứ 45 và phát đoạn: "Khách: Tôi chưa nhận được... / Agent: Anh nghe tôi nói đã..." (nói đè lên nhau)
  │
  ▼
[Xác nhận chấm điểm] QA kiểm tra bảng điểm cột bên phải, thấy AI đã tự động trừ 10 điểm mục "Thái độ tôn trọng" -> QA nhấn "Đồng ý với AI"
  │
  ▼
[Tạo task đào tạo] QA bôi đen đoạn transcript lỗi -> Nhấn "Gửi đào tạo" -> Nhập ghi chú: "Huy chú ý không được ngắt lời khi khách đang trình bày lỗi"
  │
  ▼
[Kết thúc] Điện thoại viên nhận được thông báo lỗi kèm clip âm thanh 5 giây để nghe lại tự rút kinh nghiệm
```

### Alternative Flow: Xây dựng quy tắc chấm điểm tự động mới
```
[Bắt đầu] QA Leader mở Scorecard Designer -> Chọn "Tạo bộ tiêu chí mới"
  │
  ▼
[Khai báo thông tin] Đặt tên: "Quy chuẩn bán gói Home Mesh 2026"
  │
  ▼
[Thêm tiêu chí AI] Chọn khối điều kiện "Kiểm tra kịch bản bán hàng" (Script Compliance)
  │
  ▼
[Thiết lập quy tắc] Nhập danh sách từ khóa bắt buộc: "Home Mesh", "Wifi Mesh", "Khuyến mãi tặng tháng"
  │
  ▼
[Thiết lập logic] Cài đặt: Nếu thiếu 1 trong 3 cụm từ trên -> Trừ 5 điểm. Nếu thiếu cả 3 -> Trừ 15 điểm.
  │
  ▼
[Chạy thử nghiệm (Simulate)] Chọn 10 cuộc gọi cũ chạy thử nghiệm bộ quy tắc mới -> AI tự động quét và đưa ra kết quả giả lập
  │
  ▼
[Áp dụng] Kết quả giả lập chính xác -> Nhấn "Áp dụng cho toàn hệ thống" -> Tất cả cuộc gọi mới từ thời điểm này sẽ được AI tự chấm điểm theo quy tắc đó
```

---

## BƯỚC 13. ĐỀ XUẤT WIREFRAME CẤP CAO (MÀN HÌNH AUDIT WORKSPACE)

*   **Header Bar:**
    *   Left: Tên Agent (`Nguyễn Văn A`), Mã nhân viên, ID cuộc gọi.
    *   Center: Nút trạng thái duyệt (`Đạt` / `Cần Đào Tạo` / `Khiếu Nại`).
    *   Right: Tổng điểm AI chấm (`85/100`), nút "Lưu kết quả" và nút "Chuyển tiếp cho Quản lý".
*   **Left Panel (Danh sách cuộc gọi cần duyệt):**
    *   Danh sách cuộn dọc các cuộc gọi bị gắn cờ, sắp xếp theo thời gian hoặc mức độ rủi ro giảm dần.
    *   Mỗi item gồm: Tên Agent, Thời lượng cuộc gọi, Nhãn cảnh báo (`[Nói tranh chấp]`, `[Cảm xúc tiêu cực]`).
*   **Central Workspace (Trình nghe âm thanh & Text):**
    *   *Phía trên:* Trình phát âm thanh Waveform chia làm 2 làn sóng âm song song: làn trên là Agent (màu xanh dương), làn dưới là Customer (màu hồng). Trên dòng thời gian có các chấm đánh dấu lỗi màu đỏ/vàng tương ứng với vị trí lỗi trong cuộc gọi.
    *   *Phía dưới:* Khung Transcript cuộn dọc. Chữ viết của Agent căn lề trái, chữ của Khách hàng căn lề phải. Đoạn text bị AI nghi ngờ vi phạm kịch bản/lỗi thái độ được bôi nền đỏ nhạt. Khi audio chạy đến đâu, chữ tương ứng tự động tô đậm và cuộn màn hình đến đó.
*   **Right Panel (Scorecard - Bảng điểm):**
    *   Danh sách các nhóm tiêu chí chấm điểm: `1. Chào hỏi & Kết thúc (10đ)`, `2. Tuân thủ kịch bản (40đ)`, `3. Thái độ & Kỹ năng (30đ)`, `4. Giải quyết vấn đề (20đ)`.
    *   Mỗi tiêu chí con có điểm AI đề xuất, nút điều chỉnh thủ công (+/-), hộp nhập lý do điều chỉnh và biểu tượng con mắt để QA click nhảy nhanh đến đoạn ghi âm chứng minh cho tiêu chí đó.

---

## BƯỚC 14. ĐÁNH GIÁ UX THEO HEURISTIC (10 NGUYÊN TẮC NIELSEN)

1.  **Visibility of System Status (Trạng thái hệ thống rõ ràng):**
    *   *Mức độ đáp ứng:* Cao. Khi tải tệp âm thanh ghi âm lên hệ thống, có thanh tiến trình xử lý chi tiết: `[Đang tải tệp...]` -> `[AI đang chuyển thoại sang văn bản...]` -> `[AI đang chấm điểm Scorecard...]`.
2.  **Match Between System and Real World (Gần gũi thực tế):**
    *   *Mức độ đáp ứng:* Cao. Sử dụng các khái niệm nghiệp vụ tổng đài quen thuộc như: Agent, QA, Scorecard, Chặn cuộc gọi, Khiếu nại điểm, Chỉ số SLA.
3.  **User Control and Freedom (Quyền kiểm soát của người dùng):**
    *   *Mức độ đáp ứng:* Khá.
    *   *Rủi ro:* AI tự động chấm điểm và cập nhật thẳng vào KPI của Agent có thể gây ức chế cho nhân viên nếu AI chấm sai.
    *   *Đề xuất cải thiện:* Thiết kế nút **"Yêu cầu phúc khảo" (Dispute)** trên giao diện của Agent, cho phép gửi cuộc gọi lên bộ phận QA con người chấm lại nếu thấy AI chấm chưa chuẩn.
4.  **Consistency and Standards (Nhất quán & Tiêu chuẩn):**
    *   *Mức độ đáp ứng:* Cao. Toàn bộ icon, khoảng cách, màu sắc các nút hành động tuân thủ chặt chẽ tiêu chuẩn chung của hệ thống phần mềm doanh nghiệp VNPT.
5.  **Error Prevention (Phòng tránh lỗi):**
    *   *Mức độ đáp ứng:* Khá.
    *   *Rủi ro:* QA Specialist bận rộn dễ bấm nhầm nút lưu điểm khi chưa xem hết các lỗi nghiêm trọng.
    *   *Đề xuất cải thiện:* Nếu cuộc gọi có cảnh báo lỗi mức độ cực kỳ nghiêm trọng (như agent văng tục), khi QA nhấn lưu kết quả mà chưa nghe đoạn lỗi đó, hệ thống sẽ hiển thị cảnh báo nhắc nhở kiểm tra lại.
6.  **Recognition Rather Than Recall (Nhận diện thay vì ghi nhớ):**
    *   *Mức độ đáp ứng:* Cao. Bôi đỏ trực tiếp các lỗi trên văn bản và dòng thời gian sóng âm giúp QA chỉ cần click vào để nhận biết lỗi thay vì phải tự nghe từ đầu đến cuối và ghi nhớ mốc thời gian phát sinh lỗi.
7.  **Flexibility and Efficiency of Use (Linh hoạt & Hiệu quả):**
    *   *Mức độ đáp ứng:* Rất cao. Cung cấp các tính năng tối ưu tốc độ làm việc cho QA lâu năm: Phím tắt chấm điểm nhanh, tính năng tự động nhảy đến lỗi tiếp theo (Auto-next error), và tùy chỉnh tốc độ phát âm thanh (0.75x, 1x, 1.25x, 1.5x).
8.  **Aesthetic and Minimalist Design (Thẩm mỹ & Tối giản):**
    *   *Mức độ đáp ứng:* Khá. Giao diện chứa nhiều thông tin phức tạp (Transcript, Waveform, Scorecards).
    *   *Đề xuất cải thiện:* Cho phép QA thu gọn cột danh sách cuộc gọi bên trái và cột Scorecard bên phải để mở rộng tối đa khu vực đọc transcript ở giữa khi cần.
9.  **Help Users Recover From Errors (Hỗ trợ sửa lỗi):**
    *   *Mức độ đáp ứng:* Khá. Nếu kết nối mạng tổng đài bị ngắt giữa chừng, hệ thống tự động lưu tạm (Autosave) bảng điểm QA đang chấm dở để không bị mất dữ liệu.
10. **Help and Documentation (Trợ giúp):**
    *   *Mức độ đáp ứng:* Khá. Tích hợp sẵn cẩm nang định nghĩa các lỗi chuẩn hóa trong doanh nghiệp ngay cạnh mỗi tiêu chí chấm điểm để QA tiện tra cứu khi phân vân.

---

## BƯỚC 15. ĐÁNH GIÁ KHẢ NĂNG SỬ DỤNG (USABILITY ASSESSMENT)

*   **Learnability (Khả năng học hỏi):** **8.0/10** (QA cần khoảng 1 - 2 ngày đào tạo để làm quen với giao diện Split-screen và trình thiết kế quy tắc Scorecard).
*   **Efficiency (Hiệu suất sử dụng):** **9.8/10** (Rút ngắn thời gian thẩm định chất lượng cuộc gọi từ 10 phút xuống còn 1.5 phút/cuộc gọi lỗi, và tự động hóa hoàn toàn 100% cuộc gọi bình thường).
*   **Accessibility (Khả năng tiếp cận):** **8.0/10** (Sử dụng hệ thống màu sắc có độ tương phản cao trên nền tối, hỗ trợ tăng giảm cỡ chữ transcript để giảm mỏi mắt cho QA làm việc ca đêm).
*   **Satisfaction (Mức độ hài lòng):** **9.5/10** (Giúp loại bỏ hoàn toàn cảm giác nhàm chán khi phải nghe hàng trăm cuộc gọi lặp đi lặp lại một cách ngẫu nhiên).

---

## BƯỚC 16. PHÂN TÍCH RỦI RO UX & GIẢI PHÁP ĐỀ XUẤT

| Rủi ro trải nghiệm | Mức độ | Giải pháp đề xuất |
| :--- | :---: | :--- |
| **"AI Bias & Hallucination" (Chấm điểm sai lệch):** AI nhận diện sai từ ngữ do tạp âm/nói ngọng dẫn đến chấm điểm oan cho Agent, gây bức xúc nội bộ. | **Cao** | Thiết kế quy trình bắt buộc: Điểm số do AI chấm chỉ mang tính chất đề xuất (Draft). Với các cuộc gọi có điểm số quá thấp gây phạt KPI, bắt buộc phải có QA con người thẩm định và nhấn nút "Phê duyệt" mới có hiệu lực chính thức. |
| **Scrolling Fatigue (Mỏi mắt khi đọc Transcript quá dài):** Các cuộc gọi hỗ trợ kỹ thuật kéo dài trên 15 phút có đoạn text transcript rất dài, QA cuộn trang tìm lỗi dễ bị sót. | **Medium** | Tích hợp thanh cuộn nhiệt (Heatmap Scrollbar) hiển thị các vạch màu đỏ/vàng dọc theo thanh cuộn trang, cho phép QA click trượt thẳng đến vị trí có lỗi một cách nhanh chóng. |
| **Sự phản kháng từ phía Agent:** Nhân viên cảm thấy bị "soi mói" quá mức khi 100% cuộc gọi bị AI giám sát chặt chẽ. | **Cao** | Chuyển đổi thông điệp của hệ thống từ "Giám sát phạt lỗi" sang **"Trợ lý hỗ trợ phát triển năng lực"**. Cung cấp giao diện Agent Portal khuyến khích học tập tự chủ, thưởng điểm phạt nếu Agent tích cực hoàn thành các bài học huấn luyện cải thiện lỗi. |

---

## BƯỚC 17. ƯU TIÊN PHÁT TRIỂN MVP (MOSCOW)

### Must Have (Bắt buộc phải có trong bản đầu tiên)
*   Tính năng Speech-to-Text tiếng Việt 2 kênh (Agent & Customer) chất lượng cao cho âm thanh băng thông hẹp (8kHz).
*   Giao diện Audit Workspace (Waveform + Transcript chạy chữ + Scorecard tự động).
*   Tính năng thiết lập Scorecard chấm điểm tự động bằng các từ khóa cơ bản và kiểm tra khoảng lặng (Silence detection).
*   Agent Portal cơ bản cho nhân viên xem điểm số và nghe lại đoạn lỗi.

### Should Have (Nên có)
*   Bộ phân tích cảm xúc đàm thoại (Sentiment Analysis) tự động phát hiện giọng điệu tức giận/khiếu nại của khách hàng.
*   Trình thiết kế Scorecard kéo thả No-code Rule Engine hoàn chỉnh.
*   Quy trình phúc khảo (Dispute workflow) cho phép Agent khiếu nại điểm số lên QA Leader trực tiếp trên app.

### Could Have (Có thể có sau)
*   Tính năng Topic Modeling tự động phân tích và gom nhóm các chủ đề khách hàng phàn nàn theo dạng biểu đồ trực quan.
*   Tính năng Real-time Alerting: Cảnh báo ngay lập tức cho giám sát nếu cuộc gọi đang diễn ra xuất hiện hành vi cãi vã nghiêm trọng.

---

## BƯỚC 18. ROADMAP PHÁT TRIỂN

*   **Phase 1 (Tháng 1-3) - Nền tảng cốt lõi & Thử nghiệm hiệu quả (MVP):**
    *   Tối ưu hóa mô hình Speech-to-Text tiếng Việt chuyên biệt cho âm thanh nén tổng đài.
    *   Phát triển giao diện Audit Workspace và tính năng tự động chấm điểm theo từ khóa cơ bản.
    *   Thử nghiệm thực tế với 50 điện thoại viên tại 1 nhánh tổng đài CSKH của VNPT để đo lường độ chính xác chấm điểm của AI.
*   **Phase 2 (Tháng 4-6) - Quản trị Đào tạo & Phân tích Cảm xúc:**
    *   Tích hợp bộ phân tích cảm xúc đàm thoại nâng cao và phát triển mô-đun Rule Engine thiết kế Scorecard.
    *   Phát triển luồng công việc đào tạo (Coaching workflow) và quy trình khiếu nại điểm số (Dispute workflow).
    *   Triển khai ứng dụng diện rộng cho toàn bộ trung tâm chăm sóc khách hàng VNPT VinaPhone.
*   **Phase 3 (Tháng 7-12) - Real-time Analytics & Topic Modeling:**
    *   Tích hợp tính năng phân tích và cảnh báo cuộc gọi rủi ro theo thời gian thực (Real-time monitoring).
    *   Phát triển công cụ Topic Modeling tự động phát hiện xu hướng phàn nàn của khách hàng để làm đầu vào cho tối ưu sản phẩm viễn thông.

---

## BƯỚC 19. UX SCORECARD (ĐÁNH GIÁ CHẤT LƯỢNG)

| Tiêu chí | Điểm số (Thang 10) | Nhận xét chi tiết |
| :--- | :---: | :--- |
| **User Value** (Giá trị cho người dùng) | 9.0/10 | Giúp QA giảm tải cực lớn công việc nghe ghi âm thủ công nhàm chán; giúp Agent tiến bộ nhanh nhờ phản hồi lỗi trực quan. |
| **Business Value** (Giá trị kinh doanh) | 9.5/10 | Tăng tỷ lệ giám sát từ 2% lên 100%, bảo vệ danh tiếng thương hiệu và tối ưu chất lượng dịch vụ ở mọi quy mô. |
| **Usability** (Khả năng sử dụng) | 8.5/10 | Trình phát Waveform kết hợp text chạy trực quan, giảm thiểu nỗ lực tương tác tìm lỗi của QA. |
| **Accessibility** (Khả năng tiếp cận) | 8.0/10 | Giao diện tối (Dark mode) được thiết kế tốt, giảm mỏi mắt cho nhân viên làm ca liên tục. |
| **Scalability** (Khả năng mở rộng) | 9.0/10 | Dễ dàng mở rộng số lượng luồng ghi âm cuộc gọi phân tích hàng ngày nhờ kiến trúc vi dịch vụ (Microservices). |
| **Innovation** (Tính đổi mới sáng tạo) | 9.5/10 | Ứng dụng đột phá công nghệ AI Speech Analytics để giải quyết triệt để điểm nghẽn của quy trình QA truyền thống. |
| **Competitive Advantage** (Lợi thế cạnh tranh) | 9.0/10 | Sở hữu năng lực Speech-to-Text tiếng Việt chuyên sâu cho kênh tổng đài là rào cản công nghệ lớn đối với đối thủ ngoại. |

**TỔNG ĐIỂM UX SCORE: 8.9/10**

---

## BƯỚC 20. KẾT LUẬN CHUYÊN GIA

*   **Mức độ khả thi về mặt kỹ thuật:** **KHÁ**. Công nghệ chuyển giọng nói thành văn bản tiếng Việt hiện nay đã đạt độ chính xác > 85% trong môi trường nhiều tạp âm. Phần thách thức nhất nằm ở việc tinh chỉnh mô hình phân tích cảm xúc (Sentiment Analysis) dựa trên âm điệu và ngữ cảnh đàm thoại tiếng Việt đặc thù (ngôn từ lịch sự nhưng mang tính mỉa mai, nói lẫy...).
*   **Mức độ cạnh tranh trên thị trường:** **TRUNG BÌNH - CAO**. Trong nước đã có một số đơn vị cung cấp giải pháp Speech-to-Text nhưng hầu hết chỉ dừng lại ở dịch vụ hạ tầng (API chuyển đổi), chưa có đơn vị nào đóng gói thành một giải pháp phần mềm quản trị QA và Coaching chuyên sâu cho tổng đài Contact Center.
*   **Khuyến nghị đầu tư:** **NÊN TRIỂN KHAI NGAY**. Dự án này không chỉ giải quyết bài toán tối ưu hóa chi phí vận hành và nâng cao chất lượng dịch vụ của chính hệ thống tổng đài CSKH khổng lồ của VNPT, mà còn là sản phẩm SaaS cực kỳ tiềm năng để kinh doanh B2B bán cho các trung tâm tổng đài của các ngân hàng, công ty bảo hiểm, thương mại điện tử tại Việt Nam.
