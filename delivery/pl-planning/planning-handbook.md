# Planning — Cẩm nang cho Product Lead

**Người chịu trách nhiệm:** [PL/PM]
**Cập nhật lần cuối:** 2026-08-26
**Trạng thái:** Nháp

Bạn là PL/PM, dự án mới vừa ký xong và bạn cần tổ chức buổi Internal Kickoff Meeting. Buổi kickoff không chỉ là "họp giới thiệu dự án" — đây là **lúc duy nhất** cả team cùng ngồi lại để hiểu đúng cùng một thứ. Làm tốt thì dự án chạy mượt từ ngày đầu; làm hời hợt thì 2 tuần sau mới phát hiện mỗi người hiểu một kiểu.

Trang này giúp bạn hiểu **cách nghĩ đúng** ở từng giai đoạn của buổi kickoff — không chỉ làm gì, mà tại sao làm vậy.

---

## Tại sao kickoff meeting quan trọng đến vậy?

Kickoff meeting là buổi họp duy nhất mà **cả team cùng ngồi lại hiểu mục đích dự án** — không phải chỉ hiểu task. Sai lầm lớn nhất là biến kickoff thành buổi "giao task" — PL đọc danh sách việc, dev gật đầu, ai về nấy code. Kết quả: mỗi người hiểu scope một kiểu, 3 tuần sau mới phát hiện.

Một buổi kickoff tốt đạt được 4 điều:

1. **Cả team hiểu mục đích của khách hàng** — Khách hàng làm dự án này để làm gì? Gọi vốn? Có nhiều user? Có doanh thu từ sớm? Hiểu mục đích thì dev mới quyết định đúng khi gặp trade-off.
2. **Toàn bộ team hiểu đúng yêu cầu** — Không phải "đọc qua PRD" mà là thảo luận, hỏi, và chốt.
3. **Có Planning Report** — Kết quả cụ thể: task list, người phụ trách, deadline, rủi ro. Gửi được cho client ngay trong ngày.
4. **Đồng bộ kỳ vọng** — Kỳ vọng của khách hàng, kỳ vọng của công ty, và cách triển khai dự án — mọi người phải cùng hiểu.

> **Quy tắc:** Buổi kickoff thành công khi kết thúc có Planning Report gửi được cho client ngay trong ngày. Không có report = buổi họp thất bại.

---

## Chuẩn bị — Nếu không chuẩn bị, buổi họp sẽ lãng phí

Chuẩn bị **không phải việc của riêng PL**. PL chuẩn bị tài liệu và tổ chức; team chuẩn bị bằng cách **đọc trước PRD và ghi chú câu hỏi**. Buổi họp tốt xảy ra vì mọi người đến đã hiểu 70% — chỉ cần thảo luận 30% còn lại.

Cụ thể PL cần làm:
- Gửi PRD cho team đọc trước, yêu cầu comment trực tiếp vào tài liệu
- Gửi Planning Template để mọi người xem qua cấu trúc
- Custom template cho phù hợp với dự án cụ thể
- Book phòng họp nghiêm túc — kickoff nên **càng xa khu vực làm việc thường ngày càng tốt** (tạo không khí khác biệt, tập trung)

✅ Cách tốt:
> PL gửi PRD vào Telegram kèm tin nhắn:
> *"Team ơi, đây là PRD dự án mới — Booking Platform cho client David. Mọi người đọc trước và comment trực tiếp vào doc, đặc biệt phần booking flow (trang 5-8) và payment (trang 12). Kickoff meeting 2pm thứ Ba, phòng họp tầng 3. Ai có câu hỏi ghi sẵn vào doc nhé."*
>
> Kèm theo: link PRD (Google Doc, cho phép comment) + link Planning Template.

Tại sao tốt: Team biết đọc gì, đọc phần nào kỹ. Comment trực tiếp vào doc = PL thấy được ai đã đọc, ai chưa. Buổi họp không mất 30 phút đầu giải thích "dự án này là gì".

❌ Cách tồi:
> PL bước vào phòng họp, mở PRD trên máy:
> *"Ok, hôm nay mình kickoff dự án mới. Để anh giải thích PRD cho mọi người..."*
> → Mất 45 phút đọc PRD, team ngồi nghe thụ động, không ai hỏi vì chưa đọc trước.

Tại sao tồi: Team đến buổi họp "tay trắng" — chưa đọc, chưa nghĩ, chưa có câu hỏi. Kết quả: PL nói một mình, team gật đầu nhưng không thực sự hiểu. Về code rồi mới phát hiện "ủa, tính năng này hoạt động kiểu gì?"

---

## Hiểu sản phẩm — Đừng chỉ hiểu tính năng, hiểu MỤC ĐÍCH

