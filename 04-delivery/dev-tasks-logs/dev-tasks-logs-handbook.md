---
type: delivery
tags: [tasks, github, dev, handbook, ai-driven, spec-driven]
created: 2026-09-01
updated: 2026-09-01
author:
status: Nháp
---

# Tạo Task trên Board — Cẩm nang cho Dev

**Người chịu trách nhiệm:** [Tech Lead]
**Cập nhật lần cuối:** 2026-09-01
**Trạng thái:** Nháp

Bạn cần tạo task cho một feature mới. Ở Cyberk, task không phải là thứ bạn nghĩ ra rồi gõ tay lên board — mà là **sản phẩm của một quy trình phân tích**: từ PRD/BRD → AI breakdown → Dev review → AI push. Trang này giúp bạn hiểu **cách nghĩ** ở từng bước.

---

## Dự án chưa có PRD/BRD — làm gì?

Không có PRD = không có Feature ID = không tạo được task. Nhưng đừng hoảng — tạo BRD không mất nhiều thời gian nếu bạn hiểu scope.

**Hai lựa chọn:**

1. **Tự tạo BRD** — dùng [BRD template](../../../bootstrap/skills/write-prd/templates/brd-template.md) và [write-prd skill](../../../bootstrap/skills/write-prd/skill.md). Viết tối thiểu: Executive Summary + 1-2 Business Requirements (BR-001, BR-002) với Gherkin scenarios. 30 phút là đủ cho một feature vừa.
2. **Yêu cầu PM/PL bổ sung** — nếu scope quá lớn hoặc bạn không đủ business context. Gửi message rõ ràng: "Feature X chưa có PRD, tôi cần ít nhất Feature ID + acceptance criteria để tạo task."

**✅ Cách tốt:**

```
"Feature Authentication chưa có PRD. Tôi đã tạo BRD draft với 3 BR 
(BR-001: Login, BR-002: Register, BR-003: Password Reset) kèm Gherkin scenarios.
Anh review và approve giúp: [link to BRD file]"
```

Tại sao tốt: Chủ động tạo draft, có scope rõ ràng, có Gherkin kiểm chứng được. PM chỉ cần review, không phải viết từ đầu.

**❌ Cách tồi:**

```
"Anh ơi feature Auth cần PRD, anh viết giúp em nhé"
```

Tại sao tồi: Đẩy toàn bộ việc cho PM. Dev hiểu kỹ thuật hơn PM — Dev viết draft nhanh hơn và chính xác hơn.

---

## Cách prompt AI để breakdown feature thành tasks?

Sau khi có Feature ID, bạn prompt AI với **context đầy đủ**. AI cần biết: feature là gì, acceptance criteria, tech stack, constraints. Càng nhiều context → output càng chính xác.

**✅ Cách tốt — prompt có context:**

```
Tôi cần breakdown feature FR-003 (JWT Refresh Token) thành tasks cho GitHub Projects.

Context:
- PRD Feature: FR-003 "Implement JWT refresh token endpoint"
- Acceptance Criteria:
  - POST /api/auth/refresh nhận refresh token, trả access token mới
  - Refresh token rotation (revoke old, issue new)
  - Return 401 nếu token invalid/expired
- Tech stack: Node.js, Express, jsonwebtoken
- Database: PostgreSQL (refresh token table đã có schema)
- Branch naming: feat/FR-XXX-short-desc
- Constraint: mỗi task < 4 giờ, 1 assignee

Output yêu cầu: danh sách tasks với title, body (Mục tiêu + Checklist), 
labels, epic, milestone, branch name, estimate.
```

Tại sao tốt: AI có đủ context để output chính xác. Có acceptance criteria → AI biết scope. Có constraints → AI không tạo task 8 giờ.

**❌ Cách tồi — prompt thiếu context:**

```
Tạo tasks cho feature authentication
```

