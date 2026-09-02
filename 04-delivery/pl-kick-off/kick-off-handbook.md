---
type: delivery
tags: [kick-off, handbook, client-management]
created-date: 2026-08-27
updated-date: 2026-09-02
author: anderson
status: Nháp
---

# Kick-off với Khách hàng — Cẩm nang cho Product Lead

**Người chịu trách nhiệm:** PL/PM dự án
**Cập nhật lần cuối:** 2026-08-27
**Trạng thái:** Nháp

Bạn là PL/PM, hợp đồng vừa ký, Internal Planning đã xong. Giờ bạn cần tổ chức buổi Kick-off Meeting chính thức với khách hàng. Đây là **ấn tượng đầu tiên** — client đánh giá team qua buổi này. Chuyên nghiệp hay hời hợt, có chuẩn bị hay bị động — tất cả lộ ra trong 45 phút kick-off.

Trang này giúp bạn hiểu **cách nghĩ đúng** ở từng giai đoạn — không chỉ làm gì, mà tại sao làm vậy.

---

## Tại sao kick-off với client quan trọng?

Kick-off với client **không phải buổi planning lần 2**. Planning đã xong rồi — bạn đã có plan, có task list, có risk assessment. Buổi kick-off với client phục vụ mục đích hoàn toàn khác:

1. **Tạo niềm tin** — Client thấy team đã chủ động lập kế hoạch, có người cụ thể phụ trách, có plan rõ ràng. Niềm tin xây ở buổi đầu tiên sẽ "mua" cho bạn sự kiên nhẫn khi gặp vấn đề sau này.
2. **Đặt kỳ vọng đúng** — Scope là gì, approach ra sao, deadline nào, ai liên hệ gì. Nếu không align ở đây, 3 tuần sau client sẽ hỏi "Sao chưa có feature X?" — một thứ team chưa bao giờ cam kết.
3. **Thiết lập cách làm việc** — Kênh liên lạc, tần suất báo cáo, escalation path. Không thiết lập sớm = mỗi bên một cách, hỗn loạn từ sprint 2.

> **Quy tắc:** Mục tiêu duy nhất của buổi kick-off: client rời buổi họp với cảm giác "Team này biết mình đang làm gì. Tôi yên tâm."

---

## Tin nhắn ngày đầu tiên — chào hỏi, giới thiệu quy trình, hẹn lịch

Ngày đầu tiên không chỉ là "báo tin team bắt đầu." Đây là lần đầu client nhận tin nhắn từ PL — **ấn tượng đầu tiên**. Client cần biết 3 thứ: mình sẽ làm việc với ai, team sẽ làm gì hôm nay, và tiếp theo là gì.

Tin nhắn ngày đầu phải làm được 4 việc:
1. **Tự giới thiệu** — PL là ai, vai trò gì, liên hệ thế nào
2. **Giải thích quy trình hôm nay** — Internal Planning là gì, tại sao quan trọng
3. **Giới thiệu bước tiếp theo** — Kick-off Call để làm gì, tại sao cần
4. **Hỏi lịch** — Đề xuất hẹn kick-off call ngay trong tin nhắn đầu tiên

✅ Cách tốt:
> *"Hi David, good morning! I'm Minh, your Product Lead from Cyberk — I'll be your main point of contact throughout the project. Very excited to be working with you on BookingApp!*
>
> *I wanted to share how we kick things off at Cyberk:*
>
> *📋 Step 1 — Internal Planning (today): Our full team — developers, QA, and tech lead — will sit down together to go through the project requirements in detail. We'll build a complete project plan: task breakdown, timeline, milestones, risk assessment, and team assignments. Why? We want every team member to deeply understand the product before writing a single line of code. I'll send you the Planning Report by end of day today.*
>
> *🤝 Step 2 — Kick-off Call (with you): After the plan is ready, I'd like to schedule a call where we introduce the team, walk through the plan, and discuss our approach together. This is where we align expectations and make sure we're 100% on the same page before Sprint 1 begins.*
>
> *Could you share your availability for a 45–60 min call in the next 2–3 days? I'll send an agenda beforehand so you know exactly what we'll cover.*
>
> *Looking forward to a great collaboration!"*

Tại sao tốt: Client biết ngay PL là ai. Hiểu quy trình Cyberk — team không code bừa mà có planning bài bản. Biết sẽ có buổi kick-off call, không bị bất ngờ. Và PL đã hỏi lịch luôn — không phải chờ bước 2 rồi mới hẹn.

