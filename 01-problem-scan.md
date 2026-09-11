# 🔍 Phase 1 — SCAN (Cá nhân, 20 min)
| 1 | **Vinhomes** | **Tốn thời gian (Time-consuming)** | Nhân viên CSKH đọc phản ánh về vệ sinh, tiếng ồn hoặc thiết bị khu vực chung hỏng; xác định bộ phận phụ trách, tra cứu hướng dẫn và soạn phản hồi. Bottleneck dự kiến là đọc nội dung dài, phân loại và viết lại các phản hồi tương tự, khiến cư dân phải chờ và có thể phải chuyển lại yêu cầu nếu phân loại sai. |
| 2 | **Vinpearl** | **AI có thể tốt hơn (AI-upgrade)** | Nhân viên tư vấn làm rõ nhu cầu đặt phòng được khách diễn đạt tự do: ngày lưu trú, số người, độ tuổi trẻ em và ngân sách. Bottleneck dự kiến là tổng hợp thông tin qua nhiều lượt trao đổi và hỏi bổ sung dữ liệu còn thiếu; phản hồi theo mẫu khó bao quát các cách diễn đạt khác nhau, kéo dài thời gian tư vấn. |
| 3 | **Xanh SM** | **Pain từ người khác (Stakeholder Pain)** | Tài xế cần chọn thời điểm và trạm sạc phù hợp với lượng pin, vị trí xe và ca làm việc. Giả thuyết cần khảo sát là thông tin về khả năng phục vụ và thời gian chờ tại trạm chưa đủ để ra quyết định, khiến tài xế mất thời gian tìm trạm hoặc xếp hàng, giảm thời gian sẵn sàng nhận chuyến. |
| 4 | **Xanh SM** | **Lặp lại (Repetitive)** | Nhân viên CSKH đọc yêu cầu về đồ thất lạc, phản ánh thái độ tài xế hoặc thắc mắc cước; hỏi thông tin còn thiếu, phân loại, chuyển bộ phận và soạn phản hồi. Bottleneck dự kiến là tổng hợp nội dung qua nhiều lượt trao đổi và xử lý lặp lại các nhóm yêu cầu tương tự, kéo dài thời gian tiếp nhận và tăng nguy cơ chuyển sai bộ phận. |

---
# 🃏 Phase 2 — QUICK-ASSESS (Cá nhân, 30 min)

Chọn **top 3 bài toán** từ danh sách trên và hoàn thiện **3 Quick Problem Cards** dưới đây (10 phút/card).

**Ba bài toán được chọn:** #3 (Xanh SM — hỗ trợ chọn thời điểm và trạm sạc), #1 (Vinhomes — xử lý phản ánh cư dân) và #2 (Vinpearl — làm rõ nhu cầu đặt phòng). **Bài #3 hiện tại chính là bài #6 về pin/sạc trong danh sách 7 bài toán ban đầu, được chọn để phân tích sâu.** Số card giữ nguyên số bài toán trong Phase 1 sau khi rút gọn còn 4 bài; thứ tự trình bày là thứ tự ưu tiên cho lab.

> **Trạng thái bằng chứng:** Các workflow và thời gian dưới đây là giả định để thiết kế thử nghiệm, chưa phải kết quả khảo sát doanh nghiệp. Các ngưỡng thành công là mục tiêu đề xuất, chưa được chạy kiểm chứng. Thời gian xử lý tính từ lúc nhân viên mở yêu cầu đến lúc hoàn thành phương án, bản phản hồi hoặc chuyển tiếp đã duyệt. Không tính thời gian chờ bổ sung thông tin, di chuyển, xếp hàng, sạc pin hoặc giải quyết sự cố ngoài thực địa vào metric thời gian xử lý của nhân viên.

### Quick Problem Card #3 — Xanh SM: Hỗ trợ chọn thời điểm và trạm sạc cho tài xế