Phần đầu buổi kickoff không phải đi vào chi tiết tính năng — mà là giúp cả team hiểu **bối cảnh dự án**. Sản phẩm này giải quyết vấn đề gì? Cho ai? Tại sao khách hàng cần nó? 

Khi dev hiểu mục đích, họ sẽ tự biết cái nào quan trọng hơn khi phải trade-off. Ví dụ: nếu mục đích là "gọi vốn" → UX/UI phải đẹp, flow phải mượt, dù backend chưa perfect. Nếu mục đích là "có doanh thu" → payment phải ổn định, admin phải dễ dùng.

✅ Cách tốt:
> PL mở slide giới thiệu dự án:
> *"David là founder của một chuỗi tiệm massage ở Bangkok. Vấn đề của David: khách gọi điện book lịch nhưng hay quên, nhân viên ghi sổ tay nên hay trùng slot. David muốn build app để khách tự book online, giảm no-show, và David xem dashboard biết được revenue hàng ngày."*
>
> *"Mục tiêu chính: David cần MVP trong 3 tháng để pitch cho nhà đầu tư. Nghĩa là UX/UI phải ấn tượng, flow booking phải mượt — đó là điều quan trọng nhất."*
>
> *"Còn câu hỏi gì về bối cảnh trước khi mình đi vào PRD chi tiết không?"*

Tại sao tốt: Team thấy được "người thật, việc thật" — không phải danh sách tính năng trừu tượng. Khi code booking flow, dev sẽ tự biết "cái này phải mượt vì David cần nó để gọi vốn".

❌ Cách tồi:
> PL mở PRD, bắt đầu đọc:
> *"Feature 1: User Registration — cho phép user đăng ký bằng email hoặc social login. Feature 2: Booking — user chọn ngày giờ và book slot..."*
> → Đọc danh sách tính năng mà không ai biết tại sao client cần từng cái.

Tại sao tồi: Dev nghe tính năng mà không hiểu mục đích → code đúng spec nhưng sai spirit. Ví dụ: build booking flow 10 bước vì spec viết vậy, trong khi David cần flow "under 30 seconds". Hiểu mục đích mới code đúng.

---

## Đọc PRD cùng team — Thảo luận, không chỉ đọc

Đây là phần **lõi** của buổi kickoff. Mục tiêu không phải "đọc xong PRD" — mà là **cả team hiểu giống nhau** về những gì PRD mô tả. Nơi nào PRD chưa rõ, chưa logic → ghi lại để hỏi client.

Leader hoặc BA giải thích từng phần PRD, ưu tiên theo tính năng quan trọng. Dev và QA chủ động hỏi ngay chỗ chưa rõ — **đừng chờ về code rồi mới phát hiện**.

✅ Cách tốt:
> PL chiếu PRD, đi theo từng user flow:
> *"Ok, flow booking: user mở app → chọn dịch vụ → chọn ngày giờ → điền thông tin → thanh toán → nhận confirmation. Ai có câu hỏi gì về flow này?"*
>
> Dev hỏi: *"Payment hỗ trợ những phương thức nào? Có cần refund không?"*
> PL: *"Good question. PRD ghi Stripe, nhưng chưa nói rõ refund. Mình ghi lại để hỏi David."*
>
> QA hỏi: *"Nếu 2 user book cùng 1 slot cùng lúc thì xử lý sao?"*
> PL: *"PRD chưa cover case này. Ghi vào danh sách rủi ro — cần quyết định: first-come-first-serve hay queue?"*
>
> → Ghi lại tất cả câu hỏi chưa trả lời được vào "Follow-up Questions for Client".

Tại sao tốt: Mỗi câu hỏi bây giờ là 1 bug/conflict được **chặn trước** khi xảy ra. Dev hỏi payment = tránh build sai rồi refactor. QA hỏi concurrency = tránh bug production. Và PL có danh sách cụ thể để hỏi client.

❌ Cách tồi:
> PL đọc PRD từ đầu đến cuối. Team im lặng.
> PL: *"Ok, mọi người hiểu hết rồi nhé? Có câu hỏi gì không?"*
> Team: *"... không."*
> → 2 tuần sau, dev Slack PL lúc 11h đêm: *"Anh ơi, payment flow này em không hiểu logic, PRD viết mâu thuẫn chỗ này..."*

Tại sao tồi: "Không có câu hỏi" thường có nghĩa là "chưa hiểu đủ sâu để hỏi". Im lặng trong kickoff = câu hỏi sẽ nổ ra khi code — lúc đó tốn gấp 10 lần thời gian.

---

## Lập kế hoạch — Cả team cùng plan, không phải PL plan xong rồi giao