❌ Cách tồi:
> *(Im lặng cả ngày. Tối mới gửi file: "Hi David, attached is the plan.")*

Tại sao tồi: Client không biết PL là ai. Không hiểu team đang làm gì cả ngày. File gửi trơn không context. Mất cơ hội tạo ấn tượng chuyên nghiệp ngay từ ngày 1.

❌ Cũng tồi:
> *"Hi David, good morning! Today our team is holding an internal planning session. We'll send you the plan by end of day."*

Tại sao tồi: Không tự giới thiệu — client không biết nói chuyện với ai. Không giải thích planning là gì, tại sao quan trọng — client nghĩ đây chỉ là thủ tục. Không nhắc kick-off call — bước tiếp theo bị bỏ ngỏ. "Soon" và "by end of day" quá mờ nhạt.

> Mẫu tin nhắn hoàn chỉnh: xem [kick-off-example.md](./kick-off-example.md)

---

## Gửi plan — summary trước, file sau

Sai lầm lớn nhất khi gửi Planning Report: gửi file trơn. Client mở PDF 10 trang ra, không biết đọc phần nào quan trọng, lướt qua rồi đóng. Khi buổi kick-off diễn ra, client chưa thực sự đọc plan.

**Nguyên tắc: summary text đi trước file.** Client đọc summary trong 30 giây, nắm 3 ý chính, rồi mới mở file xem chi tiết nếu muốn.

Ba mục bắt buộc trong summary:

1. **Approach** — Team sẽ tiếp cận dự án thế nào? (Agile? Sprint bao lâu? Feature nào làm trước?)
2. **Key Risks** — Rủi ro nào đáng lưu ý nhất? Team sẽ xử lý thế nào?
3. **Strategy** — Chiến lược delivery: ưu tiên gì, tại sao thứ tự này?

Lúc này client đã biết sẽ có buổi kick-off (bạn đã hẹn ở tin nhắn sáng). Nên tin nhắn gửi plan chỉ cần focus vào **nội dung plan** — không cần hỏi lịch lại.

✅ Cách tốt:
> PL gửi Telegram kèm file:
>
> *"Hi David, our internal planning is complete! Here's the Planning Report (attached). Quick summary:*
>
> *📋 Approach: We'll run 1-week sprints with daily progress updates, starting with the booking flow — the core user journey — before building secondary features like admin reports.*
>
> *⚠️ Key Risks: The payment gateway API documentation is incomplete. We've allocated a spike in Sprint 1 to validate integration before committing to a timeline for that module.*
>
> *🎯 Strategy: Key Success Features first (booking, payment, notifications). Nice-to-have features (analytics dashboard) will be prioritized if we have capacity in Sprint 4.*
>
> *Looking forward to walking you through this in our kick-off call! I'll send the agenda once we confirm the time."*

Tại sao tốt: Client hiểu 3 ý chính trong 30 giây. Risk được frame thành "team đã nghĩ trước và có plan" — không phải "có vấn đề". Nối liền với kick-off call đã hẹn sáng — quy trình mạch lạc.

❌ Cách tồi:
> *"Hi David, please find the attached Planning Report."*

Tại sao tồi: Client mở PDF, lướt qua, đóng lại. Không nắm ý chính, không biết phần nào quan trọng. Buổi kick-off sau đó phải giải thích từ đầu — lãng phí thời gian.

❌ Cũng tồi:
> *"Hi David, the plan is done. The project has some risks but we'll handle them. Let me know when you're free to call."*

Tại sao tồi: "Some risks but we'll handle them" = mơ hồ, không chuyên nghiệp. "Let me know when you're free" = bị động — bạn đã hỏi lịch ở tin nhắn sáng rồi, đừng hỏi lại.

> Mẫu tin nhắn hoàn chỉnh: xem [kick-off-example.md](./kick-off-example.md)

> **Về agenda kick-off:** Khi client confirm giờ, gửi agenda ít nhất **1 ngày trước buổi call**. Client biết trước sẽ thảo luận gì, chuẩn bị câu hỏi, không bị bất ngờ.

---

## Buổi Kick-off Call — ấn tượng đầu tiên

Đây là lúc client **thấy team bằng mắt** lần đầu tiên. Mọi thứ trước đó là tin nhắn và file. Buổi call quyết định client nghĩ gì về team trong suốt dự án.

