# Phase 1: List bài toán của tôi:
| # | Subsidiary | Lens | Mô tả ngắn bài toán |
|---|----------------------------------|------|---------------------|
| 1 |**Vinmec** |Repetitive + Stakeholder Pain |Bệnh nhân khám bệnh nhiều lần nên có nhiêu trùng lặp và thay đổi, bác sĩ khó theo dõi và so sánh lịch sử các lần khám bệnh. Cần liên kết hồ sơ bệnh nhân và chia ra các mục cần chú ý(dị ứng, tiền sử, chuyển biến bệnh)
| 2 |**Vinhomes** | Phân loại & Điều hướng phản ánh cư dân | Phân loại tự động các khiếu nại gửi qua App Vinhomes Resident đến đúng ban quản lý từng tòa nhà. 
| 3 | **Xanh SM** | Tốn thời gian | Tối ưu hóa điểm đón taxi điện Xanh SM dựa trên phân tích ngôn ngữ tự nhiên từ tin nhắn tài xế và tọa độ GPS thực tế.
| 4 |**Vinmec**  |Repetitive| Soạn tóm tắt sau khám: Sau mỗi lượt khám, nhân viên phải tổng hợp thông tin từ nhiều trường dữ liệu thành nội dung dễ hiểu cho bệnh nhân. AI có thể tạo bản nháp từ dữ liệu đã có để nhân viên kiểm tra trước khi gửi.|
| 5 |**Vinpearl/VinWonders**|Repetitive + Stakeholder Pain|Phân tích phản ánh về tiện ích: Gom nhóm phản ánh về các tiện ích và dịch vụ để xác định vấn đề lặp lại và ưu tiên xử lý. |

---

# Phase 2 — QUICK-ASSESS (Cá nhân, 30 min)

Chọn **top 3 bài toán** từ danh sách trên và hoàn thiện **3 Quick Problem Cards** dưới đây (10 phút/card).

