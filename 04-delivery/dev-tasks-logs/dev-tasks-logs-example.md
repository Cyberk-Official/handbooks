---
type: delivery
tags: [tasks, github, dev, example, ai-driven]
created: 2026-09-01
updated: 2026-09-01
author:
status: Nháp
---

# Mẫu Task trên GitHub — Tốt vs Không Tốt

**Người chịu trách nhiệm:** [Tech Lead]
**Cập nhật lần cuối:** 2026-09-01

> Quy tắc: Mọi task PHẢI link Feature ID (`FR-XXX` / `BR-XXX`). Task do AI tạo, Dev review, push bằng GH CLI.

---

## ✅ Mẫu TỐT

### 1. AI prompt → Task output (Feature mới)

**Input — Dev prompt AI:**

```
Breakdown FR-003 (JWT Refresh Token) thành tasks cho GitHub Projects.

Context từ PRD:
- FR-003: "Implement JWT refresh token endpoint"
- POST /api/auth/refresh nhận refresh token, trả access token mới
- Refresh token rotation (revoke old, issue new)  
- Return 401 nếu token invalid/expired
- Tech: Node.js, Express, jsonwebtoken, PostgreSQL
- Branch naming: feat/FR-XXX-short-desc
- Constraint: task < 4h, 1 assignee
```

**Output — AI generates:**

#### Task 1: `[FR-003] Implement refresh token endpoint`

```markdown
## Mục tiêu
Tạo endpoint POST /api/auth/refresh cho FR-003. User gửi refresh token, nhận về access token mới + refresh token mới (rotation).

## Checklist công việc
- [ ] Tạo POST /api/auth/refresh endpoint
- [ ] Validate refresh token (expiry, signature, blacklisted)
- [ ] Generate new access token (15 min expiry)
- [ ] Implement token rotation (issue new refresh token, revoke old)
- [ ] Return proper error codes (401 invalid, 401 expired)

## Tài liệu / Lưu ý
> Feature: FR-003 (JWT Refresh Token) — [link to PRD]
> Branch: `feat/FR-003-refresh-endpoint`
> Estimate: 3h
```

| Field | Giá trị |
|-------|--------|
| Assignees | `@hungdn-cyberk` |
| Target date | `2026-09-05` |
| Labels | `dev` |
| Epic | `User Authentication` |
| Milestone | `W36` |
| Week | `36` |
| Status | `Backlog` |
| Branch | `feat/FR-003-refresh-endpoint` |

#### Task 2: `[FR-003] Write unit tests for refresh token flow`

```markdown
## Mục tiêu
Viết unit tests cho endpoint POST /api/auth/refresh, đảm bảo happy path + error cases.

## Checklist công việc
- [ ] Test case: valid refresh token → new access token + new refresh token
- [ ] Test case: expired refresh token → 401
- [ ] Test case: revoked/blacklisted refresh token → 401
- [ ] Test case: invalid signature → 401
- [ ] Đảm bảo coverage ≥ 80% cho auth module

## Tài liệu / Lưu ý
> Feature: FR-003 (JWT Refresh Token)
> Branch: `feat/FR-003-refresh-tests`
> Depends on: Task 1 (endpoint phải implement trước)
> Estimate: 2h
```

Tốt vì:
- Mỗi task gắn Feature ID `[FR-003]` — trace ngược về PRD
- Title = hành động cụ thể
- Body có acceptance criteria rõ từ PRD
- Branch name follow convention
- Estimate < 4h
- 6 trường bắt buộc đủ

---

### 2. Task Bug fix (gắn Feature ID)

**Title:** `[FR-003] Fix: refresh token not revoked after rotation`

