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
| 1 | **Vin Smart Future (R&D Strategy)** | Tốn thời gian | Phân tích & tổng hợp xu hướng công nghệ (Tech Radar / Horizon Scanning) từ hàng nghìn bài báo arXiv/bằng sáng chế để draft báo cáo đánh giá TRL. |
| 2 | **Vin Smart Future (Cross-R&D)** | Lặp lại | Phát hiện trùng lặp đề tài & gợi ý tái sử dụng module công nghệ (Knowledge Graph) giữa các đơn vị R&D (VinAI, VinBigData, VinFast R&D, VinUni). |
| 3 | **Vin Smart Future (IP / Pháp chế)** | AI có thể tốt hơn | Rà soát nghệ thuật tiền nhiệm (Prior-Art Search) & đánh giá nguy cơ vi phạm sáng chế (FTO) từ bản thảo mô tả kỹ thuật sản phẩm mới. |
| 4 | **Vin Smart Future x VinUni** | Pain từ người khác | Dịch chuyển và ghép nối nhu cầu bài toán vận hành thực tế tại doanh nghiệp (Business Pain) thành đề tài nghiên cứu học thuật cho viện/trường. |
| 5 | **Vin Smart Future (PMO)** | Lặp lại | Chuẩn hóa, phát hiện xung đột phạm vi (scope/KPIs) và tự động hợp nhất đề cương hợp tác nghiên cứu đa bên (Consortium Proposal). |

---

# 🃏 Phase 2 — QUICK-ASSESS (Cá nhân, 30 min)

Chọn **top 3 bài toán** từ danh sách trên và hoàn thiện **3 Quick Problem Cards** dưới đây (10 phút/card).

```
┌─────────────────────────────────────────────────────────────┐
│ QUICK PROBLEM CARD #1                                       │
│                                                             │
│ Bài toán (1 câu): Tự động quét và tổng hợp tín hiệu công nghệ │
│ đột phá từ arXiv/bằng sáng chế để draft báo cáo Tech Radar. │
│ Công ty thành viên: [ ] VinFast  [ ] Xanh SM  [ ] Vinhomes  │
│                     [ ] Vinmec   [x] Khác: Vin Smart Future │
│                                                             │
│ Ai đang đau (Actor)? Đội ngũ Chuyên viên Chiến lược R&D     │
│                                                             │
│ Workflow thủ công hiện tại (4 bước):                        │
│   1. Đọc lướt hàng trăm bài báo/patent ──>                  │
│   2. Lọc thủ công công nghệ tiềm năng ──>                   │
│   3. Đánh giá mức độ sẵn sàng TRL & so sánh SOTA ──>        │
│   4. Viết báo cáo tóm tắt gửi Ban Lãnh đạo R&D              │
│                                                             │
│ Bước nào tốn thời gian/lỗi nhất? Bước 2 & 3 (⏱ 120 phút/lượt)│
│ AI có thể nhảy vào hỗ trợ ở bước nào? Bước 2 & 3 (Trích     │
│ xuất thực thể, phân loại TRL và tóm tắt key findings)       │
│                                                             │
│ Đo thành công bằng gì (Metric có số)?                        │
│   "Giảm thời gian soạn 1 báo cáo Tech Brief từ 4h ──> 20 min│
│    Tăng độ phủ bài báo quét được từ 50 ──> 500 bài/tuần"    │
│                                                             │
│ Quick Architecture: [ ] No AI  [ ] Rule  [ ] LLM  [x] Agent │
└─────────────────────────────────────────────────────────────┘
```