| Nội dung | Chi tiết |
|---|---|
| **Bài toán (1 câu)** | Tài xế và nhân viên điều vận mất thời gian tổng hợp thông tin xe, ca làm việc và trạm sạc để chọn thời điểm, địa điểm sạc phù hợp, có nguy cơ chọn phương án phải chờ lâu hoặc không đáp ứng điều kiện của xe. |
| **Công ty / Lens** | Xanh SM / Pain từ người khác — tương ứng bài toán **#3 của Phase 1**, tức **#6 trong danh sách ban đầu**. |
| **Actor** | Tài xế cần phương án sạc phù hợp; trong workflow giả định của prototype, nhân viên điều vận hỗ trợ tra cứu, đối chiếu và duyệt đề xuất trước khi gửi tài xế. |
| **Workflow hiện tại — giả định** | **1.** Nhận vị trí, tình trạng pin, thông tin xe và lịch ca từ tài xế (2 phút) → **2.** Tra cứu các trạm tương thích và thời gian di chuyển (3 phút) → **3.** Đối chiếu trạng thái trạm, thời gian chờ và thời lượng sạc dự kiến (3 phút) → **4.** So sánh các phương án trạm/khung giờ đáp ứng điều kiện đã xác nhận của xe và ca làm việc (2 phút) → **5.** Soạn, kiểm tra và duyệt hướng dẫn gửi tài xế (2 phút). **Tổng: 12 phút/yêu cầu.** |
| **Bottleneck** | Bước **2–4**, giả định **8 phút/yêu cầu**: thông tin xe, trạm và ca làm việc nằm ở nhiều nguồn; mất thời gian loại phương án không phù hợp và so sánh thời gian di chuyển, chờ, sạc. |
| **AI hỗ trợ ở đâu?** | LLM hỗ trợ bước **1** để trích xuất yêu cầu của tài xế, phát hiện thông tin còn thiếu; ở bước **5**, giải thích phương án do rule tính và soạn hướng dẫn nháp. Bước **2–4** dùng dữ liệu được cung cấp và code lọc/xếp hạng, không giao việc xác định xe có thể đến trạm hay không cho LLM. Đầu ra JSON gồm `action`, `suggested_station_id`, `suggested_time_window`, `reason`, `missing_fields`, `draft_reply`, `needs_human_review`. |
| **Success Metric — mục tiêu** | Giảm thời gian lập và duyệt phương án trung bình từ **12 phút giả định xuống ≤ 5 phút**, gồm thời gian chờ mô hình, sửa và duyệt; xử lý đúng **ít nhất 27/30 tình huống** theo đáp án xác định trước về trạm/khung giờ hoặc chuyển kiểm tra thủ công; **0/30 đầu ra** đề xuất phương án bị rule đánh dấu không hợp lệ hoặc bịa trạng thái trạm. Kết quả này chỉ đánh giá hỗ trợ ra quyết định trên bộ thử; chưa chứng minh giảm thời gian xếp hàng, thời gian sạc hay tăng số chuyến thực tế. |
| **Quick Architecture** | **Rule + LLM Feature.** Rule lọc phương án theo tính tương thích, khả năng tiếp cận đã được xác nhận, độ mới dữ liệu và khung giờ được phép; xếp hạng các phương án hợp lệ theo tổng thời gian di chuyển + chờ + sạc dự kiến. LLM nhận kết quả để giải thích và viết nháp. Code kiểm tra lại ID trạm, khung giờ và các số liệu trong output; điều vận duyệt trước khi gửi. |
| **Ranh giới / Fallback** | Không tự suy ra quãng đường xe đi được từ phần trăm pin, không bịa trạm trống, không tự đặt chỗ sạc, điều xe hoặc phát lệnh cứu hộ. Dữ liệu thiếu, quá hạn, mâu thuẫn hoặc không có phương án hợp lệ thì trả `manual_review`, để trạm/khung giờ là `null` và chuyển điều vận xác minh hoặc xử lý theo quy trình hỗ trợ hiện hành. Nội dung tài xế nhập không được ghi đè dữ liệu xe/trạm đã xác nhận. |
| **Dữ liệu cần chuẩn bị** | 30 tình huống mô phỏng: 10 đủ dữ liệu có phương án hợp lệ, 10 thiếu/quá hạn/mâu thuẫn dữ liệu, 10 không có phương án hợp lệ. Chuẩn bị các phương án trạm/khung giờ với ID, loại cổng, điều kiện tiếp cận đã xác nhận, thời gian di chuyển/chờ/sạc dự kiến và thời điểm cập nhật, kèm đáp án trước khi thử. Thêm ít nhất 3 đầu vào dụ AI chọn trạm bị loại, tự bịa trụ trống hoặc bỏ bước duyệt. Các điều kiện trong dữ liệu giả lập không phải hướng dẫn an toàn vận hành thực tế. |

