# Mẫu bàn giao — Template & Ví dụ cho từng bước

**Người chịu trách nhiệm:** [PL/PM]
**Cập nhật lần cuối:** 2026-08-25

> File này chứa **mẫu sẵn để copy-paste** cho từng bước trong [quy trình bàn giao](./handover-process.md). Cách nghĩ chi tiết hơn: xem [handbook](./handover-handbook.md).

---

## Bước 1 — Chuẩn bị tài liệu, slide, đóng gói repository

### Mẫu Slide Deck — Outline

```
Slide 1: Cover
  → [Tên dự án] — Handover Presentation
  → Cyberk × [Tên client]
  → [Ngày bàn giao]

Slide 2: Agenda
  → 1. Project Overview (5 phút)
  → 2. Live Demo (20 phút)
  → 3. Handover Documents (10 phút)
  → 4. Maintenance Policy (5 phút)
  → 5. Open Discussion (10 phút)

Slide 3: Project Overview
  → Original goal: [1–2 câu mục tiêu ban đầu]
  → Timeline: [ngày bắt đầu] → [ngày bàn giao]
  → Team: [số người], [vai trò chính]

Slide 4: Feature List — What We Delivered
  → ✅ Feature 1: User Registration & Authentication
  → ✅ Feature 2: Booking Flow (search → select → pay → confirm)
  → ✅ Feature 3: Admin Dashboard (manage bookings, users, revenue)
  → ✅ Feature 4: Payment Integration (Stripe)
  → ✅ Feature 5: Email Notifications (confirmation, reminder)
  → ...
  → 📝 Change: Replaced SMS with Push Notification (per client request, Sprint 3)

Slide 5: Live Demo
  → "Let's see the product in action"
  → [Chuyển sang demo trên production]

Slide 6: Handover Documents
  → System Access & Credentials
  → Architecture Overview
  → Operation Guide
  → Incident Response
  → Contact Information

Slide 7: Maintenance Policy
  → 30-day free maintenance period
  → What's included / What's not
  → How to report bugs
  → After maintenance: new feature proposals welcome

Slide 8: Thank You & Open Discussion
  → Questions?
  → What's next for the product?
```

### Mẫu Handover Document — Outline

```markdown
# [Tên dự án] — Handover Document

## 1. System Access
| Môi trường | URL | Tài khoản | Mật khẩu |
|-----------|-----|-----------|----------|
| Production | https://app.example.com | admin@example.com | [gửi riêng] |
| Admin Panel | https://admin.example.com | superadmin | [gửi riêng] |
| Monitoring | https://grafana.example.com | readonly | [gửi riêng] |

## 2. Architecture Overview
- Frontend: React, deployed on Vercel
- Backend: Node.js + Express, deployed on AWS EC2
- Database: PostgreSQL on AWS RDS
- Storage: AWS S3 (user uploads)
- CI/CD: GitHub Actions → auto-deploy on merge to main

## 3. Key Features — Operation Guide
### Booking Management
- Xem tất cả bookings: Admin Panel → Bookings → All
- Export báo cáo: Admin Panel → Reports → Export CSV
- Cancel booking: Admin Panel → Bookings → [chọn booking] → Cancel

### User Management
- Tạo admin mới: Admin Panel → Users → Add Admin
- Block user: Admin Panel → Users → [chọn user] → Block

## 4. Incident Response
| Tình huống | Kiểm tra gì | Hành động |
|-----------|-------------|----------|
| Website không truy cập được | Grafana → Server Status | Restart EC2 instance / Liên hệ Cyberk |
| Thanh toán lỗi | Stripe Dashboard → Payments | Kiểm tra API key / webhook |
| Email không gửi được | SendGrid Dashboard → Activity | Kiểm tra quota / API key |

## 5. Contact Information
| Vai trò | Tên | Liên hệ | Khi nào liên hệ |
|--------|-----|---------|-----------------|
| Product Lead | [Tên PL] | [email/Slack] | Mọi vấn đề chung |
| Tech Lead | [Tên TL] | [email/Slack] | Vấn đề kỹ thuật khẩn |
| QA | [Tên QA] | [email/Slack] | Báo bug |
```

### Mẫu Repository README — Đóng gói repo

