---
type: delivery
tags: [planning, process]
created-date: 2026-08-27
updated-date: 2026-11-26
author: anderson
status: Nháp
---

# Lập kế hoạch dự án (Internal Planning)

**Người chịu trách nhiệm:** PO dự án
**Cập nhật lần cuối:** 2026-11-26
**Trạng thái:** Nháp

## Tại sao có trang này

Internal Planning Meeting là buổi họp quan trọng nhất trước khi bắt tay vào phát triển — quyết định cả team có cùng hiểu đúng yêu cầu, cùng thống nhất kế hoạch, hay mạnh ai nấy hiểu. Planning tốt thì dự án chạy mượt từ sprint đầu; planning hời hợt thì 2 tuần sau mới phát hiện mỗi người hiểu một kiểu.

Tại Cyberk, PO đã dựng xong board trước buổi họp: đủ Milestone, đủ task, mỗi task có số giờ và ngày xong dự kiến. Team bước vào buổi họp với mọi thứ đã sẵn sàng. Buổi Planning tập trung vào hai việc: tìm ra **Key Success Features** và đưa chúng lên đầu board, rồi **chia việc** — mỗi người nhận việc, soát kỹ phần của mình, và cam kết ngày release. Cả team cam kết xong, PO gửi thẳng board cho khách.

## Khi nào áp dụng (Trigger)

Khi board đã được dựng theo [Khởi tạo Board](../po-board-create/board-create-process.md), PRD đã sẵn sàng, và team đã được assign vào dự án — **trước khi bắt đầu sprint đầu tiên**.

---

## Luồng chính

```mermaid
flowchart LR
    A["PRIORITY"] --> B["ASSIGN"]
    B --> C["SEND"]

    style A fill:#ff6b6b,stroke:#333,color:#fff
    style B fill:#9775fa,stroke:#333,color:#fff
    style C fill:#69db7c,stroke:#333,color:#000
```

---

## Vai trò & trách nhiệm

| Vai trò | Chịu trách nhiệm gì |
|---------|---------------------|
| **Product Owner (PO)** | Gửi PRD và link board cho team đọc trước; trình bày mục đích của khách, chốt Key Success Features và bôi đỏ trên board (*Priority*); chia việc, sửa board theo góp ý, thu cam kết EOD (*Assign*); gửi board cho khách và leaders (*Send*) |
| **Tech Lead** | Góp ý thứ tự ưu tiên về mặt kỹ thuật (*Priority*); soát kiến trúc, các Estimate lớn và thứ tự phụ thuộc, xác định rủi ro công nghệ (*Assign*) |
| **Dev** | Đọc PRD và board trước; nhận task, soát kỹ task của mình (thừa/thiếu, Estimate), cam kết EOD ngày release (*Assign*) |
| **QA** | Góp ý mức ưu tiên (*Priority*); nhận và soát task QA, góp ý rủi ro chất lượng, cam kết EOD (*Assign*) |
| **Designer** | Nhận và soát task UX/UI, timeline design, cam kết EOD (*Assign*) |

---

## Các bước

| # | Việc làm | Ai làm | Đầu ra | Timeline |
|---|----------|--------|--------|----------|
| 1 | **PRIORITY — Tìm ra Key Success Features:** PO trình bày bối cảnh dự án — khách hàng là ai, vấn đề họ đang giải quyết, mục đích *(gọi vốn? doanh thu? user?)*. Từ mục đích đó, cả team thống nhất 4 mức ưu tiên *(Key Success → Thiết yếu → Không ưu tiên → Nice-to-have)*. Các Milestone **Key Success Features** được **bôi màu đỏ và đưa lên trên cùng** tab sprint, để ai mở board cũng biết đó là việc quan trọng nhất | PO + cả team | **Key Success Features bôi đỏ, nằm trên cùng board** | 30 phút |
| 2 | **ASSIGN — Chia việc, soát việc của mình, cam kết EOD:** Bắt đầu từ Key Success Features — giao cho người giỏi và đáng tin nhất, làm đầu tiên. Chia theo **độ quan trọng**, không theo độ khó. Mỗi task đúng 1 người, đúng vai trò, mỗi member 2 task/ngày, 10 task/tuần. Nhận việc xong, mỗi người soát kỹ phần của mình:<br>• Đọc lại PRD ở phần mình, task thừa hay thiếu ở đâu?<br>• Estimate và ngày xong có đúng không?<br>• Chỗ nào chưa rõ → câu hỏi cho khách; rủi ro gì → kèm giải pháp<br>PO sửa board theo góp ý. Cuối ngày, mỗi người **cam kết**: nếu không có vấn đề gì phát sinh, phần việc của mình có release đúng ngày đã estimate không? Được thì đi tiếp. Không được thì điều chỉnh *(tách task, chuyển việc, dời Milestone ít quan trọng)* rồi cam kết lại | PO + cả team | **Mỗi task có 1 Assignee** + **cam kết EOD của từng người** | Buổi họp 30–45 phút, cam kết trước EOD |
| 3 | **SEND — Gửi board cho khách:** Khi cả team đã cam kết, PO viết [Daily Report](../po-internal-daily/internal-daily-handbook.md) đầu tiên ở đầu tab `sprint_1`: kế hoạch đã chốt, rủi ro chính và câu hỏi cho khách, giải pháp team chọn. Export PDF, cấp quyền **xem** board cho khách, gửi vào group `[Project] - Cyberk devs` kèm tin nhắn summary *(Approach, Key Risks, Strategy — xem [mẫu](./planning-example.md))*. Gửi Anderson/COO qua Telegram kèm tóm tắt rủi ro chính | PO | Khách nhận board, leaders nắm tình hình | Ngay sau khi có đủ cam kết EOD |

