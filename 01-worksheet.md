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

> **Cơ sở của bản SCAN:** Các bài toán dưới đây là giả thuyết được phát triển từ tài liệu lab và trao đổi với AI, chưa được xác minh bằng phỏng vấn hoặc dữ liệu nội bộ doanh nghiệp. Cần khảo sát người thực hiện, đo thời gian xử lý và kiểm tra dữ liệu mẫu trước khi kết luận về mức độ tổn thất.

| # | Subsidiary (VinFast/Xanh SM...) | Lens | Mô tả ngắn bài toán |
|---|----------------------------------|------|---------------------|
| 1 | **Xanh SM** | **Pain từ người khác (Stakeholder Pain)** | **Hỗ trợ chọn thời điểm và trạm sạc:** Tài xế cần chọn thời điểm và trạm sạc phù hợp với lượng pin, vị trí xe và ca làm việc. Giả thuyết cần khảo sát là thông tin về khả năng phục vụ và thời gian chờ tại trạm chưa đủ để ra quyết định, khiến tài xế mất thời gian tìm trạm hoặc xếp hàng, giảm thời gian sẵn sàng nhận chuyến. |
| 2 | **Xanh SM** | **AI có thể tốt hơn (AI-upgrade)** | **Điều phối & cân bằng tài xế theo khu vực (Dispatch Rebalancing):** Nhân viên điều vận cần so sánh nhu cầu đặt xe và số tài xế sẵn sàng ở từng khu vực để đề xuất chuyển xe nhàn rỗi. Bottleneck dự kiến là tổng hợp biến động cung–cầu và các ràng buộc xe/ca làm việc chưa kịp thời, dẫn đến khu vực thiếu xe trong khi khu vực khác có xe chờ khách. |
| 3 | **Xanh SM** | **Tốn thời gian (Time-consuming)** | **Phát hiện gian lận & hành vi bất thường (Fraud & Anomaly Detection):** Nhân viên kiểm soát phải đối chiếu dữ liệu chuyến, GPS, thời gian và giao dịch để đánh giá các dấu hiệu nghi vấn. Bottleneck dự kiến là kiểm tra thông tin ở nhiều nguồn và phân biệt bất thường do lỗi dữ liệu với trường hợp cần điều tra, kéo dài thời gian rà soát và có nguy cơ bỏ sót hoặc cảnh báo nhầm. |
| 4 | **Xanh SM** | **Lặp lại (Repetitive)** | Nhân viên CSKH đọc yêu cầu về đồ thất lạc, phản ánh thái độ tài xế hoặc thắc mắc cước; hỏi thông tin còn thiếu, phân loại, chuyển bộ phận và soạn phản hồi. Bottleneck dự kiến là tổng hợp nội dung qua nhiều lượt trao đổi và xử lý lặp lại các nhóm yêu cầu tương tự, kéo dài thời gian tiếp nhận và tăng nguy cơ chuyển sai bộ phận. |

---

# 🃏 Phase 2 — QUICK-ASSESS (Cá nhân, 30 min)

Chọn **top 3 bài toán** từ danh sách trên và hoàn thiện **3 Quick Problem Cards** dưới đây (10 phút/card).

**Ba bài toán được chọn:** **#1 — Xanh SM: hỗ trợ chọn thời điểm và trạm sạc**, **#2 — Xanh SM: điều phối & cân bằng tài xế theo khu vực (Dispatch Rebalancing)** và **#3 — Xanh SM: phát hiện gian lận & hành vi bất thường (Fraud & Anomaly Detection)**. Số card khớp với số bài toán trong Phase 1. **Bài #1 về pin/sạc được chọn để phân tích sâu**; bài #4 về CSKH giữ ở bước SCAN.

> **Trạng thái bằng chứng:** Các workflow và thời gian dưới đây là giả định để thiết kế thử nghiệm, chưa phải kết quả khảo sát doanh nghiệp. Các ngưỡng thành công là mục tiêu đề xuất, chưa được chạy kiểm chứng. Thời gian xử lý tính từ lúc nhân viên mở yêu cầu đến lúc hoàn thành phương án, bản phản hồi hoặc chuyển tiếp đã duyệt. Không tính thời gian chờ bổ sung thông tin, di chuyển, xếp hàng, sạc pin hoặc giải quyết sự cố ngoài thực địa vào metric thời gian xử lý của nhân viên.

### Quick Problem Card #1 — Xanh SM: Hỗ trợ chọn thời điểm và trạm sạc

