---
type: delivery
tags: [planning, handbook]
created-date: 2026-08-27
updated-date: 2026-11-26
author: anderson
status: Nháp
---

# Planning — Cẩm nang cho Product Owner

**Người chịu trách nhiệm:** PO dự án
**Cập nhật lần cuối:** 2026-11-26
**Trạng thái:** Nháp

Bạn là PO, dự án mới vừa ký xong và bạn cần tổ chức buổi Internal Planning Meeting. Buổi planning không chỉ là "họp giới thiệu dự án" — đây là **lúc duy nhất** cả team cùng ngồi lại để hiểu đúng cùng một thứ. Làm tốt thì dự án chạy mượt từ ngày đầu; làm hời hợt thì 2 tuần sau mới phát hiện mỗi người hiểu một kiểu.

Trang này giúp bạn hiểu **cách nghĩ đúng** ở từng giai đoạn của buổi planning — không chỉ làm gì, mà tại sao làm vậy.

---

## Tại sao planning meeting quan trọng đến vậy?

Planning meeting là buổi họp duy nhất mà **cả team cùng ngồi lại hiểu mục đích dự án** — không phải chỉ hiểu task. PO đã dựng sẵn board trước buổi họp, nhưng sai lầm lớn nhất là biến buổi planning thành buổi "đọc board" — PO đọc danh sách việc, dev gật đầu, ai về nấy code. Kết quả: mỗi người hiểu scope một kiểu, 3 tuần sau mới phát hiện.

Một buổi planning tốt đạt được 4 điều:

1. **Cả team hiểu mục đích của khách hàng** — Khách hàng làm dự án này để làm gì? Gọi vốn? Có nhiều user? Có doanh thu từ sớm? Hiểu mục đích thì dev mới quyết định đúng khi gặp trade-off.
2. **Toàn bộ team hiểu đúng yêu cầu** — Không phải "đọc qua PRD" mà là thảo luận, hỏi, và chốt.
3. **Board đã chia việc xong** — Kết quả cụ thể: mỗi task có người phụ trách, deadline, rủi ro đã có giải pháp. Gửi được cho client ngay trong ngày.
4. **Đồng bộ kỳ vọng** — Kỳ vọng của khách hàng, kỳ vọng của công ty, và cách triển khai dự án — mọi người phải cùng hiểu.

> **Quy tắc:** Buổi planning thành công khi kết thúc, board đã chia việc xong và gửi được cho client ngay trong ngày.

---

## Chuẩn bị — Nếu không chuẩn bị, buổi họp sẽ lãng phí

Chuẩn bị **không phải việc của riêng PO**. PO chuẩn bị tài liệu và tổ chức; team chuẩn bị bằng cách **đọc trước PRD và ghi chú câu hỏi**. Buổi họp tốt xảy ra vì mọi người đến đã hiểu 70% — chỉ cần thảo luận 30% còn lại.

Cụ thể PO cần làm:
- Gửi PRD cho team đọc trước, yêu cầu comment trực tiếp vào tài liệu
- Gửi link board đã dựng sẵn *(theo [Khởi tạo Board](../po-board-create/board-create-process.md))* để mọi người xem trước Milestone, task và Estimate
- Book phòng họp nghiêm túc — buổi planning nên **càng xa khu vực làm việc thường ngày càng tốt** (tạo không khí khác biệt, tập trung)

❌ Cách tồi:
> PO bước vào phòng họp, mở PRD trên máy:
> *"Ok, hôm nay mình planning dự án mới. Để anh giải thích PRD cho mọi người..."*
> → Mất 45 phút đọc PRD, team ngồi nghe thụ động, không ai hỏi vì chưa đọc trước.

Tại sao tồi: Team đến buổi họp "tay trắng" — chưa đọc, chưa nghĩ, chưa có câu hỏi. Kết quả: PO nói một mình, team gật đầu nhưng không thực sự hiểu. Về code rồi mới phát hiện "ủa, tính năng này hoạt động kiểu gì?"