Sai lầm phổ biến: PL ngồi estimate rồi assign task cho từng người. Dev không đồng thuận nhưng không nói → task bị trễ → PL frustrate → dev frustrate. Vòng lặp tiêu cực.

Cách đúng: **cả team cùng tham gia lập plan**. Dev estimate task của mình (vì dev hiểu effort hơn PL). QA góp ý test strategy. Designer xác nhận design timeline. PL tổng hợp và điều phối.

### Phân loại feature — 4 mức ưu tiên

Planning Template của Cyberk chia feature thành 4 mức. Cả team cần cùng thống nhất feature nào thuộc mức nào:

| Mức | Tên | Ý nghĩa | Ví dụ |
|-----|-----|---------|-------|
| 🔴 | **Key Success Features** | Tính năng quyết định thành công. Thiếu = dự án fail. | Booking flow, Payment |
| 🟡 | **Thiết yếu** | Cần để hệ thống hoạt động đúng, nhưng không phải điểm nhấn. | User registration, Email notification |
| 🔵 | **Không ưu tiên** | Bổ sung nhưng không bắt buộc trong phiên bản đầu. | Reporting dashboard, Export CSV |
| ⚪ | **Nice-to-have** | Ý tưởng mở rộng cho tương lai. Không làm trong scope hiện tại. | SMS reminder, Multi-language |

✅ Cách tốt:
> PL chiếu danh sách feature, hỏi team:
> *"Ok, theo mọi người, Booking Flow là Key Success hay Thiết yếu?"*
> Dev: *"Key Success — không có nó thì app không có giá trị."*
> PL: *"Đồng ý. Vậy Reporting Dashboard?"*
> QA: *"Không ưu tiên — David có thể xem revenue trên Stripe dashboard trước, sprint sau mình build riêng."*
> PL: *"Good call. Ghi Reporting = Không ưu tiên."*
>
> → Sau khi phân loại xong, PL hỏi estimate cho từng Key Success Feature:
> *"Booking Flow — Dev estimate bao lâu?"*
> Dev: *"Frontend 3 ngày, backend 2 ngày, integration test 1 ngày. Tổng 6 ngày."*
> PL ghi vào Planning Template.

Tại sao tốt: Mọi người cùng quyết định ưu tiên — không có cảm giác "bị giao việc". Estimate do dev tự đưa ra → dev commit vì đó là con số của họ. PL chỉ tổng hợp và điều phối.

❌ Cách tồi:
> PL mở spreadsheet đã estimate sẵn:
> *"Booking Flow — 3 ngày. Payment — 2 ngày. Dashboard — 4 ngày. Đức làm booking, Thái làm payment, Mai làm dashboard."*
> Dev im lặng, gật đầu.
> → Sprint 2, Đức Slack: *"Anh ơi, booking flow phức tạp hơn em tưởng, cần thêm 3 ngày."*

Tại sao tồi: PL estimate thay dev = estimate sai (vì PL không hiểu chi tiết kỹ thuật). Dev không commit vì "đây không phải con số của mình". Khi trễ, ai cũng đổ lỗi.

---

## Xác định rủi ro — Chủ động hôm nay, đỡ cháy ngày mai

Nhiều team bỏ qua phần này vì "có gì thì xử lý sau". Sai. Rủi ro **luôn** xảy ra — câu hỏi chỉ là bạn đã chuẩn bị hay bị bất ngờ.

4 loại rủi ro cần xem xét:

| Loại | Ví dụ | Câu hỏi kiểm tra |
|------|-------|-------------------|
| **Tiến độ** | Thay đổi yêu cầu đột xuất, phụ thuộc bên thứ ba | Có feature nào phụ thuộc API/service ngoài không? |
| **Công nghệ** | Thư viện/công cụ chưa từng dùng | Team đã dùng tech stack này chưa? Cần PoC không? |
| **Giao tiếp client** | Phản hồi chậm, hiểu sai yêu cầu | PRD có điểm nào mâu thuẫn? Client response nhanh không? |
| **Con người** | Nghỉ việc đột xuất, quá tải | Ai là single point of failure? Có backup không? |

✅ Cách tốt:
> PL mở phần Risk trong Planning Template:
> *"Ok, rủi ro. Mình thấy Payment Integration dùng Stripe API — team đã integrate Stripe bao giờ chưa?"*
> Dev: *"Chưa. Em chỉ dùng thử sandbox."*
> PL: *"Vậy ghi rủi ro: 'Stripe integration chưa có kinh nghiệm'. Giải pháp: Đức dành 1 ngày đầu sprint làm PoC — nếu gặp blocker thì báo ngay, mình switch sang payment gateway khác."*
>
> TL: *"Thêm 1 rủi ro: design chưa final, nếu designer deliver trễ thì FE bị block."*
> PL: *"Đúng. Giải pháp: Designer commit deliver wireframe trước, high-fidelity sau. FE code theo wireframe trước."*

