---
type: delivery
tags: [process, project-management, client-management, workflow]
created-date: 2026-11-19
updated-date: 2026-11-19
author: anderson
status: Nháp
---

# Tiếp nhận và Xử lý Yêu cầu Tính năng Mới (Feature Request)

**Người chịu trách nhiệm:** PO dự án
**Cập nhật lần cuối:** 2026-11-19
**Trạng thái:** Nháp

## Tại sao có trang này

Trong quá trình làm dự án, khi thấy sản phẩm dần hình thành, khách hàng sẽ nảy sinh thêm ý tưởng và muốn bổ sung tính năng mới. Nếu PO tiếp nhận cảm tính — gật đầu nhận làm ngay hoặc từ chối cứng nhắc — dự án sẽ rơi vào một trong hai bẫy: **vỡ timeline cam kết** vì phình phạm vi (*scope creep*), hoặc **làm cụt hứng khách hàng và đánh mất cơ hội mở rộng hợp đồng**.

Quy trình này đảm bảo mọi **Feature Request** đều được tiếp nhận, đánh giá tác động và phản hồi theo cùng một chuẩn: **bảo vệ cam kết của dự án hiện tại**, đồng thời **chuyển hóa nhu cầu mới của khách thành giai đoạn phát triển tiếp theo một cách minh bạch**.

## Khi nào áp dụng (Trigger)

Áp dụng mỗi khi khách hàng đề xuất một **Yêu cầu tính năng mới (Feature Request)** trên bất kỳ kênh giao tiếp nào (Telegram, buổi họp Daily Demo, Email, hoặc comment trên Figma/GitHub):
- Là một **tính năng mới**, không nằm trong user flow đã có.
- **Chưa được mô tả** trong Scope of Work (SoW) của Proposal hoặc trong Hợp đồng.
- Tốn công sức đáng kể của team: **lớn hơn 20 giờ làm việc (`> 20h`)**.

