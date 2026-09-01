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

Ở Cyberk, task không phải thứ bạn nghĩ ra rồi gõ tay lên board. Task là **output của AI** — bạn cho AI context, AI breakdown, bạn duyệt, AI push lên board. Trang này giúp bạn làm đúng từng bước.

---

## Tại sao phải có tài liệu trước khi code?

Không phải vì sếp thích đọc tài liệu. Mà vì:

- **Bạn code nhanh hơn** — AI breakdown feature thành tasks chính xác, bạn không phải tự nghĩ "bắt đầu từ đâu"
- **Bạn ít bị hỏi lại** — task có Feature ID, PM nhìn vào biết ngay bạn đang làm gì, không cần hỏi
- **Bạn không code sai direction** — PRD là scope đã được chốt. Không có PRD = code xong mới biết sai
- **Task trên board có nghĩa** — filter Sprint Board, Personal Board, Bugs Board đều hoạt động vì mọi trường đủ

Nói ngắn: **tài liệu trước không phải thêm việc — mà bớt việc.**

---

## Bước 1: Kiểm tra Feature ID

Trước khi prompt AI, bạn cần **Feature ID** (`FR-XXX` hoặc `BR-XXX`) từ PRD/BRD của dự án.

**Có Feature ID rồi?** → Nhảy sang Bước 2.

**Chưa có?** → Hai lựa chọn:
1. **Liên hệ Dev Lead / PM** — nói rõ: "Feature X chưa có trong PRD, tôi cần Feature ID để tạo task."
2. **Tự viết BRD** nếu bạn hiểu rõ yêu cầu — xem [quy trình viết BRD](../dev-write-brd/dev-write-brd-handbook.md). Chỉ cần 3 section, mất 15-30 phút.

> Không tự nghĩ ra Feature ID. Không skip bước này.

---

## Bước 2: Prompt AI breakdown

Cho AI **Feature ID + mô tả + tech stack**. AI sẽ output danh sách tasks, branch names, estimates.

**✅ Prompt tốt:**

```
Breakdown FR-003 (JWT Refresh Token) thành tasks cho GitHub Projects.

Context:
- FR-003: POST /api/auth/refresh, token rotation, return 401 nếu invalid
- Tech: Node.js, Express, PostgreSQL
- Branch naming: feat/FR-XXX-short-desc
- Task < 4 giờ
```

**❌ Prompt tồi:**

```
Tạo tasks cho feature authentication
```

Tồi vì: không có Feature ID, không có scope. AI sẽ tưởng tượng ra 15 task bao gồm OAuth, 2FA, SSO — trong khi PRD chỉ yêu cầu login bằng email.

**Tip:** Càng nhiều context → AI output càng chính xác. Nếu output chưa đúng, bổ sung context rồi chạy lại.

---

## Bước 3: Duyệt — Tasks có khớp plan của bạn không?

AI output danh sách tasks. Bạn chỉ cần trả lời **một câu hỏi:**

> **Danh sách tasks này có khớp với kế hoạch triển khai của tôi không?**

- **Khớp** → approve, sang Bước 4.
- **Không khớp** → sửa prompt, bổ sung context, chạy lại. Hoặc thêm/bớt task cho đúng plan.

Đừng lo AI sai trường hay thiếu field — AI đã được train output đúng format. Việc của bạn là **đảm bảo scope và thứ tự triển khai hợp lý với thực tế dự án.**

---

## Bước 4: AI push lên board

Sau khi duyệt, dùng GH CLI để push. Không click tay trên GitHub UI.

```bash
gh issue create \
  --repo Cyberk-Official/[repo-name] \
  --title "[FR-003] Implement refresh token endpoint" \
  --body-file task-body.md \
  --label "dev" \
  --assignee "hungdn-cyberk" \
  --milestone "W36"
```

Có nhiều task? → Xem [script mẫu trong Example](dev-tasks-logs-example.md).

---

## Khi nào đổi trạng thái task?

```
Backlog → Todo:      Task được approve vào Sprint
Todo → In Progress:  Bạn bắt đầu code (tạo branch)
In Progress → Done:  PR merged
```

Task kéo dài hơn dự kiến? → Comment trong issue, báo Lead, tách task nếu > 4h.

---

## Tóm lại

| Bước | Bạn làm gì |
|------|-----------|
| 1 | Tìm Feature ID trong PRD. Chưa có → hỏi Dev Lead |
| 2 | Prompt AI: Feature ID + context + constraints |
| 3 | Duyệt: tasks có khớp plan của tôi không? |
| 4 | AI push lên board bằng GH CLI |

---

## Liên kết

- [Quy trình tạo Task](dev-tasks-logs-process.md) — Flowchart, quy tắc cứng
- [Mẫu Task tốt/tồi](dev-tasks-logs-example.md) — Template, GH CLI scripts
- [AI Instruction](dev-tasks-logs-ai-instruction/dev-tasks-instruction.md) — Quy tắc cho AI
- [Board Handbook](../board-handbook/handbook.md) — Tổng quan quản lý dự án
- [Daily Report](../dev-daily-report/daily-report-handbook.md) — Task → report cho khách
