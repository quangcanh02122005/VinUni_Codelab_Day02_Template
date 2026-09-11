# 🔍 Phase 1 — SCAN: Tìm kiếm cơ hội (Cá nhân)

Sử dụng 4 Lenses để quét qua hoạt động vận hành của các công ty thành viên Vingroup (VinFast, Xanh SM, Vinhomes, Vinmec...).

### 📝 Danh sách bài toán vận hành (List bài toán):

| # | Subsidiary | Lens | Mô tả ngắn bài toán |
|---|------------|------|---------------------|
| 1 | **VinFast** | Tốn thời gian | **Kiểm tra và dịch thuật tài liệu kỹ thuật linh kiện nhập khẩu:** Kỹ sư phải đọc, dịch và đối chiếu thủ công hàng nghìn trang tài liệu hướng dẫn kỹ thuật từ nhà cung cấp quốc tế sang tiếng Việt.<br>*Tổn thất ước tính:* Mất trung bình 300 - 400 giờ công/tháng cho mỗi dòng xe mới, làm chậm tiến độ tích hợp linh kiện và đưa sản phẩm ra thị trường. |
| 2 | **VinFast** | Lặp lại | **Xử lý hồ sơ bảo hành và yêu cầu bồi hoàn phụ tùng đại lý:** Nhân viên hậu mãi phải kiểm tra, đối chiếu hình ảnh lỗi linh kiện gửi về từ hàng trăm đại lý với chính sách bảo hành phức tạp.<br>*Tổn thất ước tính:* Tỷ lệ sai sót xử lý thủ công đạt 12% - 15%, dẫn đến việc chi trả bồi hoàn sai hàng trăm triệu đồng mỗi quý và khiến thời gian chờ duyệt hồ sơ kéo dài 3 - 5 ngày/vụ. |
| 3 | **VinFast** | Pain từ người khác | **Lên lịch bảo dưỡng định kỳ và điều phối phụ tùng tồn kho:** Xưởng dịch vụ thường xuyên bị động do khách hàng đến quá đông hoặc thiếu phụ tùng thay thế đúng chủng loại, gây phàn nàn lớn từ chủ xe.<br>*Tổn thất ước tính:* Công suất xưởng bị thất thoát khoảng 20% do thời gian chết của thợ máy chờ linh kiện và sự không hài lòng của khách hàng. |
| 4 | **VinFast** | AI có thể tốt hơn | **Phân tích nguyên nhân gốc rễ (Root Cause Analysis - RCA) lỗi xe từ dữ liệu nhật ký (Logs):** Khi xe thu hồi dữ liệu lỗi từ thực tế, đội ngũ kỹ thuật tốn nhiều ngày để khoanh vùng nguyên nhân do phần cứng hay phần mềm.<br>*Tổn thất ước tính:* Thời gian xử lý sự cố hàng loạt kéo dài 7 - 10 ngày trước khi phát hành bản vá lỗi OTA, gây tổn hại đến uy tín thương hiệu và tăng chi phí triệu hồi xe mẫu. |
| 5 | **VinFast** | Lặp lại | **Đối soát bảng kê thanh toán tiền công và sản lượng cho kỹ thuật viên xưởng:** Phòng kế toán và quản lý xưởng phải thủ công tổng hợp bảng chi tiết giờ công, số lượng xe hoàn thành của từng thợ để tính lương.<br>*Tổn thất ước tính:* Tiêu tốn khoảng 50 giờ/tháng cho việc kiểm tra chéo dữ liệu giữa các phần mềm quản lý xưởng và bảng tính Excel, dễ phát sinh tranh chấp khi tính nhầm lương sản lượng. |

---

# 🃏 Phase 2 — QUICK-ASSESS: 3 Quick Problem Cards (Cá nhân)

Chọn top 3 bài toán từ danh sách trên để hoàn thiện 3 Quick Problem Cards:

### 🃏 QUICK PROBLEM CARD #01
```text
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

### 🃏 QUICK PROBLEM CARD #02
```text
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

### 🃏 QUICK PROBLEM CARD #03
```text
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
