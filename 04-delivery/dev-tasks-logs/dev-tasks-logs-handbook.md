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

## Tại sao phải logs tasks đầy đủ và khớp với tài liệu?

Đây là **quy trình engineering của Cyberk** — không phải thêm việc cho bạn, mà là cách giúp bạn **làm ít hơn** mà hiệu quả hơn.

### 1. Traceability — trace mọi thứ dễ dàng

Khi tasks trên board khớp với PRD/BRD (Feature ID), mọi thứ tự liên kết:

```
PRD (FR-003) → Tasks trên board → Branch (feat/FR-003-...) → PR → Code
```

Bạn nhìn 1 task biết ngay nó thuộc feature nào. Nhìn 1 branch biết ngay task nào. Nhìn 1 PR biết ngay scope gì. **Không ai cần hỏi bạn "đang làm gì" — board tự trả lời.**

### 2. Context Engineering — chìa khóa để AI làm việc cho bạn

Đây là phần quan trọng nhất. Khi tasks, docs, code đồng bộ với nhau, bạn đang tạo **context chất lượng cao** — và AI đọc được context đó. Kết quả:

- **AI tạo tasks cho bạn** — từ docs, AI breakdown feature thành tasks với title, description, branch name, estimate. Chuyên nghiệp hơn viết tay.
- **AI viết daily report cho bạn** — AI đọc board, biết bạn làm gì hôm nay, tự viết report. Bạn chỉ duyệt.
- **AI quản lý dự án cho bạn** — sprint nào trễ, task nào block, ai đang overload — AI nhìn board trả lời được ngay.

**Effort quy trình và báo cáo của bạn giảm gần như về 0.** Nhưng điều này chỉ hoạt động khi tasks trên board đầy đủ và khớp với tài liệu. Thiếu context = AI không giúp được = bạn phải làm tay.

### 3. AI-first — AI tạo tasks, không phải bạn

Ở Cyberk, **AI là người tạo tasks**. Bạn là người duyệt. Cụ thể:

- AI đọc PRD/BRD → breakdown thành tasks với title, description, acceptance criteria, branch name
- AI viết description chuyên nghiệp từ docs — đầy đủ Mục tiêu, Checklist, Feature ID
- AI push lên board bằng GH CLI — đúng format, đủ trường, không thiếu sót
- **Bạn chỉ cần: cho AI context đúng → duyệt output → approve**

Nói ngắn: **logs tasks đầy đủ không phải thêm việc — mà là cách để AI làm việc thay bạn.**

---

## Bước 1: Kiểm tra Feature ID

Trước khi prompt AI, bạn cần **Feature ID** (`FR-XXX` hoặc `BR-XXX`) từ PRD/BRD của dự án.

**Có Feature ID rồi?** → Nhảy sang Bước 2.

**Chưa có?** → Hai lựa chọn:
1. **Liên hệ Dev Lead / PM** — nói rõ: "Feature X chưa có trong PRD, tôi cần Feature ID để tạo task."
2. **Tự viết BRD** nếu bạn hiểu rõ yêu cầu — xem [quy trình viết BRD](../dev-write-brd/dev-write-brd-handbook.md). Chỉ cần 3 section, mất 15-30 phút.

> Không tự nghĩ ra Feature ID. Không skip bước này.

---

## Bước 2: Break tasks — cách nghĩ trước khi prompt AI

AI breakdown rất nhanh, nhưng **bạn cần nghĩ trước** để output chính xác. Đây là kinh nghiệm break tasks:

### Nguyên tắc break tasks

| Tình huống | Cách xử lý |
|-----------|-----------|
| **Milestone quá lớn** | Chia thành nhiều Epic nhỏ. Mỗi Epic = 1 tính năng, 1 team < 5 người hoàn thành trong 1 tuần |
| **Task mơ hồ** — "Implement authentication" | Dừng lại. Hỏi rõ Dev Lead / PM / khách hàng: scope đến đâu? Login thôi hay cả register, reset password? |
| **Task estimate > 4 giờ** | Break thành nhiều task con. VD: "Implement auth" → task 1: DB schema, task 2: API endpoint, task 3: unit tests |
| **Nhiều task con (sub-tasks)** | Tạo **parent task** làm task tổng để quản lý domain. VD: `[FR-003] Auth — parent task` rồi sub-tasks bên dưới |
| **Task không có Epic** | Không tạo. Mọi task PHẢI có Epic để trace. Task không có Epic = task trôi nổi, không ai biết nó thuộc feature nào |

### Prompt AI

Context đã có sẵn trong BRD (Feature ID, scope, acceptance criteria) và architect docs (tech stack). **Bạn không cần nhập lại.** Prompt chỉ cần tập trung vào **quy tắc break tasks:**

**✅ Prompt tốt:**

```
Đọc BRD [link file BRD trong repo] và breakdown thành tasks cho GitHub Projects.

Quy tắc:
- Mỗi task < 4 giờ. Nếu lớn hơn, tách thành sub-tasks
- Sub-tasks phải có parent task để quản lý domain
- Mỗi task phải gắn Epic: [tên Epic]
- Branch naming: feat/FR-XXX-short-desc
- Task status mặc định: Backlog
- Output: title, body (Mục tiêu + Checklist), branch name, estimate, label
```

**❌ Prompt tồi:**

```
Tạo tasks cho feature authentication
```

Tồi vì: không link BRD, không có quy tắc break. AI sẽ tự đoán scope, tự đoán cách chia — output không khớp quy trình.

### Khi nào dừng lại hỏi thay vì prompt AI?

- **Bạn đọc PRD mà không hiểu feature cần gì** → hỏi PM/khách hàng
- **Acceptance criteria mơ hồ** ("hoạt động tốt", "nhanh") → yêu cầu con số cụ thể
- **Không biết task này thuộc Epic nào** → hỏi Dev Lead
- **Scope có thể overlap với feature khác** → confirm với team trước

> **Quy tắc vàng:** Thà dừng 5 phút hỏi rõ scope, còn hơn tạo 10 task sai direction rồi phải xoá.

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
- [Board Handbook](../board-handbook/board-handbook.md) — Tổng quan quản lý dự án
- [Daily Report](../dev-daily-report/daily-report-handbook.md) — Task → report cho khách