---

## Quy tắc cứng (không được vi phạm) + lý do

| Quy tắc | Lý do |
|---------|-------|
| Team phải đọc PRD và board **trước** buổi họp | Không đọc trước = mất 45 phút đầu giải thích lại, buổi họp không có chiều sâu thảo luận |
| Key-members (TL, dev chính, QA) bắt buộc tham gia | Thiếu người quan trọng = quyết định thiếu cơ sở kỹ thuật, phải họp lại lần 2 |
| Mỗi task có **1 Assignee + Expected done date** | Task không có owner = không ai làm. Không có deadline = không bao giờ xong |
| Key Success Features bôi màu đỏ, nằm trên cùng board, làm đầu tiên, do người giỏi và đáng tin nhất làm | Thiếu Key Success Features thì dự án fail. Việc quan trọng nhất phải ở trong tay người chắc chắn nhất, và có nhiều thời gian nhất để sửa nếu sai |
| Mỗi người cam kết EOD ngày release của phần việc mình trước khi gửi board cho khách | Dev phải cam kết với con số của chính mình, không phải "con số của PO" |
| Board gửi cho khách **trong ngày**, ngay sau khi đủ cam kết | Để lâu = câu hỏi cho khách trả lời muộn, khách lo lắng |
| Buổi planning phải có **facilitator** (người dẫn dắt) rõ ràng | Không có facilitator = buổi họp loãng, không có kết luận, không có quyết định |

---

## Ngoại lệ & Escalation

| Tình huống | Hành động |
|-----------|----------|
| PRD chưa rõ, có nhiều điểm mâu thuẫn | Ghi lại tất cả câu hỏi, follow-up với khách **trước** khi chốt các Milestone liên quan. Không estimate trên requirement mơ hồ — xem [Tạo Milestone](../po-milestone-create/milestone-create-process.md) |
| Khi soát việc, phát hiện **thiếu Milestone** hoặc Estimate sai lớn | PO sửa board ngay trong buổi họp. Nếu kế hoạch mới không kịp ngày Launch đã cam kết → escalate **AM (Anderson / Brian)** trước khi gửi board cho khách |
| Team không đủ capacity cho scope dự án | Escalate lên COO/Anderson để điều chỉnh resource, timeline, hoặc scope. Không im lặng chấp nhận rồi trễ |
| Member **chưa đủ 2 task mỗi ngày** sau khi chia việc | Kéo thêm việc từ sprint sau lên. Nếu dự án thật sự hết việc → báo Anderson để điều phối member sang hỗ trợ dự án khác |
| Khách thay đổi yêu cầu sau buổi planning | Dưới 8 giờ → đưa thẳng lên board. Từ 8 giờ trở lên → đi theo [Feature Request](../po-feature-request/feature-request-process.md) |
| Key-member vắng buổi planning | Ghi lại meeting notes, brief riêng cho người vắng trong vòng 24h. Không để ai "tự đọc meeting notes" |
| Có người chưa cam kết được trước EOD, hoặc không kịp gửi board trong ngày | Gửi bản PDF hiện có kèm ghi chú "bản cập nhật gửi trước 10am mai". Không để quá 24h |

---

## Checklist

### Trước buổi họp
- [ ] Board đã dựng xong theo [Khởi tạo Board](../po-board-create/board-create-process.md)
- [ ] PRD và link board đã gửi cho team ít nhất 1 ngày trước
- [ ] Key-members đã xác nhận tham gia
- [ ] Phòng họp đã book (nghiêm túc, xa khu vực làm việc)
- [ ] Slide giới thiệu dự án đã chuẩn bị (bối cảnh, mục đích, user)

### Trong buổi họp
- [ ] Bối cảnh + mục đích dự án đã được giải thích
- [ ] Features đã phân loại 4 mức, Key Success Features đã bôi đỏ và đưa lên đầu board
- [ ] Key Success Features do người giỏi nhất team nhận, nằm ở sprint đầu
- [ ] Mọi task có 1 Assignee
- [ ] Mỗi người đã soát task của mình, chỗ thiếu đã sửa, câu hỏi cho khách đã ghi lại
- [ ] Rủi ro đã xác định + có giải pháp

### Cuối ngày
- [ ] Mỗi người đã cam kết ngày release; ai chưa được thì đã điều chỉnh và cam kết lại

### Sau buổi họp
- [ ] Daily Report đầu tiên đã viết ở đầu tab `sprint_1`
- [ ] Board đã gửi khách (PDF + quyền xem + tin nhắn summary) trong ngày
- [ ] Anderson/COO đã nhận tóm tắt rủi ro
- [ ] Key-member vắng đã được brief riêng

---

## Liên kết

- [Cách nghĩ khi planning — triết lý & mẫu tốt/tồi](./planning-handbook.md)
- [Khởi tạo Board](../po-board-create/board-create-process.md) — Bước trước: PO dựng board đầy đủ
- [Kick-off với khách hàng](../po-kick-off/kick-off-process.md) — Bước tiếp theo
- [Mẫu tin nhắn gửi board](./planning-example.md) — Dùng cho bước Send
- [Mẫu Daily Report](../po-internal-daily/internal-daily-example.md) — Daily Report đầu tiên ở đầu tab `sprint_1`
