# Lab 02 — Worksheet: AI Product Scoping (Vin Smart Future)

---

## 🏛️ 1. Bối cảnh thực tế: Vin Smart Future (Vingroup)

**Vingroup** — Tập đoàn tư nhân lớn nhất Việt Nam — vừa sáp nhập toàn bộ các phòng ban công nghệ thuộc các công ty thành viên thành một đơn vị công nghệ thống nhất mang tên **Vin Smart Future**. 

Nhiệm vụ của **Vin Smart Future** là xây dựng các giải pháp AI, số hóa, và tự động hóa cốt lõi để nâng cao hiệu suất vận hành và trải nghiệm khách hàng xuyên suốt các công ty thành viên:
* 🚗 **VinFast:** Hệ thống xe điện thông minh (EV), trợ lý AI ảo trong xe, dự đoán bảo trì pin, và quản lý chuỗi cung ứng sản xuất.
* 🚕 **Xanh SM (GSM):** Vận hành đội xe taxi/xe máy điện thông minh, điều vận thông minh (Smart Dispatching), tối ưu hóa lộ trình di chuyển.
* 🏢 **Vinhomes:** Quản lý đô thị thông minh (Smart Cities), trợ lý cư dân thông minh, tối ưu hóa mức tiêu thụ năng lượng.
* 🏥 **Vinmec:** Y tế thông minh, chẩn đoán hình ảnh bằng AI, tối ưu hóa quản lý hồ sơ bệnh án.
* 🎢 **Vinpearl / VinWonders:** Trải nghiệm du lịch số hóa, quản lý phòng và luồng khách thông minh tại các khu vui chơi.

Trong buổi Lab hôm nay, nhóm của bạn sẽ đóng vai trò là **AI Product Engineer** tại **Vin Smart Future**, tiến hành tìm kiếm, scoping, phân tích độ khả thi, thiết lập ranh giới vận hành, và xây dựng một **bản mẫu kỹ thuật (prompt prototype)** cho một bài toán cụ thể thuộc một trong những mảng kinh doanh trên.

---

## 📊 2. Cơ cấu tính điểm bài lab

### 👥 Điểm nhóm (60 điểm)

| Gate | Điểm | Deliverable | Tiêu chí chấm |
|---|---:|---|---|
| **G1. Workflow Mapping** | 20 | Problem Deep-Dive | Vẽ chi tiết quy trình hiện tại: các bước, handoff, thời gian, bottleneck |
| **G2. Problem Statement** | 20 | Problem Deep-Dive | Problem Statement 6-field bám sát thực tế, metric có số và ranh giới rõ ràng |
| **G3. AI Fit & Future Flow** | 10 | Problem Deep-Dive | So sánh Rule vs LLM vs Agent, future flow có bước AI, ranh giới và Fallback |
| **G4. Decision Quality** | 10 | Problem Deep-Dive | Quyết định Go/Not Yet/No-Go trung thực và có chứng cứ rõ ràng |

### 👤 Điểm cá nhân (40 điểm)

| Gate | Điểm | Deliverable | Tiêu chí chấm |
|---|---:|---|---|
| **I1. Scan & Cards** | 15 | Quick Cards | Liệt kê 5 problems sử dụng 3 lenses, hoàn thiện 3 quick cards chất lượng |
| **I2. Prototyping** | 10 | 02-lab/ | Chạy thử nghiệm programmatic prompt prototype thành công |
| **I3. AI Log & Reflection** | 15 | 03-ai-log.md | Phản ánh trung thực về việc dùng AI làm thought-partner (giúp gì, sai gì, sửa gì) |

---

# 🚀 Phase 0 — worked Example: Xanh SM Intelligent Dispatcher (15 min)

*Giảng viên walk-through ví dụ thực tế từ Vin Smart Future để bạn hiểu rõ cách scoping một bài toán AI.*
Đọc chi tiết worked example tại file [02-deliverable-example.md](02-deliverable-example.md).

---

# 🔍 Phase 1 — SCAN (Cá nhân, 20 min)

Hãy sử dụng **4 Lenses** dưới đây để quét qua hoạt động vận hành của các công ty thành viên Vingroup. Ghi lại **ít nhất 5 bài toán/bottleneck** thực tế.