Tại sao tốt: Mỗi rủi ro đã có giải pháp trước khi xảy ra. PoC ngày đầu = biết sớm có vấn đề hay không. Designer deliver wireframe trước = FE không bị block.

❌ Cách tồi:
> PL: *"Rủi ro thì... chắc không có gì đặc biệt. Ok, tiếp nhé."*
> → Sprint 2: Stripe API thay đổi, dev mất 3 ngày debug. Designer deliver trễ 1 tuần, FE ngồi chờ.

Tại sao tồi: "Không có rủi ro" là câu nói nguy hiểm nhất. Mọi dự án đều có rủi ro — chỉ khác là bạn thấy trước hay bị bất ngờ.

---

## Gửi Planning Report — Chốt trong ngày, không để qua đêm

Buổi kickoff kết thúc, PL có 1 việc quan trọng nhất: **tổng hợp Planning Report và gửi trong ngày**. Không phải "mai em gửi" — vì ngày mai bạn sẽ quên 30% chi tiết đã thảo luận.

Report cần gửi cho 2 nhóm:
1. **Client** — để xác nhận scope, timeline, và team hiểu đúng yêu cầu
2. **Leaders (Anderson/COO)** — để nắm tiến độ và hỗ trợ khi cần

✅ Cách tốt:
> Ngay sau buổi họp, PL ngồi lại 1 tiếng, tổng hợp Planning Template đã điền:
> - Kiểm tra logic: task list có cover hết Key Success Features không?
> - Kiểm tra format: mỗi task có owner + deadline chưa?
> - Thêm phần "Follow-up Questions for Client" — những điểm chưa rõ cần hỏi
>
> Xuất PDF, gửi qua Telegram cho client:
> *"Hi David, here's our project plan following today's internal kickoff. Please review the scope, timeline, and let us know if anything needs adjustment. We also have a few questions listed on page 4 — would appreciate your input on those."*
>
> Đồng thời gửi qua Telegram cho Anderson:
> *"Anh ơi, em gửi Planning Report dự án Booking Platform. Tổng timeline 3 tháng, team 3 người. Có 2 rủi ro chính: Stripe integration chưa có kinh nghiệm và design chưa final. Em đã có giải pháp cho cả 2. Anh xem có góp ý gì không ạ."*

Tại sao tốt: Client nhận report trong ngày → cảm thấy team professional và có kế hoạch rõ. Anderson nắm được tình hình ngay. Câu hỏi cho client được gửi sớm = trả lời sớm = không bị block.

❌ Cách tồi:
> PL: *"Ok, em sẽ tổng hợp report gửi sau nhé."*
> → 3 ngày sau vẫn chưa gửi. Phải hỏi lại dev "hôm đó estimate bao nhiêu ngày nhỉ?" Dev: "Em không nhớ..."
> → 1 tuần sau mới gửi report. Client: "Sao lâu vậy, mọi thứ ổn chứ?"

Tại sao tồi: Report gửi trễ = chi tiết sai (vì quên). Client lo lắng. Leaders không nắm được tình hình. Và team mất momentum — "cảm giác kickoff" đã bay mất.

---

## Tóm lại

| Giai đoạn | Nguyên tắc cốt lõi | Sai lầm hay gặp |
|-----------|-------------------|-----------------| 
| Chuẩn bị | Gửi PRD trước, team đọc và ghi chú, book phòng nghiêm túc | Không gửi trước, mất 45 phút đọc PRD trong buổi họp |
| Hiểu sản phẩm | Hiểu MỤC ĐÍCH của client, không chỉ tính năng | Đọc danh sách feature mà không ai biết tại sao |
| Đọc PRD | Thảo luận chủ động, ghi lại mọi câu hỏi chưa rõ | Team im lặng, PRD mâu thuẫn không ai phát hiện |
| Lập kế hoạch | Cả team cùng estimate, phân loại 4 mức ưu tiên | PL tự estimate rồi assign, dev không commit |
| Rủi ro | Xác định sớm 4 loại, mỗi rủi ro có kịch bản xử lý | "Không có rủi ro" — câu nói nguy hiểm nhất |
| Gửi report | Gửi cho client + leaders TRONG NGÀY | Để 1 tuần mới tổng hợp, quên chi tiết, mất momentum |

---

## Liên kết

- [Quy trình kickoff — 4 bước](kick-off-process.md)
- [Mẫu Planning Report & Agenda](./planning-example.md)
