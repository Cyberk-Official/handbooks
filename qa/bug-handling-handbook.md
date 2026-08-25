---
type: qa
tags: [bug-handling, handbook]
created: 2026-08-25
updated: 2026-08-25
author: anderson
---

# Xử lý Bugs — Cẩm nang cho QA

Khi khách hàng báo lỗi, **QA là người đầu tiên họ nói chuyện.** Cách bạn phản hồi quyết định họ tin tưởng hay mất niềm tin vào cả team.

Cuốn cẩm nang này giúp bạn biết phải làm gì — từ lúc nhận tin nhắn khách đến khi bug được đóng.

---

## Khách báo lỗi — Bạn làm gì đầu tiên?

**Reply ngay. Trong vòng 15 phút.**

Không cần biết bug thật hay giả. Không cần hiểu hết vấn đề. Việc đầu tiên là cho khách biết: *"Tôi đã nhận được, tôi đang xem."*

Im lặng 30 phút = khách nghĩ không ai quan tâm. Im lặng 1 tiếng = khách gọi sếp bạn.

Gửi tin nhắn trên **cùng kênh khách báo** (Telegram hay GitHub Issues):

**✅ Cách tốt:**

```
Hi [Client] 👋 Got it, we're looking into this now!
📋 Tracking: [PROJECT]-[NUMBER]
⏱️ Will update you within [2 hours / end of day]
Any extra info (screenshot, steps to reproduce) would help a lot 🙏
```

**❌ Cách tồi:**

```
Ok noted.
```

Tại sao tồi: Không tracking, không timeline, không biết ai xem, không biết chờ bao lâu. Khách sẽ hỏi lại liên tục vì không có gì để bám vào.

Ba thứ bắt buộc phải có: **xác nhận đã nhận** + **mã tracking** + **khi nào cập nhật tiếp**. Thiếu một trong ba là chưa đạt.

### Khách báo lỗi ở kênh khác (không phải nhóm bugs-report)

Đôi khi khách nhắn lỗi vào nhóm chung, nhóm chat riêng, hoặc DM trực tiếp. Bạn vẫn phải **reply ngay** — nhưng đồng thời hướng khách về đúng kênh bugs-report của dự án để mọi thứ được theo dõi tập trung.

**✅ Cách tốt:**

```
Hi [Client] 👋 Thanks for flagging this!
I'll move this to our bugs channel [Bugs Group Name / Link] so we can track it properly.
I'll post the details there shortly — please check there for updates!
```

Tại sao tốt: Cảm ơn khách, xác nhận đã nhận, hướng dẫn rõ ràng nơi theo dõi, và cam kết sẽ cập nhật.

**❌ Cách tồi:**

```
Please report this in the bugs channel, not here.
```

Tại sao tồi: Lạnh lùng, đẩy việc cho khách, không xác nhận đã nhận, khách cảm thấy bị từ chối thay vì được hỗ trợ.

> 📋 Xem thêm ví dụ tin nhắn tốt và không tốt: [Mẫu tin nhắn tiếp nhận](acknowledgment-messages-example.md)

---

## Xác minh — Bug thật hay không?

Sau khi reply khách, việc tiếp theo là **tự mình kiểm tra.**

1. Tạo task **"Validate: [tên bug]"** trên GitHub Project Board
2. Dùng đúng môi trường khách mô tả (browser, device, OS) — tái hiện lỗi
3. Chụp lại bằng chứng: screenshot, video, console log

Có 3 kết quả:

**Đúng là bug** → chuyển sang phần tiếp theo.

**Không phải bug** (do cách dùng, do config) → Đóng task validate. Báo khách:

**✅ Cách tốt:**

```
Hi [Client] — we checked [PROJECT]-[NUMBER] and it's actually working as expected 👍
[1 câu giải thích ngắn tại sao — VD: "The timeout happens because the session expires after 30 minutes of inactivity."]
Let us know if you run into anything else!
```

**❌ Cách tồi:**