```
┌─────────────────────────────────────────────────────────────┐
│ QUICK PROBLEM CARD #2                                       │
│                                                             │
│ Bài toán (1 câu): Phát hiện trùng lặp đề tài và gợi ý module │
│ công nghệ tái sử dụng giữa các đơn vị R&D nội bộ Vingroup.  │
│ Công ty thành viên: [ ] VinFast  [ ] Xanh SM  [ ] Vinhomes  │
│                     [ ] Vinmec   [x] Khác: Vin Smart Future │
│                                                             │
│ Ai đang đau (Actor)? Ban Thẩm định Dự án R&D & Tech Leads   │
│                                                             │
│ Workflow thủ công hiện tại (4 bước):                        │
│   1. Nhận đề xuất nghiên cứu/dự án mới (Proposal) ──>       │
│   2. Hỏi thăm thủ công các Tech Lead ở đơn vị khác ──>      │
│   3. Rà soát danh mục dự án & kho code cũ ──>               │
│   4. Đánh giá trùng lặp & ra quyết định cấp ngân sách       │
│                                                             │
│ Bước nào tốn thời gian/lỗi nhất? Bước 2 & 3 (⏱ 180 phút/lượt)│
│ AI có thể nhảy vào hỗ trợ ở bước nào? Bước 2 & 3 (Semantic  │
│ Search & Knowledge Graph so khớp proposal với kho tài sản)  │
│                                                             │
│ Đo thành công bằng gì (Metric có số)?                        │
│   "Phát hiện trùng lặp trước phê duyệt đạt > 90% độ chính xác│
│    Giảm 30% chi phí compute/nhân sự do phát triển lại từ đầu"│
│                                                             │
│ Quick Architecture: [ ] No AI  [ ] Rule  [ ] LLM  [x] Agent │
└─────────────────────────────────────────────────────────────┘
```

```
┌─────────────────────────────────────────────────────────────┐
│ QUICK PROBLEM CARD #3                                       │
│                                                             │
│ Bài toán (1 câu): Chuyển hóa bài toán vận hành thực tế tại  │
│ công ty thành viên thành đề tài nghiên cứu học thuật VinUni. │
│ Công ty thành viên: [ ] VinFast  [ ] Xanh SM  [ ] Vinhomes  │
│                     [ ] Vinmec   [x] Khác: Vin Smart Future x VinUni│
│                                                             │
│ Ai đang đau (Actor)? Đội ngũ Hợp tác Doanh nghiệp & Viện/Trường│
│                                                             │
│ Workflow thủ công hiện tại (4 bước):                        │
│   1. Tiếp nhận phản ánh bài toán kinh doanh/vận hành ──>    │
│   2. Họp giải nghĩa thuật ngữ kinh doanh sang bài toán R&D ──>│
│   3. Tìm kiếm thủ công hồ sơ nghiên cứu giảng viên/Lab ──>  │
│   4. Soạn thảo Project Scope & Request for Proposal (RFP)   │
│                                                             │
│ Bước nào tốn thời gian/lỗi nhất? Bước 2 & 3 (⏱ 90 phút/lượt) │
│ AI có thể nhảy vào hỗ trợ ở bước nào? Bước 2 & 3 (Phân tích │
│ ngôn ngữ tự nhiên, dịch sang bài toán ML/AI và match lab)   │
│                                                             │
│ Đo thành công bằng gì (Metric có số)?                        │
│   "Rút ngắn thời gian từ tiếp nhận bài toán đến khi match lab│
│    từ 14 ngày ──> dưới 2 ngày; Match accuracy > 85%"        │
│                                                             │
│ Quick Architecture: [ ] No AI  [ ] Rule  [x] LLM  [ ] Agent │
└─────────────────────────────────────────────────────────────┘
```

> [!TIP]
> **🤖 AI Prompts — Stress-Test thẻ bài toán:**
> Hãy dán nội dung thẻ bài toán của bạn vào LLM để nhận phản biện:
> *"Đây là một thẻ bài toán vận hành tôi đề xuất cho Vin Smart Future: [Dán nội dung]. Hãy đóng vai trò là một CFO và Trưởng phòng Vận hành cực kỳ khắt khe, chỉ ra cho tôi 3 điểm yếu về logic, metric, và giải thích vì sao rule-based code thông thường có thể giải quyết bài toán này tốt hơn là dùng AI."*

---

# 🏗️ Phase 3 — DEEP-DIVE (Nhóm, 85 min)

## 3.1. Current-State Workflow Mapping (25 min)
**Quy trình thẩm định & soạn thảo báo cáo Tech Radar thủ công hiện tại:**

```
[1. Thu thập tài liệu thô] (arXiv, Google Patents, TechCrunch) ──(⏱ 60 min)──>
      │
      🔄 Handoff 1: Tải PDF/Link thủ công vào thư mục lưu trữ nội bộ
      ▼
[2. Đọc lướt & Trích xuất thông tin kỹ thuật] ──(🔴 Bottleneck 1: ⏱ 120 min)──>
      │
      ▼
[3. Phân loại TRL & Đánh giá ứng dụng vào Vingroup] ──(🔴 Bottleneck 2: ⏱ 90 min)──>
      │
      🔄 Handoff 2: Chuyển bảng ghi chú cho Lead R&D Strategy
      ▼
[4. Soạn thảo tài liệu Tech Radar Brief] ──(⏱ 60 min)──>
      │
      🔄 Handoff 3: Trình báo cáo lên Ban Lãnh đạo Vin Smart Future
      ▼
[5. Họp thẩm định & Phê duyệt Roadmap] ──(⏱ 30 min)
```

