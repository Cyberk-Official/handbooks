# Handover Meeting — Instruction (Nội bộ)

> Tài liệu nội bộ dành cho team Cyberk.
> Mục đích: Hướng dẫn team hiểu **tại sao** và **cách** vận hành từng bước trong buổi bàn giao sản phẩm, để thực hiện đúng, đủ và chuyên nghiệp.

---

## Trước buổi họp — Thông báo hoàn thành & hẹn lịch

**Mục đích:** Thông báo chính thức cho khách hàng rằng dự án đã hoàn thành, tạo tâm lý tốt trước buổi họp và đặt kỳ vọng rõ ràng về nội dung sẽ diễn ra. Đây cũng là cơ hội để PM kiểm soát narrative — khách hàng biết trước agenda thì buổi họp sẽ mượt hơn, ít bị lạc đề hơn.

**Người thực hiện:** PM hoặc người đại diện team

Gửi tin nhắn trước buổi họp ít nhất **1 ngày làm việc**. Không gửi sát giờ.

**Mẫu tin nhắn:**

> Hi [Client Name],
>
> We have some exciting news — the team has just completed 100% of the project! Here's a quick summary of what's been done:
>
> - All features are fully built and working, including [list key features]
> - We've run a full QA round to make sure there are no major bugs affecting the user experience
> - The infrastructure is fully deployed and ready to go
>
> To wrap things up properly, we'd love to set up a Handover meeting & Final Demo session together. The plan for the session is:
>
> - Cyberk will demo the full product flow from end to end
> - We'll walk through the Handover documents together
> - And we can talk about next steps from there
>
> After the demo, the development phase will officially come to a close, and we'll shift into the maintenance phase. Here's how that works:
>
> - We'll have 2 weeks — through [end date] — to catch and fix any bugs that come up. All fixes during this period are free of charge.
> - The maintenance phase won't cover new features or changes to what's already been delivered.
>
> Really proud of what the team has built here, and we're looking forward to showing it to you. Let us know your availability for the Handover session!
>
> Best,
> [Your name] & the Cyberk team

---

## Phần 1 — Project Overview

**Người trình bày:** PM / Tech Lead

**Mục đích:** Kéo khách hàng về cùng một điểm xuất phát trước khi vào demo. Khách hàng thường không nhớ hết những gì đã thống nhất từ đầu dự án — việc nhắc lại goal và function list giúp họ đánh giá sản phẩm đúng theo cam kết ban đầu, tránh so sánh với những kỳ vọng phát sinh ngoài scope. Đây cũng là lúc team chứng minh rằng mình đã deliver đúng và đủ những gì đã hứa.

### Nội dung cần trình bày:

**1.1 Mục tiêu dự án (Project Goal)**

- Trình bày lại bài toán và mục tiêu kinh doanh mà dự án hướng tới
- Nguồn tham chiếu: file Planning từ buổi họp kickoff

**1.2 Function List**

- Trình bày danh sách đầy đủ các tính năng đã được cam kết từ đầu dự án
- Đối chiếu với kết quả thực tế: tính năng nào đã hoàn thành, có thay đổi gì so với ban đầu không
- Nguồn tham chiếu: file Planning / scope document

> Không bỏ qua phần này dù nghĩ là khách hàng đã biết. Việc nhắc lại tạo nền tảng để demo và tạo sự tin tưởng — khách hàng thấy mình làm đúng cam kết.

---

## Phần 2 — Final Demo

**Người trình bày:** Dev / Tech Lead

**Mục đích:** Cho khách hàng thấy tận mắt sản phẩm hoạt động thật sự — không phải qua slide, không phải qua mô tả. Đây là phần quan trọng nhất của buổi họp. Một buổi demo tốt sẽ tạo ra sự phấn khích, củng cố niềm tin và giảm thiểu tranh luận sau này về việc tính năng có hoạt động hay không.

### Cách thực hiện:

- Demo trên môi trường **Production** (không dùng local hoặc staging)
- Đi theo từng **flow người dùng thực tế**, không chỉ click qua màn hình
- Với mỗi tính năng: giới thiệu ngắn mục đích → demo → hỏi khách hàng có câu hỏi không