✅ Cách tốt:
> PO gửi PRD vào Telegram kèm tin nhắn:
> *"Team ơi, đây là PRD dự án mới — Booking Platform cho client David. Mọi người đọc trước và comment trực tiếp vào doc, đặc biệt phần booking flow (trang 5-8) và payment (trang 12). Board anh đã dựng xong, mọi người xem trước task và Estimate phần mình, thấy chỗ nào thiếu hay sai thì ghi lại. Planning meeting 2pm thứ Ba, phòng họp tầng 3. Ai có câu hỏi ghi sẵn vào doc nhé."*
>
> Kèm theo: link PRD (Google Doc, cho phép comment) + link board `Booking-Management`.

Tại sao tốt: Team biết đọc gì, đọc phần nào kỹ. Comment trực tiếp vào doc = PO thấy được ai đã đọc, ai chưa. Buổi họp không mất 30 phút đầu giải thích "dự án này là gì".

---

## PRIORITY — Hiểu MỤC ĐÍCH để tìm ra Key Success Features

Phần đầu buổi planning không phải đi vào chi tiết tính năng — mà là giúp cả team hiểu **bối cảnh dự án**. Sản phẩm này giải quyết vấn đề gì? Cho ai? Tại sao khách hàng cần nó? 

Khi dev hiểu mục đích, họ sẽ tự biết cái nào quan trọng hơn khi phải trade-off. Ví dụ: nếu mục đích là "gọi vốn" → UX/UI phải đẹp, flow phải mượt, dù backend chưa perfect. Nếu mục đích là "có doanh thu" → payment phải ổn định, admin phải dễ dùng.

❌ Cách tồi:
> PO mở PRD, bắt đầu đọc:
> *"Feature 1: User Registration — cho phép user đăng ký bằng email hoặc social login. Feature 2: Booking — user chọn ngày giờ và book slot..."*
> → Đọc danh sách tính năng mà không ai biết tại sao client cần từng cái.

Tại sao tồi: Dev nghe tính năng mà không hiểu mục đích → code đúng spec nhưng sai spirit. Ví dụ: build booking flow 10 bước vì spec viết vậy, trong khi David cần flow "under 30 seconds". Hiểu mục đích mới code đúng.

✅ Cách tốt:
> PO mở slide giới thiệu dự án:
> *"David là founder của một chuỗi tiệm massage ở Bangkok. Vấn đề của David: khách gọi điện book lịch nhưng hay quên, nhân viên ghi sổ tay nên hay trùng slot. David muốn build app để khách tự book online, giảm no-show, và David xem dashboard biết được revenue hàng ngày."*
>
> *"Mục tiêu chính: David cần MVP trong 3 tháng để pitch cho nhà đầu tư. Nghĩa là UX/UI phải ấn tượng, flow booking phải mượt — đó là điều quan trọng nhất."*
>
> *"Còn câu hỏi gì về bối cảnh trước khi mình đi vào PRD chi tiết không?"*

Tại sao tốt: Team thấy được "người thật, việc thật" — không phải danh sách tính năng trừu tượng. Khi code booking flow, dev sẽ tự biết "cái này phải mượt vì David cần nó để gọi vốn".

### Phân loại feature — 4 mức ưu tiên

Hiểu mục đích rồi, cả team cùng thống nhất feature nào thuộc mức nào. Trên board, PO đã xếp Milestone theo 4 mức dưới đây:

| Mức | Tên | Ý nghĩa | Ví dụ |
|-----|-----|---------|-------|
| 🔴 | **Key Success Features** | Tính năng quyết định thành công. Thiếu = dự án fail. | Booking flow, Payment |
| 🟡 | **Thiết yếu** | Cần để hệ thống hoạt động đúng, nhưng không phải điểm nhấn. | User registration, Email notification |
| 🔵 | **Không ưu tiên** | Bổ sung nhưng không bắt buộc trong phiên bản đầu. | Reporting dashboard, Export CSV |
| ⚪ | **Nice-to-have** | Ý tưởng mở rộng cho tương lai. Không làm trong scope hiện tại. | SMS reminder, Multi-language |