**Phạm vi chọn cho lab:** Hỗ trợ lập phương án sạc kế tiếp cho **một tài xế tại một thời điểm**, từ danh sách trạm và khung giờ ứng viên được cung cấp. Đây là bước đầu của bài toán chọn thời điểm/trạm sạc; chưa xây dựng mô hình dự báo hay lịch sạc tối ưu cho toàn đội xe. Nếu chỉ có dữ liệu giả lập, chỉ kết luận về tính đúng của luồng xử lý và chất lượng bản nháp trong các tình huống đó. Cần dữ liệu thực và thử nghiệm vận hành để đánh giá tác động đến thời gian chờ hoặc thời gian sẵn sàng nhận chuyến.

### Quick Problem Card #1 — Vinhomes: Phân loại phản ánh cư dân và soạn phản hồi nháp

| Nội dung | Chi tiết |
|---|---|
| **Bài toán (1 câu)** | Nhân viên CSKH mất thời gian đọc phản ánh về vệ sinh, tiếng ồn và thiết bị khu vực chung hỏng để xác định bộ phận phụ trách và soạn phản hồi phù hợp. |
| **Công ty / Lens** | Vinhomes / Tốn thời gian — tương ứng bài toán **#1 của Phase 1**. |
| **Actor** | Nhân viên CSKH hoặc ban quản lý tiếp nhận phản ánh; cư dân phải chờ khi thông tin vị trí thiếu hoặc yêu cầu bị chuyển sai bộ phận. |
| **Workflow hiện tại — giả định** | **1.** Nhận phản ánh, ghi tòa và vị trí nếu có (1 phút) → **2.** Đọc và phân loại vấn đề (2 phút) → **3.** Tra cứu hướng dẫn, đối chiếu bộ phận phụ trách (2 phút) → **4.** Soạn phản hồi hoặc câu hỏi làm rõ (2 phút) → **5.** Kiểm tra, gửi và chuyển tiếp nếu đủ thông tin (1 phút). **Tổng: 8 phút/phản ánh.** |
| **Bottleneck** | Bước **2–4**, giả định **6 phút/phản ánh**: phải hiểu mô tả tự do, đối chiếu đúng hướng dẫn cho từng nhóm vấn đề và tránh đưa ra cam kết không có căn cứ. |
| **AI hỗ trợ ở đâu?** | Bước **2–4**: LLM tóm tắt, gợi ý một trong ba nhóm vấn đề, phát hiện thiếu vị trí và soạn nháp theo hướng dẫn mẫu. Nhân viên xác nhận trường hợp có nhiều vấn đề hoặc nội dung mơ hồ. |
| **Success Metric — mục tiêu** | Giảm thời gian xử lý trung bình từ **8 phút giả định xuống ≤ 4 phút**, gồm cả sửa và duyệt; phân loại đúng **ít nhất 27/30 phản ánh có nhãn**; **0/30 phản hồi** bịa chính sách, mức bồi thường hoặc thời hạn sửa chữa. |
| **Quick Architecture** | **LLM Feature + Rule.** LLM đọc nội dung và viết nháp; rule đối chiếu nhóm vấn đề với bộ phận trong danh mục, kiểm tra thông tin vị trí. Phạm vi lab dùng tài liệu mẫu được cung cấp trực tiếp cho mô hình. |
| **Ranh giới / Fallback** | Không kết luận trách nhiệm, hứa bồi thường hoặc tự gửi phản hồi. Thiếu vị trí thì hỏi lại; không có hướng dẫn phù hợp, có yếu tố khẩn cấp hoặc AI phân loại không rõ thì chuyển nhân viên. Nhân viên duyệt cả nội dung lẫn bộ phận nhận trước khi chuyển. |
| **Dữ liệu cần chuẩn bị** | 30 phản ánh mô phỏng: 10 vệ sinh, 10 tiếng ồn, 10 thiết bị khu vực chung hỏng; gán nhãn trước và thêm biến thể thiếu vị trí. Chuẩn bị hướng dẫn xử lý và danh mục bộ phận giả lập, ghi rõ không phải quy định chính thức của Vinhomes. |

