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

👉 *Ví dụ:* **80% công việc** đã hoàn thành, **nhanh hơn 3 ngày** so với kế hoạch, Dự kiến ngày hoàn thành dự án: 20 Steptember. 10 còn lại. 

###  

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

