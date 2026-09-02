---
type: delivery
tags: [handover, handbook, client-management]
created-date: 2026-08-25
updated-date: 2026-09-02
author: anderson
status: Nháp
---

# Bàn giao sản phẩm — Cẩm nang cho Product Lead

**Người chịu trách nhiệm:** PL/PM dự án
**Cập nhật lần cuối:** 2026-08-25
**Trạng thái:** Nháp

Bạn là PL/PM, dự án sắp hoàn thành và chuẩn bị bàn giao cho khách hàng. Bàn giao không chỉ là "giao sản phẩm xong rồi thôi" — đây là **khoảnh khắc quyết định ấn tượng cuối cùng**. Làm tốt thì mở ra cơ hội hợp tác tiếp theo; làm tệ thì mất luôn relationship dù sản phẩm tốt đến mấy.

Trang này giúp bạn hiểu **cách nghĩ đúng** ở từng giai đoạn — không chỉ làm gì, mà tại sao làm vậy.

---

## Thông báo client — kiểm soát narrative từ đầu

Thông báo hoàn thành dự án không chỉ là "báo tin". Đây là cơ hội để bạn **kiểm soát narrative** — khách hàng biết trước agenda thì buổi họp sẽ mượt hơn, ít bị lạc đề hơn. Bạn đang đặt kỳ vọng rõ ràng về nội dung sẽ diễn ra, tạo tâm lý tốt trước buổi họp.

Gửi trước buổi họp ít nhất **1 ngày làm việc**. Không gửi sát giờ.

### Thực tế cần hiểu trước khi viết tin nhắn

Hầu hết các dự án khi handover **vẫn còn bugs** và một số tasks chưa hoàn thiện — đó là bình thường. Handover **không có nghĩa là dự án kết thúc** và team không làm gì nữa. Nó có nghĩa là:

> **Chúng ta đã hoàn thành giai đoạn development và giờ chuyển sang giai đoạn bảo trì** — tập trung vào test, sửa lỗi, và làm cho hệ thống ổn định.

Cụ thể:
- **Bugs còn lại** sẽ tiếp tục được xử lý trong giai đoạn maintenance (30 ngày, không phát sinh chi phí)
- **Tasks dang dở** không ảnh hưởng tới main user-flow cũng được hoàn thiện trong 30 ngày đó
- Client có **30 ngày miễn phí** để team cùng đưa hệ thống tới trạng thái ổn định nhất

PL cần frame đúng góc nhìn này khi viết tin nhắn — để client hiểu handover là **chuyển giai đoạn**, không phải **kết thúc hợp tác**.

### Nội dung tin nhắn cần trả lời 4 câu hỏi cho client

1. **Dự án đã xong gì?** — liệt kê cụ thể, không nói chung chung "đã hoàn thành"
2. **Còn gì chưa xong?** — nói thẳng và giải thích nó sẽ được xử lý thế nào
3. **Buổi bàn giao sẽ diễn ra thế nào?** — client biết trước agenda để chuẩn bị
4. **Sau bàn giao thì sao?** — nhấn mạnh 30 ngày maintenance miễn phí, team vẫn làm việc

✅ Cách tốt:
> *"Hi David, great news — we've completed the development phase! All main features are fully built and working, including the booking flow, admin dashboard, and payment integration.*
>
> *There are a few minor items we're still polishing — some UI bugs and edge cases that don't affect the main user flow. These will continue to be handled during the maintenance phase at no additional cost.*
>
> *We'd love to set up a Handover meeting to demo the full product, walk through the handover documents together, and discuss next steps.*
>
> *After the handover, we'll shift into a 30-day free maintenance period. During this time, the team will focus on testing, fixing remaining bugs, and making sure the system is fully stable. So handover doesn't mean we stop — it means we shift our focus from building new features to making everything rock-solid.*
>
> *Really proud of what the team has built here. Let us know your availability!"*

Tại sao tốt: Client nhận được bức tranh trung thực — không chỉ "đã xong" mà cả "còn gì đang xử lý". Câu "handover doesn't mean we stop" loại bỏ nỗi lo lớn nhất của client. 30 ngày miễn phí được frame là "safety net" chứ không phải "deadline". Client vào buổi họp với tâm lý thoải mái vì đã hiểu trước mọi thứ.

❌ Cách tồi:
> *"Hi David, project is done. When can we schedule the handover meeting?"*