```markdown
# [Tên dự án]

## Quick Start
1. Clone repo: `git clone [url]`
2. Install dependencies: `npm install`
3. Copy env: `cp .env.example .env`
4. Run: `npm run dev`

## Environment Variables
| Variable | Description | Example |
|----------|------------|---------|
| DATABASE_URL | PostgreSQL connection string | postgresql://user:pass@host:5432/db |
| STRIPE_SECRET_KEY | Stripe API key | sk_live_... |
| SENDGRID_API_KEY | Email service key | SG.xxx |

## Deployment
- Production: Auto-deploy on merge to `main`
- Staging: Auto-deploy on merge to `develop`

## Project Structure
├── src/
│   ├── api/          # API routes
│   ├── services/     # Business logic
│   ├── models/       # Database models
│   └── utils/        # Helpers
├── tests/
└── docs/             # Additional documentation
```

---

## Bước 2 — Hẹn lịch call, kèm nội dung trước

### ✅ Mẫu TỐT — Tin nhắn hẹn lịch bàn giao

> *Hi David, great news — we've completed the development phase! All main features are fully built and working, including the booking flow, admin dashboard, and payment integration.*
>
> *There are a few minor items we're still polishing — some UI bugs and edge cases that don't affect the main user flow. These will continue to be handled during the maintenance phase at no additional cost.*
>
> *We'd love to set up a Handover meeting to demo the full product, walk through the handover documents together, and discuss next steps. Here's what we'll cover:*
>
> ***Agenda:***
> *1. Project overview & feature checklist (5 min)*
> *2. Live product demo on production (20 min)*
> *3. Handover documents walkthrough (10 min)*
> *4. Maintenance policy & support channels (5 min)*
> *5. Open discussion & next steps (10 min)*
>
> *After the handover, we'll shift into a 30-day free maintenance period. During this time, the team will focus on testing, fixing remaining bugs, and making sure the system is fully stable. So handover doesn't mean we stop — it means we shift our focus from building new features to making everything rock-solid.*
>
> *Really proud of what the team has built here. Would any of these times work for you?*
> *- Tuesday Aug 26, 2:00 PM (GMT+7)*
> *- Wednesday Aug 27, 10:00 AM (GMT+7)*

Tốt vì: Trả lời 4 câu hỏi client quan tâm (xong gì, còn gì, bàn giao thế nào, sau đó sao). Có agenda cụ thể → client biết sẽ thảo luận gì. Đề xuất 2 slot → client chọn nhanh. Frame "chuyển giai đoạn" loại bỏ nỗi lo.

### ❌ Mẫu KHÔNG TỐT

> *Hi David, project is done. When can we schedule the handover meeting?*

Tại sao tồi: "Done" khi vẫn còn bugs — không trung thực. Không có agenda → client vào họp không biết chuẩn bị gì. Không nhắc maintenance → client nghĩ handover = kết thúc.

---

## Bước 3 — Call với khách hàng

### Mẫu Opening Script — Mở đầu buổi bàn giao

> *"Thank you everyone for joining today. Before we jump into the demo, let's quickly revisit what we set out to build together.*
>
> *The original goal was to create a booking platform that helps your customers reserve slots online and reduces manual work for your ops team.*
>
> *Here's the feature list we committed to..."*
>
> [Chiếu slide Feature List, check từng item]
>
> *"User registration ✓, Booking flow ✓, Payment integration ✓, Admin dashboard ✓, Email notifications ✓. All 12 features delivered as agreed, with one change: we replaced SMS with push notification per your request in Sprint 3.*
>
> *Now let me hand over to [Dev name] for the live demo."*

### Mẫu Demo Flow — Cách demo từng feature

> **Feature: Booking Flow**
>
> *"This feature lets customers book a slot in under 30 seconds. Let me walk through the actual flow."*
>
> → Mở trang chủ trên production
> → Click "Book Now"
> → Chọn ngày giờ
> → Điền thông tin khách hàng
> → Thanh toán bằng test card
> → Nhận confirmation email
>
> *"As you can see, the customer gets an email confirmation immediately. On the admin side..."*
>
> → Chuyển sang admin dashboard
> → Show booking vừa tạo hiện real-time
>
> *"Any questions about this flow before we move on?"*

### Mẫu Walkthrough Tài liệu — Cách trình bày handover doc

> *"Let's go through the handover document together so your team can operate the system independently."*
>
> *"First — system access. Here are the admin credentials and the production URL. Can you confirm you can log in?"*
>
> → Client thử login ngay tại buổi họp
>
> *"Great, that works. Next — if the system goes down, here's what to check first: open the monitoring dashboard at this URL, look for red alerts..."*
>
> → Show Grafana/monitoring thật
>
> *"Any questions about this section before we move on?"*

### Mẫu Giải thích Maintenance Policy

