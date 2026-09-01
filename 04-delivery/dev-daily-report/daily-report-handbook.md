---
type: delivery
tags: [daily-report, handbook]
created: 2026-08-25
updated: 2026-09-01
author:
status: Nháp
---

# Viết Daily Report — Cẩm nang cho Dev

**Người chịu trách nhiệm:** [Tech Lead / PM]
**Trạng thái:** Nháp

Daily report không phải để "báo cáo sếp". Nó là công cụ để **bạn tự tổ chức công việc** và để PM **biết đang ở đâu mà report cho khách hàng**. Viết tốt = ít bị hỏi lại. Viết tồi = khách hàng lo lắng, PM hỏi liên tục.

Report gồm **4 mục cố định** — luôn giữ đúng thứ tự. Nếu dự án đã launch, thêm mục **📊 Production Metrics** ngay sau Progress:

```
1. Project Progress
📊 Production Metrics (nếu đã launch)
2. What I did
3. Next Steps
4. Risks and Blockers
```

---

## 1. Project Progress — Tổng quan tiến độ trong 1 dòng

Mục này hiển thị **tổng quan tiến độ** đã hoàn thành, ngắn gọn trong 1–2 dòng. PM đọc mục này đầu tiên. Họ cần biết ngay: xong bao nhiêu %, có đúng tiến độ không, bao giờ xong.

**Phải có:**
- Phần trăm trên tổng tiến độ
- So sánh với kế hoạch (nhanh/chậm bao nhiêu ngày)
- Ngày hoàn thành dự kiến
- Số ngày làm việc còn lại

**✅ Cách tốt:**

```
## 1. Project Progress
80% of work completed, 3 days ahead of schedule
Expected completion date: Sep 20, 10 working days remaining
```

**❌ Cách tồi:**

```
## 1. Project Progress
Project is progressing well
Work is on track
```

Tại sao tồi: "Well" nghĩa là gì? "On track" so với cái gì? Không %, không ngày, không số — PM không có gì để report cho khách.

---

## 📊 Production Metrics — Chỉ số vận hành khi dự án đã Launch

> **Khi nào áp dụng:** Dự án đã launch, có người dùng thật, có doanh thu hoặc giao dịch.

Sau khi launch, PM/khách hàng không chỉ quan tâm "dev xong bao nhiêu %" — họ cần biết sản phẩm **đang sống như thế nào**. Mục này nằm ngay sau Project Progress.

**Số liệu do Leader/PM cung cấp** — dev chỉ copy vào report. Nếu chưa có, ghi: `⚠️ Awaiting data from PM/Leader`.

**3 nhóm metrics bắt buộc:**

| Nhóm | Metrics | Nguồn |
|------|---------|-------|
| 👥 **Users** | Active Users / Total Users / New Users Today | Firebase, Mixpanel, v.v. |
| 💰 **Business** | Revenue / Transactions / Profit (hoặc KPI quan trọng khác) | Stripe, internal dashboard |
| 🐛 **Bugs** | Open (by severity) / Fixed / Total since launch | GitHub Issues, project board |

**✅ Cách tốt:**

```
## 📊 Production Metrics (Post-Launch)
> Snapshot ngày 17 Sep — Số liệu do PM cung cấp

- 👥 Users: 1,250 active / 5,000 total / +45 new today (source: Firebase)
- 💰 Business: $12,500 revenue / 320 transactions (source: Stripe)
- 🐛 Bugs: 12 open (2 critical, 4 high) / 85 fixed / 97 total since launch
```

**❌ Cách tồi:**

```
- Có nhiều người dùng mới
- Doanh thu tốt
- Có vài bugs cần fix
```

Tại sao tồi: Không có số, không nguồn, không severity. "Doanh thu tốt" không nói gì cả.

**Quy tắc cảnh báo:** Nếu có biến động bất thường (users giảm >20%, revenue drop, critical bugs tăng đột biến) — PHẢI highlight `⚠️ WARNING` và ghi thêm vào mục **4. Risks and Blockers**.

---

## 2. What I did — Liệt kê cụ thể từng task đã hoàn thành

Liệt kê công việc đã hoàn thành kể từ báo cáo trước. Viết ngắn gọn, gắn kèm ID task/bug nếu có.

**Quy tắc:**
- PHẢI liệt kê task cụ thể kèm chi tiết
- Nếu hôm trước có risk/blocker đã được giải quyết → **liệt kê ở đây**

**✅ Cách tốt:**

```
## 2. What I did
- Completed JWT authentication API, implemented login/logout functionality
- Deployed staking contract with gas optimization, reduced cost by 30%
- Completed new dashboard UI with dark mode support
- The problem of deepseek API pending: resolved ← (risk hôm trước)
```

**❌ Cách tồi:**