* 🔴 **Bottleneck 1:** Bước 2 — Đọc thủ công hàng trăm trang paper/patent để lọc ra phương pháp, phần cứng và benchmark SOTA.
* 🔴 **Bottleneck 2:** Bước 3 — Đối chiếu thủ công mức độ sẵn sàng công nghệ (TRL) với nhu cầu của các đơn vị (VinFast/Vinmec/Vinhomes).
* 🔄 **Handoff:** 3 điểm chuyển giao thông tin thủ công (Tải file -> Gửi bảng nháp -> Trình báo cáo).
* ⏱ **Tổng thời gian vận hành trung bình = 360 phút (6.0 giờ) / một bản báo cáo Tech Brief**.

## 3.2. Problem Statement (6-field) & Metrics (15 min)
Điền đầy đủ 6 trường thông tin của bài toán:

| Field | Nội dung chi tiết |
|---|---|
| **1. Actor / Operator** | Chuyên viên Phân tích Chiến lược Công nghệ & Tech Intelligence tại **Vin Smart Future**. |
| **2. Current Workflow** | Thu thập thủ công tài liệu học thuật (arXiv, USPTO, WIPO), đọc lướt, trích xuất thông số SOTA, đánh giá TRL và tự viết báo cáo tóm tắt trên Docs/Slides. |
| **3. Bottleneck** | Bước đọc lọc, trích xuất cấu trúc dữ liệu kỹ thuật và phân loại TRL sơ bộ ngốn 60-70% thời gian; dễ bỏ sót công nghệ mới do khối lượng công bố quá lớn. |
| **4. Business Impact** | Mỗi chuyên viên chỉ xử lý tối đa 30-50 bài/tuần; độ trễ cập nhật xu hướng công nghệ từ 2-4 tuần; nguy cơ bỏ lỡ cơ hội đầu tư R&D đột phá trước đối thủ. |
| **5. Success Metric** | 1. Giảm thời gian soạn thảo 1 Tech Radar Brief từ **360 phút ──> dưới 30 phút** (giảm >90%).<br>2. Tăng năng lực quét tài liệu từ **50 ──> 500+ tài liệu/tuần**.<br>3. F1-score trích xuất thông tin kỹ thuật & phân loại TRL sơ bộ đạt **>= 88%**.<br>4. 100% bản nháp gắn nhãn **`[DRAFT_ONLY]`** và đầy đủ URL nguồn trích dẫn. |
| **6. Operational Boundary** | **ĐƯỢC PHÉP:** Trích xuất thực thể, tóm tắt phương pháp cốt lõi, so sánh benchmark, đề xuất điểm TRL sơ bộ (1-9), gắn thẻ công ty ứng dụng (VinFast/Vinmec...).<br>**TUYỆT ĐỐI CẤM:** Không tự ý đưa ra quyết định duyệt ngân sách/đầu tư R&D; không được tự động xuất bản báo cáo ra ngoài; không bịa đặt nguồn/benchmark.<br>**HITL:** Bắt buộc Chuyên viên R&D review, kiểm chứng nguồn và ký phê duyệt trước khi đưa vào Master Tech Radar. |

## 3.3. Future-State Flow & AI Fit (25 min)
* **Xác định mức AI Fit (AI-Fit Matrix):** **[x] Agentic Loop / LLM Feature with Structured Output**. (Xử lý ngôn ngữ tự nhiên phức tạp, trích xuất JSON cấu trúc từ tài liệu phi cấu trúc).
* **Vẽ Future-State Flow:**

