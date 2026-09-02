---
type: delivery
tags: [daily-report, ai-instruction]
created-date: 2026-06-29
updated-date: 2026-09-02
author: anderson
status: Nháp
---

# **Cyberk Daily Report Instruction** 

Các Quy tắc cần tuân thủ: 

\- Liệt kê cụ thể các việc đã làm, không thừa, không thiếu.   
\- Next-step cần có ETA cụ thể. ví dụ: tôi sẽ hoàn thành màn home-page vào ngày 20 tháng 9\.   
\- Nếu các risk của ngày hôm trước đã được giải quyết, cần viết rõ tại mục “**What I did**”, nếu chúng chưa được giải quyết thì phải tiếp tục viết trong mục risk, mà không được bỏ qua.   
\- Nếu risk/blocker này phụ thuộc vào khách hàng, cần viết rõ actions của khách hàng: Ví dụ: vấn đang chờ Jon cung cấp Tài khoản Google dev account   
\- Các blocker cần có solution: Đang gặp trục trặc với việc request OpenAI key từ Jon, Đang liên hệ để giải quyết vấn đề.   
\- Có cảnh báo nếu như các blocker từ buổi lần trước chưa được giải quyết: ví dụ: Không thể liên lạc được với Jon, nên không thể lấy được key. và đảm bảo nó được high-ligh   
   
*Dứoi đây là hướng dẫn cho AI của các bạn:* 

### **1\. Tổng Quan Dự Án** 

**Explain:** Là mục hiển thị **tổng quan tiến độ** đã hoàn thành của dự án, ngắn gọn trong 1 dòng.   
 **Instruction:** Viết ngắn gọn,   
 

* Phải có phần trăm trên tổng tiến độ.   
* Ngày hoàn thành dự án dự kiến, số ngày còn lại   
* Ví dụ tốt: **80% of work completed**, **3 days ahead of schedule,** expected completion date: **Sep 15, 20 working days remaining**  
* Ví dụ không tốt: Project is progressing well", "Work is on track"

👉 *Ví dụ:* **80% công việc** đã hoàn thành, **nhanh hơn 3 ngày** so với kế hoạch, Dự kiến ngày hoàn thành dự án: 20 September. 10 còn lại. 

---

### **📊 Production Metrics (Nếu dự án đã Launch)**

**Explain:** Khi dự án đã launch và có người dùng thật, mục Overview cần bổ sung các chỉ số vận hành thực tế bên cạnh tiến độ phát triển feature mới.

**Instruction:**
- Số liệu do **Leader/PM cung cấp**, dev copy vào report.
- Nếu PM chưa cung cấp, dev PHẢI ghi: `⚠️ Awaiting data from PM/Leader`
- Metrics là **snapshot cuối ngày hôm trước**, không cần real-time.
- Nếu có **biến động bất thường** (users giảm >20%, revenue drop, critical bugs tăng), PHẢI highlight bằng `⚠️ WARNING` và ghi thêm vào mục **Risks and Blockers**.

#### **👥 Users (Active / Total / New)**

Phản ánh tình trạng adoption và tăng trưởng người dùng.

- Ghi rõ nguồn data (Firebase, Mixpanel, v.v.)
- Format: `Active Users / Total Users / New Users Today`

*Ví dụ tốt:* `👥 Users: 1,250 active / 5,000 total / +45 new today (source: Firebase)`

*Ví dụ tệ:* `"Có nhiều người dùng mới"`, `"Users tăng"`

#### **💰 Business KPIs (Revenue / Transactions / Profit)**

Tùy dự án chọn metrics phù hợp: Revenue, Transactions, Profit margin, hoặc KPI quan trọng khác.

- Ghi rõ nguồn data (Stripe, internal dashboard, v.v.)
- Nếu không có data, ghi: `N/A — awaiting PM input`

*Ví dụ tốt:* `💰 Revenue: $12,500 / 320 transactions / Profit margin: 15% (source: Stripe Dashboard)`

*Ví dụ tệ:* `"Doanh thu tốt"`, `"Có giao dịch mới"`

#### **🐛 Production Bugs (Open / Fixed / Total)**

Số liệu bug **tích lũy từ ngày launch** (không reset theo sprint). Lấy từ GitHub Issues hoặc project board.

- Phân theo severity: Critical / High / Medium / Low
- PHẢI highlight nếu có **Critical bugs chưa fix**

*Ví dụ tốt:* `🐛 Bugs: 12 open (2 critical, 4 high) / 85 fixed / 97 total since launch`

*Ví dụ tệ:* `"Có vài bugs cần fix"`, `"Đang fix bugs"`

---

### **2\. Tôi đã làm những gì (What I did)**

**Explain:** Liệt kê công việc đã hoàn thành kể từ báo cáo trước.  
 **Instruction:** Viết ngắn gọn, có thể gắn kèm ID task/bug.

\- MUST list specific completed tasks with details

\- Nếu hôm trước có một vấn đề trong mục “risk” được giải quyết, hãy liệt kê chúng ở đây. 

*Ví dụ tốt: "Completed JWT authentication API, implemented login/logout functionality, The problem of deepseek API pending: resolved"*

*Ví dụ tệ: "worked on frontend", "finished coding feature", "fixed bugs"*

*Ví dụ rất tệ:  “use generic descriptions like "worked on frontend"*

---

### **3\. Next-step tôi sẽ làm (Next steps)**

**Explain:** Kế hoạch công việc tiếp theo, kèm **ngày dự kiến hoàn thành** (ETA).  
 **Instruction:** Ghi task cụ thể \+ deadline rõ ràng. Không dùng câu chung chung như “tiếp tục code”.  
 👉 *Ví dụ:*

* Implement reward distribution module– **ETA: Aug 25**  
* Write unit tests for NFT minting contract – **ETA: Aug 27**

---

### **4\. Risk hoặc rủi ro (Blockers / Risks)**

**Explain:** Báo cáo những vấn đề đang cản trở hoặc rủi ro tiềm tàng.  
 **Instruction:** Ghi rõ nguyên nhân \+ cần hỗ trợ từ ai. Sau đó đề xuất giải pháp.

* MỖI vấn đề PHẢI có giải pháp hoặc action plan  
* Nêu lại các vấn đề   
* PHẢI có đánh giá về mức độ ảnh hưởng của vấn đề đến dự án, (Critical, High, Medium, Low)  
* PHẢI nếu lại vấn đề của hôm trước nếu như chúng chưa được giải quyết   
* PHẢI viết rõ ràng vấn đề, và hậu quả, nguyên nhân  
* \- Nếu risk/blocker này phụ thuộc vào khách hàng, cần viết rõ actions của khách hàng: Ví dụ: vấn đang chờ Jon cung cấp Tài khoản Google dev account


       \- VÍ DỤ TỐT: "**CRITICAL**: Deepseek có vấn đề về độ chính xác, và cần test kỹ hơn dự kiến dẫn tới **chậm tiến độ 2 ngày**. Action plan: Tăng cường QA resource và parallel testing để bù tiến độ"

       \- VÍ DỤ KHÔNG TỐT: "Có một số vấn đề về performance", "Backend đang bị lỗi", "Chưa có risk gì đáng kể"\`

---

📌 **Note cho dev:**

* Báo cáo nên ngắn gọn, dễ đọc (bullet-point).

* **Next-step luôn phải có ETA.**

* **Blocker phải có giải pháp đi kèm**, không chỉ liệt kê vấn đề.