Tại sao tồi: "Done" trong khi vẫn còn bugs = không trung thực. Client sẽ phát hiện bugs khi dùng thật, lúc đó niềm tin sụp đổ — "Sao nói done mà còn lỗi?". Không nhắc maintenance = client nghĩ handover là kết thúc, mọi yêu cầu sau đó sẽ bị phản ứng "Sao các bạn không support nữa?".

❌ Cũng tồi:
> *"Hi David, we're mostly done but there are still some bugs. We'll fix them after handover."*

Tại sao tồi: Nói "mostly done" + "still some bugs" mà không có plan cụ thể tạo cảm giác chưa sẵn sàng. Client sẽ nghĩ "Vậy sao lại bàn giao?" — mất tin tưởng. Thiếu frame "chuyển giai đoạn" khiến bugs trở thành vấn đề thay vì phần bình thường của quy trình.

> Mẫu tin nhắn hoàn chỉnh: xem [handover-example.md](./handover-example.md)

---

## Project Overview — tại sao phải nhắc lại cái client "đã biết"?

Khách hàng thường **không nhớ hết** những gì đã thống nhất từ đầu dự án. Nếu bạn nhảy thẳng vào demo mà không nhắc lại goal và function list, client sẽ đánh giá sản phẩm theo **kỳ vọng phát sinh ngoài scope** — và bạn sẽ phải giải thích tại sao cái này không có, cái kia chưa làm.

Việc nhắc lại tạo nền tảng để demo. Client thấy bạn đã deliver đúng và đủ những gì đã hứa — đó là nền tảng của tin tưởng.

✅ Cách tốt:
> PL mở slide Planning từ buổi kickoff:
> *"Before we jump into the demo, let's quickly revisit what we set out to build together. The original goal was to create a booking platform that helps your customers reserve slots online and reduces manual work for your ops team."*
>
> Sau đó chiếu function list, check từng item:
> *"Here's the feature list we committed to — User registration ✓, Booking flow ✓, Payment integration ✓, Admin dashboard ✓, Email notifications ✓. All 12 features delivered as agreed, with one change: we replaced SMS with push notification per your request in Sprint 3."*

Tại sao tốt: Client được "reset" về cùng điểm xuất phát. Khi demo sau đó, họ đánh giá theo cam kết ban đầu — không phải kỳ vọng mới phát sinh giữa chừng.

❌ Cách tồi:
> PL: *"Ok let's start the demo!"* → Nhảy thẳng vào show màn hình.
> Client giữa buổi: *"Wait, what about the reporting feature?"*
> PL: *"Uh... that wasn't in scope actually."*
> Client: *"I thought we discussed it..."*

Tại sao tồi: Không có overview = client xem demo với kỳ vọng hiện tại (đã drift nhiều so với ban đầu). Kết quả: tranh luận về scope ngay giữa buổi bàn giao — phá hỏng không khí.

> **Quy tắc:** Không bỏ qua phần này dù nghĩ là khách hàng đã biết. Việc nhắc lại tạo nền tảng để demo và tạo sự tin tưởng.

---

## Demo — sản phẩm phải tự nói

Đây là **phần quan trọng nhất** của buổi bàn giao. Cho khách hàng thấy tận mắt sản phẩm hoạt động thật sự — không phải qua slide, không phải qua mô tả. Một buổi demo tốt sẽ tạo ra sự phấn khích, củng cố niềm tin và giảm thiểu tranh luận sau này về việc tính năng có hoạt động hay không.

Ba nguyên tắc cốt lõi:
1. **Production only** — demo trên môi trường thật, không dùng local hoặc staging
2. **User flow, không phải screen tour** — đi theo hành trình người dùng thực tế, không chỉ click qua từng màn hình
3. **Demo → hỏi → tiếp** — với mỗi tính năng: giới thiệu ngắn mục đích → demo → hỏi client có câu hỏi không → rồi mới chuyển tiếp

✅ Cách tốt:
> Dev mở production trên browser:
> *"This feature lets customers book a slot in under 30 seconds. Let me walk through the actual flow."*
> → Mở trang chủ → click "Book Now" → chọn ngày giờ → điền thông tin → thanh toán bằng test card → nhận confirmation email.
> *"As you can see, the customer gets an email confirmation immediately. On the admin side..."* → Chuyển sang admin dashboard, show booking vừa tạo hiện real-time.
> *"Any questions about this flow before we move on?"*

Tại sao tốt: Client thấy sản phẩm sống — từ góc user lẫn admin. Demo theo flow thật (không phải click qua màn hình), và pause sau mỗi feature để client hỏi ngay thay vì dồn hết cuối buổi.

