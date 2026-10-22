---
type: team
tags: [handbook, communication, client-management, setup]
created-date: 2026-10-22
updated-date: 2026-10-22
author: neo
status: Nháp
---

# Lập 4 group chat — Cẩm nang cho Account và Product Owner

**Người chịu trách nhiệm:** Account
**Cập nhật lần cuối:** 2026-10-22
**Trạng thái:** Nháp

Trang này dành cho Account khi tạo group lúc khách đồng ý, và cho PO khi add team lúc dự án bắt đầu. Trang chỉ nói về hai việc: đặt tên group và add đúng người vào đúng group. Các bước theo thứ tự nằm ở [Lập 4 group](chat-groups-setup-process.md).

Đặt sai tên thì đổi lại được. Add nhầm người thì khó hơn, vì người đó đã đọc được tin nhắn trong group.

---

## 1. Tên dự án khác tên công ty khách thì đặt theo tên nào?

Ví dụ khách là công ty Acme, còn dự án tên Leaseform. Đặt theo tên dự án, viết giống tên board trên GitHub Projects. Gõ "Leaseform" trong Telegram sẽ ra group, gõ trên GitHub sẽ ra board `leaseform-management`.

**Cách tốt:**

```
Leaseform - Cyberk Management
Leaseform - Cyberk devs
Leaseform - Cyberk Internal
```

Gõ "Leaseform" vào ô search của Telegram là thấy cả 3 group.

**Cách tồi:**

```
Acme - Cyberk devs
Leaseform Internal
LF - Cyberk Management
```

Ba group của cùng một dự án mang ba kiểu tên. Search "Leaseform" chỉ ra một group, và người mới không biết `Acme` với `LF` là cùng một dự án.

---

## 2. Khách có thêm dự án thứ hai thì sao?

Tạo một bộ group mới theo tên dự án mới. Group Broker thì dùng lại, vì mỗi broker chỉ có một group.

**Cách tốt:**

```
Cyberk - Andre                    (dùng lại, không tạo mới)
Leaseform - Cyberk Management     (dự án 1)
Leaseform - Cyberk devs
Leaseform - Cyberk Internal
Tenantly - Cyberk Management      (dự án 2, bộ mới)
Tenantly - Cyberk devs
Tenantly - Cyberk Internal
```

Hai dự án có thể do hai team làm và có hoá đơn riêng. Tách group thì dev của dự án này không phải đọc việc của dự án kia.

**Cách tồi:**

```
Đổi tên "Leaseform - Cyberk devs" thành "Leaseform & Tenantly - Cyberk devs"
```

Dev Leaseform phải đọc việc của Tenantly, và hoá đơn của hai dự án nằm lẫn trong một group Management.

---

## 3. Account tạo group xong thì làm gì trước?

Trên Telegram, ai tạo group thì người đó là owner, nên lúc vừa tạo xong Account đang là owner của cả 4 group. Việc đầu tiên là chuyển owner cho Anderson, trước khi add người và trước khi group có tin nhắn nào.

Telegram chỉ cho chuyển owner khi tài khoản đã bật xác thực 2 lớp (2FA). Account bật 2FA trước khi bắt đầu.

**Cách tốt:**

```
1. Tạo 4 group, đặt tên theo quy tắc
2. Chuyển owner cả 4 group cho Anderson
3. Add COO làm admin ở Devs và Internal
4. Add bot Neo và Smith vào đúng group
5. Add người vào Management: người ra quyết định bên khách, broker
```

Từ lúc group có người, quyền cao nhất đã nằm ở Anderson. Sau này Account nghỉ việc thì group và lịch sử chat vẫn ở lại Cyberk.

**Cách tồi:**

```
Tạo group, add khách, gửi Agreement ngay, định chuyển owner sau.
```

Nếu sau đó quên chuyển và Account nghỉ việc, cả 4 group vẫn đứng tên một tài khoản không còn ở Cyberk.

---

## 4. Bot nào vào group nào?

Neo vào group Broker và Management. Smith vào group Devs và Internal. Mỗi bot chỉ ở trong những group có loại thông tin nó cần: Neo với deal và hoá đơn, Smith với việc dự án.