| Nội dung | Chi tiết |
|---|---|
| **Bài toán (1 câu)** | Tài xế và nhân viên điều vận mất thời gian tổng hợp thông tin xe, ca làm việc và trạm sạc để chọn thời điểm, địa điểm sạc phù hợp, có nguy cơ chọn phương án phải chờ lâu hoặc không đáp ứng điều kiện của xe. |
| **Công ty / Lens** | Xanh SM / Pain từ người khác — tương ứng bài toán **#1 của Phase 1**. |
| **Actor** | Tài xế cần phương án sạc phù hợp; trong workflow giả định của prototype, nhân viên điều vận hỗ trợ tra cứu, đối chiếu và duyệt đề xuất trước khi gửi tài xế. |
| **Workflow hiện tại — giả định** | **1.** Nhận vị trí, tình trạng pin, thông tin xe và lịch ca từ tài xế (2 phút) → **2.** Tra cứu các trạm tương thích và thời gian di chuyển (3 phút) → **3.** Đối chiếu trạng thái trạm, thời gian chờ và thời lượng sạc dự kiến (3 phút) → **4.** So sánh các phương án trạm/khung giờ đáp ứng điều kiện đã xác nhận của xe và ca làm việc (2 phút) → **5.** Soạn, kiểm tra và duyệt hướng dẫn gửi tài xế (2 phút). **Tổng: 12 phút/yêu cầu.** |
| **Bottleneck** | Bước **2–4**, giả định **8 phút/yêu cầu**: thông tin xe, trạm và ca làm việc nằm ở nhiều nguồn; mất thời gian loại phương án không phù hợp và so sánh thời gian di chuyển, chờ, sạc. |
| **AI hỗ trợ ở đâu?** | LLM hỗ trợ bước **1** để trích xuất yêu cầu của tài xế, phát hiện thông tin còn thiếu; ở bước **5**, giải thích phương án do rule tính và soạn hướng dẫn nháp. Bước **2–4** dùng dữ liệu được cung cấp và code lọc/xếp hạng, không giao việc xác định xe có thể đến trạm hay không cho LLM. Đầu ra JSON gồm `action`, `suggested_station_id`, `suggested_time_window`, `reason`, `missing_fields`, `draft_reply`, `needs_human_review`. |
| **Success Metric — mục tiêu** | Giảm thời gian lập và duyệt phương án trung bình từ **12 phút giả định xuống ≤ 5 phút**, gồm thời gian chờ mô hình, sửa và duyệt; xử lý đúng **ít nhất 27/30 tình huống** theo đáp án xác định trước về trạm/khung giờ hoặc chuyển kiểm tra thủ công; **0/30 đầu ra** đề xuất phương án bị rule đánh dấu không hợp lệ hoặc bịa trạng thái trạm. Kết quả này chỉ đánh giá hỗ trợ ra quyết định trên bộ thử; chưa chứng minh giảm thời gian xếp hàng, thời gian sạc hay tăng số chuyến thực tế. |
| **Quick Architecture** | **Rule + LLM Feature.** Rule lọc phương án theo tính tương thích, khả năng tiếp cận đã được xác nhận, độ mới dữ liệu và khung giờ được phép; xếp hạng các phương án hợp lệ theo tổng thời gian di chuyển + chờ + sạc dự kiến. LLM nhận kết quả để giải thích và viết nháp. Code kiểm tra lại ID trạm, khung giờ và các số liệu trong output; điều vận duyệt trước khi gửi. |
| **Ranh giới / Fallback** | Không tự suy ra quãng đường xe đi được từ phần trăm pin, không bịa trạm trống, không tự đặt chỗ sạc, điều xe hoặc phát lệnh cứu hộ. Dữ liệu thiếu, quá hạn, mâu thuẫn hoặc không có phương án hợp lệ thì trả `manual_review`, để trạm/khung giờ là `null` và chuyển điều vận xác minh hoặc xử lý theo quy trình hỗ trợ hiện hành. Nội dung tài xế nhập không được ghi đè dữ liệu xe/trạm đã xác nhận. |
| **Dữ liệu cần chuẩn bị** | 30 tình huống mô phỏng: 10 đủ dữ liệu có phương án hợp lệ, 10 thiếu/quá hạn/mâu thuẫn dữ liệu, 10 không có phương án hợp lệ. Chuẩn bị các phương án trạm/khung giờ với ID, loại cổng, điều kiện tiếp cận đã xác nhận, thời gian di chuyển/chờ/sạc dự kiến và thời điểm cập nhật, kèm đáp án trước khi thử. Thêm ít nhất 3 đầu vào dụ AI chọn trạm bị loại, tự bịa trụ trống hoặc bỏ bước duyệt. Các điều kiện trong dữ liệu giả lập không phải hướng dẫn an toàn vận hành thực tế. |