Tại sao tồi: "Authentication" là cả module — login, register, reset password, 2FA, OAuth... AI không biết scope nào, sẽ output hàng chục task hoặc bỏ sót. Không có Feature ID → task trôi nổi.

> **Tip:** Đọc file [AI Instruction](dev-tasks-logs-ai-instruction/dev-tasks-instruction.md) để biết chính xác AI cần input gì và output format.

---

## Review output của AI — kiểm tra gì?

AI không hoàn hảo. Output cần được kiểm tra trước khi push lên board. Checklist nhanh:

| Kiểm tra | Cách verify | Red flag |
|----------|-------------|----------|
| **Scope đúng FR** | So sánh task list với acceptance criteria trong PRD | Task vượt scope, hoặc thiếu criteria |
| **Task < 4 giờ** | Đọc checklist trong body — quá nhiều item? | Body có > 7 checklist items → tách task |
| **Branch name đúng convention** | Pattern: `feat/FR-XXX-short-desc` hoặc `fix/FR-XXX-short-desc` | Thiếu Feature ID, dùng dấu cách, quá dài |
| **6 trường đủ** | Assignees, Target date, Labels, Epic, Milestone, Week | Trường nào trống → bổ sung |
| **Title có Feature ID** | Pattern: `[FR-XXX] Hành động + đối tượng` | Thiếu `[FR-XXX]`, title là danh từ |
| **Không hallucinate** | Feature không có trong PRD mà AI tự thêm | "Implement 2FA" khi PRD chỉ yêu cầu login |

**✅ Cách review tốt:**

```
AI output 5 tasks cho FR-003:
1. [FR-003] Implement refresh token endpoint ✅ (scope đúng, 2h)
2. [FR-003] Implement token rotation logic ✅ (scope đúng, 2h)
3. [FR-003] Add refresh token validation middleware ✅ (scope đúng, 1h)
4. [FR-003] Write unit tests for refresh flow ✅ (scope đúng, 3h)
5. [FR-003] Implement OAuth2 integration ❌ → Hallucination! PRD không yêu cầu OAuth2

→ Loại bỏ task 5, approve 4 task còn lại.
```

**❌ Cách review tồi:**

```
"Looks good" → approve hết không đọc
```

Tại sao tồi: AI có thể thêm task ngoài scope, miss acceptance criteria, hoặc tạo task 8 giờ. "Looks good" không phải review.

---

## AI output bị sai/thiếu — xử lý thế nào?

Iterate. Không cần bỏ toàn bộ output — chỉnh prompt và chạy lại phần bị sai.

**Chiến lược iterate:**

1. **Sai scope** → Bổ sung acceptance criteria cụ thể hơn trong prompt
2. **Task quá to** → Thêm constraint: "Mỗi task tối đa 3 checklist items"
3. **Thiếu task** → Gợi ý: "Cần thêm task cho error handling / testing / migration"
4. **Branch name sai** → Cho ví dụ đúng trong prompt
5. **3 lần AI vẫn sai** → Dev tự viết task, ghi note "AI-assisted, manually refined"

> **Quy tắc vàng:** Đừng sửa output AI bằng cách click tay trên GitHub UI. Sửa prompt → re-generate → push bằng CLI. Giữ nguyên quy trình automation.

---

## Push task lên board bằng GH CLI — cách nào?

Sau khi review xong, dùng GH CLI để push. Không click tay trên GitHub UI.

**Bước 1: Tạo issue**

```bash
gh issue create \
  --repo Cyberk-Official/[repo-name] \
  --title "[FR-003] Implement refresh token endpoint" \
  --body "## Mục tiêu
Tạo endpoint POST /api/auth/refresh cho FR-003.

## Checklist công việc
- [ ] Tạo POST /api/auth/refresh endpoint
- [ ] Validate refresh token
- [ ] Implement token rotation
- [ ] Return 401 nếu invalid

## Tài liệu / Lưu ý
> Feature: FR-003 (JWT Refresh Token)
> Branch: feat/FR-003-refresh-token" \
  --label "dev" \
  --assignee "hungdn-cyberk" \
  --milestone "W36"
```

