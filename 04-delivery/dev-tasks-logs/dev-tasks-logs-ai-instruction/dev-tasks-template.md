---
type: delivery
tags: [tasks, ai-instruction, template]
created: 2026-09-01
updated: 2026-09-01
author:
status: Nháp
---

# Task Output Template — cho AI

> File này là mẫu đầu ra (output template) cho AI khi breakdown feature thành tasks.
> Quy tắc chi tiết: xem [dev-tasks-instruction.md](dev-tasks-instruction.md).

---

## Mẫu output cho 1 task

```markdown
### Task [N]: `[FR-XXX] [Hành động + đối tượng cụ thể]`

**Branch:** `feat/FR-XXX-short-desc`
**Estimate:** [X]h
**Labels:** [dev / design / qa / bug]
**Assignee:** [GitHub ID hoặc "TBD"]

## Mục tiêu
[1-2 câu: kết quả cần đạt được. Reference Feature ID và mô tả ngắn từ PRD.]

## Checklist công việc
- [ ] [Đầu việc cụ thể 1 — đo lường được, verify được]
- [ ] [Đầu việc cụ thể 2]
- [ ] [Đầu việc cụ thể 3]
(3-7 items. Quá ít = chưa rõ scope. Quá nhiều = task quá to, cần tách.)

## Tài liệu / Lưu ý
> Feature: [FR-XXX] ([Tên feature]) — [link to PRD nếu có]
> Branch: `feat/FR-XXX-short-desc`
> Dependencies: [Task nào phải xong trước, hoặc "none"]
> Estimate: [X]h
```

---

## Mẫu bảng tóm tắt (đặt cuối output)

```markdown
## Tóm tắt

| # | Title | Branch | Est. | Labels | Deps |
|---|-------|--------|------|--------|------|
| 1 | [FR-XXX] [Title 1] | feat/FR-XXX-... | [X]h | dev | - |
| 2 | [FR-XXX] [Title 2] | feat/FR-XXX-... | [X]h | dev | Task 1 |
| 3 | [FR-XXX] [Title 3] | feat/FR-XXX-... | [X]h | dev | Task 2 |

**Tổng estimate:** [Sum]h
**Tổng tasks:** [Count]
```

---

## Mẫu GH CLI command (đặt cuối output nếu Dev yêu cầu)

```bash
# Task 1
gh issue create \
  --repo Cyberk-Official/[repo-name] \
  --title "[FR-XXX] [Title]" \
  --body-file task1-body.md \
  --label "[label]" \
  --assignee "[github-id]" \
  --milestone "[W-number]"

# Thêm vào Project Board
gh project item-add [PROJECT_NUMBER] \
  --owner Cyberk-Official \
  --url [ISSUE_URL]
```