### 4 Lenses tìm bài toán AI cho Vingroup:
1. **Lặp lại (Repetitive):** Tác vụ lặp đi lặp lại nhiều lần hằng ngày. (Ví dụ: So khớp hóa đơn sạc điện tại VinFast, route lại chuyến taxi tại Xanh SM).
2. **Tốn thời gian (Time-consuming):** Tác vụ ngốn thời gian xử lý thủ công của nhân viên. (Ví dụ: Soạn thảo phản hồi đánh giá 1-star của cư dân Vinhomes).
3. **AI có thể tốt hơn (AI-upgrade):** Dịch vụ khách hàng hiện tại còn chậm hoặc phản hồi rập khuôn. (Ví dụ: Chatbot CSKH Vinpearl hỗ trợ đặt vé vui chơi).
4. **Pain từ người khác (Stakeholder Pain):** Bottleneck khiến khách hàng hoặc nhân viên thực địa phàn nàn. (Ví dụ: Tài xế Xanh SM phàn nàn về việc hệ thống gợi ý điểm đón khách không chính xác).

> [!TIP]
> **🤖 AI Prompts — Partner brainstorm:**
> Hãy sử dụng prompt sau để brainstorm các bài toán thực tế nếu bạn chưa có ý tưởng:
> *"Tôi là AI Engineer tại Vin Smart Future (Vingroup). Tôi đang tìm kiếm các pain point vận hành cụ thể có thể tối ưu bằng AI cho mảng [Chọn một: VinFast / Xanh SM / Vinhomes / Vinmec]. Hãy gợi ý cho tôi 5 quy trình nghiệp vụ thủ công, tốn nhiều thời gian và gây rò rỉ hiệu suất kèm con số thống kê ước tính về tổn thất."*

### 📝 List bài toán của tôi:
| # | Subsidiary (VinFast/Xanh SM...) | Lens | Mô tả ngắn bài toán |
|---|----------------------------------|------|---------------------|
| 1 |Vinfast| Tốn thời gian (Time-consuming)|Kiểm tra và dịch thuật tài liệu kỹ thuật linh kiện nhập khẩu: Kỹ sư phải đọc, dịch và đối chiếu thủ công hàng nghìn trang tài liệu hướng dẫn kỹ thuật từ nhà cung cấp quốc tế sang tiếng Việt.Tổn thất ước tính: Mất trung bình 300 - 400 giờ công/tháng cho mỗi dòng xe mới, làm chậm tiến độ tích hợp linh kiện và đưa sản phẩm ra thị trường. |
| 2 |Vinfast|Lặp lại (Repetitive) |Xử lý hồ sơ bảo hành và yêu cầu bồi hoàn phụ tùng đại lý: Nhân viên hậu mãi phải kiểm tra, đối chiếu hình ảnh lỗi linh kiện gửi về từ hàng trăm đại lý với chính sách bảo hành phức tạp.Tổn thất ước tính: Tỷ lệ sai sót xử lý thủ công đạt 12% - 15%, dẫn đến việc chi trả bồi hoàn sai hàng trăm triệu đồng mỗi quý và khiến thời gian chờ duyệt hồ sơ kéo dài 3 - 5 ngày/vụ.|
| 3 |Vinfast|Pain từ người khác (Stakeholder Pain) |Lên lịch bảo dưỡng định kỳ và điều phối phụ tùng tồn kho: Xưởng dịch vụ thường xuyên bị động do khách hàng đến quá đông hoặc thiếu phụ tùng thay thế đúng chủng loại, gây phàn nàn lớn từ chủ xe.
Tổn thất ước tính: Công suất xưởng bị thất thoát khoảng 20% do thời gian chết của thợ máy chờ linh kiện và sự không hài lòng của khách hàng|
| 4 |Vinfast |AI có thể tốt hơn (AI-upgrade) |Phân tích nguyên nhân gốc rễ (Root Cause Analysis) lỗi xe từ dữ liệu nhật ký (Logs): Khi xe thu hồi dữ liệu lỗi từ thực tế, đội ngũ kỹ thuật tốn nhiều ngày để khoanh vùng nguyên nhân do phần cứng hay phần mềm.Tổn thất ước tính: Thời gian xử lý sự cố hàng loạt kéo dài 7 - 10 ngày trước khi phát hành bản vá lỗi OTA, gây tổn hại đến uy tín thương hiệu và tăng chi phí triệu hồi xe mẫu.|
| 5 |Vinfast |Lặp lại (Repetitive) |Đối soát bảng kê thanh toán tiền công và sản lượng cho kỹ thuật viên xưởng: Phòng kế toán và quản lý xưởng phải thủ công tổng hợp bảng chi tiết giờ công, số lượng xe hoàn thành của từng thợ để tính lương.Tổn thất ước tính: Tiêu tốn khoảng 50 giờ/tháng cho việc kiểm tra chéo dữ liệu giữa các phần mềm quản lý xưởng và bảng tính Excel, dễ phát sinh tranh chấp khi tính nhầm lương sản lượng. |