**Phạm vi chọn cho lab:** Hỗ trợ lập phương án sạc kế tiếp cho **một tài xế tại một thời điểm**, từ danh sách trạm và khung giờ ứng viên được cung cấp. Đây là bước đầu của bài toán chọn thời điểm/trạm sạc; chưa xây dựng mô hình dự báo hay lịch sạc tối ưu cho toàn đội xe. Nếu chỉ có dữ liệu giả lập, chỉ kết luận về tính đúng của luồng xử lý và chất lượng bản nháp trong các tình huống đó. Cần dữ liệu thực và thử nghiệm vận hành để đánh giá tác động đến thời gian chờ hoặc thời gian sẵn sàng nhận chuyến.

### Quick Problem Card #2 — Xanh SM: Điều phối & cân bằng tài xế theo khu vực (Dispatch Rebalancing)

| Nội dung | Chi tiết |
|---|---|
| **Bài toán (1 câu)** | Nhân viên điều vận mất thời gian xác định vùng thừa/thiếu xe và lập phương án chuyển tài xế nhàn rỗi khi nhu cầu đặt xe thay đổi giữa các khu vực. |
| **Công ty / Lens** | Xanh SM / AI có thể tốt hơn — tương ứng bài toán **#2 của Phase 1**. |
| **Actor** | Nhân viên điều vận lập phương án; tài xế có thể chờ lâu ở vùng thừa xe, trong khi khách tại vùng thiếu xe phải chờ đón. |
| **Workflow hiện tại — giả định** | **1.** Thu thập số yêu cầu và tài xế sẵn sàng theo vùng (2 phút) → **2.** So sánh cung–cầu trong cùng khung thời gian (3 phút) → **3.** Kiểm tra xe đủ điều kiện chuyển vùng theo trạng thái chuyến, pin và ca làm việc (3 phút) → **4.** Lập phương án chuyển xe, kiểm tra khả năng đáp ứng tại vùng xuất phát và vùng đích (2 phút) → **5.** Kiểm tra, duyệt và soạn thông báo điều phối (2 phút). **Tổng: 12 phút/lượt lập phương án.** |
| **Bottleneck** | Bước **2–4**, giả định **8 phút/lượt**: cần đối chiếu số liệu nhiều vùng cùng lúc, tránh chuyển quá nhiều xe và tránh phân công xe không sẵn sàng. |
| **AI hỗ trợ ở đâu?** | Khi mở rộng, mô hình dự báo nhu cầu có thể cung cấp đầu vào cho bước **2** nếu có dữ liệu lịch sử phù hợp. Trong prototype, dùng dự báo giả lập có sẵn; code tính chênh lệch cung–cầu và phương án chuyển ở bước **2–4**. LLM hỗ trợ bước **5** bằng cách tóm tắt lý do, các ràng buộc và soạn nháp thông báo từ phương án đã tính. |
| **Success Metric — mục tiêu** | Giảm thời gian lập và duyệt phương án trung bình từ **12 phút giả định xuống ≤ 5 phút**; **30/30 phương án** tuân thủ ràng buộc về số xe, trạng thái sẵn sàng, vùng hợp lệ và khả năng tiếp cận đã xác nhận; **ít nhất 27/30 bản giải thích** khớp toàn bộ số liệu và quyết định trong đáp án tham chiếu. Chưa dùng các mục tiêu này để khẳng định giảm thời gian chờ khách hoặc tăng doanh thu thực tế. |
| **Quick Architecture** | **Rule + LLM Feature trong lab; dự báo nhu cầu là hướng mở rộng.** Code phân bổ theo dữ liệu cung–cầu và giới hạn chuyển xe đã cấu hình, kiểm tra không phân một xe cho nhiều vùng và không tạo số xe âm. LLM chỉ diễn giải phương án. Điều vận duyệt trước khi phát lệnh. |
| **Ranh giới / Fallback** | Không tự điều xe, thay đổi ca, gán chuyến, bịa số liệu nhu cầu hoặc ghi đè trạng thái xe đã xác nhận. Thiếu dữ liệu, dữ liệu quá hạn hoặc phương án vi phạm ràng buộc thì trả `manual_review` để điều vận xử lý. Vùng đã cân bằng thì giữ nguyên; không bắt buộc đề xuất chuyển xe trong mọi trường hợp. |
| **Dữ liệu cần chuẩn bị** | 30 tình huống mô phỏng: 10 cung–cầu đã cân bằng, 10 mất cân bằng có phương án hợp lệ, 10 thiếu dữ liệu hoặc không có phương án hợp lệ. Mỗi tình huống có số xe sẵn sàng, nhu cầu dự kiến trong cùng khung giờ, xe đủ điều kiện chuyển, thời gian di chuyển, mức xe tối thiểu cần giữ và đáp án tham chiếu. Thêm đầu vào dụ AI dùng xe đang có khách hoặc phát lệnh chưa duyệt. |

