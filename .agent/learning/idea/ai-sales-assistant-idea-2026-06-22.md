# Báo cáo Phân tích Chiến lược & Đề xuất Ý tưởng Sản phẩm (Product Discovery) - Hệ thống AI Hỗ trợ Kênh bán & Tự động hóa Phát triển SPDV (VNPT ASAP)

- **Tên ý tưởng sản phẩm:** VNPT ASAP (AI-powered Sales Assistant & Prototyping)
- **Mục tiêu:** Tự động hóa chuỗi giá trị từ tiếp nhận yêu cầu khách hàng trong cuộc họp, đối khớp danh mục sản phẩm VNPT, sinh prototype demo tức thời đến tự động tạo tài liệu đặc tả (URD, SRS) chuyển giao cho đội sản xuất IT.
- **Ngày thực hiện:** 22/06/2026
- **Chuyên gia thực hiện:** Senior Product Designer, Product Manager & UX Strategist (.agent)
- **Dựa trên quy trình:** [idea.md](file:///Volumes/CHAOS/VNPT/AI/CX/.agent/skills/idea.md)

---

## BƯỚC 1. PRODUCT OVERVIEW (PHÂN TÍCH SẢN PHẨM)

| Nội dung | Phân tích chi tiết ý tưởng |
| :--- | :--- |
| **Sản phẩm đề xuất** | **VNPT ASAP** - Hệ thống trợ lý AI toàn diện dành cho lực lượng bán hàng (AM/Sales) và đội ngũ phát triển sản phẩm của VNPT. |
| **Bài toán cần giải quyết** | 1. **Khoảng cách tri thức sản phẩm:** VNPT có hệ sinh thái sản phẩm dịch vụ (SPDV) cực kỳ lớn. AM không thể nhớ và hiểu sâu tất cả để đối khớp nhanh với yêu cầu khách hàng ngay tại cuộc họp.<br>2. **Chu kỳ chốt sales (Sales Cycle) kéo dài:** Việc tiếp nhận yêu cầu, gửi về phòng ban kỹ thuật làm đề xuất giải pháp, thiết kế mockup/wireframe thủ công mất từ 1 - 2 tuần, khiến cơ hội bán hàng bị nguội đi.<br>3. **Sai lệch thông tin khi chuyển giao (Handover Friction):** Yêu cầu khách hàng truyền đạt từ Sales qua BA đến Dev thường bị tam sao thất bản. Tài liệu SRS/URD viết thủ công tốn thời gian và dễ thiếu sót. |
| **Mục tiêu kinh doanh** | 1. Rút ngắn thời gian từ tiếp xúc ban đầu đến khi chốt hợp đồng (giảm 70% thời gian giai đoạn pre-sales).<br>2. Tăng tỷ lệ chốt deal nhờ trực quan hóa giải pháp ngay lập tức bằng Prototype sinh động.<br>3. Tối ưu hóa nguồn lực BA và UX Designer ở giai đoạn khảo sát yêu cầu ban đầu. |
| **Mục tiêu người dùng** | 1. **Đối với AM:** Tự tin tư vấn giải pháp chuẩn xác, có ngay demo tương tác để thuyết phục khách hàng mà không cần đợi IT.<br>2. **Đối với Khách hàng B2B:** Thấy ngay sản phẩm tương lai của mình hình thành trực quan, dễ dàng điều chỉnh ý muốn.<br>3. **Đối với đội IT/Sản xuất:** Nhận được gói bàn giao chuẩn hóa (SRS, URD, Prototype liên kết trực tiếp) rõ ràng, giảm thiểu việc sửa đổi mã nguồn sau này (rework). |
| **Giá trị cốt lõi** | **"From Conversation to Prototype in Minutes. From Agreement to IT Sprint in Seconds."** (Biến cuộc hội thoại thành bản demo trong vài phút. Chuyển đổi thỏa thuận thành dự án IT trong vài giây). |

---

## BƯỚC 2. XÁC ĐỊNH NHU CẦU NGƯỜI DÙNG

| Nhóm đối tượng | Functional Needs (Hành vi/Chức năng) | Emotional Needs (Cảm xúc) | Social Needs (Xã hội/Vị thế) |
| :--- | :--- | :--- | :--- |
| **Account Manager (AM) / Sales VNPT** | - Ghi âm và tự động tóm tắt biên bản cuộc họp.<br>- Tra cứu nhanh khả năng đáp ứng của VNPT đối với yêu cầu của khách hàng.<br>- Sinh nhanh prototype thô để khách hàng xem trực tiếp. | - Sợ bị khách hàng đánh giá thiếu năng lực kỹ thuật khi đi họp một mình.<br>- Mong muốn chốt hợp đồng nhanh để đạt KPI doanh số. | - Khẳng định vị thế chuyên gia tư vấn giải pháp chuyển đổi số chuyên nghiệp trước đối tác. |
| **Khách hàng B2B / Khối chính phủ** | - Muốn giải thích yêu cầu bằng ngôn ngữ nghiệp vụ thông thường và thấy giao diện trực quan.<br>- Muốn chỉnh sửa nhanh các trường dữ liệu hoặc luồng hoạt động trên màn hình demo. | - Lo ngại đối tác công nghệ không hiểu đúng quy trình nghiệp vụ đặc thù của đơn vị mình.<br>- Cần sự chắc chắn trực quan trước khi ký biên bản chốt yêu cầu. | - Dễ dàng trình bày và bảo vệ dự án trước hội đồng phê duyệt nội bộ của đơn vị. |
| **Đội ngũ sản xuất IT (BA / Developer / QA)** | - Cần đặc tả yêu cầu chi tiết (SRS, URD) chuẩn hóa, không mơ hồ.<br>- Cần prototype có tính khả thi về mặt lập trình (dựa trên Component Library sẵn có của VNPT). | - Ức chế khi yêu cầu liên tục thay đổi giữa chừng do Sales chốt hớ với khách hàng.<br>- Muốn tập trung phát triển chuyên môn thay vì đi họp khảo sát lặp đi lặp lại. | - Hoàn thành dự án đúng hạn, đảm bảo KPI về chất lượng phần mềm và tiến độ bàn giao. |

---

## BƯỚC 3. XÂY DỰNG USER PERSONA

### Persona 1: Anh Quốc Nam (34 tuổi) - Senior AM Khối Khách hàng Doanh nghiệp (VNPT Enterprise)
*   **Mục tiêu:** Tiếp cận và thuyết phục một chuỗi bệnh viện tư nhân lớn ký hợp đồng sử dụng hệ thống quản lý phòng khám tích hợp thanh toán không tiền mặt.
*   **Nhu cầu:** Cần biết ngay giải pháp VNPT HIS hiện tại đã có sẵn module thanh toán tích hợp ví điện tử chưa, và cần mô phỏng được luồng thanh toán cho khách hàng xem tại chỗ để chốt chủ trương.
*   **Pain Point:** Không có nền tảng kỹ thuật. Thường phải xin lịch hẹn kéo theo 1 BA và 1 Giải pháp viên đi cùng, rất khó xếp lịch trùng nhau làm lỡ cơ hội tiếp cận nhanh.
*   **Hành vi với ASAP:** Bật chế độ ghi âm cuộc họp trên máy tính bảng, để AI tự động trích xuất yêu cầu và đối khớp. Sau đó mở màn hình sinh Prototype để hiển thị giao diện luồng thanh toán cho khách hàng.

### Persona 2: Chị Thu Trang (30 tuổi) - Business Analyst (BA) tại VNPT IT
*   **Mục tiêu:** Chuyển hóa các yêu cầu nghiệp vụ từ biên bản họp của phòng Kinh doanh thành tài liệu đặc tả chức năng chi tiết và bàn giao cho đội Dev.
*   **Nhu cầu:** Cấu trúc tài liệu SRS chuẩn hóa theo IEEE, có mô tả chi tiết các Use Case, tác nhân, điều kiện tiên quyết và sơ đồ luồng dữ liệu (Data Flow).
*   **Pain Point:** Mất quá nhiều thời gian viết các tài liệu mẫu (template) lặp đi lặp lại. Đôi khi thông tin nhận lại từ AM rất sơ sài, phải gọi điện đối chất nhiều lần để làm rõ.
*   **Hành vi với ASAP:** Đăng nhập vào không gian bàn giao (Handover Space), duyệt lại tài liệu SRS/URD do AI tự động soạn thảo từ biên bản họp, tinh chỉnh các chi tiết nghiệp vụ sâu và nhấn nút đồng bộ hóa sang Jira.

---

## BƯỚC 4. PHÂN TÍCH ĐỐI THỦ CẠNH TRANH

| Đối thủ / Công cụ đơn lẻ | Điểm mạnh | Điểm yếu | Bài học cho VNPT ASAP |
| :--- | :--- | :--- | :--- |
| **Fireflies.ai / Otter.ai** (Hỗ trợ cuộc họp) | - Ghi âm, chuyển văn bản và tóm tắt cuộc họp cực kỳ chính xác.<br>- Hỗ trợ nhiều ngôn ngữ. | - Chỉ dừng lại ở ghi biên bản họp (Minutes of Meeting).<br>- Không hiểu sâu về nghiệp vụ các sản phẩm viễn thông/CNTT và tài liệu Salekit đặc thù của VNPT. | Kế thừa khả năng nhận diện giọng nói tiếng Việt chuyên sâu, nhưng tích hợp thêm bộ RAG (Retrieval-Augmented Generation) kết nối với kho tài liệu sản phẩm VNPT. |
| **v0.dev / Uizard.io / Galileo AI** (Sinh UI/Prototype) | - Tạo giao diện và prototype tương tác cực nhanh từ mô tả văn bản (Prompt).<br>- Giao diện hiện đại, bóng bẩy. | - Giao diện sinh ra mang tính ngẫu nhiên, không tuân thủ Design System chuẩn của VNPT.<br>- Không khả thi 100% khi lập trình vì dùng các thành phần UI lạ.<br>- Không liên kết với tài liệu đặc tả kỹ thuật. | Định hướng AI sinh UI chỉ được phép sử dụng các nguyên tử UI (Atomic Components) từ **VNPT Design System Library** (ví dụ: các thư viện Angular/React có sẵn của VNPT). |
| **Claude / ChatGPT** (Soạn tài liệu SRS/URD) | - Viết tài liệu nghiệp vụ rất trôi chảy, đúng cấu trúc. | - Dễ bị ảo tưởng (hallucination) về mặt kỹ thuật hệ thống nội bộ.<br>- Không tích hợp trực tiếp với luồng thiết kế UI và hệ thống quản trị task (Jira/GitLab). | Tạo luồng tự động: Ý kiến khách hàng từ cuộc họp -> Tạo Use Case -> Sinh UI tương ứng -> Khớp nội dung UI vào tài liệu SRS (ví dụ: màn hình có nút nào thì SRS mô tả chức năng nút đó). |

---

## BƯỚC 5. SO SÁNH TÍNH NĂNG (FEATURE COMPARISON MATRIX)

| Tính năng cốt lõi | Công cụ tóm tắt họp (Fireflies) | Công cụ sinh UI (Uizard/v0) | LLM thông thường (ChatGPT) | Giải pháp đề xuất VNPT ASAP |
| :--- | :---: | :---: | :---: | :---: |
| **Tóm tắt & phân tích cuộc họp họp bằng tiếng Việt** | **Có** | Không | Có (cần prompt thủ công) | **Có (Chuyên sâu ngữ cảnh VNPT)** |
| **Đối khớp thư viện sản phẩm nội bộ (Salekit)** | Không | Không | Không | **Có (Kết nối cơ sở dữ liệu SPDV VNPT)** |
| **Đánh giá mức độ đáp ứng (Fit-Gap Analysis)** | Không | Không | Không | **Có (Đề xuất giải pháp sẵn có/phát triển mới)** |
| **Sinh Prototype tương tác tức thời** | Không | **Có** | Không | **Có (Tuân thủ VNPT Design System)** |
| **Chỉnh sửa Prototype bằng giọng nói/văn bản** | Không | Có (hạn chế) | Không | **Có (Thời gian thực ngay tại cuộc họp)** |
| **Tự động xuất tài liệu đặc tả SRS/URD** | Không | Không | Có (thiếu liên kết UI) | **Có (Liên kết chặt chẽ với Prototype)** |
| **Đồng bộ hóa 1-click sang Jira/GitLab** | Không | Không | Không | **Có (Chuyển giao IT tự động)** |

---

## BƯỚC 6. PHÁT HIỆN KHOẢNG TRỐNG THỊ TRƯỜNG & CƠ HỘI NỘI BỘ

| Cơ hội cạnh tranh / Tối ưu hóa | Giá trị mang lại cho VNPT |
| :--- | :--- |
| **Chuỗi giá trị khép kín từ Sales đến IT (End-to-End Workflow)** | Hiện tại trên thế giới chưa có một công cụ thương mại nào liên kết mượt mà từ "Lời nói khách hàng" sang "Phân tích khả năng đáp ứng sản phẩm doanh nghiệp" -> "Sinh UI Prototype" -> "Viết tài liệu kỹ thuật" -> "Tạo Task cho Lập trình viên". Làm được điều này sẽ giúp VNPT đi trước các đối thủ lớn như Viettel, FPT một bước dài về tốc độ triển khai dự án. |
| **Tái sử dụng tài nguyên số (Design System & Product Catalog RAG)** | Tận dụng kho dữ liệu khổng lồ về các sản phẩm đã đóng gói của VNPT và hệ thống thư viện giao diện lập trình sẵn để ép AI hoạt động trong khung kỹ thuật thực tế, loại bỏ hoàn toàn các đề xuất phi thực tế. |

---

## BƯỚC 7. ĐỀ XUẤT Ý TƯỞNG THIẾT KẾ (PRODUCT CONCEPT)

*   **Product Concept:** **VNPT ASAP** hoạt động như một nền tảng Web-app kết hợp Mobile-app (chuyên cho AM đi thực địa). Hệ thống sử dụng mô hình đa tác tử AI (Multi-Agent System) phối hợp nhịp nhàng:
    *   *Agent 1 (Meeting Listener):* Lắng nghe, chuyển dịch giọng nói và trích xuất thực thể yêu cầu.
    *   *Agent 2 (Solution Matcher):* RAG tìm kiếm trên kho Salekit và Product Catalog để đánh giá Fit-Gap.
    *   *Agent 3 (UI Generator):* Sinh layout dựa trên VNPT Design System JSON.
    *   *Agent 4 (Technical Writer):* Soạn thảo tài liệu SRS/URD dựa trên các Use Case đã thống nhất.
*   **UX Vision:** **"Interactive Collaboration"** - AM và khách hàng cùng tham gia vào quá trình thiết kế giao diện bằng cách tương tác tự nhiên (Nói, Viết hoặc Kéo thả nhẹ nhàng). Xóa bỏ rào cản kỹ thuật phức tạp.
*   **UI Direction:** **Modern Enterprise AI Portal (Glassmorphism & Electric Blue Theme)**.
    *   *Màu sắc:* Nền tối (Deep Slate Grey/Navy) tạo cảm giác công nghệ cao và bảo mật cao. Màu nhấn là Electric Blue và màu cam đặc trưng của VNPT được tinh chỉnh sang tông sáng để nhấn mạnh các CTA hành động.
    *   *Bố cục:* Split-screen (màn hình chia đôi) khi làm việc trực tiếp: Một bên hiển thị biên bản cuộc họp / danh mục tính năng đề xuất, một bên hiển thị màn hình Prototype tương tác thời gian thực để khách hàng thấy sự thay đổi ngay lập tức khi ra lệnh.

---

## BƯỚC 8. XÂY DỰNG USER JOURNEY (HÀNH TRÌNH TRẢI NGHIỆM)

| Giai đoạn | Hành động người dùng (AM & Khách hàng) | Trải nghiệm cảm xúc | Cơ hội cải thiện chuyển đổi (CRO) |
| :--- | :--- | :--- | :--- |
| **1. Khởi động** | AM tạo phiên họp mới trên VNPT ASAP, chọn lĩnh vực khách hàng (VD: Y tế, Giáo dục, Chính phủ số). | Tò mò, mong chờ hệ thống hỗ trợ tốt. | Gợi ý nhanh các template cuộc họp và salekit liên quan đến lĩnh vực đã chọn để AM không phải tìm kiếm. |
| **2. Tiếp nhận & Đối khớp** | AI lắng nghe hội thoại, hiển thị trực quan các từ khóa yêu cầu và đối khớp tức thì với Catalog sản phẩm VNPT. | "Bất ngờ" vì hệ thống nhận diện nhanh và gợi ý đúng các sản phẩm VNPT đang có. | Thiết kế bảng so khớp phân loại màu sắc rõ ràng: Xanh (Đáp ứng hoàn toàn), Vàng (Đáp ứng 1 phần), Đỏ (Cần phát triển mới). |
| **3. Đồng sáng tạo UI** | AM chọn các tính năng cần phát triển mới/đáp ứng 1 phần, ra lệnh cho AI sinh giao diện. Khách hàng chỉnh sửa trực tiếp. | Thích thú và tin tưởng tuyệt đối vì thấy ý tưởng của mình được hiện thực hóa trực quan. | Cung cấp các lệnh thoại nhanh (Quick Voice Commands) như: "Thêm biểu đồ", "Đổi layout sang 3 cột" để AM thao tác chuyên nghiệp trước mặt khách hàng. |
| **4. Chốt phương án** | Khách hàng nhấn xác nhận bằng chữ ký số hoặc phê duyệt nhanh qua mã QR. AI sinh ngay bộ tài liệu bàn giao. | Yên tâm và hài lòng vì mọi thứ minh bạch. | Gửi email tự động báo cáo tóm tắt kèm link xem Prototype tương tác cho khách hàng lưu trữ. |
| **5. Bàn giao IT** | Hệ thống tự động chuyển giao tài liệu SRS/URD cùng Prototype sang Jira của đội IT. | Đội IT phấn khởi vì nhận yêu cầu sạch, rõ ràng; BA không tốn công viết tài liệu thô. | Tự động phân tích mức độ phức tạp để gợi ý estimate thời gian hoàn thành (Story Points) sơ bộ cho đội IT. |

---

## BƯỚC 9. INFORMATION ARCHITECTURE (CẤU TRÚC THÔNG TIN)

```
VNPT ASAP Workspace
├── Dashboard (Tổng quan phiên họp, trạng thái dự án, thống kê chuyển đổi)
├── Meeting Assistant (Quản lý và thực hiện phiên họp ghi âm)
│   ├── Active Session (Ghi âm, Live Transcript, trích xuất yêu cầu thời gian thực)
│   └── History Sessions (Lưu trữ các cuộc họp trước)
├── Product Discovery & Solution Discovery
│   ├── Fit-Gap Analyzer (Bảng so khớp danh mục sản phẩm VNPT)
│   └── Salekit Knowledge Base (Tra cứu tài liệu hướng dẫn bán hàng)
├── Interactive Prototyping Studio
│   ├── AI UI Canvas (Không gian hiển thị Prototype sinh bởi AI)
│   ├── Component Palette (Thư viện thành phần chuẩn VNPT Design System)
│   └── Prompt Assistant (Nhập lệnh điều chỉnh giao diện bằng giọng nói/văn bản)
└── IT Handover & Document Hub
    ├── URD & SRS Document Editor (Soạn thảo văn bản kỹ thuật)
    ├── Export Center (Xuất PDF, Word, HTML Prototype)
    └── Integration Manager (Cấu hình đồng bộ hóa Jira, GitLab, Redmine)
```

---

## BƯỚC 10. THIẾT KẾ SITEMAP

```
/ (Dashboard - Trang quản trị chính)
├── /sessions (Danh sách & Tạo phiên họp mới)
│   └── /sessions/[id] (Chi tiết phiên họp active: Transcript + Matching)
├── /discovery (Quản lý danh mục sản phẩm VNPT & RAG)
├── /prototype (Studio thiết kế giao diện demo tương tác với AI)
│   └── /prototype/[project_id] (Không gian làm việc canvas)
├── /handover (Trực quan hóa luồng tài liệu & Tích hợp IT)
│   └── /handover/[project_id] (Biên tập SRS/URD & Đồng bộ Jira)
└── /settings (Cấu hình tài khoản, Design System Library, APIs)
```

---

## BƯỚC 11. DANH SÁCH MÀN HÌNH CHÍNH

| Màn hình | Mục tiêu trải nghiệm | Thành phần chính |
| :--- | :--- | :--- |
| **1. Dashboard** | Giúp AM và quản lý theo dõi toàn bộ phễu bán hàng công nghệ và tiến độ bàn giao IT. | - Biểu đồ thống kê số lượng deal chốt qua ASAP.<br>- Danh sách các phiên họp gần đây.<br>- Trạng thái bàn giao các dự án sang IT (Đang dev, Đợi duyệt, Đã xong). |
| **2. Meeting Assistant (Split-Screen)** | Trực quan hóa nội dung cuộc họp và đối khớp sản phẩm song song. | - Cột trái: Live Speech-to-Text Transcript, danh sách các "yêu cầu trích xuất" (Feature Tags).<br>- Cột phải: Gợi ý giải pháp VNPT tương thích từ Salekit (Fit-Gap Matrix). |
| **3. Prototyping Studio** | Giúp AM và khách hàng đồng sáng tạo giao diện tức thời. | - Canvas trung tâm hiển thị Prototype hoạt động được (clickable).<br>- Thanh Chatbot AI bên phải để nhập lệnh hiệu chỉnh UI.<br>- Thanh sidebar chứa thư viện các component chuẩn của VNPT để kéo thả thủ công nếu cần. |
| **4. Handover & SRS Editor** | Giúp BA duyệt lại tài liệu kỹ thuật trước khi đẩy sang IT. | - Trình soạn thảo văn bản chia đôi màn hình: Cột trái là tài liệu SRS/URD cấu trúc phân đoạn; Cột phải là màn hình UI tương ứng với Use Case đang soạn thảo.<br>- Nút hành động "Sync to Jira/GitLab". |

---

## BƯỚC 12. USER FLOW (LUỒNG NGƯỜI DÙNG CHÍNH)

```
[Bắt đầu họp] AM bật ASAP ghi âm 
  │
  ▼
[Trong cuộc họp] AI lắng nghe -> Trích xuất yêu cầu khách hàng -> Gợi ý sản phẩm VNPT phù hợp
  │
  ▼
[Khảo sát Fit-Gap] Xác định các tính năng cần phát triển mới hoặc tích hợp thêm
  │
  ▼
[Sinh Prototype] AM ra lệnh: "AI hãy sinh màn hình Đăng ký Dịch vụ công có thanh toán ngân hàng" 
  │
  ▼
[Khách hàng xem & Sửa] Khách hàng yêu cầu: "Đổi nút Xác nhận sang màu xanh lá và thêm ô nhập mã OTP" -> AI cập nhật UI ngay lập tức
  │
  ▼
[Chốt phương án] Khách hàng ký nhận biên bản điện tử/quét QR -> Chốt yêu cầu
  │
  ▼
[Tự động viết SRS] AI tự biên soạn tài liệu URD, SRS dựa trên luồng Prototype đã chốt
  │
  ▼
[IT Handover] BA duyệt qua -> Nhấn "Đồng bộ" -> Hệ thống tự động tạo Epic/User Stories trên Jira, đính kèm link tài liệu và Prototype cho Dev
```

---

## BƯỚC 13. ĐỀ XUẤT WIREFRAME CẤP CAO (MÀN HÌNH PROTOTYPING STUDIO)

*   **Header Bar:**
    *   Left: Tên dự án, trạng thái kết nối cuộc họp (Live/Paused).
    *   Center: Thanh tiến trình 4 bước: `1. Meeting -> 2. Discovery -> 3. Prototyping (Active) -> 4. Handover`.
    *   Right: Nút "Share Demo Link" (cho khách hàng) và nút "Finish & Generate Documents" (chuyển sang bước Handover).
*   **Left Sidebar (Component Library & Flow):**
    *   Danh mục các màn hình đã tạo (Trang chủ, Trang đăng ký, Trang xác nhận...).
    *   Thư viện các component chuẩn VNPT (Buttons, Input Fields, Tables, Charts, Modals).
*   **Central Canvas (Giao diện tương tác):**
    *   Khu vực hiển thị mockup giao diện của ứng dụng được sinh ra. Có thể chuyển đổi chế độ xem: `Desktop / Tablet / Mobile`.
    *   Các phần tử trên Canvas có thể click vào để xem các liên kết luồng (ví dụ: click Button Đăng nhập chuyển sang Màn hình Dashboard).
*   **Right Panel (AI Co-Pilot):**
    *   Khung chat AI chuyên nhận lệnh thoại hoặc văn bản. Ví dụ: *"AI ơi, thêm cho tôi một biểu đồ cột thể hiện doanh thu ở góc dưới bên trái màn hình dashboard"* hoặc *"Đổi toàn bộ font chữ sang font Inter theo chuẩn của VNPT portal"*.
    *   Hiển thị danh sách các Use Cases được AI tự động phân tích và gắn với màn hình hiện tại.

---

## BƯỚC 14. ĐÁNH GIÁ UX THEO HEURISTIC (10 NGUYÊN TẮC NIELSEN)

1.  **Visibility of System Status (Trạng thái hệ thống rõ ràng):** Khi AI đang xử lý sinh giao diện hoặc xuất tài liệu SRS, phải hiển thị thanh tiến trình cụ thể (đang tạo layout, đang sinh mã CSS, đang cấu trúc tài liệu...) thay vì chỉ hiển thị vòng xoay tải trang vô định.
2.  **Match Between System and Real World (Gần gũi thực tế):** Sử dụng các thuật ngữ nghiệp vụ quen thuộc với AM và BA (ví dụ: "Đặc tả tính năng", "Khảo sát yêu cầu", "Sản phẩm đóng gói", "Yêu cầu phát triển mới") thay vì các từ ngữ lập trình thuần túy.
3.  **User Control and Freedom (Quyền kiểm soát của người dùng):** Cho phép người dùng dễ dàng "Undo" (Hoàn tác) hoặc "Redo" khi AI thực hiện sinh giao diện sai ý muốn. Phải có tính năng khôi phục phiên bản trước (Version History).
4.  **Consistency and Standards (Nhất quán & Tiêu chuẩn):** Toàn bộ giao diện sinh ra bắt buộc phải kế thừa token màu sắc, typography và khoảng cách (spacing) từ VNPT Design System chung để đảm bảo tính đồng bộ của thương hiệu.
5.  **Error Prevention (Phòng tránh lỗi):** Khi sinh Prototype, AI cần kiểm tra tính hợp lệ của luồng (ví dụ: nếu có nút "Tiếp tục" thì phải liên kết tới màn hình tiếp theo, không được để nút "chết").
6.  **Recognition Rather Than Recall (Nhận diện thay vì ghi nhớ):** Hiển thị các gợi ý câu lệnh AI (Prompts) mẫu ngay trong khung chat để AM dễ dàng lựa chọn mà không cần nhớ cú pháp ra lệnh.
7.  **Flexibility and Efficiency of Use (Linh hoạt & Hiệu quả):** Người dùng có kinh nghiệm có thể kéo thả trực tiếp trên Canvas, trong khi AM có thể dùng giọng nói để ra lệnh nhanh.
8.  **Aesthetic and Minimalist Design (Thẩm mỹ & Tối giản):** Tập trung hiển thị sản phẩm demo sắc nét. Ẩn bớt các thanh công cụ kỹ thuật phức tạp đối với giao diện của AM và chỉ hiển thị đầy đủ khi BA hoặc Designer đăng nhập.
9.  **Help Users Recover From Errors (Hỗ trợ sửa lỗi):** Nếu kết nối internet bị gián đoạn khi ghi âm cuộc họp, hệ thống tự động lưu bản cache local và đồng bộ lại ngay khi có mạng mà không làm mất dữ liệu transcript.
10. **Help and Documentation (Trợ giúp):** Tích hợp chatbot hỗ trợ hướng dẫn sử dụng nhanh từng tính năng trực tiếp trong ứng dụng.

---

## BƯỚC 15. ĐÁNH GIÁ USABILITY SCORE (HỆ THỐNG MỚI ĐỀ XUẤT)

*   **Learnability (Dễ học):** **8.5/10** (AM chỉ cần mất 30 phút đào tạo là có thể sử dụng thành thạo các tính năng ghi âm và ra lệnh cho AI sinh UI).
*   **Efficiency (Hiệu suất sử dụng):** **9.5/10** (Rút ngắn thời gian tạo một bản prototype cơ bản từ 3 ngày xuống còn 5 phút).
*   **Accessibility (Khả năng tiếp cận):** **8.0/10** (Hỗ trợ tốt điều khiển bằng giọng nói tiếng Việt, nhận diện được giọng nói các vùng miền Bắc - Trung - Nam).
*   **Satisfaction (Mức độ hài lòng):** **9.0/10** (Mang lại trải nghiệm "Wow" cho khách hàng và giảm áp lực ghi chép cho AM).

---

## BƯỚC 16. PHÂN TÍCH RỦI RO UX & GIẢI PHÁP ĐỀ XUẤT

| Rủi ro trải nghiệm | Mức độ | Giải pháp đề xuất |
| :--- | :---: | :--- |
| **AI tóm tắt sai** hoặc bỏ sót ý kiến quan trọng của khách hàng do tạp âm cuộc họp hoặc khách hàng nói ngọng/nói nhanh. | **Cao** | Thiết kế tính năng cho phép AM nhấn nút "Đánh dấu sự kiện" (Flag Event) ngay lúc họp để AI tập trung nghe kỹ đoạn đó. Cung cấp trình biên tập text (Interactive Transcript Editor) để AM sửa nhanh biên bản sau cuộc họp. |
| **Giao diện AI sinh ra quá ảo**, không thể lập trình thực tế (ví dụ: các luồng dữ liệu quá phức tạp, biểu đồ không có API hỗ trợ). | **Medium** | Ràng buộc AI chỉ được sử dụng các "Thành phần giao diện đã được chứng thực" (Pre-validated Components) trong thư viện VNPT IT. Nếu yêu cầu vượt quá khả năng, AI sẽ tự động gắn tag "Custom Dev Required" trong tài liệu SRS để cảnh báo đội phát triển. |
| **Khách hàng e ngại tính bảo mật** khi cuộc họp bị ghi âm và truyền dữ liệu lên đám mây. | **Cao** | Triển khai mô hình AI chạy local tại On-premise hạ tầng bảo mật của VNPT (VNPT IDC). Hiển thị thông báo bảo mật rõ ràng trên màn hình khi bắt đầu ghi âm để khách hàng yên tâm. |

---

## BƯỚC 17. ƯU TIÊN PHÁT TRIỂN MVP (MOSCOW)

### Must Have (Bắt buộc phải có trong bản đầu tiên)
*   Tính năng ghi âm cuộc họp, chuyển Speech-to-Text tiếng Việt và tóm tắt biên bản họp.
*   Công cụ RAG tìm kiếm và đối khớp tính năng dựa trên bộ tài liệu Salekit + Product Catalog VNPT (PDF/Word).
*   Trình sinh Prototype giao diện tĩnh cơ bản từ văn bản (dựa trên thư viện UI cốt lõi của VNPT).
*   Tự động xuất biên bản cuộc họp và danh sách yêu cầu tính năng (Feature List) ra file Word/PDF.

### Should Have (Nên có)
*   Tính năng tương tác điều khiển giao diện Prototype bằng giọng nói thời gian thực.
*   Trình tự động sinh tài liệu SRS và URD theo biểu mẫu chuẩn của VNPT IT.
*   Tích hợp đồng bộ hóa 1-click tạo Project, Epic và Tasks trên hệ thống Jira của VNPT IT.

### Could Have (Có thể có sau)
*   Tính năng chia sẻ link Prototype tương tác trực tiếp cho khách hàng tự kéo thả chỉnh sửa tại nhà (Collaborative Canvas).
*   AI tự động đề xuất ước lượng chi phí (Cost Estimation) và nhân sự cần thiết cho dự án dựa trên tài liệu SRS vừa tạo.

---

## BƯỚC 18. ROADMAP TRIỂN KHAI ĐỀ XUẤT

*   **Phase 1 (Tháng 1-3) - Nền tảng cốt lõi & Trợ lý cuộc họp (MVP):**
    *   Xây dựng mô hình Speech-to-Text tiếng Việt tối ưu cho ngữ cảnh doanh nghiệp.
    *   Hoàn thiện công cụ đối khớp sản phẩm (Fit-Gap Agent) kết nối dữ liệu Salekit VNPT.
    *   Thử nghiệm thực tế với 10 AM tiêu biểu để tinh chỉnh trải nghiệm người dùng.
*   **Phase 2 (Tháng 4-6) - Sinh Prototype & Tài liệu đặc tả:**
    *   Tích hợp AI sinh giao diện tuân thủ nghiêm ngặt Design System của VNPT.
    *   Xây dựng công cụ tự động soạn thảo SRS/URD liên kết với Prototype.
    *   Tích hợp cổng kết nối với Jira/GitLab của VNPT IT.
*   **Phase 3 (Tháng 7-12) - Tối ưu hóa & Nhân rộng:**
    *   Tích hợp tính năng chỉnh sửa Prototype tương tác thời gian thực bằng giọng nói.
    *   Triển khai diện rộng cho toàn bộ lực lượng AM khối Khách hàng doanh nghiệp và các đơn vị sản xuất phần mềm của VNPT trên cả nước.

---

## BƯỚC 19. UX SCORECARD (ĐÁNH GIÁ CHẤT LƯỢNG)

| Tiêu chí | Điểm số (Thang 10) | Nhận xét chi tiết |
| :--- | :---: | :--- |
| **User Value (Giá trị cho người dùng)** | 9.5/10 | Giải quyết triệt để nỗi đau của AM (thiếu kiến thức kỹ thuật) và IT (yêu cầu không rõ ràng). |
| **Business Value (Giá trị kinh doanh)** | 9.5/10 | Rút ngắn Sales Cycle cực kỳ mạnh mẽ, tăng khả năng cạnh tranh của VNPT trong các gói thầu lớn. |
| **Usability (Khả năng sử dụng)** | 8.5/10 | Cần tối ưu hóa trải nghiệm điều khiển AI bằng giọng nói để đảm bảo mượt mà trong phòng họp ồn. |
| **Accessibility (Khả năng tiếp cận)** | 8.0/10 | Đảm bảo hoạt động tốt trên cả máy tính bảng (cho AM đi thị trường) và máy tính để bàn (cho BA/IT). |
| **Innovation (Tính đổi mới sáng tạo)** | 10.0/10 | Đi tiên phong trong việc khép kín chu trình từ Sales sang IT bằng công nghệ AI thế hệ mới. |

**TỔNG ĐIỂM UX SCORE: 9.1/10**

---

## BƯỚC 20. KẾT LUẬN CHUYÊN GIA

*   **Mức độ khả thi về mặt kỹ thuật:** **TRUNG BÌNH - KHÁ**. Phần ghi âm tóm tắt và sinh tài liệu SRS có độ khả thi rất cao dựa trên các mô hình ngôn ngữ lớn hiện tại (LLMs). Phần sinh Prototype tuân thủ nghiêm ngặt Design System nội bộ đòi hỏi phải xây dựng một mô hình tinh chỉnh (Fine-tuning) hoặc kỹ thuật prompt phức tạp (RAG trên UI Component Metadata) để đảm bảo đầu ra khả thi về mặt lập trình.
*   **Mức độ cạnh tranh trên thị trường:** **CỰC KỲ CAO**. Đây là vũ khí chiến lược giúp VNPT thay đổi hoàn toàn cuộc chơi tiếp cận khách hàng doanh nghiệp B2B và chính phủ số.
*   **Khuyến nghị đầu tư:** **NÊN TRIỂN KHAI NGAY**. Nên bắt đầu bằng việc xây dựng bản thử nghiệm giới hạn (PoC - Proof of Concept) cho Phase 1 tập trung vào Trợ lý cuộc họp và Đối khớp sản phẩm trong vòng 2 tháng, sau đó đánh giá hiệu quả thực tế trước khi phát triển mảng Sinh Prototype và tài liệu kỹ thuật ở Phase 2.