### Checklist trước khi demo:

- [ ] Tài khoản demo đã được chuẩn bị sẵn (đủ dữ liệu mẫu)
- [ ] Môi trường production đang hoạt động ổn định
- [ ] Màn hình chia sẻ rõ ràng, âm thanh ổn
- [ ] Đã chạy thử toàn bộ flow demo ít nhất 1 lần trước buổi họp

> Không để bug xảy ra lúc demo trực tiếp. Nếu có rủi ro, hãy chuẩn bị video backup.

---

## Phần 3 — Handover Document

**Người trình bày:** PM / Tech Lead

**Mục đích:** Trao cho khách hàng đủ kiến thức để tự vận hành hệ thống sau khi Cyberk không còn can thiệp hàng ngày. Phần này không chỉ là "giao file" — mà là đảm bảo khách hàng **thực sự hiểu** cách dùng. Nếu sau này họ gặp vấn đề và không biết làm gì, trải nghiệm sau dự án sẽ xấu dù sản phẩm tốt.

### Nội dung tài liệu Handover cần bao gồm:

- Hướng dẫn truy cập hệ thống (credentials, environments)
- Hướng dẫn vận hành các tính năng chính
- Thông tin hạ tầng và cách theo dõi hệ thống
- Quy trình xử lý khi có sự cố
- Thông tin liên hệ hỗ trợ

> Walk through từng mục trong tài liệu — không chỉ gửi file rồi thôi. Dừng lại ở mỗi mục và hỏi khách hàng có câu hỏi không trước khi chuyển sang mục tiếp theo.

---

## Phần 4 — Maintenance Policy

**Người trình bày:** PM

**Mục đích:** Thiết lập ranh giới rõ ràng giữa giai đoạn development và maintenance ngay tại buổi họp — khi khách hàng đang ở trạng thái tốt, thoải mái và đồng thuận. Việc clarify policy sớm sẽ tránh được hiểu nhầm, tranh chấp sau này về việc Cyberk có phải fix cái gì hay không, có phải làm thêm feature không. Đây là bảo vệ cho cả hai bên.

### Nội dung cần trình bày:

**Thời gian bảo trì miễn phí:**
- Bắt đầu từ ngày ký biên bản bàn giao
- Kết thúc vào [ngày cụ thể]
- Trong giai đoạn này: Cyberk fix bug và cập nhật miễn phí

**Phạm vi bảo trì:**
- Bao gồm: Sửa lỗi kỹ thuật, bug ảnh hưởng đến trải nghiệm người dùng
- Không bao gồm: Phát triển tính năng mới, thay đổi các tính năng đã hoàn thành

**Sau giai đoạn bảo trì:**
- Các yêu cầu mới sẽ được estimate và thực hiện theo hợp đồng mới

> Trình bày nhẹ nhàng, không cứng nhắc. Mục tiêu là để khách hàng hiểu, không phải để từ chối. Nếu có câu hỏi hoặc phản ứng, xử lý tại đây — không để sau.

---

## Phần 5 — Open Talk / Next Move

**Người điều phối:** PM

**Mục đích:** Tạo không gian để khách hàng nói ra những gì còn băn khoăn, đồng thời mở ra cơ hội thảo luận về hướng phát triển tiếp theo. Đây là phần quan trọng cho relationship — khách hàng được lắng nghe, team biết được kỳ vọng tiếp theo, và cả hai bên kết thúc buổi họp trong trạng thái tích cực.

### Gợi ý câu hỏi để mở đầu:

- "Is there anything you'd like us to revisit or explain further?"
- "Do you have any feedback from the QA session on your side?"
- "What are you thinking about next for the product?"

---

## Kết thúc buổi họp

- Xác nhận biên bản bàn giao (nếu có)
- Gửi lại toàn bộ tài liệu Handover qua email hoặc kênh liên lạc chính thức
- Ghi lại các action items phát sinh từ Open Talk (nếu có)

---

*Tài liệu này thuộc bộ Project Management — Cyberk.*
*Cập nhật lần cuối: 2026-06-29*
