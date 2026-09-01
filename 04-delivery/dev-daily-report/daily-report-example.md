---
type: delivery
tags: [daily-report, example, template]
created: 2026-08-25
updated: 2026-09-01
author:
status: Nháp
---

# Mẫu Daily Report — Tốt vs Không Tốt

**Người chịu trách nhiệm:** [tên/vai trò]
**Cập nhật lần cuối:** [ngày]

> Quy tắc: Ngắn gọn, cụ thể, có số liệu. Next-step luôn có ETA. Blocker luôn có giải pháp.

---

## ✅ Mẫu TỐT

### Daily Report hoàn chỉnh

```markdown
# Cyberk Daily Report - [Date]

## 1. Project Progress
85% completed, 2 days ahead of schedule
Expected completion: Oct 15, 15 working days remaining

## 📊 Production Metrics (Post-Launch)
> Snapshot ngày 17 Sep — Số liệu do PM cung cấp

- 👥 Users: 1,250 active / 5,000 total / +45 new today (source: Firebase)
- 💰 Business: $12,500 revenue / 320 transactions (source: Stripe)
- 🐛 Bugs: 12 open (2 critical, 4 high) / 85 fixed / 97 total since launch

## 2. What I did
- Deployed staking contract with gas optimization, reduced cost by 30%
- Completed new dashboard UI with dark mode support
- Fixed API rate limiting with token bucket algorithm
- Resolved testnet downtime issue from yesterday

## 3. Next Steps
- Smart contract development and audit - ETA: Sep 24
- Portfolio analytics dashboard integration - ETA: Sep 23
- Vesting test plan and automation - ETA: Sep 22

## 4. Risks and Blockers
- CRITICAL: Gas optimization needed for vesting contract
  → Action: Implementing batch processing, external audit scheduled
- HIGH: Expected high network load
  → Action: Setting up load balancing with DevOps
- MEDIUM: Pending dark mode specs from Jon
  → Action: Implementing light mode first, following up daily
```

Tốt vì:
- Progress có %, có ngày dự kiến, có số ngày còn lại
- Production Metrics: có số cụ thể, có nguồn data, phân severity cho bugs
- What I did: cụ thể từng task, có chi tiết kỹ thuật
- Next steps: mỗi task có ETA rõ ràng
- Risks: phân loại severity + mỗi cái có action plan

---

## ❌ Mẫu KHÔNG TỐT

### 1. Project Progress tồi

```
Project is progressing well
Work is on track
```

Tồi vì: Không có %, không có ngày, không ai biết "well" nghĩa là gì.

### 📊 Production Metrics tồi

```
- Có nhiều người dùng mới
- Doanh thu tốt
- Có vài bugs cần fix
```

Tồi vì: Không có số, không nguồn data, không severity. "Doanh thu tốt" không nói gì cả — tốt so với cái gì?

### 2. What I did tồi

```
- Worked on frontend
- Finished coding feature
- Fixed bugs
```

Tồi vì: "Worked on frontend" — làm gì trên frontend? "Fixed bugs" — bug nào? Không truy vết được.

### 3. Next steps tồi

```
- Continue coding
- Will work on backend
```

Tồi vì: Không có ETA. "Continue coding" không phải kế hoạch — đó là mô tả trạng thái.

### 4. Risks tồi

```
- Có một số vấn đề về performance
- Backend đang bị lỗi
- Chưa có risk gì đáng kể
```

Tồi vì: Không severity, không action plan, không nguyên nhân. "Chưa có risk" thường là chưa nghĩ kỹ.

---

## 📋 Template trống (copy để dùng)

```markdown
# Cyberk Daily Report - [Date]

## 1. Project Progress
[X]% completed, [ahead/behind X days]
Expected completion: [Date], [X] working days remaining

## 📊 Production Metrics (Post-Launch)
> Snapshot ngày [Date] — Số liệu do PM cung cấp

- 👥 Users: [active] active / [total] total / +[new] new today (source: [tool])
- 💰 Business: $[revenue] revenue / [transactions] transactions (source: [tool])
- 🐛 Bugs: [open] open ([critical] critical) / [fixed] fixed / [total] total since launch

> ⚠️ Nếu dự án chưa launch → bỏ qua mục này

## 2. What I did
- [Task cụ thể + chi tiết]
- [Task cụ thể + chi tiết]
- [Risk đã resolved từ hôm trước (nếu có)]

## 3. Next Steps
- [Task] - ETA: [Date]
- [Task] - ETA: [Date]

## 4. Risks and Blockers
- [CRITICAL/HIGH/MEDIUM/LOW]: [Vấn đề + hậu quả]
  → Action: [Giải pháp / đang làm gì]
- [Nếu chờ khách hàng]: Đang chờ [Tên] cung cấp [gì]
- [Nếu metrics bất thường]: ⚠️ WARNING: [Mô tả biến động + impact]
```

---

## Nguyên tắc chung

| Không nên | Nên |
|-----------|-----|
| "Worked on frontend" | "Completed dashboard UI with dark mode support" |
| "Will continue coding" | "Implement reward module – ETA: Aug 25" |
| "Có vấn đề performance" | "CRITICAL: Response time > 3s, Action: profiling + cache" |
| "Chưa có risk" | Nghĩ kỹ lại — luôn có ít nhất 1 risk tiềm ẩn |
| Bỏ qua risk hôm trước | Nêu lại nếu chưa resolved, highlight nếu kéo dài |
| "Users tăng", "Doanh thu tốt" | "1,250 active / 5,000 total / +45 new (Firebase)" |

---

## Liên kết

- [Quy trình Daily Report](daily-report-process.md)
- [Cẩm nang Daily Report](daily-report-handbook.md)
