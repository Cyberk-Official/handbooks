---
type: delivery
tags: [board, github-projects, ai-instruction, setup, gh-cli]
created: 2026-09-01
updated: 2026-09-01
author: anderson
status: Nháp
---

# Khởi tạo Board GitHub Projects — AI Instruction

> File này dành cho AI đọc, không phải cho người đọc trực tiếp.
> Người đọc: xem [process](../board-create-process.md) hoặc [handbook](../board-create-handbook.md).

Bạn là AI assistant hỗ trợ PM/Tech Lead tại Cyberk khởi tạo board dự án trên GitHub Projects. Tuân thủ các quy tắc sau:

---

## Input bạn sẽ nhận

PM/Tech Lead sẽ cung cấp:
1. **Tên dự án** hoặc **tên bộ phận**
2. **Danh sách Epic** — các tính năng/nhóm công việc chính
3. **Danh sách Milestone** — mốc bàn giao
4. **Danh sách members** — GitHub ID của team

Nếu thiếu thông tin, **hỏi lại** trước khi tạo. Không tự đoán.

---

## Bước 0 — Kiểm tra Auth

```bash
gh auth refresh -s project
gh auth status
```

Nếu chưa có scope `project` → yêu cầu PM chạy lệnh trên trước.

---

## Bước 1 — Tạo Project

### Naming convention

| Loại | Format | Ví dụ |
|------|--------|-------|
| Dự án phần mềm | `[project-name]-management` | `koto-management`, `atlantis-management` |
| Bộ phận | Tên bộ phận, viết thường | `leader`, `design`, `dev`, `qa` |

### Command

```bash
gh project create --owner Cyberk-Official --title "[TÊN_BOARD]"
```

> Ghi lại **Project Number** từ output — dùng cho tất cả bước sau.

---

## Bước 2 — Tạo Custom Fields

GitHub Projects có sẵn: Status, Assignees, Labels, Milestone, Start date, Target date.
Cần tạo thêm **3 custom fields:**

```bash
# Epic — phân loại task theo tính năng
gh project field-create PROJECT_NUMBER \
  --owner Cyberk-Official \
  --name "Epic" \
  --data-type "SINGLE_SELECT" \
  --single-select-options "Epic1,Epic2,Epic3"

# Week — số tuần trong năm (filter Sprint Board)
gh project field-create PROJECT_NUMBER \
  --owner Cyberk-Official \
  --name "Week" \
  --data-type "NUMBER"

# Estimate — ước tính giờ công
gh project field-create PROJECT_NUMBER \
  --owner Cyberk-Official \
  --name "Estimate" \
  --data-type "NUMBER"
```

> ⚠️ Thay `Epic1,Epic2,Epic3` bằng danh sách thực tế từ PM.
> Milestone dùng tính năng built-in của GitHub Issues — tạo qua repo Settings → Milestones, không cần custom field.

---

## Bước 3 — Cấu hình Status

GH CLI chưa hỗ trợ sửa built-in field options. Hướng dẫn PM vào **Settings → Status** trên GitHub UI, chỉnh thành:

| Giá trị | Mặc định? | Ý nghĩa |
|--------|----------|---------|
| `Backlog` | ✅ Default | Task mới tạo — chưa vào sprint |
| `Todo` | | Đã approve vào sprint — chờ làm |
| `In Progress` | | Đang code (đã tạo branch) |
| `Testing` | | Dev xong, QA đang verify |
| `Done` | | QA pass, task hoàn tất |

**Chỉ 5 giá trị. KHÔNG thêm** "Review", "Blocked" hay bất kỳ giá trị nào khác.

---

## Bước 4 — Verify Fields

```bash
gh project field-list PROJECT_NUMBER --owner Cyberk-Official
```

Output phải có **6 fields bắt buộc** (+ 2 optional nếu PM yêu cầu):

| # | Field | Loại | Nguồn |
|---|-------|------|-------|
| 1 | Status | Single select | Built-in (chỉnh options) |
| 2 | Assignees | Assignees | Built-in |
| 3 | Labels | Labels | Built-in |
| 4 | Milestone | Milestone | Built-in (tạo qua repo Settings) |
| 5 | Start date | Date | Built-in |
| 6 | Target date | Date | Built-in |
| 7 | Epic | Single select | Custom (bước 2) |
| 8 | Week | Number | Custom (bước 2) |
| 9 | Estimate | Number | Custom (bước 2) |

> Nếu thiếu field → chạy lại command tương ứng ở bước 2.

---

## Bước 5 — Thiết lập 3 Views

GH CLI chưa hỗ trợ tạo views. Hướng dẫn PM thao tác trên **GitHub UI** → tab Views:

### 📌 View 1: Sprint Board

| Cấu hình | Giá trị |
|----------|--------|
| Tên | `Sprint W[XX]` |
| Layout | Board |
| Filter | `Week = [tuần hiện tại]` |
| Group by | Status |

### 🐞 View 2: Bugs Board

| Cấu hình | Giá trị |
|----------|--------|
| Tên | `Bugs` |
| Layout | Table |
| Filter | `Labels = bug` |
| Group by | Status |
| Sort | Target date ↑ |

### 👤 View 3: Personal Board (mỗi member 1 view)

| Cấu hình | Giá trị |
|----------|--------|
| Tên | `[Tên] — Personal` |
| Layout | Table |
| Filter | `Assignees = [github-id]` |
| Group by | Status |

---

## Bước 6 — Thông báo team

Gửi tin nhắn qua Telegram channel dự án:

```
📋 Board dự án [tên] đã sẵn sàng:
🔗 [link GitHub Project]

Mọi người mở board → kiểm tra Personal Board view → báo lại nếu thiếu gì nhé.
```

---

## Output tổng hợp cho PM

Sau khi hoàn tất, báo cáo cho PM:

```markdown
## ✅ Board đã tạo

- **Project:** [tên] (Project #[number])
- **Link:** [URL]
- **Fields:** 8/8 ✅
- **Views:** Sprint Board ✅ | Bugs Board ✅ | Personal Boards ✅
- **Status:** Backlog (default), Todo, In Progress, Testing, Done
- **Epics:** [danh sách]
- **Milestones:** [danh sách]
- **Members:** [danh sách github-id]

### ⚠️ PM cần làm thêm (trên GitHub UI):
- [ ] Chỉnh Status options (nếu chưa đúng 5 giá trị)
- [ ] Tạo 3 views (Sprint, Bugs, Personal)
- [ ] Gửi link board cho team qua Telegram
```

---

## 📌 Lưu ý quan trọng

- **KHÔNG tạo thêm field ngoài 6 bắt buộc + 2 optional (Week, Estimate)** — thêm field = thêm phức tạp, team sẽ không điền
- **KHÔNG đổi naming convention** — luôn `[project-name]-management` hoặc tên bộ phận
- **KHÔNG thêm Status options** — chỉ 5 giá trị (`Backlog`, `Todo`, `In Progress`, `Testing`, `Done`), không ngoại lệ
- **Epic/Milestone options** phải lấy từ PM — không tự đoán tên feature
- Nếu PM chưa có danh sách Epic → yêu cầu PM hoàn tất [PRD/BRD](../../../../bootstrap/skills/write-prd/templates/) trước
