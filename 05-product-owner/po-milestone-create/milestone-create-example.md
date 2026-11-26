---
type: delivery
tags: [example, milestone, estimate, board, google-sheet]
created-date: 2026-11-26
updated-date: 2026-11-26
author: anderson
status: Nháp
---

# Tạo Milestone — Mẫu Milestone & Task

**Người chịu trách nhiệm:** PO dự án
**Cập nhật lần cuối:** 2026-11-26

> Mỗi mẫu có một bản chưa tốt đặt trước và một bản tốt đặt sau, để so trực tiếp. Mọi thứ trên board viết bằng tiếng Anh, vì khách đọc board qua bản PDF mỗi ngày. Cách nghĩ đằng sau từng mẫu nằm ở [Cẩm nang Tạo Milestone](./milestone-create-handbook.md).

---

## 1. Milestone

### Mẫu chưa tốt

```
Milestones
----------
M1
Backend
Week 2
Fix bugs
Misc
```

Khách đọc không biết `M1` là tính năng gì. `Backend` và `Fix bugs` là loại công việc, không phải thứ khách nhận được. `Week 2` trùng với tên tab sprint. `Misc` là nơi task không thuộc về đâu.

### Mẫu tốt

Đặt lại tên cho các Milestone đang có trên board Koto và Flux. Cột bên trái là tên đang dùng, cột bên phải là tên nên dùng.

| Tên đang dùng | Tên nên dùng |
|---|---|
| `Lighter - Trading` | `Lighter Platform Integration` |
| `Monochrome Trading Competition` | `Monochrome Trading Competition Launch` |
| `Custom Referral Link` | `Custom Referral Link Rollout` |
| `Trading Audit` | `Trading UI Audit Fixes` |
| `Vaults, sign-in and contracts` | `Vault Contracts & Privy Sign-in Setup` |
| *(dự án audit)* | `Smart Contract Audit Report Cover` |

Đọc `Lighter Platform Integration` là cả team hình dung ra ngay: kết nối tài khoản, đặt lệnh, nạp rút, test trên mainnet với sàn Lighter. Còn `Lighter - Trading` chỉ cho biết chủ đề, không cho biết phải làm gì với nó.

### Danh sách task của một Milestone — mẫu chưa tốt

Ba lỗi cơ bản hay gặp nhất khi tách một Milestone thành task: chỉ có luồng chạy đúng mà thiếu xử lý lỗi, thiếu task UX/UI, thiếu task QA.

| Milestones | Tasks | Assignee | Estimate (h) |
|---|---|---|---|
| Lighter Platform Integration | Connect venue, account and market selection | Shota | 4 |
| Lighter Platform Integration | Market Buy/Sell: submit market orders | Shota | 4 |
| Lighter Platform Integration | Limit Orders: submit limit orders | Shota | 4 |
| Lighter Platform Integration | Withdraw from Lighter to Koto | Dennis | 4 |

Toàn bộ là luồng người dùng làm đúng và mạng chạy ổn. Không có task nào cho lúc lệnh bị từ chối, sàn trả lỗi rate-limit, hay rút tiền bị treo giữa chừng. Không có task UX/UI, nên dev tự nghĩ ra giao diện cho trạng thái lỗi và trạng thái rỗng. Không có task QA, nên đến ngày release mới thấy chưa ai test trên mainnet.

### Danh sách task của một Milestone — mẫu tốt

| Milestones | Tasks | Assignee | Estimate (h) |
|---|---|---|---|
| Lighter Platform Integration | UX/UI: order ticket, positions panel, error and empty states | Việt | 4 |
| Lighter Platform Integration | Connect venue, account and market selection | Shota | 4 |
| Lighter Platform Integration | Market Buy/Sell: submit market orders, slippage protection, execution states | Shota | 4 |
| Lighter Platform Integration | Limit Orders: submit limit orders, handle partial fills | Shota | 4 |
| Lighter Platform Integration | Error handling: rejected orders, rate-limits, venue downtime messages | Shota | 3 |
| Lighter Platform Integration | Withdraw from Lighter to Koto, with recovery when a transfer gets stuck | Dennis | 4 |
| Lighter Platform Integration | QA: smoke test account, funding and trading on mainnet | Kate | 3 |
| Lighter Platform Integration | Code Refactor: clean up order state handling | Shota | 2 |

Milestone có đủ task UX/UI, QA, Code Refactor theo Board Rule, và có task riêng cho xử lý lỗi. Mỗi việc nằm ở một dòng, có người nhận, có số giờ, nên khi estimate cả team thấy ngay Milestone này thật sự tốn bao nhiêu công.

---

## 2. Task

### Mẫu chưa tốt

| Milestones | Tasks | Assignee | Status | Progress | Estimate (h) | Expected done date | Notes |
|---|---|---|---|---|---|---|---|
| Lighter Platform Integration | Trading | Shota, Kate | Doing | 50% | | next week | |
| Lighter Platform Integration | fix rounding util + refactor hook | Shota | Pending | 0% | 2 | | |
| Lighter Platform Integration | Order form + API + chart + test | Shota | Todo | 0% | 16 | 2026-11-20 | |

Dòng 1 không ai hiểu "Trading" là việc gì, có 2 người nhận, thiếu Estimate, ngày xong là "next week". Dòng 2 viết bằng ngôn ngữ của dev và đang `Pending` mà Notes trống. Dòng 3 gộp 4 việc thành một task 16 tiếng.

### Mẫu tốt

Phỏng theo board Koto, sprint 16–20/11. Tên task lấy nguyên từ board, số Estimate và Status điền để minh hoạ.

| Milestones | Tasks | Assignee | Status | Progress | Estimate (h) | Expected done date | Notes |
|---|---|---|---|---|---|---|---|
| Lighter Platform Integration | Mainnet Handle: handle rate-limits, verify real book depth/spread aggregation & fee tiers | Shota | Done | 100% | 4 | 2026-11-16 | |
| Lighter Platform Integration | Wire New Trading UI: orderbook, order ticket, order and positions data | Shota | Done | 100% | 4 | 2026-11-17 | |
| Lighter Platform Integration | Smoke Test - Account, Funding: account creation/L2 onboarding, deposit, internal transfer, withdraw | Kate | Done | 100% | 3 | 2026-11-17 | Koto → Lighter only (Lighter → Koto pending) |
| Lighter Platform Integration | Smoke Test - Trading: place/cancel limit order with TP/SL | Kate | Doing | 50% | 2 | 2026-11-18 | |
| Trading UI Audit Fixes | [P1] P-1: Show the amount actually sent after step rounding, with a round-up to the next step | Jimmy | Todo | 0% | 2 | 2026-11-25 | |

Mỗi dòng là một việc khách đọc là hiểu, một người nhận, không quá 4 tiếng, có ngày cụ thể. Task QA của Kate có ngày xong sau task dev của Shota. Bug có mức độ `[P1]` ở đầu tên. Notes chỉ ghi khi có điều cần biết.

---

## Liên kết

- [Cẩm nang Tạo Milestone](./milestone-create-handbook.md)
- [Cẩm nang Board](../po-board-create/board-create-handbook.md) — 8 cột
