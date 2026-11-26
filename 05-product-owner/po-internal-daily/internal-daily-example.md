---
type: delivery
tags: [example, dev-daily, client-management, board, google-sheet]
created-date: 2026-11-26
updated-date: 2026-11-26
author: anderson
status: Nháp
---

# Internal Daily — Mẫu Daily Report & Tin nhắn Summary

**Người chịu trách nhiệm:** PO dự án
**Cập nhật lần cuối:** 2026-11-26

> Mỗi mẫu có một bản chưa tốt đặt trước và một bản tốt đặt sau, để so trực tiếp. Daily Report và tin nhắn summary viết bằng tiếng Anh, vì người đọc là khách. Cách nghĩ đằng sau từng mẫu nằm ở [Cẩm nang Internal Daily](./internal-daily-handbook.md). Mẫu Milestone và Task nằm ở [Tạo Milestone — Mẫu](../po-milestone-create/milestone-create-example.md).

---

## 1. Daily Report ở đầu tab sprint

Daily Report trả lời 4 câu hỏi: team đã làm xong những gì, đang gặp vấn đề gì, có những giải pháp nào, team chọn giải pháp nào và tại sao.

### Mẫu chưa tốt

```
Koto Daily Report - Nov 18th

Done:
- Worked on frontend
- Fixed some bugs

Everything is on track.
```

Khách không biết frontend nào, bug nào. "Everything is on track" trong khi chiều rút tiền Lighter → Koto chưa chạy được. Khách sẽ phát hiện ra chuyện này lúc tự dùng thử, và lúc đó là team mất điểm.

### Mẫu tốt

Phỏng theo board Koto ngày 18/11.

```
Koto Daily Report - Nov 18th

What we completed
- Mainnet trading on Lighter: market orders, rate limits, real order book depth
- New trading UI wired to live data: order book, order ticket, positions
- Smoke test passed for account creation, deposit, internal transfer

What we're stuck on
- Withdraw from Lighter back to Koto doesn't work yet. Lighter has no direct
  route back, so users can move funds in but not out.

Options
- A. Wait for Lighter to support the return route. No date from Lighter.
- B. Route funds through the Mayan Swift bridge, reusing our gas sponsorship.
     About 1 day of work.
- C. Release Lighter on Nov 20 with deposit only, add withdraw later.

What we chose and why
- B. Users can't be stuck with funds they can't withdraw, and B fits before
  the Nov 20 release. Dennis starts today, Kate tests it tomorrow.
```

Phần làm xong ghi những thứ khách mở sản phẩm ra là thấy. Phần vấn đề nói thẳng chỗ chưa chạy và ảnh hưởng tới người dùng ra sao. Ba phương án có kèm cái giá của từng cái, nên khách tự đánh giá được. Lý do chọn B nằm ngay cạnh quyết định, kèm tên người làm và ngày test.

---

## 2. Tin nhắn summary gửi kèm PDF

Gửi trong group `[Project] - Cyberk devs`, ngay dưới file PDF.

### Mẫu chưa tốt

```
[PDF] Koto_Management_Nov18.pdf
```

hoặc:

```
Dear Jon,

I hope this message finds you well. Please find attached today's daily report
for the Koto project. Yesterday the team made great progress across several
areas including the trading interface, mainnet integration and testing...

(3 đoạn nữa)

Best regards,
```

Bản thứ nhất bắt khách mở PDF mới biết có gì. Bản thứ hai dài như email, câu quan trọng nhất nằm ở đoạn thứ ba nên khách đọc lướt là bỏ qua.

### Mẫu tốt

```
Hi Jon, today's report is attached 📎

Done: mainnet trading and the new trading UI on Lighter are live on staging.
Issue: withdraw from Lighter back to Koto isn't possible yet.
We're routing it through the Mayan bridge (~1 day), so the Nov 20 release stays on track.
Details and the other options are in the PDF.
```

Tin nhắn chỉ có bốn dòng, khách đọc trên điện thoại là biết có gì xong, có vấn đề gì, team đang xử lý ra sao, và có cần mở PDF ra xem kỹ không.

---

## Liên kết

- [Quy trình Internal Daily](./internal-daily-process.md)
- [Cẩm nang Internal Daily](./internal-daily-handbook.md)
- [Tạo Milestone — Mẫu](../po-milestone-create/milestone-create-example.md) — Mẫu Milestone và Task