Các Milestone **Key Success Features** được **bôi màu đỏ và đưa lên trên cùng** của tab sprint. Mở board ra, ai cũng thấy ngay đâu là việc quan trọng nhất của dự án.

❌ Cách tồi:
> Board xếp Milestone theo thứ tự PRD: Registration, Profile, Booking Flow, Payment, Reporting. Không có Milestone nào được đánh dấu.
> → Mai làm xong Profile trước vì nó nằm trên cùng. Booking Flow — thứ David cần để pitch — bắt đầu muộn 3 ngày.

Tại sao tồi: Nhìn board không biết việc nào quan trọng hơn việc nào. Mỗi người tự chọn việc theo thứ tự trên màn hình.

✅ Cách tốt:
> PO chiếu board:
> *"Mục đích của David là pitch nhà đầu tư trong 3 tháng. Nên Booking Flow và Payment là Key Success — mình bôi đỏ và đưa lên đầu sprint_1. Mọi người thấy đúng chưa?"*
> Dev: *"Đúng — không có nó thì app không có giá trị."*
> PO: *"Còn Reporting Dashboard mình đang để Thiết yếu, sprint_2."*
> QA: *"Em nghĩ là Không ưu tiên — David có thể xem revenue trên Stripe dashboard trước, sprint sau mình build riêng."*
> PO: *"Good call. Chuyển Reporting xuống Không ưu tiên, dời sang sprint_3."*

Tại sao tốt: Mọi người cùng quyết định ưu tiên — không có cảm giác "bị giao việc". Hai dòng đỏ trên cùng board nói cho cả team biết việc gì phải xong trước.

---

## ASSIGN — Chia việc, rồi mỗi người soát việc của mình và cam kết

PO đã dựng xong board trước buổi họp. Nhưng kế hoạch của PO mới là bản nháp: PO không thấy hết chi tiết kỹ thuật, không biết hết ai mạnh phần nào. Sai lầm phổ biến là PO đọc board rồi assign luôn. Dev không đồng thuận nhưng không nói → task bị trễ → PO frustrate → dev frustrate. Vòng lặp tiêu cực.

Cách đúng: **chia việc trước, rồi mỗi người soát kỹ phần việc của mình**. Dev soát task và Estimate của mình. QA soát task QA và test strategy. Designer soát task UX/UI và timeline design. PO sửa board ngay khi có góp ý. Cuối ngày, mỗi người cam kết ngày release — đó là con số của họ, không phải của PO.

❌ Cách tồi:
> PO mở board đã estimate sẵn:
> *"Booking Flow — 3 ngày. Payment — 2 ngày. Dashboard — 4 ngày. Đức làm booking, Thái làm payment, Mai làm dashboard."*
> Dev im lặng, gật đầu.
> → Sprint 2, Đức nhắn Telegram: *"Anh ơi, booking flow phức tạp hơn em tưởng, cần thêm 3 ngày."*

Tại sao tồi: Không ai soát kế hoạch của PO = Estimate sai không ai phát hiện (vì PO không hiểu hết chi tiết kỹ thuật). Dev không commit vì "đây không phải con số của mình". Khi trễ, ai cũng đổ lỗi.

### Chia việc theo độ quan trọng, không theo độ khó

Buổi planning luôn phải tìm ra **Key Success Features** — những tính năng thiếu là dự án fail — và làm chúng đầu tiên.

Khi chia việc, phản xạ thường gặp là chia theo độ khó: task khó cho người giỏi, task dễ cho người mới. Nghe hợp lý, nhưng task khó chưa chắc là task quan trọng. Một bài toán tối ưu performance có thể rất khó, nhưng nếu nó nằm ở tính năng Nice-to-have thì làm chậm một tuần cũng không ai thấy. Còn Booking Flow có thể không khó, nhưng nếu nó chạy sai thì David không có gì để pitch nhà đầu tư.

Vì vậy Cyberk chia việc theo **độ quan trọng**. Người quan trọng là người làm những việc quan trọng: người giỏi nhất, đáng tin nhất team nhận Key Success Features, và làm ở sprint đầu — để nếu có gì sai thì còn nhiều thời gian nhất để sửa.

