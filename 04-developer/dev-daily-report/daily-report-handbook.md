---
type: delivery
tags: [daily-report, handbook]
created: 2026-08-25
updated: 2026-11-26
author: anderson
status: Nháp
---

# Viết Daily Report — Cẩm nang cho PO

**Người chịu trách nhiệm:** PO / Product Owner
**Trạng thái:** Nháp

Daily report không phải để "báo cáo sếp". Nó là công cụ để PO **tổng hợp tiến độ từ board** và **report cho khách hàng**. Viết tốt = khách yên tâm. Viết tồi = khách hàng lo lắng, hỏi liên tục.

Daily Report nằm ở đầu tab sprint, trả lời **4 câu hỏi cố định** — luôn giữ đúng thứ tự. Nếu dự án đã launch, thêm **📊 Production Metrics** ngay sau câu 1:

```
1. Team đã làm xong những gì?
📊 Production Metrics (nếu đã launch)
2. Đang gặp vấn đề gì?
3. Có những giải pháp nào?
4. Chọn giải pháp nào, tại sao?
```

Câu 1 cho khách thấy tiến độ. Ba câu sau cho khách thấy team đang suy nghĩ thế nào. Khách đọc được vấn đề cùng các phương án và lý do chọn, thì khi cần quyết, khách quyết được ngay trong ngày thay vì phải hẹn một buổi họp.

---

## 1. Team đã làm xong những gì? — Liệt kê cụ thể từng việc

Liệt kê công việc đã hoàn thành kể từ báo cáo trước. Mỗi dòng là một việc khách mở sản phẩm ra là thấy được. Mở đầu bằng **một dòng tiến độ chung**: xong bao nhiêu %, nhanh hay chậm so với kế hoạch, ngày dự kiến hoàn thành Milestone.

**Quy tắc:**
- Liệt kê việc cụ thể kèm chi tiết, đúng tên task trên board
- Nếu hôm trước có vấn đề đã được giải quyết → **liệt kê ở đây**

**Cách tồi:**

```
What we completed
- Worked on frontend
- Finished coding feature
- Fixed bugs
Project is progressing well
```

Tại sao tồi: "Worked on frontend" — frontend có 50 component, làm cái nào? "Fixed bugs" — bug nào? "Progressing well" so với cái gì? Không ai truy vết được, khách đọc xong vẫn phải nhắn hỏi PO.

**Rất tồi:**

```
What we completed
- Use generic descriptions like "worked on frontend"
```

Tại sao rất tồi: Copy nguyên instruction vào report thay vì viết nội dung thật. Đây là lỗi thường gặp khi dùng AI viết report mà không kiểm tra.

**Cách tốt:**

```
What we completed
80% of Lighter Platform Integration done, on schedule for Nov 20
- Completed JWT authentication API, login/logout working on staging
- Deployed staking contract with gas optimization, reduced cost by 30%
- Completed new dashboard UI with dark mode support
- Deepseek API pending from yesterday: resolved
```

---

## 📊 Production Metrics — Chỉ số vận hành khi dự án đã Launch

> **Khi nào áp dụng:** Dự án đã launch, có người dùng thật, có doanh thu hoặc giao dịch.

Sau khi launch, khách hàng không chỉ quan tâm "dev xong bao nhiêu %" — họ cần biết sản phẩm **đang sống như thế nào**. Mục này nằm ngay sau câu 1.

**Số liệu do Leader/PO cung cấp.** Nếu chưa có, ghi: `⚠️ Awaiting data from PO/Leader`.

**3 nhóm metrics bắt buộc:**

| Nhóm | Metrics | Nguồn |
|------|---------|-------|
| 👥 **Users** | Active Users / Total Users / New Users Today | Firebase, Mixpanel, v.v. |
| 💰 **Business** | Revenue / Transactions / Profit (hoặc KPI quan trọng khác) | Stripe, internal dashboard |
| 🐛 **Bugs** | Open (by severity) / Fixed / Total since launch | GitHub Issues |

**Cách tồi:**

```
- Có nhiều người dùng mới
- Doanh thu tốt
- Có vài bugs cần fix
```

Tại sao tồi: Không có số, không nguồn, không severity. "Doanh thu tốt" không nói gì cả.

**Cách tốt:**

```
Production Metrics (snapshot Sep 17)
- Users: 1,250 active / 5,000 total / +45 new today (source: Firebase)
- Business: $12,500 revenue / 320 transactions (source: Stripe)
- Bugs: 12 open (2 critical, 4 high) / 85 fixed / 97 total since launch
```

**Quy tắc cảnh báo:** Nếu có biến động bất thường (users giảm >20%, revenue drop, critical bugs tăng đột biến) — đó là một vấn đề, đưa vào **câu 2** và tìm giải pháp như mọi vấn đề khác.

---

## 2. Đang gặp vấn đề gì? — Phần quan trọng nhất

Báo cáo những vấn đề đang cản trở hoặc rủi ro tiềm tàng. Nhiều người viết "Chưa có risk gì đáng kể" — gần như luôn sai. Nghĩ kỹ hơn: mở board ra, nhìn các dòng bôi đỏ, các task `Pending`, các task sắp tới Expected done date.

Viết vấn đề thật, kể cả khi đó là tin xấu. Mục vấn đề để trống cả tuần vì sợ khách lo, rồi đến ngày bàn giao Milestone trễ 3 ngày và khách nghe tin lần đầu, thì mất niềm tin rất khó lấy lại. Khách chấp nhận được một vấn đề khi biết sớm.

