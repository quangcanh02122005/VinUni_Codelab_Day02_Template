# 03 — AI Interaction & Reflection Log (Nhật ký Tương tác AI)

**Học viên / Kỹ sư:** AI Engineer — Vin Smart Future (Vingroup)  
**Chủ đề:** Xây dựng AI Scoping & Prompt Prototype cho Hệ thống AI Tech Radar & Horizon Scanning  
**Mô hình sử dụng:** Gemini 2.5 Flash / Gemini 3.7 Flash  

---

## 🤖 1. AI đã hỗ trợ những gì? (What AI helped with)
1. **Brainstorming & Scoping Đa chiều (Phase 1 & 2):**
   * AI đã hỗ trợ quét các bài toán vận hành thực tế tại hệ sinh thái Vingroup qua 4 Lenses (Lặp lại, Tốn thời gian, AI-Upgrade, Stakeholder Pain).
   * Cụ thể hóa bài toán *Tech Radar & Horizon Scanning* cho Vin Smart Future: chuyển đổi một ý tưởng trừu tượng thành quy trình 5 bước với các điểm nghẽn (Bottlenecks) và chỉ số đo lường (Metrics) có định lượng rõ ràng.

2. **Thiết kế Kiến trúc Vận hành & Ranh giới an toàn (Phase 3):**
   * Giúp phân tách rõ ràng trách nhiệm giữa LLM và Con người (Human-in-the-loop).
   * Xây dựng cơ chế Fallback xử lý khi dữ liệu đầu vào bị thiếu hoặc khi độ tự tin của mô hình thấp (< 0.7).

3. **Cài đặt & Thử nghiệm Prompt Prototype (Phase 4):**
   * Hỗ trợ viết code Python tích hợp Gemini SDK với cấu trúc JSON đầu ra chặt chẽ.
   * Xây dựng các ca kiểm thử tấn công biên (Adversarial test cases) để kiểm tra tính tuân thủ ranh giới an toàn của Prompt.

---

## ⚠️ 2. Những điểm AI trả lời sai / Chưa tối ưu & Cách phát hiện (Hallucinations & Flaws)
1. **Ảo tưởng về quyền tự trị (Over-autonomy Hallucination):**
   * *Vấn đề:* Trong lần draft đầu tiên, AI đề xuất để LLM *"Tự động cập nhật trực tiếp vào Lộ trình Công nghệ chính thức của Tập đoàn và gửi email thông báo cho toàn bộ ban lãnh đạo"*.
   * *Nguy cơ:* Đây là vi phạm nghiêm trọng về an toàn vận hành trong môi trường R&D chiến lược — AI không được phép tự động ban hành quyết định khi chưa qua thẩm định chuyên gia.
   * *Cách khắc phục:* Áp dụng nguyên tắc **Operational Boundary**: Bắt buộc mọi output phải gắn nhãn `[DRAFT_ONLY]` và yêu cầu Chuyên viên R&D kiểm chứng nguồn trước khi phê duyệt.

2. **Chỉ số đo lường (Metrics) chung chung, thiếu số liệu:**
   * *Vấn đề:* Ban đầu AI đưa ra các metric mơ hồ như *"Nâng cao hiệu suất nghiên cứu"* hoặc *"Tiết kiệm nhiều thời gian"*.
   * *Cách khắc phục:* Đã prompt lại và ép khuôn số liệu định lượng: *"Giảm thời gian từ 360 phút xuống dưới 30 phút"*, *"Tăng năng lực quét từ 50 lên 500+ bài/tuần"*, *"Độ chính xác F1-score >= 88%"*.

---

## 🛠️ 3. Bài học kinh nghiệm & Tinh chỉnh Prompt (Prompt Refinements & Reflection)
* **Quy tắc "Operational Boundary First":** Khi thiết kế sản phẩm AI cho doanh nghiệp, ranh giới an toàn và cơ chế Fallback quan trọng ngang bằng (thậm chí hơn) năng lực tạo sinh của mô hình.
* **Tư duy Task-level vs Workflow-level:** AI không thay thế toàn bộ công việc của chuyên viên chiến lược mà chỉ giải phóng họ khỏi 2 bước tắc nghẽn nặng nề nhất (Đọc lọc dữ liệu thô và Chấm điểm TRL sơ bộ), giúp con người tập trung vào bước ra quyết định cấp cao.