**Phạm vi thử của Card #2:** Một lượt lập phương án cho một số khu vực giả lập. So sánh kết quả phân bổ với quy tắc điều phối tham chiếu; so sánh bản giải thích LLM với mẫu thông báo điền sẵn. Chưa huấn luyện mô hình dự báo và chưa chứng minh hiệu quả cân bằng đội xe trong vận hành thực tế.

### Quick Problem Card #3 — Xanh SM: Phát hiện gian lận & hành vi bất thường (Fraud & Anomaly Detection)

| Nội dung | Chi tiết |
|---|---|
| **Bài toán (1 câu)** | Nhân viên kiểm soát mất thời gian đối chiếu dữ liệu chuyến và giao dịch để nhận diện dấu hiệu bất thường, chuẩn bị bằng chứng và xác định hồ sơ cần điều tra thêm. |
| **Công ty / Lens** | Xanh SM / Tốn thời gian — tương ứng bài toán **#3 của Phase 1**. |
| **Actor** | Nhân viên kiểm soát gian lận hoặc kiểm toán vận hành rà soát hồ sơ; tài xế và khách hàng có thể bị ảnh hưởng nếu hệ thống bỏ sót hoặc cảnh báo nhầm. |
| **Workflow hiện tại — giả định** | **1.** Nhận cảnh báo hoặc hồ sơ cần rà soát (1 phút) → **2.** Tập hợp dữ liệu chuyến, GPS, thời gian và giao dịch liên quan (3 phút) → **3.** Đối chiếu chỉ báo, kiểm tra dữ liệu thiếu và khả năng lỗi hệ thống (3 phút) → **4.** Ghi bằng chứng và đề xuất cần điều tra thêm hay chưa đủ dữ liệu (2 phút) → **5.** Nhân viên kiểm tra, duyệt và chuyển hồ sơ (1 phút). **Tổng: 10 phút/hồ sơ rà soát ban đầu.** |
| **Bottleneck** | Bước **2–4**, giả định **8 phút/hồ sơ**: dữ liệu ở nhiều nguồn, tín hiệu bất thường có thể do lỗi GPS hoặc dữ liệu thiếu; cần gắn từng nhận định với bằng chứng cụ thể thay vì kết luận vội. |
| **AI hỗ trợ ở đâu?** | Code tính chỉ báo bất thường ở bước **3**; LLM hỗ trợ bước **4** bằng cách tóm tắt tín hiệu, nêu dữ liệu còn thiếu và soạn báo cáo có tham chiếu ID bằng chứng. Đầu ra gồm `review_status`, `signals`, `evidence_ids`, `missing_fields`, `review_summary`, `needs_human_review`. Các trạng thái chỉ là `needs_review`, `insufficient_data`, `no_trigger`; không có trạng thái tự kết luận gian lận. |
| **Success Metric — mục tiêu** | Giảm thời gian rà soát ban đầu trung bình từ **10 phút giả định xuống ≤ 5 phút**, gồm kiểm tra và duyệt; nhận diện **ít nhất 9/10 hồ sơ cần xem xét**, gắn cờ nhầm **không quá 1/10 hồ sơ bình thường**, và chuyển đúng **10/10 hồ sơ thiếu dữ liệu** sang `insufficient_data` trên bộ mô phỏng có đáp án trước. **0/30 báo cáo** bịa bằng chứng hoặc khẳng định cá nhân đã gian lận. Nhãn ở đây là nhu cầu rà soát theo kịch bản, không phải kết quả điều tra gian lận thực tế. |
| **Quick Architecture** | **Rule + LLM Feature trong lab.** Rule phát hiện chỉ báo theo tiêu chí giả lập được định nghĩa trước; LLM tổng hợp báo cáo từ tín hiệu và bằng chứng đã có. Code kiểm tra ID bằng chứng, số liệu và trạng thái hợp lệ trước khi nhân viên duyệt. Mô hình anomaly detection là hướng mở rộng khi có dữ liệu và kết quả thẩm định phù hợp. |
| **Ranh giới / Fallback** | Không tự khóa tài khoản, thu hồi thưởng, trừ tiền, thông báo cáo buộc hoặc kết luận gian lận từ một dấu hiệu GPS. Thiếu hoặc mâu thuẫn dữ liệu thì ghi rõ giới hạn và chuyển nhân viên xác minh. `no_trigger` chỉ nghĩa là chưa thấy tín hiệu theo bộ rule hiện tại, không chứng minh hồ sơ hoàn toàn không có gian lận. |
| **Dữ liệu cần chuẩn bị** | 30 hồ sơ mô phỏng với ID giả: 10 có tín hiệu cần rà soát theo tiêu chí đã định nghĩa, 10 bình thường, 10 thiếu dữ liệu để đánh giá. Mỗi hồ sơ có bản ghi liên quan, chỉ báo tính sẵn, ID bằng chứng và đáp án kiểm tra; không coi kết quả LLM là nhãn chuẩn. Thêm đầu vào dụ AI kết luận gian lận khi thiếu bằng chứng hoặc tự khóa tài khoản. |