❌ Cách tồi:
> PO: *"Phần Stripe integration khó nhất, Đức giỏi nhất nên Đức làm Stripe. Booking Flow dễ hơn, để Mai mới vào làm cho quen."*
> → Booking Flow là Key Success Feature, nhưng nằm trong tay người mới nhất team. Sprint 2 demo cho David, flow book còn lỗi trùng slot.

Tại sao tồi: Chia theo độ khó. Việc quan trọng nhất của dự án lại giao cho người chưa có kinh nghiệm.

✅ Cách tốt:
> PO: *"Booking Flow là Key Success, David cần nó để pitch. Đức nhận Booking Flow, làm ngay sprint_1. Stripe mình làm sau, Thái nhận, Đức review giúp phần integration."*

Tại sao tốt: Key Success Feature nằm trong tay người giỏi nhất, làm đầu tiên. Việc khó nhưng ít quan trọng hơn vẫn có người làm và có người giỏi review.

### Mỗi người soát kỹ phần việc của mình — Thảo luận, không chỉ đọc

Nhận việc xong, mỗi người đọc lại PRD **ở phần việc của mình** và soát task của mình: thừa ở đâu, thiếu ở đâu, Estimate có đúng không. Việc riêng của mình thì mình soát tỉ mỉ hơn bất kỳ ai. Mục tiêu không phải "đọc xong PRD" — mà là **cả team hiểu giống nhau** về những gì PRD mô tả. Nơi nào PRD chưa rõ, chưa logic → ghi lại để hỏi client.

Leader hoặc BA giải thích từng phần PRD, ưu tiên theo tính năng quan trọng. Dev và QA chủ động hỏi ngay chỗ chưa rõ — **đừng chờ về code rồi mới phát hiện**.

❌ Cách tồi:
> PO đọc PRD từ đầu đến cuối. Team im lặng.
> PO: *"Ok, mọi người hiểu hết rồi nhé? Có câu hỏi gì không?"*
> Team: *"... không."*
> → 2 tuần sau, dev nhắn Telegram PO lúc 11h đêm: *"Anh ơi, payment flow này em không hiểu logic, PRD viết mâu thuẫn chỗ này..."*

Tại sao tồi: "Không có câu hỏi" thường có nghĩa là "chưa hiểu đủ sâu để hỏi". Im lặng trong buổi planning = câu hỏi sẽ nổ ra khi code — lúc đó tốn gấp 10 lần thời gian.

✅ Cách tốt:
> PO chiếu PRD, đi theo từng user flow:
> *"Ok, flow booking: user mở app → chọn dịch vụ → chọn ngày giờ → điền thông tin → thanh toán → nhận confirmation. Ai có câu hỏi gì về flow này?"*
>
> Dev hỏi: *"Payment hỗ trợ những phương thức nào? Có cần refund không?"*
> PO: *"Good question. PRD ghi Stripe, nhưng chưa nói rõ refund. Mình ghi lại để hỏi David."*
>
> QA hỏi: *"Nếu 2 user book cùng 1 slot cùng lúc thì xử lý sao?"*
> PO: *"PRD chưa cover case này. Ghi vào danh sách rủi ro — cần quyết định: first-come-first-serve hay queue?"*
>
> → Ghi lại tất cả câu hỏi chưa trả lời được vào "Follow-up Questions for Client".

Tại sao tốt: Mỗi câu hỏi bây giờ là 1 bug/conflict được **chặn trước** khi xảy ra. Dev hỏi payment = tránh build sai rồi refactor. QA hỏi concurrency = tránh bug production. Và PO có danh sách cụ thể để hỏi client.

Soát task cũng là lúc Estimate của PO được kiểm lại bởi chính người sẽ làm:

> Đức nhận Booking Flow, đọc lại phần booking trong PRD:
> *"Task 'Booking calendar' anh để 4h là thiếu, còn phần chặn 2 người book trùng slot. Em tách ra thành 2 task, mỗi task 4h."*
> PO sửa board ngay.