```markdown
## Mục tiêu
Fix bug: old refresh token vẫn valid sau khi rotation. 
Vi phạm acceptance criteria FR-003: "Refresh token rotation (revoke old, issue new)".

## Checklist công việc
- [ ] Add old token to blacklist table sau khi issue new token
- [ ] Add unit test: old token MUST return 401 after rotation
- [ ] Verify trên staging

## Tài liệu / Lưu ý
> Feature: FR-003 (JWT Refresh Token)
> Bug report: #215
> Branch: `fix/FR-003-token-revocation`
> Reproduce: Login → refresh → dùng old refresh token → vẫn thành công (BUG)
```

| Field | Giá trị |
|-------|--------|
| Assignees | `@truonglx-cyberk` |
| Target date | `2026-09-03` |
| Labels | `bug` |
| Epic | `User Authentication` |
| Milestone | `W36` |
| Week | `36` |

Tốt vì:
- Bug gắn Feature ID — biết ngay thuộc feature nào
- Mô tả cụ thể vi phạm acceptance criteria nào
- Có steps to reproduce
- Branch prefix `fix/` thay vì `feat/`

---

### 3. GH CLI — Script push nhiều task

```bash
#!/bin/bash
# Push tasks cho FR-003 lên board
REPO="Cyberk-Official/koto-backend"
PROJECT_NUMBER=1

# Task 1
ISSUE_URL=$(gh issue create \
  --repo $REPO \
  --title "[FR-003] Implement refresh token endpoint" \
  --body-file task1-body.md \
  --label "dev" \
  --assignee "hungdn-cyberk" \
  --milestone "W36" \
  | grep -oE 'https://[^ ]+')

gh project item-add $PROJECT_NUMBER \
  --owner Cyberk-Official \
  --url "$ISSUE_URL"

echo "✅ Task 1 created: $ISSUE_URL"

# Task 2
ISSUE_URL=$(gh issue create \
  --repo $REPO \
  --title "[FR-003] Write unit tests for refresh token flow" \
  --body-file task2-body.md \
  --label "dev" \
  --assignee "hungdn-cyberk" \
  --milestone "W36" \
  | grep -oE 'https://[^ ]+')

gh project item-add $PROJECT_NUMBER \
  --owner Cyberk-Official \
  --url "$ISSUE_URL"

echo "✅ Task 2 created: $ISSUE_URL"
```

Tốt vì:
- Automation — chạy 1 lần push nhiều task
- Body từ file markdown — dễ review trước khi push
- Reproducible — chạy lại được nếu cần

---

## ❌ Mẫu KHÔNG TỐT

### 1. Task không có Feature ID ("trôi nổi")

```
Title: "Implement authentication"
Body: (trống)
Assignees: (trống)
Feature ID: ❌ KHÔNG CÓ
```

Tại sao tồi: Task này thuộc feature nào? Ai yêu cầu? Acceptance criteria là gì? Scope đến đâu? Không ai trả lời được → code sai direction, sprint fail.

### 2. Task tạo manual trên GitHub UI

```
Dev mở GitHub → New Issue → gõ title → quên điền Labels, Epic, Week → Submit
```

Tại sao tồi: Manual = thiếu trường, không nhất quán, không audit trail. Sprint Board filter theo Week — task này không xuất hiện. Bugs Board filter theo `bug` — task này cũng không xuất hiện.

### 3. Skip review AI output

```
AI output 10 tasks → Dev: "Looks good" → push hết
→ 3 task ngoài scope, 2 task 8 giờ, 1 task duplicate
```

Tại sao tồi: AI hallucinate — thêm feature không có trong PRD. Task 8 giờ không ai track được. Sprint bị phình.

### 4. Prompt AI thiếu context

```
"Tạo tasks cho feature login"
→ AI output: 15 tasks bao gồm OAuth, 2FA, SSO, biometric...
→ PRD chỉ yêu cầu email + password login
```

Tại sao tồi: Prompt không có Feature ID, không có acceptance criteria, không có scope → AI tưởng tượng ra scope. 15 tasks khi chỉ cần 4.

---

## 📋 Template trống (copy để dùng)