### Phần 1: Team Introduction (10 phút)

**Mục đích:** Client biết mình sẽ làm việc với ai, liên hệ ai khi cần gì.

Đừng chỉ nói tên + chức danh. Client cần biết: **người này sẽ giúp tôi gì?**

✅ Cách tốt:
> PL: *"Let me introduce the team. I'm [Name], I'll be your main point of contact for everything — progress updates, questions, changes. If you need anything, come to me first."*
>
> *"This is [TL Name], our Tech Lead. He'll be leading the technical architecture and code quality. If you ever have questions about how something works under the hood, he's the person."*
>
> *"And this is [Dev Name], our lead developer on this project. He'll be building the core booking flow."*

Tại sao tốt: Mỗi người được giới thiệu với vai trò cụ thể trong dự án **này** — không phải bio chung chung. Client biết ngay: "Có vấn đề gì → liên hệ PL. Câu hỏi kỹ thuật → TL."

❌ Cách tồi:
> *"I'm [Name], PM. This is [TL], senior developer. This is [Dev], developer."*

Tại sao tồi: Chức danh không nói gì. Client không biết ai phụ trách gì, liên hệ ai khi cần gì.

### Phần 2: Planning Walk-through (15 phút)

**Mục đích:** Client hiểu plan — không phải đọc lại plan.

Client đã nhận Planning Report rồi (có thể đã đọc, có thể chưa). Phần này bạn **walk through** — không phải đọc lại từng dòng.

Focus vào 4 ý chính:
1. **Scope** — Chúng ta sẽ build gì? (Feature list, phân loại ưu tiên)
2. **Timeline** — Khi nào xong? (Milestones, sprint plan)
3. **Ownership** — Ai làm gì? (Task breakdown theo người)
4. **Risks** — Điều gì có thể chậm trễ và team sẽ xử lý thế nào?

✅ Cách tốt:
> PL share screen, mở Planning Report:
> *"You've received the full plan — let me walk through the key points. We've prioritized features into 4 levels. The Key Success Features — booking flow, payment, and notifications — will be delivered in Sprints 1–3. These are the must-haves that determine whether the product works."*
>
> *"One risk I want to flag early: the payment API docs are incomplete. We're running a validation spike in Sprint 1 — by the end of week 2, we'll know if we need to adjust the approach."*

Tại sao tốt: Không đọc lại plan — tóm ý chính. Risk được frame chủ động ("team đã có plan"), không bị động ("có vấn đề").

❌ Cách tồi:
> PL mở slide 1, đọc: *"Page 1, Project Overview..."* → Đọc từng trang, y hệt file PDF.

Tại sao tồi: Client đã có file. Đọc lại = lãng phí thời gian. Buổi call phải tạo giá trị **thêm** so với đọc file — đó là giải thích, highlight, và trả lời câu hỏi.

### Phần 3: Approach & Strategy Discussion (15 phút)

**Mục đích:** Client hiểu **tại sao** team chọn cách này, và có cơ hội góp ý.

Đây là phần quan trọng nhất — nơi client thấy team có suy nghĩ, không chỉ nhận yêu cầu và code. Nội dung thảo luận:

- **Development methodology** — Agile/Sprint, tần suất báo cáo, cách feedback
- **Technical approach** — Tại sao chọn tech stack này? Architecture như thế nào?
- **Risk mitigation** — Team sẽ xử lý risk thế nào nếu nó xảy ra?
- **Communication cadence** — Daily demo? Daily report qua kênh nào?

✅ Cách tốt:
> PL: *"Let me explain our approach. We'll work in 1-week sprints, with daily progress updates and demos. Every day, you'll see what's been built — you can see it running and give feedback immediately. If something needs to change, we catch it the next day, not next week."*
>
> TL: *"On the technical side, we're using Next.js with a PostgreSQL database. This gives us the best balance between development speed and scalability for your expected 10,000 users in the first 6 months."*
>
> PL: *"For communication, we'll send you a daily progress report via Telegram — including what was built, what's next, and any blockers. Each day ends with a quick demo of what's been completed, so you can see the product evolving in real-time and give feedback immediately. Does that work for your team?"**

Tại sao tốt: Client hiểu methodology (sẽ thấy output mỗi ngày, không phải chờ cuối sprint), TL giải thích tech choice bằng ngôn ngữ business (không phải jargon), và communication được thiết lập cụ thể — ngày, kênh, tần suất.

