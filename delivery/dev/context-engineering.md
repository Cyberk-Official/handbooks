---
type: dev
tags: [agentic, cyberk-way]
alias: [context-engineering]
---

# Context-Engineering: Quản lý ngữ cảnh

Mục đích của tài liệu này là làm rõ khái niệm **Context-Engineering**. Nếu bạn đang làm việc chung với AI, đây là kỹ năng đầu tiên bạn cần nắm chắc.

---

## 1. Tại sao AI cần Context?

Để AI viết code đúng, nó cần hiểu toàn bộ dự án. Tuy nhiên, mọi phiên làm việc với AI đều bắt đầu với bộ nhớ bằng 0.

Nhiều người nghĩ lập trình với AI là nhắn một đoạn prompt ngắn và chờ copy code. Trò này chỉ dùng được khi bạn giải một bài toán thuật toán nhỏ. Khi làm một sản phẩm thực tế, máy móc cần biết cấu trúc database, logic nghiệp vụ, các file đang chia thư mục thế nào và dự án đang dùng thư viện gì.

**Context-Engineering** là bước bạn hệ thống hóa các thông tin này thành văn bản để nạp cho AI trước khi yêu cầu nó chạy. Cung cấp ngữ cảnh chuẩn, AI sinh ra code cũng chuẩn. Để AI phải tự đoán, nó sẽ sinh ra bug.

## 2. Nguyên tắc vàng: Đủ dùng, không dư thừa

Chúng ta quản lý tài liệu theo nguyên tắc: **"Không thừa, không thiếu"**.

- **Thiếu ngữ cảnh:** AI bắt đầu tự bịa ra logic (hallucination). Hậu quả là code chạy lỗi sai bét, bạn mất hàng giờ mò mẫm tự sửa lại theo cách thủ công.
- **Thừa ngữ cảnh:** Bạn bắt AI đọc quá nhiều file không liên quan (nhét nguyên cả document của công ty vào một cái task nhỏ). AI bị nhiễu, làm sai yêu cầu xuất phát.
- **Đúng ngữ cảnh:** Bạn chỉ chia sẻ đúng lượng tài liệu cần thiết. AI biết chính xác mục tiêu (Why) và giới hạn (Constraints).

## 3. Cách chia lớp ngữ cảnh để quản lý

Để máy móc làm việc tập trung, chúng ta chia Context thành 4 nhóm. Khi giao việc cho AI, tùy yêu cầu mà bạn quyết định đưa loại tài liệu nào vào.

### A. Context Sản phẩm (Product Context)

Tài liệu giải thích lý do làm tính năng này. Dùng để AI hiểu hướng đi.

- **PRD (Product Requirements Document):** Mục tiêu của tính năng, vấn đề kinh doanh cần giải quyết.
- **User Stories:** Người dùng sẽ bấm vào nút nào, mong đợi kết quả gì.

### B. Context Kỹ thuật (Technical Context)

Bản vẽ để AI dựa vào đó gõ code.

- **SRS (Software Requirements Specification):** Ghi rõ logic tính toán, file schema database, và cấu trúc API.
- **ADR (Architecture Decision Records):** Ghi chú lại lý do dùng một công nghệ (VD: tại sao lại dùng Redis thay vì trực tiếp gọi DB cho chức năng này).

### C. Context Quy tắc (Rules Context)

Dùng để bắt AI tuân thủ luật lệ, không làm càng.

- **Skill files / Cursor Rules:** Các luật coding của team. Ví dụ: luôn thụt lề 2 spaces, bắt buộc phải viết unit test trước khi đổi logic, không tự ý sửa các file cấu hình.

### D. Context Lịch sử (Historical Context)

- **Changelogs / Tech Debt:** Những bản fix cũ. AI cần biết hệ thống đang vướng nợ kỹ thuật ở đâu để không vô ý xóa đi đoạn code sửa lỗi trước đó.

## 4. Tài liệu phải luôn khớp với Code

Bỏ viết Docs sau khi dự án Release là sai lầm lặp lại nhiều nhất của các kỹ sư. Quy tắc của chúng ta là: **Tài liệu phải luôn khớp với trạng thái Code hiện tại.**

Khi có thay đổi logic từ khách hàng, bạn tuyệt đối không được tự ý sửa code bằng tay lắt nhắt. Cách xử lý chuẩn là:

1. Mở file đặc tả (PRD/SRS) và viết lại logic mới vào văn bản.
2. Bấm nạp file vừa sửa cho AI và yêu cầu nó đập đi code lại dựa trên ngữ cảnh vừa thay đổi.

Cách làm này đảm bảo 100% logic của sản phẩm đều nằm trên mặt chữ. Nếu ngày mai dự án có người mới vào, hoặc bạn xin nghỉ phép, người tiếp theo chỉ cần mở file Docs là nắm được nguyên dự án và tiếp tục nhờ AI làm việc. Không ai phải hao tâm tổn trí ngồi đọc hiểu từng dòng code nữa.

Tóm lại, kỹ năng Context-Engineering giúp chúng ta quản lý dự án bằng văn bản, giảm phụ thuộc vào trí nhớ cá nhân (Bus factor) và làm cho hệ thống AI hoạt động đều đặn, ít hỏng hóc.