**Phạm vi thử của Card #3:** Sàng lọc tín hiệu bất thường và hỗ trợ chuẩn bị hồ sơ điều tra. Cần dữ liệu có kết quả thẩm định thực tế để đo chất lượng phát hiện gian lận; bộ mô phỏng chỉ kiểm tra quy tắc và khả năng tóm tắt có căn cứ. So sánh LLM với báo cáo tự điền theo mẫu để xác định lợi ích bổ sung.

### Đối chiếu lựa chọn và hướng phát triển

| Bài toán ở Phase 1 | Quyết định tại Phase 2 | Lý do |
|---|---|---|
| **#1 — Xanh SM: thời điểm/trạm sạc** | **Ưu tiên 1; chọn deep-dive** | Chọn theo hướng pin/sạc. Thu hẹp vào một yêu cầu sạc với dữ liệu trạm/khung giờ được cung cấp, dùng rule chọn phương án và LLM soạn giải thích có duyệt. Chưa có dữ liệu thực nên chưa kết luận hiệu quả tối ưu vận hành. |
| **#2 — Xanh SM: điều phối & cân bằng tài xế** | **Ưu tiên 2; hoàn thiện card** | Có thể mô phỏng một lượt phân bổ xe và kiểm tra ràng buộc. Dự báo nhu cầu và hiệu quả cân bằng thực tế cần dữ liệu theo khu vực, thời gian và đánh giá vận hành riêng. |
| **#3 — Xanh SM: gian lận & hành vi bất thường** | **Ưu tiên 3; hoàn thiện card** | Có thể thử phát hiện tín hiệu bằng rule và tóm tắt bằng chứng. Chưa có dữ liệu thẩm định nên chỉ đánh giá hỗ trợ rà soát, chưa kết luận hiệu quả phát hiện gian lận thực tế. |
| **#4 — Xanh SM: khiếu nại** | **Giữ ở SCAN; chưa chọn làm card** | Là phương án có thể thử bằng dữ liệu văn bản, nhưng hướng phân tích sâu đã chọn là pin/sạc. Giữ bài toán này trong Phase 1 để đối chiếu, không gộp luồng CSKH vào prototype sạc. |

**Cách kiểm chứng chung:** Các bộ dữ liệu trên mới là kế hoạch chuẩn bị. Khi thử, đo cả quy trình thủ công và quy trình có AI trên các tình huống có độ khó tương đương, đổi thứ tự giữa hai cách để hạn chế lợi thế do đã đọc trước. Tính thời gian trung bình gồm xử lý, chờ mô hình, sửa và duyệt; thay các baseline giả định bằng số đo thực tế. So sánh từng giải pháp với rule và mẫu hướng dẫn/báo cáo được điền tự động; tách lợi ích của phần tính toán bằng code khỏi lợi ích của phần diễn giải bằng LLM. Chỉ kết luận AI có lợi khi đạt ngưỡng chất lượng và giảm thời gian so với phương án đơn giản; chưa suy rộng kết quả mô phỏng thành ROI thực tế.