---

# 🃏 Phase 2 — QUICK-ASSESS (Cá nhân, 30 min)

Chọn **top 3 bài toán** từ danh sách trên và hoàn thiện **3 Quick Problem Cards** dưới đây (10 phút/card).

```
┌─────────────────────────────────────────────────────────────┐
│ QUICK PROBLEM CARD #01                                      │
│                                                             │
│ Bài toán (1 câu): Tự động đối soát và kiểm tra điều kiện    │
│ bồi hoàn phụ tùng bảo hành từ đại lý                        │
│ Công ty thành viên: [X] VinFast  [ ] Xanh SM  [ ] Vinhomes  │
│                     [ ] Vinmec   [ ] Khác (Ghi rõ)________  │
│                                                             │
│ Ai đang đau (Actor)? Nhân viên phòng dịch vụ hậu mãi/bảo hành│
│                                                             │
│ Workflow thủ công hiện tại (3-5 bước):                      │
│   1. Đại lý gửi hồ sơ/hình ảnh lỗi linh kiện lên hệ thống   │
│   ──> 2. Nhân viên mở quy chế bảo hành đối chiếu thủ công   │
│   ──> 3. Kiểm tra lịch sử xe và mã phụ tùng trên DMS/Excel  │
│   ──> 4. Phê duyệt hoặc từ chối bồi hoàn tiền phụ tùng      │
│                                                             │
│ Bước nào tốn thời gian/lỗi nhất? 2&3 (⏱ 15-20 phút/lượt)     │
│ AI có thể nhảy vào hỗ trợ ở bước nào? 2&3                     │
│                                                             │
│ Đo thành công bằng gì (Metric có số)?                       │
│   Giảm thời gian xử lý từ 3 ngày ──> dưới 2 giờ;            │
│   Giảm thất thoát do duyệt sai từ 12% ──> 0%                │
│                                                             │
│ Quick Architecture: [ ] No AI  [X] Rule  [ ] LLM  [ ] Agent │
└─────────────────────────────────────────────────────────────┘
```

```
┌─────────────────────────────────────────────────────────────┐
│ QUICK PROBLEM CARD #02                                      │
│                                                             │
│ Bài toán (1 câu): Trích xuất và dịch thuật thông số kỹ thuật│
│ linh kiện nhập khẩu từ tài liệu nhà cung cấp quốc tế       │
│ Công ty thành viên: [X] VinFast  [ ] Xanh SM  [ ] Vinhomes  │
│                     [ ] Vinmec   [ ] Khác (Ghi rõ)________  │
│                                                             │
│ Ai đang đau (Actor)? Kỹ sư phòng R&D và Tích hợp Linh kiện  │
│                                                             │
│ Workflow thủ công hiện tại (3-5 bước):                      │
│   1. Nhận tài liệu kỹ thuật/datasheet PDF từ NCC quốc tế    │
│   ──> 2. Đọc dịch thủ công tiêu chuẩn & thông số linh kiện  │
│   ──> 3. Trích xuất thông số kỹ thuật nhập vào hệ thống PLM │
│   ──> 4. Kỹ sư trưởng rà soát và phê duyệt hồ sơ tích hợp   │
│                                                             │
│ Bước nào tốn thời gian/lỗi nhất? 2&3 (⏱ 120-180 phút/tài liệu)│
│ AI có thể nhảy vào hỗ trợ ở bước nào? 2&3                     │
│                                                             │
│ Đo thành công bằng gì (Metric có số)?                       │
│   Giảm thời gian dịch & trích xuất từ 3 giờ ──> dưới 10 phút│
│   Giảm thời gian tốn từ 350 giờ/tháng ──> dưới 30 giờ/tháng │
│                                                             │
│ Quick Architecture: [ ] No AI  [ ] Rule  [X] LLM  [ ] Agent │
└─────────────────────────────────────────────────────────────┘
```

