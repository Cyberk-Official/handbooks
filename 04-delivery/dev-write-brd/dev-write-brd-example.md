---
type: delivery
tags: [brd, documentation, dev, example]
created: 2026-09-01
updated: 2026-09-01
author: anderson
status: Nháp
---

# Mẫu BRD — Feature phát sinh trong quá trình code

**Người chịu trách nhiệm:** [Tech Lead]
**Cập nhật lần cuối:** 2026-09-01

> Quy tắc: BRD tối thiểu 3 section (Summary + BR + Scope). Viết trong repo, commit PR + thông báo team.

---

## ✅ Mẫu TỐT — BRD cho feature phát sinh

### Tình huống

Dev đang code portfolio page, phát hiện hệ thống không có tính năng auto-sync transaction history. User phải nhập tay → UX rất tệ.

### BRD Draft

```markdown
---
title: BRD — Auto-Sync Transaction History
version: 1.0
status: Nháp
created_at: 2026-09-01
author: hungdn-cyberk
project: Koto
---

# BRD — Auto-Sync Transaction History

## 1. Executive Summary

### 1.1 Problem
Khi user tạo portfolio và thêm wallet address, hệ thống không tự động 
sync transaction history từ blockchain. User phải nhập tay từng transaction
— mất trung bình 30 phút, tỷ lệ bỏ ngang ở bước này là 60%.

### 1.2 Solution
Tự động fetch transaction history từ blockchain RPC API khi user thêm 
wallet address. Background job chạy mỗi 5 phút để sync transaction mới.

### 1.3 Success Definition
- Thời gian onboarding giảm từ 30 phút → dưới 2 phút
- Tỷ lệ bỏ ngang giảm từ 60% → dưới 15%

---

## 3. Business Requirements

### BR-012: Auto-fetch Transaction History on Wallet Connect

**Requirement Statement:**
> Hệ thống **MUST** tự động fetch toàn bộ transaction history từ 
> blockchain khi user thêm wallet address vào portfolio.

**Business Rationale:**
Nhập tay transaction là friction lớn nhất trong onboarding flow. 
60% user bỏ ngang. Auto-sync xóa bỏ friction này hoàn toàn.

**Acceptance Criteria:**
- [ ] Khi user thêm wallet address → hệ thống fetch history trong ≤ 30 giây
- [ ] Background job sync transaction mới mỗi 5 phút
- [ ] Hiển thị trạng thái: "Đang sync..." / "Đã sync" / "Lỗi"
- [ ] Nếu API timeout → retry 3 lần, sau đó show error + fallback nhập tay
- [ ] Không fetch transaction cũ hơn 1 năm (performance)

**Priority:** Critical

---

### BR-013: Sync Status Visibility

**Requirement Statement:**
> Hệ thống **MUST** hiển thị trạng thái sync cho user để họ biết 
> dữ liệu đã sẵn sàng hay chưa.

**Business Rationale:**
User không biết sync xong chưa → hoang mang → support ticket tăng.

**Acceptance Criteria:**
- [ ] Badge trạng thái trên portfolio page: Syncing / Synced / Error
- [ ] Nếu Error → show nút "Retry" và option nhập tay
- [ ] Sau khi sync xong → auto-refresh portfolio data

**Priority:** High

---

## 2.4. In Scope / Out of Scope

**In Scope:**
- Auto-sync từ Ethereum và Polygon
- Background job mỗi 5 phút
- Error handling + retry (3 lần)
- Sync status UI (badge)

**Out of Scope:**
- Support thêm blockchain (Solana, BSC) — Phase 2
- Transaction analytics / charts — thuộc Epic khác
- Manual edit transaction — chưa cần, evaluate sau 1 tháng user feedback
- NFT transaction sync — Phase 2
```

Tốt vì:
- 3 section đủ: Summary + 2 BR + Scope
- Problem có con số: "30 phút", "60% bỏ ngang"
- Acceptance criteria cụ thể, verify được
- Out of Scope rõ ràng, có lý do
- Viết trong 20 phút, đủ để AI breakdown thành tasks