**Bước 2: Thêm vào Project Board**

```bash
# Lấy issue number từ output bước 1
gh project item-add [PROJECT_NUMBER] \
  --owner Cyberk-Official \
  --url https://github.com/Cyberk-Official/[repo-name]/issues/[ISSUE_NUMBER]
```

**Bước 3: Set fields trên Project**

```bash
# Set Week, Epic, Target date... qua GraphQL hoặc gh project item-edit
gh project item-edit [PROJECT_NUMBER] \
  --owner Cyberk-Official \
  --id [ITEM_ID] \
  --field-id [FIELD_ID] \
  --text "36"
```

> **Tip:** Nếu có nhiều task, viết script loop. AI có thể sinh script cho bạn — xem [mẫu trong Example](dev-tasks-logs-example.md).

---

## Khi nào đổi trạng thái task?

Board chỉ có giá trị khi trạng thái phản ánh đúng thực tế.

```
Backlog → Todo:      Khi task được approve vào Sprint (Lead kéo, hoặc Dev tự kéo nếu đã confirm)
Todo → In Progress:  Khi BẮT ĐẦU code — tạo branch và viết dòng code đầu tiên
In Progress → Done:  Khi PR được MERGED (theo Git Policy: 1 Branch = 1 Task)
```

**✅ Cách tốt:** Kéo In Progress khi `git checkout -b feat/FR-003-refresh-token`. Kéo Done khi PR merged.

**❌ Cách tồi:** Kéo hết sang In Progress từ đầu tuần "cho có task". Task "In Progress" 5 ngày = red flag.

---

## Task kéo dài hơn dự kiến thì làm gì?

1. Task ước lượng 3h nhưng đã code 2h mà mới xong 30%
2. → **Ngay lập tức:** comment trong issue giải thích tại sao
3. → **Nếu > 4h:** tách task, phần chưa xong tạo task mới (có Feature ID)
4. → Báo Lead trong Daily standup hoặc qua Telegram
5. → Cập nhật vào Daily Report (Risk section)

---

## Tóm lại

| Bước | Ai | Output |
|------|----|--------|
| 1. Kiểm tra PRD/BRD | Dev | Feature ID (`FR-XXX`) confirmed |
| 2. AI soạn tasks | AI + Dev | Draft task list + branch names |
| 3. Dev review | Dev | Approved task list (scope, estimate, fields OK) |
| 4. AI push lên board | AI | Tasks trên board, status = Backlog |

| Câu hỏi | Trả lời nhanh |
|---------|---------------|
| Chưa có PRD? | Tự tạo BRD hoặc yêu cầu PM. Không skip |
| Prompt AI thế nào? | Feature ID + acceptance criteria + tech stack + constraints |
| Review output AI gì? | Scope đúng FR, task < 4h, 6 trường đủ, không hallucinate |
| Push bằng gì? | `gh issue create` + `gh project item-add`. Không click tay |

---

## Liên kết

- [Quy trình tạo Task](dev-tasks-logs-process.md) — Flowchart, bảng bước, quy tắc cứng
- [Mẫu Task tốt/tồi](dev-tasks-logs-example.md) — Template copy-paste + GH CLI commands
- [AI Instruction](dev-tasks-logs-ai-instruction/dev-tasks-instruction.md) — Quy tắc cho AI breakdown
- [Board Handbook](../board-handbook/handbook.md) — Tổng quan quản lý dự án
- [PRD/BRD Templates](../../../bootstrap/skills/write-prd/templates/) — Template viết requirement
- [Git Policy](../../../policy/dev-policy/source-code-and-git.md) — Branch naming, 1 Branch = 1 Task
- [Daily Report](../dev-daily-report/daily-report-handbook.md) — Task trên board → report cho khách hàng