```
┌─────────────────────────────────────────────────────────────┐
│ QUICK PROBLEM CARD #4                                     │
│                                                             │
│ Bài toán (1 câu): Tự động tạo bản nháp tóm tắt sau khám từ dữ liệu khám bệnh có sẵn để nhân viên chỉ cần kiểm tra và gửi cho bệnh nhân. │
│ Công ty thành viên: [ ] VinFast  [ ] Xanh SM  [ ] Vinhomes  │
│                     [x ] Vinmec   [ ] Khác (Ghi rõ)________  │
│                                                             │
│ Ai đang đau (Actor)? Nhân viên/bác sĩ phụ trách hoàn thiện thông tin, Bệnh nhân │
│                                                             │
│ Workflow thủ công hiện tại (3-5 bước):                      │
│   1.Bác sĩ hoàn tất thông tin khám →
  Nhân viên tổng hợp thông tin từ các trường dữ liệu (triệu chứng, chẩn đoán, thuốc, chỉ định...) → 2. Viết lại thành nội dung dễ hiểu cho bệnh nhân → 3. Kiểm tra thông tin → 4.Gửi bản tóm tắt cho bệnh nhân.                 │
│                                                             │
│ Bước nào tốn thời gian/lỗi nhất? Bước 2–3: đọc nhiều trường dữ liệu và diễn đạt lại thành nội dung dễ hiểu (⏱  5–10 phút/lượt )      │
│ AI có thể nhảy vào hỗ trợ ở bước nào?  Bước 2–3: LLM nhận dữ liệu khám đã được chuẩn hóa và tạo bản nháp tóm tắt sau khám theo template được phê duyệt.│
│                                                             │
│ Đo thành công bằng gì (Metric có số)? Giảm thời gian soạn tóm tắt từ 5–10 phút → ≤2 phút/lượt, đồng thời đạt ≥95% thông tin quan trọng chính xác và 100% bản gửi bệnh nhân được nhân viên/bác sĩ kiểm duyệt. │
│                                                             │
│ Quick Architecture: [ ] No AI  [ ] Rule  [X] LLM  [ ] Agent │
└─────────────────────────────────────────────────────────────┘

─────────────────────────────────────────────────────────────┐
│ QUICK PROBLEM CARD #1                                     │
│ Bài toán (1 câu):Liên kết và tóm tắt lịch sử khám bệnh của bệnh nhân qua nhiều lần khám │
│ Công ty thành viên: [ ] VinFast  [ ] Xanh SM  [ ] Vinhomes  │
│                     [X ] Vinmec   [ ] Khác (Ghi rõ)________  │
│                                                             │
│ Ai đang đau (Actor)? Bác sĩ: phải đọc và đối chiếu nhiều hồ sơ/lần khám để hiểu diễn biến.
Bệnh nhân: có nguy cơ phải lặp lại thông tin đã cung cấp ở các lần khám trước. │
│                                                             │
│ Workflow thủ công hiện tại (3-5 bước):                      │
│   1. Bệnh nhân đến khám →2.Bác sĩ mở hồ sơ bệnh án và xem các lần khám trước → 3.Đọc kết quả xét nghiệm/chẩn đoán/đơn thuốc liên quan →4.Tự đối chiếu các thay đổi theo thời gian →  5. Ghi nhận các thông tin quan trọng để phục vụ lần khám hiện tại.                 │
│                                                             │
│ Bước nào tốn thời gian/lỗi nhất? Bước 2–4: Đọc và đối chiếu lịch sử bệnh án.

 (⏱10–15 phút/bệnh nhân có lịch sử khám dài)      │
│ AI có thể nhảy vào hỗ trợ ở bước nào? Bước 2–4 │
│                                                             │
│ Đo thành công bằng gì (Metric có số)? Giảm thời gian bác sĩ cần để nắm lịch sử bệnh nhân từ 10–15 phút → ≤5 phút/bệnh nhân, đồng thời đạt ≥95% độ chính xác khi trích xuất các thông tin quan trọng và 100% thông tin AI đưa ra có thể truy xuất về hồ sơ nguồn. │
│                                                             │
│ Quick Architecture: [ ] No AI  [ ] Rule  [X ] LLM  [ ] Agent │
└─────────────────────────────────────────────────────────────┘
─────────────────────────────────────────────────────────────┐
│ QUICK PROBLEM CARD #3                                     │
│                                                             │
│ Bài toán (1 câu):Phân tích tin nhắn của tài xế kết hợp với tọa độ GPS để xác định điểm đón thực tế phù hợp hơn  │
│ Công ty thành viên: [ ] VinFast  [ X] Xanh SM  [ ] Vinhomes  │
│                     [ ] Vinmec   [ ] Khác (Ghi rõ)________  │
│                                                             │
│ Ai đang đau (Actor)? Tài xế: mất thời gian tìm/tiếp cận điểm đón, phải nhắn tin giải thích vị trí thực tế.
Khách hàng: có thể phải chờ hoặc di chuyển đến vị trí khác để gặp tài xế.
Bộ phận điều vận: phải xử lý các trường hợp điểm đón không chính xác/thực tế không thuận tiện. │
│                                                             │
│ Workflow thủ công hiện tại (3-5 bước):                      │
│   1.Khách đặt chuyến và hệ thống xác định điểm đón → 2.Tài xế di chuyển đến điểm đón → 3.ài xế gặp vấn đề và gửi tin nhắn mô tả vị trí/thực trạng → 4.Điều phối viên đọc tin nhắn + kiểm tra GPS →5. Xác định điểm đón thay thế và hướng dẫn tài xế/khách hàng.                │
│                                                             │
│ Bước nào tốn thời gian/lỗi nhất?Bước 3–5: Đọc hiểu tin nhắn + đối chiếu GPS + xác định điểm đón thay thế (⏱3–5 phút phút/lượt)      │
│ AI có thể nhảy vào hỗ trợ ở bước nào? Bước 3–4 │
│                                                             │
│ Đo thành công bằng gì (Metric có số)? Giảm thời gian xử lý một case điểm đón từ 3–5 phút → ≤1 phút, đồng thời đạt ≥90% độ chính xác trong phân loại nguyên nhân và ≥85% tỷ lệ đề xuất điểm đón được điều phối viên chấp nhận."│
│                                                             │
│ Quick Architecture: [ ] No AI  [X ] Rule  [ X] LLM  [ ] Agent │
└─────────────────────────────────────────────────────────────┘