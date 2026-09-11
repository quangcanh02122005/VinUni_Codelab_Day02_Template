# 02 — Deep-Dive Report (Vin Smart Future)

**Dự án AI:** AI Tech Radar & Horizon Scanning System
**Đơn vị:** Vin Smart Future (R&D Strategy)

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