### Xác định rủi ro — Chủ động hôm nay, đỡ cháy ngày mai

Nhiều team bỏ qua phần này vì "có gì thì xử lý sau". Sai. Rủi ro **luôn** xảy ra — câu hỏi chỉ là bạn đã chuẩn bị hay bị bất ngờ.

4 loại rủi ro cần xem xét:

| Loại | Ví dụ | Câu hỏi kiểm tra |
|------|-------|-------------------|
| **Tiến độ** | Thay đổi yêu cầu đột xuất, phụ thuộc bên thứ ba | Có feature nào phụ thuộc API/service ngoài không? |
| **Công nghệ** | Thư viện/công cụ chưa từng dùng | Team đã dùng tech stack này chưa? Cần PoC không? |
| **Giao tiếp client** | Phản hồi chậm, hiểu sai yêu cầu | PRD có điểm nào mâu thuẫn? Client response nhanh không? |
| **Con người** | Nghỉ việc đột xuất, quá tải | Ai là single point of failure? Có backup không? |

❌ Cách tồi:
> PO: *"Rủi ro thì... chắc không có gì đặc biệt. Ok, tiếp nhé."*
> → Sprint 2: Stripe API thay đổi, dev mất 3 ngày debug. Designer deliver trễ 1 tuần, FE ngồi chờ.

Tại sao tồi: "Không có rủi ro" là câu nói nguy hiểm nhất. Mọi dự án đều có rủi ro — chỉ khác là bạn thấy trước hay bị bất ngờ.

✅ Cách tốt:
> PO mở Milestone Payment trên board, hỏi team:
> *"Ok, rủi ro. Mình thấy Payment Integration dùng Stripe API — team đã integrate Stripe bao giờ chưa?"*
> Dev: *"Chưa. Em chỉ dùng thử sandbox."*
> PO: *"Vậy ghi rủi ro: 'Stripe integration chưa có kinh nghiệm'. Giải pháp: Đức dành 1 ngày đầu sprint làm PoC — nếu gặp blocker thì báo ngay, mình switch sang payment gateway khác."*
>
> TL: *"Thêm 1 rủi ro: design chưa final, nếu designer deliver trễ thì FE bị block."*
> PO: *"Đúng. Giải pháp: Designer commit deliver wireframe trước, high-fidelity sau. FE code theo wireframe trước."*

Tại sao tốt: Mỗi rủi ro đã có giải pháp trước khi xảy ra. PoC ngày đầu = biết sớm có vấn đề hay không. Designer deliver wireframe trước = FE không bị block.

### Cam kết EOD — Release được đúng ngày không?

Cuối ngày (EOD), mỗi người soát xong phần việc của mình và đưa ra cam kết: **nếu không có vấn đề gì phát sinh, phần việc của mình có release được đúng ngày đã estimate không?**

Ai trả lời "được" thì kế hoạch đi tiếp. Ai trả lời "không" thì điều chỉnh ngay: tách lại task, chuyển bớt việc cho người khác, hoặc dời Milestone ít quan trọng hơn sang sprint sau. Board chỉ được gửi cho khách khi mọi người đã cam kết.

❌ Cách tồi:
> PO: *"Ok mọi người nhận việc rồi nhé, mình gửi khách luôn."*
> → Tối đó Thái mới đọc kỹ phần Payment, thấy cần thêm 2 ngày. Nhưng board đã gửi David với ngày cũ.

Tại sao tồi: Kế hoạch gửi khách khi chưa ai soát kỹ việc của mình. Ngày trên board là ngày của PO, không phải ngày team cam kết.

✅ Cách tốt:
> Cuối ngày, trong group Internal:
> Đức: *"Booking Flow ok, thứ 5 release được."*
> Thái: *"Payment em cần thêm 1 task xử lý refund, 4h. Nếu thêm vào thì vẫn kịp thứ 6."*
> PO thêm task, cập nhật ngày, rồi mới gửi board cho David.

