---
title: "[Project Name] — Feature Request BRD & Expansion Proposal: [Feature Name]"
type: delivery
tags: [templates, project-management, client-management]
project: "[Project Name]"
client: "[Client Name]"
request-id: "FR-001"
author: "[PO Name]"
tech-lead: "[Tech Lead Name]"
approver: "[Anderson / Brian]"
created-date: 2026-11-19
updated-date: 2026-11-26
status: Nháp
---

<!--
================================================================================
HƯỚNG DẪN SỬ DỤNG CHO PO & TECH LEAD (XÓA KHỐI NÀY TRƯỚC KHI XUẤT PDF GỬI KHÁCH)
================================================================================
1. BƯỚC UNDERSTAND (PO):
   - Ngay sau buổi họp làm rõ yêu cầu với khách, PO điền Mục 1, 2 và 3.
   - Gửi link/bản nháp phần BRD này kèm tin nhắn báo quy trình tiếp theo & đơn giá chuẩn $25/giờ.

2. BƯỚC ESTIMATE — DEADLINE ≤ 24H (Tech Lead):
   - PO & Tech Lead tách Milestone thành task và estimate theo handbook/05-product-owner/po-milestone-create/
     (danh sách task giữ nội bộ, KHÔNG đưa vào file gửi khách).
   - Tech Lead gom task thành 4 hạng mục và điền tại Mục 4 (4.1 → 4.4).
   - QUAN TRỌNG: Cộng sẵn buffer 30%–50% thẳng vào số giờ của từng vai trò ở bảng 4.4.
     TUYỆT ĐỐI KHÔNG tạo dòng chữ "Buffer" hay ghi phần trăm buffer ra tài liệu này!
   - Nếu ước lượng vượt quá 24h chưa xong → Báo ngay cho Anderson.

3. BƯỚC APPROVAL (AM — Anderson / Brian):
   - PO gửi file đã có Mục 1–4 cho AM duyệt mức phí ở Mục 5.1:
     • Trường hợp Tính phí: Giữ bảng "Option 1 — Paid Expansion", áp dụng mẹo làm tròn xuống
       khoảng 10%–15% kèm ghi chú thân thiện (xóa bảng Miễn phí).
     • Trường hợp Miễn phí: Giữ bảng "Option 2 — Complimentary Support", vẫn giữ nguyên số giờ
       và giá trị quy đổi ($25/h) để khách thấy rõ giá trị được tài trợ (xóa bảng Tính phí).

4. BƯỚC PROPOSAL & EMAIL CONFIRM (PO):
   - Dùng tài liệu hoàn chỉnh này để share màn hình trình bày trực tiếp cho khách.
   - Khi khách gật đầu đồng ý chi phí & chọn Option lịch trình, xuất file này ra PDF bằng skill
     export-pdf và đính kèm vào Email chốt confirm để khách reply "Confirmed".
================================================================================
-->

# Feature Expansion Proposal & BRD: `[Feature Name]`

| Project | `[Project Name, e.g., Koto]` | Request ID | `FR-[001]` |
|---------|------------------------------|------------|------------|
| **Client** | `[Client Name, e.g., Jon]` | **Date** | `[YYYY-MM-DD]` |
| **Prepared By** | `[PO Name]`, Product Owner | **Tech Review** | `[Tech Lead Name]`, Tech Lead |
| **Status** | `Draft / Pending Client Confirmation / Confirmed` | **Standard Rate** | `$25 USD / hour` |
| **Milestone** | `[Object + Action, e.g., Referral & Fee Rebate Rollout]` | | |

---

## 1. Executive Summary

### 1.1. Business Context & Opportunity
`[2–3 sentences describing why the client wants this feature now and what business value it unlocks. Example: "To accelerate organic user acquisition right after the v1 launch, Koto wants to reward early traders who invite their network with an automated trading-fee rebate."]`

### 1.2. Proposed Solution Overview
`[2–3 sentences summarizing how the feature works from a user perspective — no deep code details yet. Example: "Introduce a single-tier Referral & 20% Fee Rebate module where verified users receive a unique invite link, track referred friends, and earn daily USDC rebates from their invitees' trading fees."]`

### 1.3. Relationship to Current Contract Scope
This capability introduces a net-new user flow outside the baseline `[v1.0 Scope of Work / Proposal dated YYYY-MM-DD]`. Documenting and scoping it separately ensures full engineering quality while protecting the committed launch schedule.

---

## 2. Scope Boundary

### 2.1. In Scope (Included in This Expansion)
- `[Item 1 — e.g., Unique referral code & shareable invite link generation per verified user]`
- `[Item 2 — e.g., Referral dashboard displaying invited users, volume, and daily USDC rebates]`
- `[Item 3 — e.g., Automated daily 00:00 UTC rebate calculation (20% of net trading fee)]`
- `[Item 4 — e.g., Admin overview table to monitor payouts and flag self-referrals]`

### 2.2. Out of Scope (Excluded — Future Phases)
- `[Excluded item 1 — e.g., Multi-tier / MLM commission structures (Tier 2, Tier 3) — deferred to Phase 2]`
- `[Excluded item 2 — e.g., Custom influencer promo codes with variable commission rates]`

---

## 3. Business Requirements & Acceptance Criteria

### BR-001: `[Requirement Title — e.g., Referral Attribution on User Signup]`

**Requirement Statement:**
> The system **MUST** `[specific action/behavior]` so that `[business outcome]`.

**Business Rules & Constraints:**
- `[Rule 1 — e.g., A referee can only be linked to one referrer permanently at signup.]`
- `[Rule 2 — e.g., Self-referral using the same IP/device fingerprint or linked wallet is blocked from earning rebates.]`

