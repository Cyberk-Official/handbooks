---
type: delivery
tags: [daily-report, example, template]
created: 2026-08-25
updated: 2026-08-25
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
Expected completion: Sep 15, 15 working days remaining

## 2. What I did
- Deployed staking contract with gas optimization, reduced cost by 30%
- Completed new dashboard UI with dark mode support
- Fixed API rate limiting with token bucket algorithm
- Resolved testnet downtime issue from yesterday

## 3. Next Steps
- Smart contract development and audit - ETA: Aug 24
- Portfolio analytics dashboard integration - ETA: Aug 23
- Vesting test plan and automation - ETA: Aug 22

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

---

## Liên kết

- [Quy trình Daily Report](daily-report-process.md)
- [Cẩm nang Daily Report](daily-report-handbook.md)
