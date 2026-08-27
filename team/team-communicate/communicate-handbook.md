# Giao tiếp trong team — Cẩm nang cho mọi thành viên Cyberk

**Người chịu trách nhiệm:** [COO/Anderson]
**Cập nhật lần cuối:** 2026-08-27
**Trạng thái:** Nháp

Bạn vừa vào Cyberk, hoặc bạn đã ở đây lâu nhưng chưa bao giờ ai nói rõ: "Công ty kỳ vọng bạn giao tiếp thế nào?" Trang này trả lời câu đó.

Cyberk áp dụng **Horenso** (報連相) — bộ quy tắc giao tiếp công sở từ Nhật Bản. Không phải vì nghe "Nhật" là hay, mà vì nó giải quyết đúng 3 vấn đề lớn nhất trong mọi team phần mềm: **không ai biết tiến độ, gặp vấn đề không nói, và họp xong không ai hành động.**

---

## Horenso là gì?

Horenso gồm 3 trụ cột:

| Trụ cột | Tiếng Nhật | Nghĩa | Dùng khi |
|---------|-----------|-------|----------|
| **Báo cáo** (報告) | Houkoku | Thông tin từ dưới lên — tiến độ, kết quả, vấn đề | Leader cần biết bạn đang ở đâu |
| **Liên lạc** (連絡) | Renraku | Thông tin ngang hàng — cập nhật, chia sẻ, phối hợp | Đồng đội cần biết để làm việc nhịp nhàng |
| **Thảo luận** (相談) | Soudan | Hỏi ý kiến, tìm giải pháp — khi gặp bài toán khó | Bạn cần sự giúp đỡ hoặc góc nhìn khác |

> **Quy tắc:** Horenso không phải "thêm việc". Đó là cách bạn bảo vệ chính mình — khi bạn báo cáo đúng, liên lạc kịp, thảo luận sớm, không bao giờ bạn phải gánh hậu quả một mình.

---

## Báo cáo — tin tốt ai cũng báo được, tin xấu mới là đẳng cấp

Báo cáo không phải "viết văn cho sếp đọc". Báo cáo là giúp leader **ra quyết định đúng** dựa trên thông tin bạn cung cấp. Báo cáo tốt = leader yên tâm = bạn được tin tưởng. Báo cáo tệ = leader phải hỏi đi hỏi lại = mất thời gian cả hai bên.

### 3 nguyên tắc cốt lõi

1. **Định kỳ, không ngẫu hứng** — Thống nhất tần suất với leader (VD: 11h30 và 17h mỗi ngày). Không đợi leader hỏi.
2. **Phân tích, không liệt kê** — Đừng gửi danh sách task. Cho leader biết: đang ở đâu, cái gì xong, cái gì chưa, và **bạn đề xuất gì**.
3. **Tin xấu báo sớm** — Khi "cảm thấy" tín hiệu xấu, báo ngay. Không đợi đến lúc chắc chắn hỏng mới nói.

✅ Cách tốt:
> *"Anh ơi, update cuối ngày: đã xong 5/8 task sprint này. Còn 3 task khó — đặc biệt task tích hợp payment, em gặp vấn đề với API docs thiếu. Khả năng cao không kịp deadline nếu làm một mình. Em đề xuất: cho anh B hỗ trợ phần này, em handle 2 task còn lại. Sáng mai em update tiếp."*

Tại sao tốt: Có số liệu cụ thể (5/8). Tin xấu nói thẳng + có giải pháp đề xuất. Leader không cần hỏi thêm gì — đọc xong là ra quyết định được.

❌ Cách tồi:
> *"Đang làm, vẫn ổn."*

Tại sao tồi: "Ổn" là ổn theo nghĩa nào? Leader không biết tiến độ thực tế. Khi hỏng thì đã quá trễ.

❌ Cũng tồi:
> *(Đến tận deadline mới nói: "Em không xong được rồi anh ạ.")*

Tại sao tồi: Leader đã chờ, đã tin tưởng, và giờ hết thời gian can thiệp. Dù task khó đến mấy, nếu báo sớm thì leader còn xoay được. Báo muộn = cả team gánh hậu quả.