```
We checked and it works fine on our end. It might be your network.
```

Tại sao tồi: "Works on our end" = đổ lỗi. Không giải thích lý do, không tracking, khách cảm thấy bị phủi tay.

**Chưa rõ, cần thêm thông tin** → Giữ task mở, hỏi khách:

```
Hi [Client] 👋 We're looking into [PROJECT]-[NUMBER] but need a bit more info to reproduce it:
1. What browser/device are you on?
2. Can you share a screenshot or screen recording?
3. What steps did you take right before the error?
```

---

## Xác nhận là bug — Log lên GitHub

Đóng task validate → **Done**. Tạo **Bug Issue** mới trên GitHub với đầy đủ thông tin:

```markdown
## 🐛 Bug Report
**Severity:** P[0/1/2/3]
**Reported by:** [Client] via [Telegram/GitHub]
**Environment:** [Production/Staging] — [Browser/OS]

### Steps to Reproduce
1. ...
2. ...

### Expected vs Actual
- Expected: ...
- Actual: ...

### Evidence
[Screenshot / Video / Logs]
```

Gắn labels: `bug` + `severity:p0/p1/p2/p3` + `client-reported`

> 📋 Cách phân loại P0/P1/P2/P3 và deadline tương ứng: [Phân loại Severity & SLA](bug-severity-sla-handbook.md)

---

## Báo lại khách — Và giao cho developer

Đây là lúc khách cần biết hai điều: **bug đã được ghi nhận chính thức** và **bao lâu sẽ được fix.**

**✅ Cách tốt:**

```
Hi [Client] — bug confirmed ✅
🐛 #[NUMBER]: [link GitHub Issue]
📊 Severity: P[X]
⏱️ Expected fix: [timeline]
Dev is on it, will update you when it's done 👍
```

**❌ Cách tồi:**

```
Yeah it's a bug. We'll fix it soon.
```

Tại sao tồi: Không mã bug, không link, không severity, không timeline. "Soon" nghĩa là gì? Khách không có gì để theo dõi.

Đồng thời trên GitHub:
- **Assign** developer phù hợp + gắn deadline
- P0 hoặc P1: **nhắn thêm qua Telegram** cho developer và PM — đừng chỉ rely vào GitHub notification

---

## Developer fix xong — Bạn test lại

Không tin developer nói "done" — **tự test lại.**

- Tái hiện bug bằng đúng các bước ban đầu
- Kiểm tra thêm vài trường hợp liên quan — fix xong chỗ này có hỏng chỗ khác không?

**Pass ✅** — Đóng issue. Báo khách:

**✅ Cách tốt:**

```
Hi [Client] — Bug #[NUMBER] fixed and verified ✅
Could you give it a quick check on your end? Let us know if all good 👍
```

**❌ Cách tồi:**

```
Fixed.
```

Tại sao tồi: Không nói bug nào, không nhờ verify, không thân thiện. Khách có 5 bug đang mở thì biết cái nào fixed?

**Fail ❌** — Reopen issue, comment chi tiết lỗi còn lại, tag developer. **Chưa báo khách** — chờ fix xong mới báo.

---

## Tóm lại

Toàn bộ quy trình gói gọn trong 6 việc:

| # | Việc | Thời gian |
|---|------|-----------|
| 1 | Nhận bug từ khách | — |
| 2 | Reply xác nhận | ≤ 15 phút |
| 3 | Tự validate | 2h–1 ngày |
| 4 | Log bug trên GitHub | Ngay sau validate |
| 5 | Báo khách + assign dev | Ngay sau log |
| 6 | Verify fix → báo khách | Khi dev fix xong |

Nguyên tắc xuyên suốt: **Reply nhanh. Có mã tracking. Có timeline. Không hứa hẹn mơ hồ.**

---

*Đọc thêm: [Mẫu tin nhắn](acknowledgment-messages-example.md) · [Severity & SLA](bug-severity-sla-handbook.md)*
