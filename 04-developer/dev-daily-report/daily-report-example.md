---
type: delivery
tags: [daily-report, example, template]
created: 2026-08-25
updated: 2026-11-26
author: anderson
status: Nháp
---

# Mẫu Daily Report — Chưa tốt vs Tốt

**Người chịu trách nhiệm:** PO / Product Owner
**Cập nhật lần cuối:** 2026-11-26

> Mỗi mẫu có một bản chưa tốt đặt trước và một bản tốt đặt sau, để so trực tiếp. Daily Report viết bằng tiếng Anh, vì người đọc là khách. Cách nghĩ đằng sau từng câu nằm ở [Cẩm nang Daily Report](./daily-report-handbook.md). Mẫu Daily Report Koto và tin nhắn summary gửi kèm PDF nằm ở [Internal Daily — Mẫu](../../05-product-owner/po-internal-daily/internal-daily-example.md).

---

## 1. Daily Report của dự án đang chạy

### Mẫu chưa tốt

```
Daily Report - Sep 17th

What we completed
- Worked on frontend
- Finished coding feature
- Fixed bugs

What we're stuck on
- Có một số vấn đề về performance
- Chưa có risk gì đáng kể

Next steps
- Continue coding
- Will work on backend
```

Khách không biết frontend nào, bug nào. Vấn đề performance không có severity, không biết ảnh hưởng gì. Không có giải pháp nào, nên khách đọc xong chỉ thấy lo. "Continue coding" là mô tả trạng thái, không phải kế hoạch, và Next steps đã có trên board ngay bên dưới.

### Mẫu tốt

```
Daily Report - Sep 17th

What we completed
85% of AI Assistant Milestone done, 2 days behind plan
- Deployed staking contract with gas optimization, reduced cost by 30%
- Completed new dashboard UI with dark mode support
- Fixed API rate limiting with token bucket algorithm
- Testnet downtime from yesterday: resolved

What we're stuck on
- CRITICAL: Deepseek API accuracy is lower than expected.
  Impact: AI answers are wrong on 1 in 5 test questions, Milestone moves
  from Sep 20 to Sep 22.
- MEDIUM: Dark mode specs from Jon still pending (day 3).
  Impact: Cannot finalize the settings screen.

Options
- Deepseek
  A. Wait for Deepseek to improve their model. No date from Deepseek.
  B. Add a validation step and run parallel QA. 2 extra days.
  C. Switch to OpenAI for this feature. 1 day of work, +$200/month.
- Dark mode
  A. Wait for Jon's specs before building the settings screen.
  B. Build light mode first, add dark mode when specs arrive.

What we chose and why
- Deepseek: B. Keeps the model the client chose, no extra monthly cost.
  Dennis adds validation today, Kate runs parallel QA from Sep 18.
- Dark mode: B. The settings screen is not blocked. Need Jon's specs
  by Sep 20 to keep dark mode in this Milestone.
```

Câu 1 mở bằng một dòng tiến độ, nói thẳng là đang chậm 2 ngày. Mỗi việc đã xong là thứ khách mở sản phẩm ra là thấy. Vấn đề có severity, có ảnh hưởng bằng con số, có ngày thứ mấy. Mỗi vấn đề có các giải pháp kèm cái giá. Lý do chọn nằm ngay cạnh quyết định, kèm tên người làm, ngày, và việc khách cần làm trước ngày nào.

---

## 2. Production Metrics của dự án đã launch

### Mẫu chưa tốt

```
Production Metrics
- Có nhiều người dùng mới
- Doanh thu tốt
- Có vài bugs cần fix
```

Không có số, không nguồn data, không severity. "Doanh thu tốt" không nói gì cả — tốt so với cái gì?

### Mẫu tốt

```
Production Metrics (snapshot Sep 17)
- Users: 1,250 active / 5,000 total / +45 new today (source: Firebase)
- Business: $12,500 revenue / 320 transactions (source: Stripe)
- Bugs: 12 open (2 critical, 4 high) / 85 fixed / 97 total since launch
```

Mỗi dòng có số và nguồn. Bug tính từ ngày launch, chia theo severity. Nếu active users hôm nay giảm hơn 20%, con số đó cũng được đưa lên câu 2 như một vấn đề cần giải pháp.

---

## 📋 Template trống (copy để dùng)

```
[Project] Daily Report - [Date]

What we completed
[X]% of [Milestone] done, [ahead / behind / on] plan
- [Việc cụ thể khách thấy được]
- [Việc cụ thể khách thấy được]
- [Vấn đề hôm trước đã giải quyết (nếu có)]

Production Metrics (snapshot [Date])   ← bỏ nếu chưa launch
- Users: [active] active / [total] total / +[new] new today (source: [tool])
- Business: $[revenue] revenue / [transactions] transactions (source: [tool])
- Bugs: [open] open ([critical] critical) / [fixed] fixed / [total] total since launch

What we're stuck on
- [CRITICAL/HIGH/MEDIUM/LOW]: [Vấn đề]
  Impact: [Ảnh hưởng tới người dùng / ngày bàn giao]
- [Nếu chờ khách hàng]: Waiting for [Tên] to provide [gì] (day [N])

Options
- A. [Giải pháp] — [thời gian / chi phí / ảnh hưởng]
- B. [Giải pháp] — [thời gian / chi phí / ảnh hưởng]

What we chose and why
- [A/B]. [Lý do]. [Người làm] [việc gì], done by [Date].
- [Nếu cần khách duyệt]: Need [Tên] to confirm by [Date].
```

---

## Nguyên tắc chung

| Chưa tốt | Tốt |
|-----------|-----|
| "Worked on frontend" | "Completed dashboard UI with dark mode support" |
| "Project is progressing well" | "85% of AI Assistant Milestone done, 2 days behind plan" |
| "Có vấn đề performance" | "CRITICAL: Response time > 3s on checkout. Impact: users drop at payment" |
| "Chưa có risk" | Nghĩ kỹ lại — mở board xem dòng bôi đỏ, task `Pending` |
| Chỉ có một giải pháp | Ít nhất 2 giải pháp, mỗi cái kèm cái giá |
| "We will handle it" | "B. Dennis adds validation today, Kate runs QA from Sep 18" |
| Bỏ qua vấn đề hôm trước | Nêu lại nếu chưa giải quyết, ghi ngày thứ mấy |
| "Users tăng", "Doanh thu tốt" | "1,250 active / 5,000 total / +45 new (Firebase)" |

---

## Liên kết

- [Quy trình Daily Report](daily-report-process.md)
- [Cẩm nang Daily Report](daily-report-handbook.md)