**Quy tắc:**
- Mỗi vấn đề có **severity**: Critical / High / Medium / Low
- Mỗi vấn đề có **mức ảnh hưởng** đến dự án và người dùng
- Vấn đề hôm trước **chưa giải quyết** → nêu lại, ghi đã kéo dài bao nhiêu ngày
- Vấn đề **phụ thuộc khách hàng** → ghi rõ cần khách làm gì: VD "Đang chờ Jon cung cấp Google Dev account"

**Cách tồi:**

```
What we're stuck on
- Có một số vấn đề về performance
- Backend đang bị lỗi
- Chưa có risk gì đáng kể
```

Tại sao tồi: Không severity, không impact. "Chưa có risk" = chưa nghĩ kỹ. "Có vấn đề performance" — nghiêm trọng cỡ nào? Ảnh hưởng gì?

**Cách tốt:**

```
What we're stuck on
- CRITICAL: Deepseek API accuracy is lower than expected, needs more testing.
  Impact: AI feature delayed 2 days, Milestone pushed to Sep 22.
- MEDIUM: Dark mode specs from Jon still pending (day 3).
  Impact: Cannot finalize UI.
```

> **Quy tắc vàng:** Risk biến mất khỏi report KHÔNG có nghĩa biến mất khỏi dự án. Nếu chưa giải quyết → nêu lại, ghi rõ ngày thứ mấy.

---

## 3. Có những giải pháp nào? — Cho khách thấy team đã cân nhắc

Với mỗi vấn đề, liệt kê **ít nhất 2 giải pháp**, mỗi giải pháp kèm **cái giá** của nó: mất bao lâu, tốn gì, ảnh hưởng gì tới người dùng. Một giải pháp duy nhất thì khách không biết team có nghĩ tới cách khác không. Các giải pháp không kèm cái giá thì khách không tự đánh giá được.

"Chờ" cũng là một giải pháp, và thường nên có trong danh sách, để khách thấy cái giá của việc không làm gì.

**Cách tồi:**

```
Options
- Fix the bug
- Ask the client
```

Tại sao tồi: "Fix the bug" là mục tiêu, không phải giải pháp. Không cái nào có thời gian hay cái giá, khách không có gì để so.

**Cách tốt:**

```
Options
- A. Wait for Deepseek to fix their model. No date from Deepseek.
- B. Add a validation step and run parallel QA. 2 extra days, no scope change.
- C. Switch to OpenAI for this feature. 1 day of work, +$200/month API cost.
```

---

## 4. Chọn giải pháp nào, tại sao? — Quyết định có lý do

Ghi giải pháp team chọn, **lý do chọn**, **người làm** và **ngày xong**. Đây là cam kết cho những ngày tới. Không có ngày = không có cam kết.

Lý do nằm ngay cạnh quyết định, để khách đọc là hiểu tại sao không chọn cách khác. Nếu giải pháp cần khách duyệt (tốn thêm chi phí, đổi scope), ghi rõ team đề xuất cách nào và khách cần trả lời trước ngày nào.

**Cách tồi:**

```
What we chose and why
- We will handle it.
```

Tại sao tồi: Không biết chọn cách nào, ai làm, bao giờ xong. Giống nói "Ngày mai tôi sẽ thở". Đúng, nhưng vô nghĩa.

**Cách tốt:**

```
What we chose and why
- B. Keeps the Deepseek model the client asked for and fits the Sep 22 date.
  Dennis adds validation today, Kate runs parallel QA from tomorrow.
- Dark mode: we build light mode first. Need Jon's specs by Nov 21
  to keep the release date.
```

---

## Next steps đi đâu?

Daily Report không còn mục Next Steps riêng. Kế hoạch công việc tiếp theo nằm ngay trên board: mỗi task có **Expected done date**, và bản PDF gửi khách đã có bảng task ngay dưới Daily Report. Viết lại danh sách đó trong report chỉ làm report dài thêm, và dễ lệch với board.

Việc nào thay đổi kế hoạch vì một vấn đề, thì ghi ở câu 4 kèm ngày mới, rồi sửa Expected done date trên board cho khớp.

---

## Tóm lại

| Câu | Phải có | Tuyệt đối không |
|-----|---------|-----------------|
| **1. Đã làm xong** | Dòng tiến độ chung, việc cụ thể khách thấy được, vấn đề cũ đã giải quyết | "Worked on X", "Fixed bugs", "Progressing well" |
| **📊 Metrics** *(post-launch)* | Users (active/total/new), Business KPIs, Bugs (open/fixed/total) + nguồn data | "Users tăng", "Doanh thu tốt" |
| **2. Vấn đề** | Severity + impact + vấn đề cũ chưa giải quyết + việc cần khách làm | "Có vấn đề", "Chưa có risk" |
| **3. Giải pháp** | Ít nhất 2 giải pháp, mỗi cái có cái giá | Một giải pháp duy nhất, giải pháp không có thời gian |
| **4. Chọn & tại sao** | Giải pháp đã chọn + lý do + người làm + ngày xong | "We will handle it" |

---

## Liên kết

- [Quy trình Daily Report](daily-report-process.md) — Flowchart, bảng bước, quy tắc cứng
- [Mẫu Daily Report](daily-report-example.md) — Ví dụ chưa tốt / tốt, template trống
- [Internal Daily — Mẫu](../../05-product-owner/po-internal-daily/internal-daily-example.md) — Daily Report Koto và tin nhắn summary gửi kèm PDF