### Quick Problem Card #2 — Vinpearl: Trích xuất nhu cầu đặt phòng và hỏi thông tin còn thiếu

| Nội dung | Chi tiết |
|---|---|
| **Bài toán (1 câu)** | Nhân viên tư vấn phải đọc nhiều lượt trao đổi để tổng hợp nhu cầu đặt phòng và hỏi lại các thông tin còn thiếu trước khi chuyển sang bước kiểm tra phòng hoặc báo giá. |
| **Công ty / Lens** | Vinpearl / AI có thể tốt hơn — tương ứng bài toán **#2 của Phase 1**. |
| **Actor** | Nhân viên tư vấn đặt phòng tổng hợp thông tin; khách hàng có thể phải trả lời lại những nội dung đã cung cấp. |
| **Workflow hiện tại — giả định** | **1.** Đọc tin nhắn hoặc email yêu cầu (1 phút) → **2.** Nhập ngày lưu trú, số người, độ tuổi trẻ em và ngân sách vào phiếu (2 phút) → **3.** Kiểm tra thông tin thiếu hoặc mâu thuẫn (1 phút) → **4.** Soạn câu hỏi làm rõ (1 phút) → **5.** Kiểm tra, gửi câu hỏi hoặc chuyển phiếu đủ thông tin sang bước tư vấn tiếp (1 phút). **Tổng: 6 phút/yêu cầu.** |
| **Bottleneck** | Bước **2–4**, giả định **4 phút/yêu cầu**: thông tin phân tán giữa nhiều tin nhắn, khách thay đổi ngày hoặc số người, cách diễn đạt chưa rõ. |
| **AI hỗ trợ ở đâu?** | Bước **2–4**: LLM trích xuất nhu cầu thành JSON, chỉ cập nhật khi khách xác nhận thay đổi rõ ràng, liệt kê trường thiếu hoặc mâu thuẫn và soạn một lượt hỏi làm rõ. Thông tin không được cung cấp để `null`, không tự suy đoán. |
| **Success Metric — mục tiêu** | Giảm thời gian xử lý trung bình từ **6 phút giả định xuống ≤ 3 phút**, gồm cả sửa và duyệt; **ít nhất 27/30 hồ sơ** khớp toàn bộ trường với đáp án chuẩn, kể cả giá trị thiếu và cờ mâu thuẫn; **0/30 phản hồi** tự khẳng định giá, phòng trống hoặc đặt phòng thành công. |
| **Quick Architecture** | **LLM Feature + Rule.** LLM trích xuất hội thoại và viết câu hỏi; rule kiểm tra kiểu dữ liệu, số lượng người hợp lệ và ngày nhận/trả phòng khi đã có ngày cụ thể. Nhân viên duyệt trước khi gửi. |
| **Ranh giới / Fallback** | Chỉ thu thập và làm rõ nhu cầu. Không truy cập hệ thống đặt phòng, báo giá, xác nhận phòng trống hay tạo booking. Ngày như “cuối tuần sau” thiếu mốc xác định, ngân sách thiếu đơn vị hoặc dữ liệu mâu thuẫn thì hỏi khách xác nhận; output lỗi thì nhân viên điền phiếu thủ công. |
| **Dữ liệu cần chuẩn bị** | 30 hội thoại mô phỏng: 10 đủ thông tin, 10 thiếu thông tin, 10 có thay đổi hoặc mâu thuẫn; chuẩn bị JSON đáp án trước khi thử. Chỉ cần phiếu nhu cầu mẫu, chưa cần API giá hoặc tồn phòng cho phạm vi này. |