❌ Cách tồi:
> PL: *"We'll use Agile. Any questions?"*

Tại sao tồi: Client nghe "Agile" hàng chục lần rồi. Không nói gì mới, không tạo giá trị.

### Phần 4: Open Q&A (10 phút)

**Mục đích:** Client hỏi bất cứ gì — kể cả điều họ ngại hỏi.

Mở bằng câu mời rõ ràng, không hỏi chung chung "Có câu hỏi gì không?"

✅ Cách tốt:
> *"Before we wrap up — is there anything you'd like us to do differently? Any concerns about the timeline, the approach, or anything else? This is the best time to raise it — we'd rather adjust now than discover a misalignment in Sprint 3."*

Tại sao tốt: "Do differently" mời client góp ý (không chỉ hỏi). "Rather adjust now" = frame rằng feedback sớm là tốt, không phải phàn nàn.

❌ Cách tồi:
> *"Any questions? No? Ok let's wrap up."*

Tại sao tồi: Hỏi nhanh, không chờ = client nghĩ team không thực sự muốn nghe. Những lo lắng chưa nói ra sẽ thành vấn đề 3 tuần sau.

### Phần 5: Next Steps (5 phút)

**Mục đích:** Ai làm gì tiếp theo, khi nào, bằng kênh nào.

Kết thúc buổi call bằng 3 câu cụ thể:
1. *"Sprint 1 starts on [Date]."*
2. *"I'll send a summary email today with everything we discussed."*
3. *"You'll receive daily progress reports via Telegram, starting from day one. I'll set up the group today."*

> **Quy tắc:** Không kết thúc buổi call mà không có 3 thứ: ngày bắt đầu, next action item, và kênh liên lạc đã confirm.

---

## Sau buổi call — tổng kết trong ngày

Email tổng kết phải gửi **trong ngày** — không phải "mai tổng hợp rồi gửi." Lý do:

- Client vừa rời buổi họp với ấn tượng tốt → email ngay = củng cố ấn tượng
- Để qua đêm = client quên 30% nội dung, bạn cũng quên
- Email tổng kết là **tài liệu tham chiếu** — client sẽ mở lại khi cần

Email tổng kết cần có:
- Danh sách attendees
- Key decisions (những gì đã thống nhất)
- Action items (ai, làm gì, khi nào)
- Next steps (ngày bắt đầu sprint, first sync, kênh liên lạc)

✅ Cách tốt:
> Gửi email 2 tiếng sau buổi call, structured rõ ràng, có bảng action items.

❌ Cách tồi:
> Gửi ngày hôm sau, nội dung là 1 đoạn văn dài không bullet points.

> Mẫu email hoàn chỉnh: xem [kick-off-example.md](./kick-off-example.md)

---

## Mẫu tốt vs Mẫu tồi — tổng hợp

| Giai đoạn | Mẫu tốt ✅ | Mẫu tồi ❌ |
|-----------|-----------|-----------| 
| Tin nhắn ngày đầu | Tự giới thiệu, giải thích 2-step process, hỏi lịch kick-off luôn | Im lặng cả ngày, hoặc gửi tin không giới thiệu mình |
| Gửi plan | Summary text (Approach, Risks, Strategy) + file PDF | Gửi file trơn: "Please see attached" |
| Team intro | Giới thiệu vai trò cụ thể trong dự án **này** | Đọc chức danh: "PM, Senior Dev, Dev" |
| Walk-through | Tóm ý chính, highlight risk, mời hỏi | Đọc lại PDF từng trang |
| Approach | Giải thích methodology + tech choice bằng business language | "We use Agile. Any questions?" |
| Q&A | Mời góp ý: "Is there anything you'd like us to do differently?" | "Any questions? No? Ok done." |
| Next Steps | 3 câu: start date, summary email, first sync | Kết thúc không commit gì cụ thể |
| Email tổng kết | Gửi trong ngày, structured, có action items table | Gửi hôm sau, đoạn văn dài |

---

## Liên kết

- [Quy trình kick-off với client — từng bước](./kick-off-process.md)
- [Mẫu agenda, tin nhắn & email](./kick-off-example.md)
- [Internal Planning — họp nội bộ lập kế hoạch](../pl-planning/planning-handbook.md)