> **Case study:** Xem phần [Các tình huống thực tế](#các-tình-huống-thực-tế) bên dưới.

---

## Liên lạc — chia sẻ thông tin, không chờ được hỏi

Liên lạc là truyền tin **ngang hàng** — giữa bạn với đồng đội, giữa các team với nhau. Mục đích: mọi người nắm được tình hình của nhau, phối hợp nhịp nhàng, tránh "mỗi người một hướng".

### 3 nguyên tắc cốt lõi

1. **Nhanh nhất có thể** — Ưu tiên: nói trực tiếp > gọi điện > Telegram. Đừng gửi email khi ngồi cùng bàn.
2. **Càng nhiều người biết càng tốt** — Trừ thông tin nhạy cảm, mặc định là chia sẻ. Thông tin "chỉ mình tôi biết" = rủi ro cho team.
3. **Liên tục, không ngẫu hứng** — Chia sẻ thường xuyên, không đợi "có gì quan trọng mới nói".

✅ Cách tốt:
> Dev viết vào group Telegram dự án:
> *"Heads up — API endpoint /bookings đang trả lỗi 500 trên staging. Em đang investigate. QA nếu đang test booking flow thì tạm hold nhé, em fix xong sẽ ping."*

Tại sao tốt: QA biết ngay, không mất thời gian test rồi log bug giả. Dev khác biết staging đang có vấn đề. Leader thấy tình hình mà không cần hỏi.

❌ Cách tồi:
> *(Dev fix xong mới nói. QA đã test 2 tiếng, log 5 bug giả, rồi phát hiện "à, staging bị lỗi từ sáng.")*

Tại sao tồi: Mất 2 tiếng QA. Mất thời gian close bug giả. Cả team đã bị ảnh hưởng mà chỉ 1 người biết.

---

## Thảo luận — hỏi sớm, không tự chìm

Thảo luận không phải yếu đuối. Thảo luận là **sử dụng trí tuệ tập thể** để giải quyết bài toán mà một người không giải được (hoặc giải được nhưng chậm hơn).

### Khi nào cần thảo luận?

- Bạn stuck quá **30 phút** mà không tiến triển
- Bạn có giải pháp nhưng **không chắc** nó đúng
- Vấn đề ảnh hưởng đến **người khác** (API, database, shared component)
- Bạn cần quyết định mà **không đủ thẩm quyền**

### 3 nguyên tắc cốt lõi

1. **Đến với giải pháp, không chỉ mang vấn đề** — "Em gặp vấn đề X, em nghĩ giải pháp A hoặc B, anh thấy sao?" — tốt hơn nhiều so với "Em bị stuck."
2. **Ghi nhận rồi mới phản biện** — Lắng nghe ý kiến trước khi bác bỏ. "Hay đấy, nhưng em nghĩ..." > "Không, cái đó sai."
3. **Có quyết định cuối cùng** — Thảo luận không phải để nói cho sướng. Phải kết thúc bằng: ai làm gì, khi nào xong.

✅ Cách tốt:
> Dev: *"Anh ơi, em đang implement caching cho API bookings. Em thấy 2 options: Redis (nhanh, nhưng thêm infra) hoặc in-memory cache (đơn giản, nhưng mất khi restart). Với scale dự kiến ~1000 users, em nghiêng về in-memory. Anh thấy sao?"*

Tại sao tốt: Đến với 2 giải pháp đã phân tích. Nêu trade-off rõ ràng. Có đề xuất cá nhân. Leader chỉ cần confirm hoặc gợi ý thêm — không mất thời gian nghĩ từ đầu.

❌ Cách tồi:
> *"Em bị stuck caching, anh giúp em với."*

Tại sao tồi: Leader không biết bạn đã nghĩ gì, đã thử gì, muốn giải quyết thế nào. Phải hỏi 5 câu trước khi bắt đầu giúp = mất thời gian cả hai.

---

## Các tình huống thực tế

### Case 1: Xác nhận trước khi làm — đừng giả định

**Tình huống:** A nhận task từ B. A hiểu theo cách của mình, cắm đầu làm cả ngày. Cuối ngày bàn giao — B nói: "Đây không phải cái tôi cần."

**Sai ở đâu:** A nghĩ mình hiểu đúng nhưng không xác nhận. Kể cả khi B đã "OK" trên chat — "OK" có thể là "OK tôi đã đọc", không phải "OK tôi đồng ý cách làm này."

**Bài học:**
> Trước khi làm, xác nhận cách hiểu của bạn. Trong khi làm, xác nhận tiến độ. **Kể cả khi nghĩ mình hiểu đúng — vẫn xác nhận.** Giả định sai → làm lại từ đầu. Xác nhận mất 5 phút → tiết kiệm cả ngày.

---

### Case 2: Báo cáo định kỳ — đừng để leader phải hỏi

**Tình huống:** A được B giao task gấp, deadline 2 ngày. A rất tập trung, không muốn bị phiền. B lo lắng hỏi mỗi ngày, A chỉ nói "Vẫn đúng deadline." Cuối cùng A xong đúng hạn — nhưng B nghĩ: "Lần sau không biết có nên giao cho A không."

**Sai ở đâu:** A làm đúng deadline nhưng **B mất niềm tin**. Vì sao? Vì B không biết chuyện gì đang xảy ra. Im lặng ≠ ổn. Im lặng = bất an.

**Bài học:**
> Chủ động báo cáo, đừng đợi leader hỏi. Thống nhất tần suất trước: "Em sẽ update lúc 11h30 và 17h mỗi ngày." Nội dung ngắn gọn: đã làm gì, đang ở đâu, cần gì không. **Người chủ động luôn được đánh giá cao hơn.**

---

### Case 3: Tin xấu báo sớm — tin xấu nói sớm thành tin tốt

**Tình huống:** A làm task gấp, gặp vấn đề khó lúc chiều. A cố xử lý đến tối vẫn không xong. Cuối ngày (deadline) mới nói: "Em không xong được rồi anh ạ."

**Sai ở đâu:** A đã biết "cảm giác không kịp" từ lúc chiều, nhưng giữ cho mình. Đến khi nói thì leader hết thời gian can thiệp.

**Bài học:**
> **Tin xấu + báo sớm = leader còn xoay được.** Tin xấu + báo muộn = không ai cứu được. Báo ngay khi "cảm thấy" tín hiệu — không đợi chắc chắn 100%.
>
> Mẫu: *"Còn 3 tiếng nữa là deadline, khả năng cao không kịp. Em đề xuất [giải pháp]. Anh có hướng nào khác không?"*

---

### Case 4: Chủ động giao tiếp — im lặng ≠ chuyên nghiệp

**Tình huống:** A làm giỏi nhưng ít nói. Leader bận, ít thời gian theo dõi. Dần dần leader giao task cho người khác — không phải vì họ giỏi hơn, mà vì họ **chủ động update** nên leader yên tâm hơn.

**Sai ở đâu:** A nghĩ "làm tốt tự khắc sếp biết." Thực tế: leader không có thời gian đoán. Người chủ động giao tiếp = người đáng tin cậy.

**Bài học:**
> Horenso xuất phát từ **hai phía**: leader yêu cầu VÀ bạn chủ động. Nếu bạn chủ động trước — bạn tiết kiệm thời gian cho leader, thể hiện thái độ nghiêm túc, và **luôn được đánh giá cao hơn** người chỉ biết im lặng làm.

---

### Case 5: Không có vấn đề gì cũng báo

Đôi khi bạn nghĩ "không có gì đáng báo". Nhưng:
- "Không có vấn đề" cũng là thông tin quý — leader yên tâm mà không cần hỏi.
- Bạn nghĩ không có vấn đề, nhưng có thể có rủi ro tiềm ẩn mà chỉ người có kinh nghiệm mới thấy.
- Báo cáo định kỳ tạo **thói quen**, không phải tạo thêm việc.

> Mẫu: *"Update cuối ngày: mọi thứ on track, 3/5 task done, 2 task còn lại straightforward, dự kiến xong trước 11h mai."*

---

## Tóm lại

| Trụ cột | Nguyên tắc sống còn | Anti-pattern |
|---------|---------------------|-------------|
| **Báo cáo** | Định kỳ. Phân tích, không liệt kê. Tin xấu báo sớm. | "Đang làm, vẫn ổn." |
| **Liên lạc** | Nhanh nhất có thể. Càng nhiều người biết càng tốt. | Biết mà không nói, đợi người khác hỏi. |
| **Thảo luận** | Đến với giải pháp. Kết thúc bằng quyết định. | "Em bị stuck, anh giúp em với." |

---

## Liên kết

- [Tài liệu Horenso gốc (Cyberk)](../02-culture/horenso.md)