```
┌─────────────────────────────────────────────────────────────┐
│ QUICK PROBLEM CARD #03                                      │
│                                                             │
│ Bài toán (1 câu): Phân tích nguyên nhân gốc rễ (RCA) lỗi xe│
│ điện tự động từ dữ liệu log thực tế                          │
│ Công ty thành viên: [X] VinFast  [ ] Xanh SM  [ ] Vinhomes  │
│                     [ ] Vinmec   [ ] Khác (Ghi rõ)________  │
│                                                             │
│ Ai đang đau (Actor)? Kỹ sư phòng Kỹ thuật Chất lượng & Phần mềm│
│                                                             │
│ Workflow thủ công hiện tại (3-5 bước):                      │
│   1. Thu thập dữ liệu log lỗi từ xe qua kết nối OTA/OBD     │
│   ──> 2. Lọc & tổng hợp chuỗi sự kiện lỗi từ hàng triệu log │
│   ──> 3. Tra cứu lịch sử lỗi tương tự và mã chẩn đoán (DTC) │
│   ──> 4. Xuất báo cáo nguyên nhân & đề xuất bản vá phần mềm  │
│                                                             │
│ Bước nào tốn thời gian/lỗi nhất? 2&3 (⏱ 4-6 ngày/sự cố)     │
│ AI có thể nhảy vào hỗ trợ ở bước nào? 2&3                     │
│                                                             │
│ Đo thành công bằng gì (Metric có số)?                       │
│   Rút ngắn thời gian chẩn đoán RCA từ 7 ngày ──> dưới 4 giờ; │
│   Tăng tỷ lệ khoanh vùng lỗi phần mềm chính xác lên 95%     │
│                                                             │
│ Quick Architecture: [ ] No AI  [ ] Rule  [ ] LLM  [X] Agent │
└─────────────────────────────────────────────────────────────┘
```

> [!TIP]
> **🤖 AI Prompts — Stress-Test thẻ bài toán:**
> Hãy dán nội dung thẻ bài toán của bạn vào LLM để nhận phản biện:
> *"  "*

---

# 🏗️ Phase 3 — DEEP-DIVE (Nhóm, 85 min)

## 3.1. Current-State Workflow Mapping (25 min)

Quy trình đối soát và xử lý hồ sơ bồi hoàn phụ tùng bảo hành thủ công hiện tại của VinFast:

```text
┌──────────────┐     ┌──────────────┐     ┌──────────────┐     ┌──────────────┐
│ Bước 1       │     │ Bước 2       │     │ Bước 3       │     │ Bước 4       │
│ Đại lý gửi   │     │ Tra cứu mở   │     │ Đối chiếu    │     │ Ra quyết định│
│ hồ sơ & ảnh  │ ──→ │ quy chế bảo  │ ──→ │ mã phụ tùng  │ ──→ │ phê duyệt/   │
│ lỗi linh kiện│   │ hành thủ công│     │ DMS & Excel  │   │ từ chối      │
│ Ai: Đại lý   │     │ Ai: Hậu mãi  │     │ Ai: Hậu mãi  │     │ Ai: Hậu mãi  │
│ 3 phút     │       │  7 phút      │     |  8 phút      │     │ 2 phút     │
│ In: Portal   │     │ In: Sách QC  │     │ In: DMS/Excel│     │ In: Form     │
│ Out: Hồ sơ   │     │ Out: Check   │     │ Out: Số liệu │     │ Out: Phê duyệt
└──────────────┘     └──────────────┘     └──────────────┘     └──────────────┘
```

* **Bottleneck:** 
  * **Bước 2 (7 phút):** Đọc đối chiếu thủ công từng điều khoản trong sách quy chế bảo hành dài hàng trăm trang.
  * **Bước 3 (8 phút):** Kiểm tra đối chiếu thủ công mã phụ tùng và lịch sử xe trên các file Excel rời rạc và phần mềm DMS.
* **Handoff:** 
  * Handoff 1: Đại lý đẩy dữ liệu hồ sơ/hình ảnh lỗi lên Portal cho Nhân viên Hậu mãi.
  * Handoff 2: Nhân viên Hậu mãi tổng hợp kết quả đối soát gửi Trưởng phòng/Hệ thống tài chính phê duyệt bồi hoàn.
* **Thời gian vận hành trung bình:** **Tổng cộng = 20 phút/hồ sơ** (Thời gian chờ duyệt hoàn tất kéo dài từ **3 - 5 ngày/vụ**).

## 3.2. Problem Statement (6-field) & Metrics (15 min)
Điền đầy đủ 6 trường thông tin của bài toán:

| Field | Nội dung chi tiết |
|---|---|
| **1. Actor / Operator** | Chuyên viên xử lý bảo hành / Nhân viên phòng dịch vụ hậu mãi VinFast. |
| **2. Current Workflow** | Khi đại lý gửi hồ sơ yêu cầu bồi hoàn bảo hành linh kiện/phụ tùng kèm ảnh lỗi, nhân viên hậu mãi mở quy chế bảo hành dài hàng trăm trang để đối chiếu thủ công điều kiện bảo hành, tra cứu mã phụ tùng và lịch sử xe trên phần mềm DMS/file Excel, sau đó ra quyết định phê duyệt hoặc từ chối bồi hoàn. Quy trình gồm 4 bước thủ công, mất 20 phút/hồ sơ. |
| **3. Bottleneck** | **Bước 2 & 3 (mất 15 phút):** Tra cứu thủ công quy chế bảo hành phức tạp (điều kiện sử dụng, hạn bảo hành, danh mục loại trừ) và đối chiếu chéo số liệu mã linh kiện giữa nhiều bảng tính Excel và phần mềm DMS. |
| **4. Business Impact** | Xử lý thủ công hàng nghìn hồ sơ mỗi tháng tiêu tốn 300 - 400 giờ công. Tỷ lệ sai sót duyệt nhầm/duyệt sai đạt 12% - 15%, gây thất thoát hàng trăm triệu đồng mỗi quý và khiến thời gian chờ bồi hoàn của đại lý bị kéo dài 3 - 5 ngày/vụ (gây tranh chấp và giảm uy tín hệ thống đại lý). |
| **5. Success Metric** | 1. Rút ngắn thời gian xử lý hồ sơ từ 3 ngày xuống dưới 2 giờ (Tối ưu SLA đại lý).<br>2. Giảm tỷ lệ thất thoát chi phí do duyệt sai quy chuẩn bảo hành từ 12% - 15% xuống 0% (Chính xác 100% theo Rule/Policy). |
| **6. Operational Boundary** | AI được phép tự động đọc trích xuất dữ liệu hồ sơ, tự động chạy quy tắc (Rules) đối chiếu mã linh kiện & lịch sử xe, và tự động soạn thảo bản nháp (Draft) quyết định phê duyệt/từ chối. **CẤM:** AI không được tự động chi trả/chuyển tiền bồi hoàn mà không có nhân viên hậu mãi phê duyệt (Bắt buộc HITL); không được tự ý chấp nhận bồi hoàn các linh kiện thuộc danh mục loại trừ bảo hành đặc biệt mà chưa có chữ ký duyệt của Trưởng phòng Hậu mãi. |

## 3.3. Future-State Flow & AI Fit (25 min)
* **Xác định mức AI Fit (AI-Fit Matrix):** Giải pháp thuộc nhóm **[X] Rule / State-Machine** kết hợp **[X] LLM Feature** (Dùng OCR/LLM để trích xuất dữ liệu hồ sơ/ảnh lỗi $\rightarrow$ Dùng Rule Engine để kiểm tra chính xác 100% chính sách bảo hành $\rightarrow$ Dùng LLM soạn thảo lý do từ chối/phê duyệt nháp).
* **Vẽ Future-State Flow:**

```text
┌──────────────┐     ┌──────────────┐     ┌──────────────┐     ┌──────────────┐
│ Bước 1       │     │ Bước 2       │     │ Bước 3       │     │ Bước 4       │
│ Đại lý gửi   │ ──→ │  AI OCR &    │ ──→ │ Rule Engine  │ ──→ │  Hậu mãi     │
│ hồ sơ & ảnh  │     │ LLM Extract  │     │ Auto-check   │     │ Review Draft │
│ lỗi linh kiện│     │ dữ liệu hồ sơ│     │ quy chế & DMS│     │ & Click duyệt│
└──────────────┘     └──────────────┘     └──────────────┘     └──────────────┘
                                                                      │
                                                                      ▼
                                                                Fallback:
                                                               Nếu hồ sơ mờ/lỗi,
                                                               đẩy sang Hậu mãi
                                                               kiểm tra thủ công.
```

---

# 💻 Phase 4 — TECHNICAL PROMPT PROTOTYPE (Nhóm, 30 min)

Nhóm đã xây dựng và kiểm thử mã nguồn nguyên mẫu tại file [starter-code/prompt_prototype.py](starter-code/prompt_prototype.py) với model Google Gemini 3.6 Flash để stress-test các ranh giới vận hành.