---

## ❌ Mẫu KHÔNG TỐT

### 1. BRD quá sơ sài

```markdown
# Transaction Sync

Cần sync transaction từ blockchain.
```

Tại sao tồi: 1 câu. Sync cái gì? Từ đâu? Khi nào? Acceptance criteria? AI không breakdown được.

### 2. BRD gửi qua Telegram thay vì repo

```
Dev: "Anh ơi, cần thêm tính năng sync transaction từ blockchain. 
Em note ở đây nhé."
Lead: "OK, làm đi"
```

Tại sao tồi: Tin nhắn chat bị chìm trong 1 giờ. Không có trace. AI không đọc được Telegram. Người mới join team không biết feature này tồn tại.

### 3. BRD viết nhưng không có acceptance criteria

```markdown
### BR-012: Auto-sync Transaction

**Requirement:** Sync transaction tự động.
**Criteria:** Phải hoạt động đúng và nhanh.
```

Tại sao tồi: "Đúng" nghĩa là gì? "Nhanh" bao nhiêu? Không verify được = không biết khi nào "xong".

### 4. BRD scope quá rộng, không có Out of Scope

```markdown
**In Scope:** Sync tất cả blockchain, tất cả loại transaction, 
có analytics dashboard, có export PDF, support mobile...
```

Tại sao tồi: Scope vô tận. 1 feature phát sinh biến thành 1 Epic mới. Không ai biết khi nào xong.

---

## 📋 Template trống (copy để dùng)

```markdown
---
title: BRD — [Tên feature]
version: 1.0
status: Nháp
created_at: [YYYY-MM-DD]
author: [github-id]
project: [Tên dự án]
---

# BRD — [Tên feature]

## 1. Executive Summary

### 1.1 Problem
[Vấn đề gì đang xảy ra? Ảnh hưởng ai? Có con số không?]

### 1.2 Solution
[Giải pháp gì? Mô tả ngắn gọn ở mức business, không đi vào kỹ thuật]

### 1.3 Success Definition
[Khi nào coi là thành công? Metric đo được]

---

## 3. Business Requirements

### BR-XXX: [Tên requirement]

**Requirement Statement:**
> Hệ thống **MUST** [hành vi cụ thể] để [mục tiêu business].

**Business Rationale:**
[Tại sao cần? Nếu không có thì sao?]

**Acceptance Criteria:**
- [ ] [Tiêu chí 1 — cụ thể, đo được]
- [ ] [Tiêu chí 2]
- [ ] [Tiêu chí 3]

**Priority:** [Critical / High / Medium / Low]

---

## 2.4. In Scope / Out of Scope

**In Scope:**
- [Cái gì SẼ LÀM trong feature này]

**Out of Scope:**
- [Cái gì KHÔNG LÀM + lý do (Phase 2 / khác Epic / chưa cần)]
```

---

## Nguyên tắc chung

| Không nên | Nên |
|-----------|-----|
| Gửi BRD qua Telegram | Commit vào repo, tạo PR |
| "Sync transaction" (1 câu) | Problem + Solution + Criteria (3 section) |
| "Phải hoạt động tốt" | "Fetch history trong ≤ 30 giây, retry 3 lần" |
| Không có Out of Scope | Ghi rõ "Phase 2" / "Khác Epic" / "Chưa cần" |
| Chờ PM viết | Dev viết draft 15 phút, commit PR, thông báo team |

---

## Liên kết

- [Quy trình viết BRD](dev-write-brd-process.md) — Flowchart, bảng bước
- [Cẩm nang viết BRD](dev-write-brd-handbook.md) — Cách viết từng section
- [BRD Template gốc](../../../bootstrap/skills/write-prd/templates/brd-template.md) — Template đầy đủ
- [Dev Tasks Logs](../dev-tasks-logs/dev-tasks-logs-process.md) — BRD → tasks
