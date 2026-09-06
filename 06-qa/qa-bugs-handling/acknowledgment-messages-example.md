---
type: qa
tags: [bug-handling, communication, client-management, templates]
created: 2026-08-25
updated: 2026-08-25
author: anderson
---

# 💬 Mẫu Tin Nhắn — Tốt vs Không Tốt

> QA giao tiếp với khách qua **tin nhắn** (Telegram), không phải email.
> Viết ngắn, thân thiện, đi thẳng vào vấn đề. Không cần "Dear", "Best regards".

---

## ✅ Mẫu TỐT

### 1. Tiếp nhận nhanh

> Vừa nhận bug report, triage nhanh và reply theo [SLA severity](bug-severity-sla-handbook.md) (P0 ≤30p, P1 ≤1h, P2 ≤4h, P3 ≤1 ngày).

```
Hi [Client] 👋 Got it, we're looking into this now!
📋 Tracking: [PROJECT]-[NUMBER]
⏱️ Will update you within [2 hours / end of day]
Any extra info (screenshot, steps to reproduce) would help a lot 🙏
```

Tốt vì: Nhanh, có tracking, có timeline, chủ động hỏi thêm info.

---

### 2. Bug từ kênh khác → hướng về bugs-report

> Khách nhắn lỗi vào nhóm chung hoặc DM. Cần chuyển về kênh bugs chính thức.

```
Hi [Client] 👋 Thanks for flagging this!
I'll move this to our bugs channel [Bugs Group Name / Link] so we can track it properly.
I'll post the details there shortly — please check there for updates!
```

Tốt vì: Nhận trách nhiệm chuyển — không bắt khách tự tìm kênh.

---

### 3. Xác nhận bug + báo timeline fix

> Đã validate xong, tạo issue trên GitHub.

```
Hi [Client] — bug confirmed ✅
🐛 #[NUMBER]: [link GitHub Issue]
📊 Severity: P[X]
⏱️ Expected fix: [timeline]
Dev is on it, will update you when it's done 👍
```

Tốt vì: Đủ 3 thứ khách cần — mã bug, mức độ, bao lâu.

---

### 4. Cần thêm thông tin

> Bug report thiếu info, chưa validate được.

```
Hi [Client] 👋 Got your report! We're on it.
📋 Tracking: [PROJECT]-[NUMBER]

Quick question — could you share a bit more so we can reproduce faster:
1. What browser/device are you using?
2. Screenshot or recording of the issue?
3. What steps did you take before seeing the error?
```

Tốt vì: Acknowledge trước, hỏi sau. Câu hỏi cụ thể, dễ trả lời.

---

### 5. Bug đã fix xong

> Developer fix, QA verify pass, đã deploy.

```
Hi [Client] — Bug #[NUMBER] fixed and verified ✅
Could you give it a quick check on your end? Let us know if all good 👍
```

Tốt vì: Ngắn gọn, đủ thông tin, nhờ khách confirm.

---

### 6. Không tái hiện được

> QA thử nhiều cách nhưng không reproduce được.

```
Hi [Client] — we've been trying to reproduce this but haven't been able to so far 🤔
📋 Tracking: [PROJECT]-[NUMBER]

Could you help us out with:
1. Browser + device you're using
2. A screenshot or screen recording
3. Exact steps you took

We're keeping this open and monitoring. If it happens again, please let us know right away!
```

Tốt vì: Không đổ lỗi, không nói "works on our end", hỏi cụ thể, giữ issue mở.

---

## ❌ Mẫu KHÔNG TỐT

### 1. ❌ Quá ngắn, thiếu info

```
Ok, noted.
```
```
Received. Will check.
```

Tại sao tồi: Không tracking, không timeline, không biết ai đang xem. Khách cảm thấy nói chuyện với bức tường.

---

### 2. ❌ Chậm + không xin lỗi

> Khách báo 10:00 sáng. QA reply 14:30 chiều:

```
Hi, we'll look into this.
```

Tại sao tồi: 4.5 tiếng mới reply, không xin lỗi, vẫn không có tracking. Nếu bị chậm, nên:

```
Hey [Client], sorry for the late reply! Got your report — tracking as [PROJECT]-[NUMBER].
Team is on it now, will update you within [timeline] 🙏
```

---

### 3. ❌ Đổ lỗi cho khách

```
We checked and it works fine on our end. 
Might be a network issue on your side. Try clearing your cache?
```

Tại sao tồi: "Works on our end" = đổ lỗi. "Clear cache" = coi thường khách. Không evidence, không tracking.

---

### 4. ❌ Hứa hẹn mơ hồ

```
Let me check, should be a quick fix.
```
```
We'll try to fix it soon.
```

Tại sao tồi: "Quick", "soon" nghĩa là gì? 1 giờ? 1 tuần? Không bao giờ dùng "soon/quick/ASAP" mà không kèm timeline cụ thể.

---

### 5. ❌ Đẩy khách sang kênh khác

```
Please report this in the bugs channel, not here.
```

Tại sao tồi: Lạnh lùng, từ chối giúp, bắt khách tự làm. QA phải nhận trách nhiệm chuyển, không phải đẩy việc.

---

## Nguyên tắc chung

| ❌ Không | ✅ Nên |
|---------|-------|
| Im lặng quá SLA severity | Triage nhanh + reply theo [SLA severity](bug-severity-sla-handbook.md) |
| "soon", "ASAP", "shortly" | "within 2 hours", "by end of day" |
| "works on my machine" | Hỏi thêm environment, thử nhiều setup |
| "quick fix" khi chưa validate | "investigating, update within [time]" |
| Copy-paste cứng nhắc | Sửa tên khách, mô tả bug cho đúng |
| Quên update | Nhắn ít nhất 1 lần/ngày cho bug đang xử lý |