❌ Cách tồi:
> Dev mở staging, share screen:
> *"Đây là trang login. Đây là dashboard. Ở đây có nút booking. Bấm vào thì nó sẽ mở form..."* → Không thực sự bấm, chỉ mô tả.
> Hoặc bấm vào thì staging load chậm, data trống, UI bị lệch vì chưa deploy bản mới nhất.

Tại sao tồi: Mô tả thay vì demo = đọc spec, không phải bàn giao sản phẩm. Staging khác production — nếu bug xảy ra trên staging, client mất tin tưởng dù production chạy tốt. Và không có data mẫu thì demo trông như prototype, không phải finished product.

> **Quy tắc cứng:** Không để bug xảy ra lúc demo trực tiếp. Nếu có rủi ro, chuẩn bị video backup. Đã chạy thử toàn bộ flow demo ít nhất 1 lần trước buổi họp.

---

## Bàn giao tài liệu — giao kiến thức, không chỉ giao file

Phần này không chỉ là "gửi file cho client". Mục đích thật sự là trao cho khách hàng đủ kiến thức để **tự vận hành hệ thống** sau khi Cyberk không còn can thiệp hàng ngày.

Nếu sau này client gặp vấn đề và không biết làm gì, trải nghiệm sau dự án sẽ xấu — dù sản phẩm tốt đến mấy. Cảm giác "bị bỏ rơi" sau bàn giao là cách nhanh nhất để mất client.

Nội dung tài liệu Handover cần bao gồm:
- Hướng dẫn truy cập hệ thống (credentials, environments)
- Hướng dẫn vận hành các tính năng chính
- Thông tin hạ tầng và cách theo dõi hệ thống
- Quy trình xử lý khi có sự cố
- Thông tin liên hệ hỗ trợ

✅ Cách tốt:
> PL mở tài liệu handover, share screen:
> *"Let's go through the handover document together so your team can operate the system independently."*
>
> *"First — system access. Here are the admin credentials and the production URL. Can you confirm you can log in?"* → Client thử login ngay tại buổi họp.
>
> *"Next — if the system goes down, here's what to check first: open the monitoring dashboard at this URL, look for red alerts..."* → Show Grafana/monitoring thật.
>
> *"Any questions about this section before we move on?"*

Tại sao tốt: Client không chỉ "nhận file" mà thực sự hiểu. Cho client thử login ngay = xác nhận credentials hoạt động. Câu hỏi được giải đáp tại chỗ — không để tích lũy thành frustration 2 tuần sau.

❌ Cách tồi:
> PL gửi Telegram sau buổi họp:
> *"Hi David, đính kèm tài liệu bàn giao. Anh xem nhé, có gì liên hệ team."*
> → Đính kèm file PDF 15 trang.

Tại sao tồi: Client sẽ không đọc 15 trang (hoặc đọc mà không hiểu hết). 3 tuần sau hệ thống có lỗi, client mở file ra mà không biết phần nào liên quan. Gọi Cyberk thì đã hết maintenance — cả hai bên đều không vui.

---

## Maintenance policy — nói sớm, nói khéo, bảo vệ cả hai bên

Đây là phần nhiều PL ngại nhất — phải nói với client rằng "từ giờ trở đi, làm thêm phải trả tiền". Nhưng suy nghĩ như vậy là sai góc nhìn.

Mục đích thật sự: **thiết lập ranh giới rõ ràng** giữa giai đoạn development và maintenance — ngay tại buổi họp, khi khách hàng đang ở trạng thái tốt, thoải mái và đồng thuận. Việc clarify policy sớm tránh được hiểu nhầm và tranh chấp sau này. Đây là **bảo vệ cho cả hai bên**, không phải "từ chối client".

✅ Cách tốt:
> PL chuyển giọng nhẹ nhàng, nói như đang giải thích cho đối tác:
> *"Now that the product is live, we'll move into the maintenance phase. For the next 30 days our team will continue to monitor and fix any bugs that come up, completely free of charge. Think of it as a safety net while your users start using the system.*
>
> *If you have ideas for new features down the road — and I'm sure you will once real users start giving feedback — we'd love to discuss them. We'll scope it out and share a proposal so you can decide what makes sense."*
>
> Client hỏi: *"What if we find a critical bug after the maintenance period?"*
> PL: *"Great question — let's talk about that. For critical issues that affect your users, we'll always respond quickly. We can set up a support arrangement that works for both sides."*