*(Xem giải thích chi tiết tại [Cẩm nang cho PO](./feature-request-handbook.md#thế-nào-là-một-yêu-cầu-tính-năng-feature-request))*

---

## Luồng chính

```mermaid
flowchart LR
    A["UNDERSTAND"] --> B["ESTIMATE"]
    B --> C["APPROVAL"]
    C --> D["PROPOSAL"]

    style A fill:#4dabf7,stroke:#333,color:#fff
    style B fill:#ffa94d,stroke:#333,color:#fff
    style C fill:#9775fa,stroke:#333,color:#fff
    style D fill:#69db7c,stroke:#333,color:#000
```

---

## Vai trò & trách nhiệm

| Vai trò | Chịu trách nhiệm gì |
|---------|---------------------|
| **Product Owner (PO)** | Tiếp nhận đề xuất của khách; họp làm rõ yêu cầu và viết **BRD** bằng skill viết BRD (*Understand*); điều phối giữa Tech Lead và AM; trình bày BRD, 4 hạng mục thay đổi và chi phí mở rộng cho khách hàng (*Proposal*) |
| **Tech Lead (TL)** | Đánh giá kỹ thuật từ BRD và lập **Báo cáo Estimate** đầy đủ 4 hạng mục trong vòng **24 giờ**, cộng **buffer 30%–50%** cho rủi ro phát sinh (*Estimate*) |
| **Account Manager — AM (Anderson / Brian)** | Duyệt ngân sách mở rộng và quyết định mức chi phí áp dụng cho khách hàng — tính phí hoặc miễn phí tuỳ hoàn cảnh dự án (*Approval*) |

---

## Các bước

| # | Việc làm | Ai làm | Đầu ra |
|---|----------|--------|--------|
| 1 | **UNDERSTAND — Họp làm rõ yêu cầu & nhắn xác nhận sau họp:** Các tính năng mới thường được thảo luận trực tiếp trong buổi họp với khách. Sau buổi họp, PO viết **BRD** theo [mẫu BRD chuẩn](./template/feature-request-brd-template.md) (bằng skill viết BRD), đồng thời **gửi tin nhắn cho khách** đính kèm BRD, báo rõ quy trình tiếp theo của Cyberk (Estimate trong 24h → Proposal) và nêu trước mức phí mở rộng tiêu chuẩn **`$25/giờ`** để khách biết chừng. | PO | Tài liệu **BRD** + Tin nhắn báo quy trình tiếp theo & đơn giá `$25/giờ` |
| 2 | **ESTIMATE — Ước lượng công sức & rủi ro (chuẩn ≤ 24h):** Dựa trên BRD, Tech Lead lập báo cáo ước lượng số giờ làm việc của team trong vòng **24 giờ**, bắt buộc cộng **buffer 30%–50%** cho các phát sinh liên quan để đánh giá rủi ro mở rộng scope. Báo cáo phải bao gồm đủ 4 hạng mục:<br>• Thiết kế UX/UI cần mở rộng<br>• Thiết kế hệ thống cần thay đổi *(nếu có)*<br>• Source code và side effects cần chỉnh sửa<br>• Team effort / Số giờ mà team cần xử lý cho yêu cầu mới | Tech Lead | **Báo cáo Estimate** (4 hạng mục + tổng giờ kèm buffer 30%–50%) |
| 3 | **APPROVAL — Duyệt ngân sách & mức chi phí:** PO trình BRD + Báo cáo Estimate cho AM. AM duyệt ngân sách mở rộng và chốt mức chi phí áp dụng cho khách hàng *(tính theo đơn giá chuẩn **`$25/giờ`** hoặc tài trợ miễn phí tuỳ hoàn cảnh dự án)*. | AM (Anderson / Brian) | Phê duyệt ngân sách + **Mức chi phí mở rộng** |
| 4 | **PROPOSAL — Trình bày phương án & chốt Email confirm:** PO trình bày **BRD** cho khách hàng kèm theo **chi phí mở rộng yêu cầu dự án** (`số giờ × $25/giờ`, hoặc thông báo tài trợ miễn phí), giải thích rõ từng hạng mục thay đổi cụ thể ở bước Estimate:<br>• Thiết kế UX/UI cần mở rộng<br>• Thiết kế hệ thống cần thay đổi *(nếu có)*<br>• Source code và side effects cần chỉnh sửa<br>• Team effort / Số giờ mà team cần xử lý cho yêu cầu mới<br>Ngay sau khi khách gật đầu đồng ý về chi phí (trên họp hoặc chat), PO **bắt buộc gửi 1 Email chốt confirm** (CC AM) để khách reply xác nhận chính thức bằng văn bản. | PO | Khách nắm rõ BRD, 4 hạng mục & chi phí → **Reply xác nhận qua Email** |

---

## Quy tắc cứng (không được vi phạm) + lý do

| Quy tắc | Lý do |
|---------|-------|
| Deadline tiêu chuẩn để **Estimate** một feature mới là **24 giờ** | Nhịp làm việc (routine) giữa khách hàng và team xoay theo chu kỳ **24 giờ mỗi ngày**. Phản hồi ngay trong phiên làm việc kế tiếp giúp team giữ tinh thần *responsive* và khách hàng cảm nhận rõ chất lượng dịch vụ |
| **Ngay sau buổi họp thảo luận tính năng mới, phải nhắn khách báo rõ quy trình tiếp theo & đơn giá mở rộng `$25/giờ`** | Tránh hiểu nhầm *"bàn trong cuộc họp rồi nghĩa là team tự làm luôn miễn phí"*; báo trước mức `$25/giờ` giúp khách biết chừng và không bị bất ngờ ở bước Proposal |
| **Không commit miệng** (về việc "làm được ngay", timeline hay miễn phí) trước khi qua bước **Approval** | Cam kết trước khi có BRD, Estimate của TL và duyệt ngân sách của AM = nợ miệng, dễ vỡ tiến độ và thiệt hại ngân sách công ty |
| **Chưa có BRD → Tech Lead không Estimate** | Ước lượng trên lời nói mơ hồ chắc chắn bỏ sót *side effects* và lệch số giờ thực tế |
| **Buffer 30%–50% gộp kín vào tổng giờ**, không tách riêng dòng "buffer" khi trình bày với khách | Tách chữ "buffer" ra ngoài sẽ khiến khách hàng mặc cả đòi cắt bỏ phần dự phòng rủi ro của team |
| **Dù AM duyệt miễn phí, PO vẫn phải trình bày đủ BRD + 4 hạng mục + số giờ ở bước Proposal** | Giúp khách hàng thấy rõ khối lượng công sức thật mà Cyberk hỗ trợ, tránh tâm lý xem nhẹ *"sửa tí là xong"* ở các lần sau |
| **Khách gật đầu đồng ý chi phí → Bắt buộc gửi Email chốt confirm và chờ khách reply xác nhận trước khi code** | Lời nói trên cuộc họp hay tin nhắn Telegram dễ trôi mất; Email xác nhận là bằng chứng văn bản chính thức khi nghiệm thu và xuất hóa đơn, triệt tiêu mọi tranh cãi về sau |

---

## Ngoại lệ & Escalation

| Tình huống | Hành động |
|-----------|----------|
| Yêu cầu tốn **dưới 8 giờ (`< 8h`)** — đơn giản hoặc là tính năng nền tảng hầu như ứng dụng nào cũng có *(VD: màn hình Terms & Policy, Forgot Password, 2FA cơ bản...)* | **Bỏ qua quy trình 4 bước này** — team ghi nhận task lên board và thực hiện luôn cho khách hàng để giữ tốc độ phục vụ |
| Yêu cầu nằm ở mức **từ 8 đến 20 giờ (`8h – 20h`)** | **Vẫn thực hiện đầy đủ quy trình 4 bước** và lên báo giá cụ thể (`số giờ × $25/giờ`). Ở lần phát sinh đầu tiên, AM & PO có thể cân nhắc **offer miễn phí**, nhưng **phải nhắc trước khách hàng rằng các lần phát sinh sau có thể phải tính phí** |
| Lúc làm mới nhận ra **khách mô tả sai**, hoặc **hai bên hiểu nhầm ý nhau** dẫn tới yêu cầu bị sai *(khách cảm thấy nguyên nhân đến từ vấn đề giao tiếp)* | Không đôi co đổ lỗi hay thu đủ 100% phí (dễ làm khách thấy *"ấm ức"* và mất thiện cảm). PO làm rõ lại BRD + lấy Estimate của TL → trình **AM (Anderson / Brian)** đề xuất **giảm giá sâu 50%** (cùng san sẻ) hoặc **miễn phí lần đầu** |
| Việc Estimate **vượt quá 24 giờ** chưa xong | Báo cáo ngay cho **Anderson** — đây là dấu hiệu của một feature rất lớn hoặc tiềm ẩn nhiều *side effects* phức tạp cần nghiên cứu cẩn trọng trước khi cam kết |
| Khách không đồng ý chi phí mở rộng ở bước **Proposal** | PO **không tự ý giảm giá hay cắt giờ Estimate** tại chỗ. Ghi nhận ý kiến khách → báo lại **AM (Anderson / Brian)** để quyết định (thu gọn scope BRD hoặc điều chỉnh chính sách phí) |
| Khách muốn chèn ngang feature mới ngay nhưng **không chịu lùi ngày Launch** | Escalate lên **AM** để đàm phán đánh đổi scope (rút tính năng khác tương đương sang Phase sau) |

---

## Checklist mỗi Feature Request

- [ ] **Understand:** Đã thảo luận rõ yêu cầu với khách, viết xong **BRD** và gửi tin nhắn sau họp thông báo quy trình tiếp theo của Cyberk + đơn giá mở rộng **`$25/giờ`**
- [ ] **Estimate:** Tech Lead đã hoàn thành báo cáo trong **≤ 24h** *(nếu quá 24h đã báo Anderson)*, đủ 4 hạng mục (UX/UI, System Design, Source code & side effects, Team effort kèm buffer 30%–50%)
- [ ] **Approval:** AM (Anderson / Brian) đã duyệt ngân sách mở rộng và chốt mức chi phí (tính phí hoặc miễn phí)
- [ ] **Proposal:** PO đã trình bày rõ cho khách **BRD + 4 hạng mục thay đổi + chi phí mở rộng**
- [ ] **Email Confirm:** Sau khi khách gật đầu về chi phí, PO đã gửi **Email chốt confirm** (CC AM) và nhận được phản hồi xác nhận của khách qua Email trước khi đưa task vào Sprint thực thi

---

## Liên kết

- [Xử lý Feature Request — Cẩm nang cho PO](./feature-request-handbook.md) — Định nghĩa, hướng dẫn cách nghĩ, mẫu tốt/tồi
- [Mẫu BRD & Báo giá mở rộng](./template/feature-request-brd-template.md) — File mẫu chuẩn PO và Tech Lead điền xuyên suốt 4 bước
- [Mẫu tin nhắn & phản hồi](./feature-request-example.md) — Tất cả mẫu tin nhắn cho mọi tình huống