| Bot | Vào group | Không vào group |
|-----|-----------|-----------------|
| Neo | Broker, Management | Devs, Internal |
| Smith | Devs, Internal | Broker, Management |

**Cách tốt:**

```
Leaseform - Cyberk Management   →  Neo
Leaseform - Cyberk devs         →  Smith
Leaseform - Cyberk Internal     →  Smith
```

**Cách tồi:**

```
Add cả Neo và Smith vào cả 4 group.
```

Smith sẽ đọc được Agreement và hoá đơn trong group Management, còn Neo đọc được trao đổi nội bộ của team trong group Internal.

Group nào chuyển sang WhatsApp thì không có bot, vì Neo và Smith chạy trên Telegram. Trang này cũng chưa mô tả cụ thể từng bot làm gì trong group.

---

## 5. COO ở group nào?

COO là admin của group Devs và Internal để theo dõi dự án, và không phải làm việc gì trong quy trình này. COO không ở group Broker và Management.

**Cách tốt:**

```
Leaseform - Cyberk devs       →  COO (admin)
Leaseform - Cyberk Internal   →  COO (admin)
```

**Cách tồi:**

```
Add COO vào cả 4 group, rồi nhờ COO add member thay PO.
```

Broker và Management nằm ngoài phần COO theo dõi. Add member là việc của PO, vì PO biết dự án cần những ai.

---

## 6. PO add team: add ai, vào đâu, lúc nào?

Group Devs và Internal có từ bước 1, nhưng lúc đó mới chỉ có COO và bot Smith. PO add người khi dự án bắt đầu. Người của Cyberk vào cả hai group, người phía khách chỉ vào Devs.

| Người | Internal | Devs |
|-------|----------|------|
| PO, Developer, Designer, QA | Có | Có |
| PO hoặc tech contact bên khách | Không | Có |
| Broker | Không | Chỉ khi Anderson đồng ý |

Hai group cùng tên dự án nằm sát nhau trong danh sách chat. Trước khi add người phía khách, PO đọc lại tên group một lần.

**Cách tốt:**

```
Ngày dự án bắt đầu:
- Internal: add PO, Hùng (dev), Lan (designer), Minh (QA)
- Devs: add PO, Hùng, Lan, Minh, Mark (tech contact bên khách)
- Trước khi add Mark, đọc lại tên group: "Leaseform - Cyberk devs"
```

Team và khách vào cùng một ngày, vào đúng group.

**Cách tồi:**

```
- Add cả team ngay khi Account vừa tạo group, trong khi 2 tuần nữa dự án mới bắt đầu
- Add Mark vào "Leaseform - Cyberk Internal" vì bấm nhầm group
- Add dev vào group Management để dev nắm tình hình
```

Add sớm thì khách có thể nhắn vào group Devs khi chưa ai được giao trả lời. Mark vào nhầm Internal sẽ đọc được trao đổi nội bộ của team. Dev ở Management sẽ thấy hợp đồng và hoá đơn, là việc của Account.

Nếu lỡ add người phía khách vào Internal, xoá họ khỏi group ngay và báo Anderson.

---

## Tóm lại

| Việc | Nên | Không nên |
|------|-----|-----------|
| Đặt tên | Theo tên dự án, giống tên board | Theo tên công ty khách, viết tắt, thêm emoji |
| Khách có dự án mới | Tạo bộ group mới, dùng lại group Broker | Đổi tên group cũ để dùng chung |
| Account tạo group xong | Chuyển owner cho Anderson ngay | Để chuyển owner sau |
| Bot | Neo ở Broker và Management, Smith ở Devs và Internal | Add cả 2 bot vào cả 4 group |
| COO | Admin ở Devs và Internal | Add vào cả 4 group, nhờ add member |
| PO add team | Đợi dự án bắt đầu, khách chỉ vào Devs | Add sớm, add khách vào Internal |

---

## Liên kết

- [Lập 4 group — các bước và quy tắc đặt tên](chat-groups-setup-process.md)
- [Project Onboarding — add member, PRD, GitHub repo](../../04-developer/dev-project-onboarding/dev-project-onboarding-process.md)
- [Project Leave — xoá khỏi group khi rời dự án](../../05-product-owner/po-project-leave/po-project-leave-process.md)
- [Mẫu tin nhắn](chat-groups-example.md)