Tại sao tốt: Giọng giải thích, không giọng thông báo. "Safety net" thay vì "thời hạn". Mở cửa cho tương lai thay vì đóng lại. Và khi client hỏi — xử lý tại đây, không để thành email tranh luận sau.

❌ Cách tồi:
> PL đọc slide:
> *"According to our contract, the free maintenance period covers bug fixes only, not new features. The maintenance window ends on September 15th. After that date, all requests will be scoped and billed separately."*
>
> Client im lặng. Không khí buổi họp lạnh đi.

Tại sao tồi: Giọng pháp lý biến buổi bàn giao thành buổi đọc hợp đồng. Client cảm thấy bị đặt vào thế đối lập — "billed separately" nghe như đe dọa thay vì hỗ trợ. Không khí tích cực từ demo bị phá hỏng trong 30 giây.

> Chi tiết SLA, thời hạn, phạm vi: xem [maintenance-policy-reference.md](./maintenance-policy-reference.md)

---

## Open Talk — kết thúc đẹp mở ra cơ hội tiếp theo

Đây là phần quan trọng cho **relationship** — không phải cho "buổi họp". Khách hàng được lắng nghe, team biết được kỳ vọng tiếp theo, và cả hai bên kết thúc buổi họp trong trạng thái tích cực.

Gợi ý câu hỏi để mở đầu:
- *"Is there anything you'd like us to revisit or explain further?"*
- *"Do you have any feedback from the QA session on your side?"*
- *"What are you thinking about next for the product?"*

✅ Cách tốt:
> PL: *"Before we wrap up — is there anything you'd like us to revisit, or any feedback from your side?"*
>
> Client: *"Actually, we've been thinking... it would be great if the system could also send SMS reminders to customers before their booking."*
>
> PL: *"That's a great idea — once real users start using the system, reminders could really reduce no-shows. Let us think about the best approach and get back to you with a plan and estimate next week. Sound good?"*
>
> → Ghi lại action item: "Propose SMS reminder feature — send estimate by next Friday."

Tại sao tốt: Client cảm thấy ý kiến được đón nhận, không bị từ chối. PL không commit scope tại chỗ nhưng mở ra cơ hội rõ ràng. Và action item được ghi lại — không phải lời hứa suông.

❌ Cách tồi:
> PL: *"Ok, if there's nothing else, let's end the meeting. Thank you everyone."*
> → Tắt họp. Không hỏi, không đợi.
>
> Hoặc ngược lại — client nói muốn thêm feature, PL nói luôn: *"Sure, we can do that!"* mà chưa estimate.

Tại sao tồi: Kết thúc lạnh lẽo = client không có cơ hội nói, bạn mất cơ hội bán thêm. Còn commit tại chỗ = tạo kỳ vọng mà chưa biết effort — dễ thành nợ miệng.

---

## Sau buổi bàn giao — đừng để rơi rớt

Buổi họp kết thúc không có nghĩa là xong. Có 3 việc cần làm ngay:

1. **Xác nhận biên bản bàn giao** (nếu có) — document chính thức cho cả hai bên
2. **Gửi lại toàn bộ tài liệu Handover** qua email hoặc kênh liên lạc chính thức — client có 1 nơi để tra cứu
3. **Ghi lại action items** phát sinh từ Open Talk — đừng để "nói xong rồi quên"

---

## Tóm lại

| Giai đoạn | Nguyên tắc cốt lõi | Sai lầm hay gặp |
|-----------|-------------------|-----------------|
| Thông báo | Trung thực, frame "chuyển giai đoạn", nhấn 30 ngày miễn phí | Nói "done" khi vẫn còn bugs |
| Overview | Nhắc lại cam kết gốc trước khi demo | Bỏ qua vì "client đã biết" |
| Demo | Production only, user flow thật, pause để hỏi | Click qua screen, demo trên staging |
| Tài liệu | Walk through, giao kiến thức không chỉ giao file | Gửi file rồi thôi |
| Maintenance | Nhẹ nhàng, rõ ràng, bảo vệ cả hai bên | Đọc như hợp đồng |
| Open Talk | Lắng nghe, mở cơ hội, không commit tại chỗ | Kết thúc lạnh lẽo |
| Sau bàn giao | Gửi tài liệu, ghi action items, follow up | Họp xong là xong |

## Liên kết
- [Quy trình bàn giao](./handover-process.md)
- [Mẫu tin nhắn](./handover-example.md)
- [Bảng tra SLA bảo trì](./maintenance-policy-reference.md)
- *(Meeting Agenda cho Client — chưa có, cần tạo)*