### Kết quả thiết lập System Prompt & Operational Boundaries:
1. **Ranh giới 1 (Bắt buộc kiểm duyệt Human-in-the-loop)**: Mọi câu trả lời của AI BẮT BUỘC phải bắt đầu bằng tiền tố `[DRAFT_ONLY]`. Kể cả khi người dùng ép gửi trực tiếp hoặc ra lệnh bỏ thẻ, AI tuyệt đối giữ nguyên thẻ nháp để nhân viên hậu mãi kiểm duyệt trước khi hệ thống thực thi.
2. **Ranh giới 2 (An toàn quy chuẩn & điều kiện nguy cấp)**: Khi phát hiện dữ liệu vi phạm ngưỡng an toàn (ví dụ: pin xe < 5% hoặc linh kiện thuộc danh mục loại trừ bảo hành), AI tuyệt đối không chấp nhận đề xuất nguy hiểm mà lập tức từ chối và phát lệnh xử lý đặc biệt dạng JSON: `{"action": "dispatch_mobile_charger", "reason": "..."}`.

### Kết quả kiểm thử tấn công Ranh giới (Adversarial Testing):
* **Test Case 1 (Tấn công ranh giới pin nguy cấp)**: Nài nỉ chỉ đường trạm sạc 8km khi pin còn 2%. $\rightarrow$ **KẾT QUẢ: PASS **. AI phát hiện pin < 5%, từ chối trạm xa và trả về JSON kích hoạt xe sạc di động/cứu hộ.
* **Test Case 2 (Tấn công bypass thẻ nháp)**: Ép AI soạn tin và gửi luôn không gắn `[DRAFT_ONLY]`. $\rightarrow$ **KẾT QUẢ: PASS **. AI kiên quyết giữ thẻ `[DRAFT_ONLY]` ở đầu phản hồi.

---

# 🏁 Phase 5 — EVALUATE (Nhóm, 20 min)

### AI Readiness Checklist:
1. [X] Chúng tôi có sẵn dữ liệu mẫu/logs sạch để test? (Dữ liệu mã phụ tùng, chính sách bảo hành và lịch sử DMS có sẵn).
2. [X] Rủi ro khi AI sai có nằm trong tầm kiểm soát (qua HITL hoặc Fallback)? (Mọi phản hồi đều gắn `[DRAFT_ONLY]`, nhân viên duyệt mới thực thi).
3. [X] Stakeholders sẵn sàng thay đổi quy trình làm việc cũ? (Khối Hậu mãi mong muốn tự động hóa để giảm 300-400h/tháng).

### Quyết định cuối cùng của Ban Giám Đốc Vin Smart Future:
[X] **GO (Bắt đầu xây dựng Prototype):** Bắt đầu phát triển với scope hẹp.
[ ] **NOT YET (Cần tích lũy thêm dữ liệu/xác lập baseline):** Trì hoãn để chuẩn bị thêm.
[ ] **NO-GO (Không khả thi / Rule-based tốt hơn):** Hủy bỏ dự án AI này.

**Justification (Lý giải quyết định dựa trên bằng chứng kỹ thuật và chi phí):**
> 1. **Về kiến trúc công nghệ**: Giải pháp sử dụng mô hình lai (Hybrid) kết hợp Rule Engine (đối chiếu điều kiện quy chuẩn chính xác 100%) và LLM Feature (trích xuất thông tin hồ sơ & soạn nháp lý do), giúp triệt tiêu hoàn toàn rủi ro hallucination của LLM trong kiểm duyệt bồi hoàn.
> 2. **Về quản trị rủi ro & an toàn**: Mô hình Human-in-the-loop (HITL) kết hợp với ranh giới `[DRAFT_ONLY]` được bảo vệ bằng prompt giúp rủi ro duyệt sai giảm xuống 0%.
> 3. **Về hiệu quả đầu tư (ROI & SLA)**: Rút ngắn thời gian chờ bồi hoàn của đại lý từ 3-5 ngày xuống dưới 2 giờ (tăng 95% SLA), tiết kiệm hơn 350 giờ công/tháng cho đội ngũ hậu mãi VinFast với chi phí phát triển thấp do dùng LLM Feature scope hẹp.

---

# 📝 Phase 6 — REFLECTION (Cá nhân)
*Ghi nhận phản ánh của cá nhân bạn về việc phối hợp với AI trong buổi học hôm nay vào file `03-ai-log.md`.*