**Acceptance Criteria:**
- [ ] `[Criterion 1 — measurable & testable]`
- [ ] `[Criterion 2 — measurable & testable]`
- [ ] `[Criterion 3 — error/edge case handling]`

**Key Scenarios:**

```gherkin
Scenario: Happy path — Valid referral signup and rebate accrual
  Given User A has an active referral link
  When  new User B signs up via User A's link and completes a trade paying $10 in fees
  Then  User B is permanently attributed to User A
    And User A accrues a $2.00 USDC rebate in the next 00:00 UTC settlement cycle

Scenario: Edge case — Self-referral attempt is rejected
  Given User A attempts to register a second account using their own referral code
  When  the system detects matching wallet funding source or device fingerprint
  Then  fee rebate accrual is flagged and paused for admin review
```

---

### BR-002: `[Requirement Title — Add more BR blocks as needed]`

**Requirement Statement:**
> The system **MUST / SHOULD** `[specific action/behavior]` so that `[business outcome]`.

**Acceptance Criteria:**
- [ ] `[Criterion 1]`
- [ ] `[Criterion 2]`

---

## 4. Technical Impact & Effort Breakdown

> *Completed by Cyberk Tech Lead — covers design, architecture, codebase side effects, and full team effort.*

### 4.1. UX/UI Design Expansion
- `[List all new screens, modals, responsive states, and components needed]`
- *Example: 4 new screens in Figma (Referral Hub, Share Invite Modal, Rebate Earnings History, Admin Payout Table) + empty/loading/error states.*

### 4.2. System Architecture Changes
- `[List new database tables, schema migrations, background workers/cronjobs, queues, or 3rd-party services — or state "No major architectural changes required"]`
- *Example: 2 new database tables (`referrals`, `rebate_ledgers`) + idempotent daily 00:00 UTC settlement worker.*

### 4.3. Source Code & Side Effects on Existing Flows
- `[List existing modules/APIs touched, potential side effects, security checks, and regression testing required]`
- *Example: Modify existing onboarding signup flow to capture attribution tokens; update trade-matching fee splitter without adding latency to order execution; full QA regression on authentication and fee ledger.*

### 4.4. Team Effort Summary

<!-- LƯU Ý NỘI BỘ CHO TECH LEAD: Số giờ điền dưới đây PHẢI ĐÃ GỘP SẴN BUFFER 30%–50%. Không ghi chữ "buffer" vào bảng! -->

| Workstream | Key Activities | Effort (Hours) |
|------------|----------------|---------------:|
| **UX/UI Design** | User flow mapping, Figma screens & component states | `[e.g., 6]` h |
| **Backend & System** | Schema migration, API endpoints, settlement worker, security rules | `[e.g., 16]` h |
| **Frontend Integration** | UI implementation, state management, API binding | `[e.g., 10]` h |
| **QA & Regression** | New flow verification + regression testing on impacted modules | `[e.g., 6]` h |
| **Total Team Effort** | **End-to-end delivery from Design to Production** | **`[e.g., 38]` hours** |

---

## 5. Expansion Cost & Delivery Options

<!-- PO CHỌN 1 TRONG 2 BẢNG DƯỚI ĐÂY THEO PHÊ DUYỆT CỦA AM Ở BƯỚC APPROVAL (XÓA BẢNG CÒN LẠI) -->

### 5.1. Expansion Budget *(Trường hợp 1: Có tính phí — giữ bảng này, xóa bảng Trường hợp 2)*

| Item | Calculation / Notes | Amount (USD) |
|------|---------------------|-------------:|
| **Standard Expansion Estimate** | `[38]` hours × `$25 / hour` *(standard expansion rate)* | `$[950]` |
| **Partner Courtesy Adjustment** | Rounded down (~10%–15%) — `[e.g., coffee is on you next visit! ☕]` | `-$[150]` |
| **Final Agreed Expansion Fee** | **Billed in `[next project invoice / upon sign-off]`** | **`$[800]` USD** |

### 5.1. Expansion Budget *(Trường hợp 2: Công ty tài trợ Miễn phí — giữ bảng này, xóa bảng Trường hợp 1)*

| Item | Calculation / Notes | Amount (USD) |
|------|---------------------|-------------:|
| **Standard Expansion Value** | `[24]` hours × `$25 / hour` *(standard expansion rate)* | `$[600]` |
| **Cyberk Strategic Sponsorship** | Covered on the house to support `[e.g., upcoming investor demo]` | `-$[600]` |
| **Final Payable Fee** | **Complimentary — Sponsored by Cyberk** | **`$0` USD** |

---

### 5.2. Delivery Schedule Options

To protect your current release goals, please select your preferred delivery path:

- **[ ] Option A — Protect Current Launch *(Recommended)*:**
  - Current release (`[v1.0]`) launches on schedule: **`[Day, Month DD, YYYY]`**
  - `[Feature Name]` ships immediately after as `[v1.1]`: **`[Day, Month DD, YYYY]`**

- **[ ] Option B — Merge into Current Release:**
  - `[Feature Name]` is built directly into the current release.
  - Revised target launch date shifts by `[X]` working days to: **`[Day, Month DD, YYYY]`**

---

## 6. Formal Confirmation & Sign-Off

> Work begins immediately once confirmation is received via email reply (**"Confirmed"**) referencing this document.

| Field | Confirmed Details |
|-------|-------------------|
| **Selected Schedule Option** | `[Option A / Option B]` |
| **Agreed Expansion Fee** | **`$[Amount]` USD** |
| **Client Approver** | `[Client Name & Email]` |
| **Cyberk Product Owner** | `[PO Name & Email]` |
| **Confirmation Date** | `[YYYY-MM-DD — Confirmed via Email]` |