### AI Prompt template

```
Breakdown [FR-XXX] ([Tên feature]) thành tasks cho GitHub Projects.

Context từ PRD:
- [FR-XXX]: "[Mô tả từ PRD]"
- Acceptance Criteria:
  - [Criteria 1]
  - [Criteria 2]
- Tech: [stack]
- Database: [DB + relevant schema]
- Branch naming: feat/FR-XXX-short-desc (hoặc fix/FR-XXX-short-desc)
- Constraint: task < 4h, 1 assignee

Output yêu cầu cho MỖI task:
- Title: [FR-XXX] + hành động
- Body: Mục tiêu + Checklist công việc + Tài liệu
- Labels, Epic, Milestone, Week
- Branch name
- Estimate (giờ)
```

### Task body template

```markdown
## Mục tiêu
[1-2 câu: kết quả cần đạt. Reference Feature ID]

## Checklist công việc
- [ ] [Đầu việc cụ thể 1]
- [ ] [Đầu việc cụ thể 2]
- [ ] [Đầu việc cụ thể 3]

## Tài liệu / Lưu ý
> Feature: [FR-XXX] ([Tên feature]) — [link to PRD]
> Branch: `[feat/FR-XXX-short-desc]`
> Estimate: [X]h
```

### GH CLI — single task

```bash
gh issue create \
  --repo Cyberk-Official/[repo-name] \
  --title "[FR-XXX] [Hành động + đối tượng]" \
  --body "## Mục tiêu
[Kết quả cần đạt — reference FR-XXX]

## Checklist công việc
- [ ] [Đầu việc 1]
- [ ] [Đầu việc 2]

## Tài liệu / Lưu ý
> Feature: FR-XXX
> Branch: feat/FR-XXX-short-desc" \
  --label "dev" \
  --assignee "[github-id]" \
  --milestone "[W-number]"
```

### Checklist review trước khi push

```markdown
- [ ] Feature ID (FR-XXX / BR-XXX) present in title & body
- [ ] Title = [FR-XXX] + hành động + đối tượng
- [ ] Body: Mục tiêu + Checklist + Tài liệu
- [ ] Task ≤ 4 giờ
- [ ] Branch name: feat/FR-XXX-short-desc
- [ ] Assignee: GitHub ID chính xác
- [ ] Target date: YYYY-MM-DD
- [ ] Labels, Epic, Milestone, Week đủ
- [ ] Scope không vượt FR/BR trong PRD
- [ ] Status = Backlog
```

---

## Nguyên tắc chung

| Không nên | Nên |
|-----------|-----|
| Title: "Authentication" | Title: "[FR-003] Implement refresh token endpoint" |
| Task không có Feature ID | Mọi task gắn `FR-XXX` hoặc `BR-XXX` |
| Prompt AI: "tạo tasks cho login" | Prompt AI: "Breakdown FR-003 với acceptance criteria + constraints" |
| Approve AI output không đọc | Review scope, estimate, fields, hallucination |
| Tạo task click tay trên GitHub UI | Push bằng `gh issue create` + `gh project item-add` |
| Skip PRD, tạo task trước | Tạo/kiểm tra PRD trước, có Feature ID rồi mới tạo task |
| Task 8 giờ "để nguyên" | Breakdown thành 2-3 task < 4h |

---

## Liên kết

- [Quy trình tạo Task](dev-tasks-logs-process.md) — Flowchart, bảng bước, quy tắc cứng
- [Cẩm nang tạo Task](dev-tasks-logs-handbook.md) — Cách nghĩ khi prompt AI, review, push
- [AI Instruction](dev-tasks-logs-ai-instruction/dev-tasks-instruction.md) — Quy tắc cho AI
- [Board Handbook](../board-handbook/board-handbook.md) — Tổng quan quản lý dự án
- [PRD/BRD Templates](../../../bootstrap/skills/write-prd/templates/) — Viết requirement