```
[Tài liệu Kỹ thuật / Abstract arXiv / Patent Claim]
         │
         ▼
 🔵 [AI Step 1: LLM trích xuất thực thể (Method, SOTA Benchmark, Hardware)]
         │
         ▼
 🔵 [AI Step 2: LLM chấm điểm TRL sơ bộ (1-9) & Draft Tech Brief kèm nhãn [DRAFT_ONLY]]
         │
         ├────────────────────────────────────────────┐
         │ (Nếu tài liệu thiếu thông tin / Conf < 0.7)│
         ▼                                            ▼
 🟢 [Human Step (HITL)]:                      ↩️ [Fallback Step]:
 Chuyên viên R&D kiểm chứng nguồn,            Hệ thống gắn cờ [MANUAL_REVIEW_REQUIRED],
 thẩm định TRL và phê duyệt vào Roadmap       chuyển tài liệu gốc cho chuyên gia đọc thủ công
```

---

# 💻 Phase 4 — TECHNICAL PROMPT PROTOTYPE (Nhóm, 30 min)

Để đảm bảo kỹ sư của Vin Smart Future luôn giữ vững năng lực lập trình, nhóm của bạn sẽ tiến hành **lập trình bản mẫu prompt** trực tiếp trên **Gemini 2.5 Flash** bằng Python để stress-test hệ thống.

### Hướng dẫn thực hiện:
1. Mở file [starter-code/prompt_prototype.py](starter-code/prompt_prototype.py) bằng VS Code/Cursor.
2. Hoàn thiện các nội dung sau:
   * **System Prompt:** Viết chỉ thị cực kỳ nghiêm ngặt quy định vai trò, nhiệm vụ, định dạng output và **Operational Boundary (Ranh giới cấm)** của mô hình.
   * **Structured Output:** Định nghĩa định dạng JSON output rõ ràng.
   * **Adversarial Test Cases:** Viết ít nhất 3 prompts "tấn công" (Adversarial inputs) cố tình dụ AI vượt ranh giới hoặc đưa ra câu trả lời không được phép để kiểm tra xem ranh giới của bạn có thực sự vững chắc.
3. Chạy file python:
   ```bash
   python3 prompt_prototype.py
   ```
4. Kiểm tra xem các ranh giới an toàn có bị LLM phá vỡ hay không và ghi lại kết quả vào worksheet.

---

# 🏁 Phase 5 — EVALUATE (Nhóm, 20 min)

### AI Readiness Checklist:
1. [x] Chúng tôi có sẵn dữ liệu mẫu/logs sạch để test? (Dữ liệu mở từ arXiv, Google Patents, HuggingFace Papers).
2. [x] Rủi ro khi AI sai có nằm trong tầm kiểm soát (qua HITL hoặc Fallback)? (Có quy trình Human-in-the-loop 100%, gắn nhãn `[DRAFT_ONLY]`, không tác động trực tiếp đến an toàn vận hành vật lý).
3. [x] Stakeholders sẵn sàng thay đổi quy trình làm việc cũ? (Đội ngũ R&D Strategy rất hào hứng vì giảm 90% gánh nặng đọc lọc tài liệu thủ công).

### Quyết định cuối cùng của Ban Giám Đốc Vin Smart Future:
[x] **GO (Bắt đầu xây dựng Prototype):** Bắt đầu phát triển với scope hẹp.
[ ] **NOT YET (Cần tích lũy thêm dữ liệu/xác lập baseline):** Trì hoãn để chuẩn bị thêm.
[ ] **NO-GO (Không khả thi / Rule-based tốt hơn):** Hủy bỏ dự án AI này.

**Justification (Lý giải quyết định dựa trên bằng chứng kỹ thuật và chi phí):**
> Dự án đạt tiêu chí **GO** vì:
> 1. **Giá trị ROI rõ ràng:** Giảm thời gian tổng hợp tài liệu từ 6 giờ xuống dưới 30 phút/báo cáo, mở rộng năng lực quét tín hiệu công nghệ gấp 10 lần.
> 2. **Rủi ro vận hành thấp:** Giải pháp đóng vai trò Co-pilot trợ lý phân tích, có ranh giới an toàn nghiêm ngặt (Operational Boundary) và cơ chế Human-in-the-loop 100% trước khi ra quyết định đầu tư R&D.
> 3. **Khả thi kỹ thuật cao:** LLM (Gemini 2.5 Flash) có khả năng đọc hiểu văn bản khoa học, trích xuất JSON có cấu trúc và so sánh SOTA cực kỳ vượt trội so với các hệ thống Rule-based truyền thống.

---

# 📝 Phase 6 — REFLECTION (Cá nhân)
*Ghi nhận phản ánh của cá nhân bạn về việc phối hợp với AI trong buổi học hôm nay vào file `03-ai-log.md`.*