```
## 2. What I did
- Worked on frontend
- Finished coding feature
- Fixed bugs
```

Tại sao tồi: "Worked on frontend" — frontend có 50 component, làm cái nào? "Fixed bugs" — bug nào? Không ai truy vết được.

**❌ Rất tồi:**

```
## 2. What I did
- Use generic descriptions like "worked on frontend"
```

Tại sao rất tồi: Copy nguyên instruction vào report thay vì viết nội dung thật. Đây là lỗi thường gặp khi dùng AI viết report mà không kiểm tra.

---

## 3. Next Steps — Kế hoạch cụ thể + ETA cho từng task

Kế hoạch công việc tiếp theo, kèm **ngày dự kiến hoàn thành (ETA)**. Đây là **cam kết** cho ngày mai. Không có ETA = không có cam kết.

**Quy tắc:**
- Ghi task cụ thể + deadline rõ ràng
- KHÔNG dùng câu chung chung như "tiếp tục code"

**✅ Cách tốt:**

```
## 3. Next Steps
- Implement reward distribution module – ETA: Aug 25
- Write unit tests for NFT minting contract – ETA: Aug 27
- Portfolio analytics dashboard integration – ETA: Aug 23
```

**❌ Cách tồi:**

```
## 3. Next Steps
- Continue coding
- Will work on backend
- Keep testing
```

Tại sao tồi: "Continue coding" không phải kế hoạch — đó là mô tả trạng thái. Giống nói "Ngày mai tôi sẽ thở". Đúng, nhưng vô nghĩa.

---

## 4. Risks and Blockers — Phần quan trọng nhất

Báo cáo những vấn đề đang cản trở hoặc rủi ro tiềm tàng. Nhiều dev viết "Chưa có risk gì đáng kể" — gần như luôn sai. Nghĩ kỹ hơn.

**Quy tắc (cứng):**
- MỖI vấn đề PHẢI có **severity**: Critical / High / Medium / Low
- MỖI vấn đề PHẢI có **đánh giá mức ảnh hưởng** đến dự án
- MỖI vấn đề PHẢI có **action plan / giải pháp**
- Risk hôm trước **chưa resolved** → PHẢI nêu lại + highlight
- Risk **phụ thuộc khách hàng** → ghi rõ action cần từ khách: VD "Đang chờ Jon cung cấp Google Dev account"

**✅ Cách tốt:**

```
## 4. Risks and Blockers
- CRITICAL: Deepseek API accuracy issue, needs more testing than expected
  → Impact: Delays AI feature by 2 days, pushing completion to Sep 22
  → Action: Increasing QA resource and parallel testing to recover timeline

- HIGH: Expected high network load during launch
  → Impact: Potential downtime if not addressed
  → Action: Setting up load balancing with DevOps, scheduled for Aug 26

- MEDIUM: Pending dark mode specs from Jon (client)
  → Impact: Cannot finalize UI, workaround available
  → Action: Implementing light mode first, following up with Jon daily

- ⚠️ UNRESOLVED from yesterday: Cannot contact Jon for Google Dev account
  → Impact: Cannot deploy to Play Store
  → Action: PM escalating via email today
```

**❌ Cách tồi:**

```
## 4. Risks and Blockers
- Có một số vấn đề về performance
- Backend đang bị lỗi
- Chưa có risk gì đáng kể
```

Tại sao tồi: Không severity, không impact, không action plan. "Chưa có risk" = chưa nghĩ kỹ. "Có vấn đề performance" — nghiêm trọng cỡ nào? Ảnh hưởng gì? Đang làm gì để sửa?

> **Quy tắc vàng:** Risk biến mất khỏi report KHÔNG có nghĩa biến mất khỏi dự án. Nếu chưa resolved → nêu lại + highlight "UNRESOLVED from yesterday".

---

## Tóm lại

| Mục | Phải có | Tuyệt đối không |
|-----|---------|-----------------|
| **1. Progress** | %, so sánh kế hoạch, ngày dự kiến, số ngày còn lại | "Progressing well", "On track" |
| **📊 Metrics** *(post-launch)* | Users (active/total/new), Business KPIs, Bugs (open/fixed/total) + nguồn data | "Users tăng", "Doanh thu tốt" |
| **2. What I did** | Task cụ thể + chi tiết + risk cũ đã resolved | "Worked on X", "Fixed bugs" |
| **3. Next steps** | Task cụ thể + ETA mỗi task | "Continue coding", "Will work on Y" |
| **4. Risks** | Severity + impact + action plan + risk cũ chưa resolved | "Có vấn đề", "Chưa có risk" |

---

## Liên kết

- [Quy trình Daily Report](daily-report-process.md) — Flowchart, bảng bước, quy tắc cứng
- [Mẫu Daily Report](daily-report-example.md) — Template copy-paste + ví dụ tốt/tồi đầy đủ
