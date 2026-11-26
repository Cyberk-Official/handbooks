---
type: delivery
tags: [handbook, milestone, estimate, board, google-sheet]
created-date: 2026-11-26
updated-date: 2026-11-26
author: anderson
status: Nháp
---

# Tạo Milestone — Cẩm nang cho PO

**Người chịu trách nhiệm:** PO dự án
**Cập nhật lần cuối:** 2026-11-26
**Trạng thái:** Nháp

Trang này dùng mỗi khi PO cần đưa một Milestone mới lên board: lúc dựng board từ Planning Report, hoặc giữa dự án khi khách chốt thêm một đợt việc. Nội dung gồm cách đặt tên, độ lớn của một Milestone, cách tách thành task và cách estimate cùng Dev.

---

## Milestone là gì, lớn cỡ nào?

Milestone là mốc bàn giao hoặc một đợt việc trong proposal: `Lighter Platform Integration`, `Monochrome Trading Competition Launch`, `Smart Contract Audit Report Cover`.

- Đủ nhỏ sao cho như là một tính năng, hoặc một cập nhật chỉnh sửa, đủ lớn để 1 người hoặc 1 team < 5 người làm việc dưới 1 tuần.
- Luôn có 1 và chỉ 1 người chịu trách nhiệm cho 1 Milestone tại 1 thời điểm.
- Có thêm Milestone có nghĩa là cần mở rộng effort, thay đổi scope. Khi cần có thêm Milestone hãy báo cáo ngay cho quản lý.
- Khi khách hàng có thêm Milestone có nghĩa là có cơ hội mở rộng hợp đồng, cần giúp khách hàng làm rõ, tư vấn, và báo cáo cho quản lý để đàm phán hợp đồng — xem [Feature Request](../po-feature-request/feature-request-process.md).

---

## Đặt tên Milestone thế nào?

Tên Milestone phải cụ thể và đủ khái quát, để đọc lên là cả team và khách hình dung ra ngay cần làm gì. Tên tốt có hai phần: **đối tượng** cụ thể và **việc cần làm** với nó — `Lighter Platform Integration`, `Vault Contracts & Privy Sign-in Setup`. Tên như `M3`, `BE phase 2` thì không ai đoán được bên trong có gì. Tên như `Lighter - Trading` mới cho biết chủ đề, chưa cho biết việc.