Tại sao tốt: Ngày gửi khách là ngày cả team đã cam kết. Chỗ thiếu được phát hiện trước khi khách thấy.

---

## SEND — Gửi board cho khách sau khi cả team đã cam kết

Cả team đã cam kết EOD, PO có 1 việc quan trọng nhất: **gửi board cho khách ngay trong ngày**. Không cần soạn một bản Planning Report riêng — board đã có đủ Milestone, task, người phụ trách và deadline. PO chỉ viết thêm [Daily Report](../po-internal-daily/internal-daily-handbook.md) đầu tiên ở đầu tab `sprint_1`, rồi export PDF. Không phải "mai em gửi" — vì ngày mai bạn sẽ quên 30% chi tiết đã thảo luận.

Gửi cho 2 nhóm:
1. **Client** — để xác nhận scope, timeline, và team hiểu đúng yêu cầu
2. **Leaders (Anderson/COO)** — để nắm tiến độ và hỗ trợ khi cần

### Tin nhắn gửi kèm board — summary trước, file sau

Sai lầm lớn nhất khi gửi board sau buổi Planning: gửi file trơn. Client mở PDF 10 trang ra, không biết đọc phần nào quan trọng, lướt qua rồi đóng. Khi buổi kick-off diễn ra, client chưa thực sự đọc plan.

**Nguyên tắc: summary text đi trước file.** Client đọc summary trong 30 giây, nắm 3 ý chính, rồi mới mở file xem chi tiết nếu muốn.

Ba mục bắt buộc trong summary:

1. **Approach** — Team sẽ tiếp cận dự án thế nào? (Agile? Sprint bao lâu? Feature nào làm trước?)
2. **Key Risks** — Rủi ro nào đáng lưu ý nhất? Team sẽ xử lý thế nào?
3. **Strategy** — Chiến lược delivery: ưu tiên gì, tại sao thứ tự này?

Lúc này client đã biết sẽ có buổi kick-off (bạn đã hẹn ở [tin nhắn sáng](../po-kick-off/kick-off-handbook.md)). Nên tin nhắn gửi board chỉ cần focus vào **nội dung plan** — không cần hỏi lịch lại.

❌ Cách tồi:
> *"Hi David, please find the attached project board."*

Tại sao tồi: Client mở PDF, lướt qua, đóng lại. Không nắm ý chính, không biết phần nào quan trọng. Buổi kick-off sau đó phải giải thích từ đầu — lãng phí thời gian.

❌ Cũng tồi:
> *"Hi David, the plan is done. The project has some risks but we'll handle them. Let me know when you're free to call."*

Tại sao tồi: "Some risks but we'll handle them" = mơ hồ, không chuyên nghiệp. "Let me know when you're free" = bị động — bạn đã hỏi lịch ở tin nhắn sáng rồi, đừng hỏi lại.

✅ Cách tốt:
> PO gửi Telegram kèm file:
>
> *"Hi David, our internal planning is complete! Here's our project board (PDF attached). Quick summary:*
>
> *📋 Approach: We'll run 1-week sprints with daily progress updates, starting with the booking flow — the core user journey — before building secondary features like admin reports.*
>
> *⚠️ Key Risks: The payment gateway API documentation is incomplete. We've allocated a spike in Sprint 1 to validate integration before committing to a timeline for that module.*
>
> *🎯 Strategy: Key Success Features first (booking, payment, notifications). Nice-to-have features (analytics dashboard) will be prioritized if we have capacity in Sprint 4.*
>
> *Looking forward to walking you through this in our kick-off call! I'll send the agenda once we confirm the time."*

Tại sao tốt: Client hiểu 3 ý chính trong 30 giây. Risk được frame thành "team đã nghĩ trước và có plan" — không phải "có vấn đề". Nối liền với kick-off call đã hẹn sáng — quy trình mạch lạc.

> Mẫu tin nhắn hoàn chỉnh: xem [kick-off-example.md](./kick-off-example.md)

> **Về agenda kick-off:** Khi client confirm giờ, gửi agenda ít nhất **1 ngày trước buổi call**. Client biết trước sẽ thảo luận gì, chuẩn bị câu hỏi, không bị bất ngờ.

