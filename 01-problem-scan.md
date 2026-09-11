# 01 — Problem Scan & Quick-Assess (Vin Smart Future)

**Học viên / Kỹ sư:** AI Engineer — Vin Smart Future (Vingroup)
**Mảng phụ trách:** Phát triển Định hướng Công nghệ & Phối hợp Nghiên cứu Đa Viện/Tập đoàn

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