**Bài toán cá nhân đã chọn cho Phase 3:** **#1 — Xanh SM: hỗ trợ chọn thời điểm và trạm sạc, có điều vận duyệt.** Phân tích sâu theo phạm vi một yêu cầu sạc nêu trong card. Việc chọn đề tài chưa phải quyết định GO triển khai thực tế, chưa thay thế quyết định của nhóm và không có nghĩa prototype đã được kiểm thử thành công.

> [!TIP]
> **🤖 AI Prompts — Stress-Test thẻ bài toán:**
> Hãy dán nội dung thẻ bài toán của bạn vào LLM để nhận phản biện:
> *"Đây là một thẻ bài toán vận hành tôi đề xuất cho Vin Smart Future: [Dán nội dung]. Hãy đóng vai trò là một CFO và Trưởng phòng Vận hành cực kỳ khắt khe, chỉ ra cho tôi 3 điểm yếu về logic, metric, và giải thích vì sao rule-based code thông thường có thể giải quyết bài toán này tốt hơn là dùng AI."*

---

# 🏗️ Phase 3 — DEEP-DIVE (Nhóm, 85 min)

## 3.1. Current-State Workflow Mapping (25 min)
**Vẽ quy trình hiện tại lên bảng/giấy A3.** Sử dụng các ký hiệu:
* 🔴 **Bottleneck:** Bước gây tắc nghẽn, tốn thời gian, hoặc sai sót nhiều nhất.
* 🔄 **Handoff:** Điểm chuyển giao thông tin giữa người và hệ thống, hoặc giữa các bộ phận.
* Ghi rõ thời gian vận hành trung bình: **Tổng cộng = ____ phút/lượt**.

## 3.2. Problem Statement (6-field) & Metrics (15 min)
Điền đầy đủ 6 trường thông tin của bài toán:

| Field | Nội dung chi tiết |
|---|---|
| **1. Actor / Operator** | Ai đang thực hiện tác vụ hằng ngày? |
| **2. Current Workflow** | Mô tả tóm tắt quy trình thủ công hiện tại và công cụ sử dụng. |
| **3. Bottleneck** | Bước nào chậm, lỗi, hoặc cần xử lý ngôn ngữ tự động nhiều nhất? |
| **4. Business Impact** | Tổn thất thực tế đo bằng thời gian, chi phí, hoặc SLA của Vingroup. |
| **5. Success Metric** | AI giải quyết được thì đạt ngưỡng số mấy? (Ví dụ: *"85% vé được phân loại dưới 10s"*). |
| **6. Operational Boundary** | AI được phép làm gì, TUYỆT ĐỐI không được làm gì, điểm nào cần duyệt? |

## 3.3. Future-State Flow & AI Fit (25 min)
* **Xác định mức AI Fit (AI-Fit Matrix):** Giải pháp thuộc nhóm nào? [ ] Rule / State-Machine [ ] LLM Feature [ ] Agentic Loop.
* **Vẽ Future-State Flow:** Đánh dấu rõ:
  * 🔵 **AI Step:** Tác vụ LLM xử lý.
  * 🟢 **Human Step (HITL):** Bước con người phê duyệt/review (Human-in-the-loop).
  * ↩️ **Fallback:** Kế hoạch dự phòng khi LLM trả về kết quả lỗi hoặc không tự tin.

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
1. [ ] Chúng tôi có sẵn dữ liệu mẫu/logs sạch để test?
2. [ ] Rủi ro khi AI sai có nằm trong tầm kiểm soát (qua HITL hoặc Fallback)?
3. [ ] Stakeholders sẵn sàng thay đổi quy trình làm việc cũ?

### Quyết định cuối cùng của Ban Giám Đốc Vin Smart Future:
[ ] **GO (Bắt đầu xây dựng Prototype):** Bắt đầu phát triển với scope hẹp.
[ ] **NOT YET (Cần tích lũy thêm dữ liệu/xác lập baseline):** Trì hoãn để chuẩn bị thêm.
[ ] **NO-GO (Không khả thi / Rule-based tốt hơn):** Hủy bỏ dự án AI này.

**Justification (Lý giải quyết định dựa trên bằng chứng kỹ thuật và chi phí):**
> *Viết lý giải chi tiết tại đây*

---

# 📝 Phase 6 — REFLECTION (Cá nhân)
*Ghi nhận phản ánh của cá nhân bạn về việc phối hợp với AI trong buổi học hôm nay vào file `03-ai-log.md`.*