### Gửi ngay trong ngày

❌ Cách tồi:
> PO: *"Ok, em sẽ tổng hợp gửi khách sau nhé."*
> → 3 ngày sau vẫn chưa gửi. Board chưa ai cập nhật lại những gì đã sửa trong buổi họp. Dev: "Hôm đó mình chốt dời Reporting sang sprint nào nhỉ?"
> → 1 tuần sau mới gửi. Client: "Sao lâu vậy, mọi thứ ổn chứ?"

Tại sao tồi: Gửi trễ = chi tiết sai (vì quên). Client lo lắng. Leaders không nắm được tình hình. Và team mất momentum — "cảm giác planning" đã bay mất.

✅ Cách tốt:
> Ngay sau buổi họp, PO kiểm lại board:
> - Mọi Key Success Feature đã có Milestone và task chưa?
> - Mỗi task có Assignee + Expected done date chưa?
>
> Viết Daily Report đầu tab `sprint_1`: kế hoạch đã chốt, 2 rủi ro chính kèm giải pháp, 2 câu hỏi cần David trả lời. Export PDF, cấp quyền xem board cho David, gửi vào group `Booking - Cyberk devs` kèm tin nhắn summary 3 mục Approach, Key Risks, Strategy như trên.
>
> Đồng thời gửi qua Telegram cho Anderson:
> *"Anh ơi, em gửi board dự án Booking Platform. Tổng timeline 3 tháng, team 3 người. Có 2 rủi ro chính: Stripe integration chưa có kinh nghiệm và design chưa final. Em đã có giải pháp cho cả 2. Anh xem có góp ý gì không ạ."*

Tại sao tốt: Client nhận board trong ngày → cảm thấy team professional và có kế hoạch rõ. Từ hôm sau client nhận đúng định dạng PDF này mỗi ngày, nên quen ngay cách đọc. Anderson nắm được tình hình ngay. Câu hỏi cho client được gửi sớm = trả lời sớm = không bị block.

---

## Tóm lại

| Giai đoạn | Nguyên tắc cốt lõi | Sai lầm hay gặp |
|-----------|-------------------|-----------------| 
| Chuẩn bị | Dựng board trước, gửi PRD + board cho team đọc và ghi chú, book phòng nghiêm túc | Không gửi trước, mất 45 phút đọc PRD trong buổi họp |
| PRIORITY | Hiểu MỤC ĐÍCH của client, tìm ra Key Success Features, bôi đỏ và đưa lên đầu board | Xếp Milestone theo thứ tự PRD, không ai biết việc nào quan trọng nhất |
| ASSIGN — chia việc | Chia theo độ quan trọng: Key Success Features cho người giỏi và đáng tin nhất, làm đầu tiên | Chia theo độ khó, việc quan trọng nhất rơi vào tay người mới |
| ASSIGN — soát việc mình | Mỗi người đọc PRD phần mình, soát task thừa/thiếu, hỏi ngay chỗ chưa rõ | Team im lặng, PRD mâu thuẫn không ai phát hiện |
| ASSIGN — rủi ro | Xác định sớm 4 loại, mỗi rủi ro có kịch bản xử lý | "Không có rủi ro" — câu nói nguy hiểm nhất |
| ASSIGN — cam kết EOD | Mỗi người cam kết release đúng ngày; không được thì điều chỉnh trước khi gửi khách | Gửi khách khi chưa ai soát kỹ việc của mình |
| SEND | Sau khi cả team cam kết, gửi PDF board + Daily Report cho client, tóm tắt cho leaders TRONG NGÀY | Để 1 tuần mới gửi, quên chi tiết, mất momentum |

---

## Liên kết

- [Quy trình planning — `PRIORITY → ASSIGN → SEND`](./planning-process.md)
- [Khởi tạo Board](../po-board-create/board-create-process.md) — Board dựng trước buổi họp
- [Mẫu Daily Report & tin nhắn summary](../po-internal-daily/internal-daily-example.md)