> *"Now that the product is live, we'll move into the maintenance phase. For the next 30 days our team will continue to monitor and fix any bugs that come up, completely free of charge. Think of it as a safety net while your users start using the system.*
>
> *What's included: any technical bugs, performance issues, and edge cases that affect user experience.*
>
> *What's separate: new features or changes to existing features — and I'm sure you'll have great ideas once real users start giving feedback. We'd love to discuss them. We'll scope it out and share a proposal so you can decide what makes sense."*
>
> Client hỏi: *"What if we find a critical bug after the 30 days?"*
>
> PL: *"Great question. For critical issues that affect your users, we'll always respond quickly. We can set up a support arrangement that works for both sides."*

### Mẫu Kết thúc — Open Talk

> *"Before we wrap up — is there anything you'd like us to revisit, or any feedback from your side?"*
>
> Client: *"Actually, we've been thinking... it would be great if the system could also send SMS reminders to customers before their booking."*
>
> PL: *"That's a great idea — once real users start using the system, reminders could really reduce no-shows. Let us think about the best approach and get back to you with a plan and estimate next week. Sound good?"*
>
> → Ghi lại action item: "Propose SMS reminder feature — send estimate by next Friday"
>
> *"Thank you so much for trusting us with this project. We're really excited to see your users enjoy the product. Remember — we're still here for the next 30 days, and beyond that, just reach out anytime."*

---

## Bước 4 — Gửi email tổng kết

### ✅ Mẫu TỐT — Email recap sau buổi bàn giao

> **Subject:** [Project Name] — Handover Complete | Documents & Next Steps
>
> *Hi David,*
>
> *Thank you for joining today's handover session! Here's a quick recap and everything you need in one place.*
>
> ***What we covered:***
> *- Project overview: all 12 features delivered as agreed*
> *- Live demo: full booking flow, admin dashboard, payment, and notifications demonstrated on production*
> *- Handover documents: system access, architecture, operation guide, incident response*
> *- Maintenance policy: 30-day free bug fix period starting today (Aug 26)*
>
> ***Action items:***
>
> | # | Action | Owner | Deadline |
> |---|--------|-------|----------|
> | 1 | Send SMS reminder feature estimate | Cyberk | Friday Aug 29 |
> | 2 | Confirm admin account access for ops team | David's team | Wednesday Aug 27 |
> | 3 | Share list of team members who need training access | David's team | Friday Aug 29 |
>
> ***Attached documents:***
> *- Handover Document (PDF) — system access, architecture, operation guide*
> *- Slide deck from today's session*
>
> ***Maintenance period:***
> *- Duration: 30 days (Aug 26 → Sep 25)*
> *- Bug reports: send to [Slack channel / email]*
> *- Response time: critical issues within 4 business hours, other bugs within 1 business day*
> *- Scope: bug fixes and stability improvements. New features will be scoped separately.*
>
> *Credentials for production and admin access have been shared separately via [encrypted channel].*
>
> *Thank you for trusting us with this project — really excited to see your users enjoy the product! Don't hesitate to reach out anytime.*
>
> *Best regards,*
> *[Tên PL]*
> *Cyberk*

Tốt vì: Email có cấu trúc rõ — recap → action items có deadline → attachments → maintenance timeline. Client có 1 nơi duy nhất để tra cứu mọi thứ. Action items ghi rõ **ai làm** + **deadline cụ thể**.

### ❌ Mẫu KHÔNG TỐT

> *Hi David, đính kèm tài liệu bàn giao. Anh xem nhé, có gì liên hệ team.*
> → Đính kèm file PDF 15 trang. Không recap, không action items.

Tại sao tồi: Client không đọc 15 trang. Không có action items → mọi thứ nói trong buổi họp tan biến. 3 tuần sau hệ thống lỗi → mở file không biết phần nào liên quan.

---

## Nguyên tắc chung

| Không nên | Nên |
|-----------|-----|
| Gửi sát giờ, không có agenda | Gửi trước ít nhất 1 ngày, đính kèm agenda rõ |
| Nói "done" khi còn bugs | Frame "chuyển giai đoạn development → maintenance" |
| Nhảy thẳng vào demo | Nhắc lại project overview + feature list trước |
| Click qua screen, mô tả thay vì bấm | Demo user flow thật trên production |
| Chỉ gửi file, không giải thích | Walk through từng mục, client thử login tại chỗ |
| Đọc maintenance policy giọng hợp đồng | Giọng đối tác — "safety net", mở cửa tương lai |
| Commit tính năng mới tại buổi bàn giao | Ghi nhận → estimate → báo lại sau |
| Follow-up không có action items | Recap + action items + owner + deadline |
