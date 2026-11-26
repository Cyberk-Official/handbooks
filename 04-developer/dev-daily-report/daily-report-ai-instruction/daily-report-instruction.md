---
type: delivery
tags: [daily-report, ai-instruction]
created-date: 2026-06-29
updated-date: 2026-11-26
author: anderson
status: Nháp
---

# **Cyberk Daily Report Instruction**

Daily Report nằm ở đầu tab sprint trong file Management. Đầu vào cho AI là board đã cập nhật (các cột Milestones, Tasks, Assignee, Status, Progress, Estimate (h), Expected done date, Notes), ghi chú buổi Internal Daily, và Daily Report hôm trước.

Các quy tắc cần tuân thủ:

- Trả lời đúng 4 câu hỏi, đúng thứ tự: What we completed → What we're stuck on → Options → What we chose and why.
- Liệt kê cụ thể các việc đã làm, không thừa, không thiếu. Lấy từ task chuyển sang `Done` kể từ report hôm trước.
- Nếu các vấn đề của ngày hôm trước đã được giải quyết, viết rõ ở câu 1. Nếu chưa giải quyết thì tiếp tục viết ở câu 2, ghi ngày thứ mấy, không được bỏ qua.
- Nếu vấn đề phụ thuộc vào khách hàng, viết rõ khách cần làm gì. Ví dụ: đang chờ Jon cung cấp tài khoản Google dev account.
- Mỗi vấn đề có ít nhất 2 giải pháp, mỗi giải pháp kèm cái giá (thời gian, chi phí, ảnh hưởng).
- Giải pháp đã chọn có lý do, người làm và ngày xong.
- Không viết mục Next Steps: kế hoạch đã nằm ở cột Expected done date trên board.
- Viết bằng tiếng Anh, ngắn gọn, bullet-point.

*Dưới đây là hướng dẫn cho AI của các bạn:*

### **1\. What we completed — Team đã làm xong những gì?**

**Explain:** Mở đầu bằng 1 dòng tiến độ chung của Milestone, sau đó liệt kê công việc đã hoàn thành kể từ báo cáo trước.
**Instruction:**

* Dòng tiến độ có phần trăm Milestone, nhanh/chậm so với kế hoạch, hoặc ngày dự kiến hoàn thành.
* Mỗi dòng là một việc khách thấy được trên sản phẩm, đúng tên task trên board.
* Nếu hôm trước có một vấn đề được giải quyết, liệt kê ở đây.
* Ví dụ tốt: "80% of Lighter Platform Integration done, on schedule for Nov 20", "Completed JWT authentication API, login/logout working on staging", "Deepseek API pending from yesterday: resolved"
* Ví dụ tệ: "Project is progressing well", "worked on frontend", "finished coding feature", "fixed bugs"
* Ví dụ rất tệ: "use generic descriptions like "worked on frontend""

---

### **📊 Production Metrics (Nếu dự án đã Launch)**

**Explain:** Khi dự án đã launch và có người dùng thật, thêm các chỉ số vận hành ngay sau câu 1.

**Instruction:**
- Số liệu do **Leader/PO cung cấp**.
- Nếu PO chưa cung cấp, ghi: `⚠️ Awaiting data from PO/Leader`
- Metrics là **snapshot cuối ngày hôm trước**, không cần real-time.
- Nếu có **biến động bất thường** (users giảm >20%, revenue drop, critical bugs tăng), đưa vào câu 2 như một vấn đề.

#### **👥 Users (Active / Total / New)**

- Ghi rõ nguồn data (Firebase, Mixpanel, v.v.)
- Format: `Active Users / Total Users / New Users Today`

*Ví dụ tốt:* `Users: 1,250 active / 5,000 total / +45 new today (source: Firebase)`

*Ví dụ tệ:* `"Có nhiều người dùng mới"`, `"Users tăng"`

#### **💰 Business KPIs (Revenue / Transactions / Profit)**

Tùy dự án chọn metrics phù hợp: Revenue, Transactions, Profit margin, hoặc KPI quan trọng khác.

- Ghi rõ nguồn data (Stripe, internal dashboard, v.v.)
- Nếu không có data, ghi: `N/A — awaiting PO input`

*Ví dụ tốt:* `Business: $12,500 revenue / 320 transactions (source: Stripe)`

*Ví dụ tệ:* `"Doanh thu tốt"`, `"Có giao dịch mới"`

#### **🐛 Production Bugs (Open / Fixed / Total)**

Số liệu bug **tích lũy từ ngày launch** (không reset theo sprint). Lấy từ GitHub Issues.

- Phân theo severity: Critical / High / Medium / Low
- Critical bugs chưa fix → đưa vào câu 2

*Ví dụ tốt:* `Bugs: 12 open (2 critical, 4 high) / 85 fixed / 97 total since launch`

*Ví dụ tệ:* `"Có vài bugs cần fix"`, `"Đang fix bugs"`

---

### **2\. What we're stuck on — Đang gặp vấn đề gì?**

**Explain:** Báo cáo những vấn đề đang cản trở hoặc rủi ro tiềm tàng. Tìm trong board: dòng bôi đỏ (task `Doing` quá 2 ngày), task `Pending`, task sắp tới Expected done date mà Progress còn thấp.
**Instruction:**

* Mỗi vấn đề có severity: Critical, High, Medium, Low.
* Viết rõ vấn đề, nguyên nhân và ảnh hưởng tới người dùng hoặc ngày bàn giao.
* Nêu lại vấn đề của hôm trước nếu chưa giải quyết, ghi ngày thứ mấy.
* Nếu vấn đề phụ thuộc vào khách hàng, viết rõ khách cần làm gì.
* Ví dụ tốt: "CRITICAL: Deepseek API accuracy is lower than expected. Impact: Milestone moves from Sep 20 to Sep 22."
* Ví dụ không tốt: "Có một số vấn đề về performance", "Backend đang bị lỗi", "Chưa có risk gì đáng kể"

---

### **3\. Options — Có những giải pháp nào?**

**Explain:** Với mỗi vấn đề, liệt kê các cách giải quyết.
**Instruction:**

* Ít nhất 2 giải pháp cho mỗi vấn đề, đánh A, B, C.
* Mỗi giải pháp kèm cái giá: thời gian, chi phí, ảnh hưởng.
* "Chờ" cũng là một giải pháp, ghi kèm cái giá của việc chờ.
* Ví dụ tốt: "B. Add a validation step and run parallel QA. 2 extra days." "C. Switch to OpenAI. 1 day of work, +$200/month."
* Ví dụ không tốt: "Fix the bug", "Ask the client"

---

### **4\. What we chose and why — Chọn giải pháp nào, tại sao?**

**Explain:** Quyết định của team cho từng vấn đề.
**Instruction:**

* Ghi giải pháp đã chọn, lý do chọn, người làm, ngày xong.
* Nếu cần khách duyệt, ghi rõ khách cần trả lời trước ngày nào.
* Ví dụ tốt: "B. Keeps the model the client chose, no extra monthly cost. Dennis adds validation today, Kate runs parallel QA from Sep 18."
* Ví dụ không tốt: "We will handle it"

---

📌 **Note:**

* Báo cáo nên ngắn gọn, dễ đọc (bullet-point).
* **Mỗi vấn đề có giải pháp đi kèm**, không chỉ liệt kê vấn đề.
* **Giải pháp đã chọn luôn có ngày xong.**