Xem [mẫu đặt tên Milestone](./milestone-create-example.md#1-milestone).

---

## Tách Milestone thành task: vì sao phải có UX/UI, QA, Code Refactor và xử lý lỗi?

Đây là 3 luật đầu tiên trong Board Rule *(nằm ở tab `README` của mọi board, xem đủ ở phần quy tắc cứng của [quy trình Khởi tạo Board](../po-board-create/board-create-process.md))*. Ba luật này là ba việc **dễ bị quên nhất** — không có dòng trên board thì không ai làm:

- **UX/UI** — Dev code xong mới phát hiện chưa có design cho trạng thái lỗi, trạng thái rỗng. Có task UX/UI ngay từ đầu Milestone = design đi trước code.
- **QA** — Không có task QA, đến ngày bàn giao mới thấy chưa ai test. Có task QA với Expected done date sau các task dev = QA có chỗ đứng trong kế hoạch, không phải "làm thêm nếu còn thời gian".
- **Code Refactor** — Refactor là nợ kỹ thuật mà **chỉ dev biết** — code cũ cần viết lại, performance cần tối ưu, dependency cần cập nhật. Không có task riêng, refactor sẽ luôn bị đẩy xuống cuối vì không "gấp" bằng feature mới — rồi nợ chồng nợ cho đến khi hệ thống quá chậm hoặc quá khó maintain. Mỗi Milestone một task refactor = trả nợ đều đặn, không để dồn.

Ngoài 3 luật trên, khi tách Milestone thành task, hãy kiểm thêm **xử lý lỗi**. Task thường chỉ được viết cho luồng người dùng làm đúng và mạng chạy ổn: đặt lệnh thành công, rút tiền thành công. Lúc lệnh bị từ chối, sàn trả lỗi, giao dịch treo giữa chừng thì không có task nào, nên cũng không có giờ nào trong Estimate. Tách xử lý lỗi thành task riêng thì nó được estimate, được làm, và được QA test. Xem [mẫu danh sách task của một Milestone](./milestone-create-example.md#danh-sách-task-của-một-milestone--mẫu-chưa-tốt).

---

## Vì sao PO estimate cùng Dev?

PO hiểu khách cần gì. Dev hiểu hệ thống cần gì. Estimate một mình thì chỉ thấy một nửa bức tranh.

- **PO estimate một mình** sẽ sót hạng mục kỹ thuật — rồi giữa sprint mới nghe *"cái này phải viết thêm migration nữa anh ơi"*, *"phải cấu hình lại server mới chạy được"*.
- **Dev estimate một mình** sẽ sót hạng mục khách cần — màn hình trạng thái lỗi, email thông báo, trang hướng dẫn — những thứ không nằm trong code nhưng khách nhìn thấy đầu tiên.

Cách tốt:

```
PO mở Planning Report, đi qua từng Milestone cùng Tech Lead.
PO: "Milestone Withdraw có 3 task: form rút tiền, xác nhận, lịch sử giao dịch."
TL: "Thiếu task xử lý rút tiền bị treo ở bridge, cái đó mất 4h. Form rút tiền cũng phải tách đôi — 6h là quá 4h rồi."
→ Board có đủ hạng mục, không task nào quá 4 tiếng.
```

Tại sao tốt: Dev chỉ ra phần PO không thấy. Task được tách nhỏ ngay khi estimate, không phải đợi tới lúc làm mới biết.

Cách tồi:

```
PO tự điền Estimate cho 30 task trong 15 phút, gửi link board vào group:
"Mọi người xem task tuần này nhé."
→ Thứ Tư Dev báo: "Task deposit này phải 2 ngày chứ không phải 4h đâu anh."
```

Tại sao tồi: Estimate theo cảm giác, nên mới giữa tuần sprint đã trễ.

---

## Bỏ trống Estimate thì sao?

*"Task nhỏ thôi, điền giờ làm gì."* Rồi đến cuối tuần, board có 30 task mà không ai biết team đã bỏ ra bao nhiêu giờ.

Khi khách hỏi effort của tuần này, PO không có số để trả lời. Khó thấy hơn là chuyện Estimate còn là dữ liệu để đánh giá team và để báo giá dự án sau. Cột Estimate bỏ trống hoặc điền đại thì số liệu đánh giá và thực tế không khớp nhau, và lần báo giá tới lại phải đoán.

Vì vậy task mới lên board lúc nào cũng có số giờ, ước lượng cùng người sẽ làm — kể cả task phát sinh giữa sprint trong buổi [Internal Daily](../po-internal-daily/internal-daily-process.md).

---

## Tóm lại

| Câu hỏi | Trả lời |
|---------|---------|
| Milestone lớn cỡ nào? | Một tính năng, 1 người hoặc team < 5 người làm dưới 1 tuần |
| Ai chịu trách nhiệm? | Đúng 1 người cho 1 Milestone tại 1 thời điểm |
| Đặt tên thế nào? | Đối tượng cụ thể + việc cần làm: `Lighter Platform Integration` |
| Tách task cần đủ gì? | UX/UI, QA, Code Refactor, xử lý lỗi, mỗi task ≤ 4 tiếng |
| Estimate với ai? | PO ngồi cùng Dev |

---

## Liên kết

- [Mẫu Milestone & Task](./milestone-create-example.md)
- [Khởi tạo Board](../po-board-create/board-create-process.md) — Board Rule, 8 cột
- [Feature Request](../po-feature-request/feature-request-process.md) — Khi khách thêm Milestone mới
