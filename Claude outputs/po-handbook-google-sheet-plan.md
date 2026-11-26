---
type: plan
tags: [plan, product-owner, handbook, project-management, google-sheet]
created-date: 2026-11-25
updated-date: 2026-11-25
author: neo
status: draft
---

# Kế hoạch: Chuyển PO Handbook từ GitHub Projects sang Google Sheet

## Bối cảnh

Cyberk không dùng GitHub Projects để quản lý dự án nữa. Mỗi dự án giờ có một Google Sheet `<Project>-Management`, nằm trong folder Drive Project Management: https://drive.google.com/drive/folders/1Yo-AivRaa4vDYkOE9-UEP5W3nNjzlj5S

Code vẫn nằm trên GitHub. Chỉ phần **quản lý task** chuyển sang Sheet.

Cách làm: sửa **từng bước một**. Xong mỗi bước thì dừng lại để Anderson duyệt. **Mỗi lần chỉ hỏi một câu.**

---

## Đã chốt (25/11/2026)

| # | Quyết định |
|---|-----------|
| 1 | Có cột **Estimate (giờ)**. Cột này quan trọng, bắt buộc điền |
| 2 | Tab đặt tên theo **sprint** (`sprint_1`, `sprint_2`...) |
| 3 | **Không có tab Backlog.** Việc chưa xếp được vào sprint hiện tại thì đưa sang sprint tiếp theo |
| 4 | Tab Aethir sót lại sẽ được dọn riêng (đã ghi trong `anderson/tasks.md`, nhắc team ngày 26/11) |
| 5 | **Bỏ toàn bộ GitHub board** ở mọi nơi trong handbook (không chỉ phần PO). Sheet là công cụ quản lý dự án duy nhất |
| 6 | Sheet template gốc: `TEMPLATE` trong folder Drive (https://docs.google.com/spreadsheets/d/1PA2c5UgSfVdYbqnafB0_hLelpRm8gluAt0MIA2W8vlg). **25/11: đã thêm cột `Estimate (h)`** vào `sprint_1`, `sprint_2` (cột F, thay cột Expected Done Date trống bị trùng). Tab `data` (ẩn) tự lấy theo bằng QUERY |
| 7 | Khách hàng được **quyền xem** Sheet. Mỗi ngày PO **export tab sprint ra PDF** gửi khách làm Daily Report |

### Template rút ra từ các sheet đang chạy (Koto, Flux, Blockwrap, Precept)

- **Cột (theo TEMPLATE):** Milestones · Tasks · Assignee · Status · Progress · **Estimate (h)** · Expected done date · Notes
- **Daily Report** nằm ở đầu tab sprint hiện tại: Upcoming Milestones, Completed Tasks, Today's Focus, Risks
- **Board Rule** (tab README):
  - Mỗi Milestone có 1 task UX/UI và 1 task QA (Flux có thêm 1 task Code Refactor)
  - Mỗi sub-task không quá 4 giờ
  - Mỗi member có 2 task mỗi ngày, 10 task mỗi tuần
  - Task mô tả sao cho khách đọc hiểu
  - Meeting với khách có task mới thì cập nhật vào sheet ngay
  - PO đưa task lên và assign cho member; member tự cập nhật tiến độ

---

## Các bước sửa

| Bước | File | Việc cần làm | Mức độ |
|:---:|------|-------------|:---:|
| **1** ✍️ *process đã sửa lần 3 (26/11), chờ duyệt; handbook & README đang để bản gốc* | `po-board-create/` (README, handbook, process) | Viết lại Chương 3: tạo Sheet từ template, đặt tên, để vào folder Drive, phân quyền, điền scope từ proposal, chia sprint | Viết lại |
| **2** ✍️ *đã viết, chờ duyệt 25/11* | `po-board-create/board-create-ai-instruction/` | Viết lại AI instruction: từ proposal/PRD, AI soạn các dòng task (có Estimate) để dán vào Sheet, thay cho GH CLI | Viết lại |
| **3** | `board-handbook/` (README, handbook) | Giữ phần tư duy (Scope/Deadline/Resource/Responsibility, Epic, Milestone, Task, Bug). Thay phần GitHub bằng: Board Rule, cách cập nhật hằng ngày, Daily Report, cách chốt sprint và đẩy việc dở sang sprint sau | Sửa lớn |
| **4** | `05-product-owner/README.md` | Sửa sơ đồ mermaid, tên Chương 3 và 4, link AI Instruction | Sửa nhỏ |
| **5** | `po-project-leave/` (process, lead-handbook, member-handbook) | "Task trên GitHub Projects" đổi thành Sheet. Giữ nguyên phần thu hồi quyền GitHub repo | Sửa nhỏ |
| **6** | `po-feature-request/` (README, example) | "Đưa lên GitHub board" đổi thành "đưa vào Sheet" | Sửa nhỏ |
| **7** | Ngoài PO: `04-developer/dev-tasks-logs/`, `dev-daily-report/`, `dev-daily/`, `06-qa/`, `AGENTS.md`, `workflow/playbook.md`... | Bỏ GitHub board, chuyển sang Sheet. Liệt kê trước, Anderson duyệt danh sách rồi mới sửa | Sửa |

Mỗi file sửa xong thì cập nhật `updated-date` trong front matter.

---

## Câu hỏi còn mở (hỏi lần lượt)

1. Có giữ tab tổng scope (như tab `board` của Flux: toàn bộ proposal theo milestone tuần) song song với các tab `sprint_N` không?
2. Bug để ở đâu: một tab riêng trong Sheet, hay vẫn ở GitHub Issues?
5. Có đổi tên folder `po-board-create/` và `board-handbook/` không? (Đổi tên sẽ phải sửa link ở nhiều nơi)
6. Có giữ tab Members (dashboard) và tab Finance trong template chuẩn không?

---

## Ghi chú khi sửa (26/11)

- Luồng tạo board chốt **3 bước: `ESTIMATE → ASSIGN → PLAN`**. Copy TEMPLATE là việc chuẩn bị trước, không phải một bước.
- Phần export PDF + Daily Report gửi khách hằng ngày **chuyển sang Chương 4** (`board-handbook/`), không nằm trong quy trình tạo board.
- Bảng **8 cột** và **các tab chuẩn** đã gỡ khỏi process, cần đưa vào `board-create-handbook.md` khi sửa file đó.
- Lối viết theo mẫu `po-feature-request/`: "Tại sao" nêu bẫy, mỗi bước là đoạn đầy đủ có `•`, vai trò gắn bước *(in nghiêng)*, lý do có câu nói thật, ngoại lệ là tình huống thật.
- **Không viết lại cả file.** Khôi phục bản gốc, giữ hồn, sửa từng đoạn, mỗi file xong thì thảo luận.
- **Process đúng khung `workflow/process-template.md`:** không thêm mục ngoài template, bảng Các bước có cột Timeline. Mẹo, hướng dẫn mềm → handbook.
- **Quy tắc cứng ít, đơn giản, viết theo hướng "việc cần làm"** (VD: "Tên tab đặt theo sprint: `sprint_1`, `sprint_2`..."), không viết "không được làm X" — vì việc không được làm thì vô số. Cách làm sai → đưa vào ví dụ ❌ trong handbook/example.

## Nội dung chuyển sang Chương 4 (`board-handbook/`) — gỡ khỏi `board-create-handbook.md` ngày 26/11

PO mở tab sprint ra mỗi sáng — 10 giây biết:
- Còn bao nhiêu task `Todo`? (chưa ai bắt đầu)
- Task `Doing` nào kéo dài bất thường? (đang nghẽn)
- Số task `Done` có đang tăng? (team đang tiến triển)

Nếu thứ 4 mà chưa có task nào `Done` — sprint đang có vấn đề. Không cần ai nói, board tự nói.

✅ Tab sprint tốt: Thứ 2 — 8 task Todo, 0 Doing, 0 Done. Thứ 5 — 2 Todo, 3 Doing, 3 Done. → Đang ổn.

❌ Tab sprint tệ: Thứ 5 — 1 Todo, 7 Doing, 0 Done. → 7 task đang làm dở, không cái nào xong. Sprint sẽ vỡ.


## Nâng cao — Khi nào mới cần?

Không phải dự án nào cũng cần. Thêm khi **có nhu cầu thật**, không thêm cho đủ.

### Chuẩn bị sprint tiếp theo

Thứ 5 – thứ 6, PO mở sẵn tab sprint tuần tới: kiểm tra đã có đủ task chưa, estimate chưa, assign chưa. Không cần ngay khi mới tạo board.


---

## Rà soát toàn handbook (26/11) — chỗ còn dùng GitHub Projects

**Sửa nhỏ (đổi chữ/link):** `05-product-owner/README.md`, `po-board-create/README.md`, `po-feature-request/README.md` (dòng 45), `feature-request-example.md` (dòng 407), `po-project-leave/` (3 file, ~8 chỗ), `00-account/team-chat-groups/` (2 chỗ "tên board trên GitHub Projects"), `08-media/Media-source-management-vi.md` (2 chỗ), `handbook/README.md` (dòng 72), `metadata.md` (tag `github-projects`), `workflow/playbook.md` (bảng Công cụ chuẩn + checklist), `04-developer/dev-project-onboarding/` (5 chỗ), `dev-project-offboarding/` (3 chỗ "Personal Board").

**Sửa lớn:** `05-product-owner/board-handbook/` (Chương 4), `po-board-create/board-create-ai-instruction/`, `04-developer/dev-daily/` (xoay quanh Personal Board), `04-developer/dev-tasks-logs/` (cả folder dựa trên GH CLI push — mâu thuẫn Board Rule "PO đưa task lên board"), `04-developer/dev-daily-report/` (trùng với Daily Report đầu tab sprint + PDF).

**Chờ quyết định bug:** `06-qa/qa-bugs-handling/`, `06-qa/qa-bugs-logs/` (bug đang là GitHub Issues).

**Ngoài handbook:** `AGENTS.md` mục "Board & Task Management — GitHub Projects", "GitHub Boards", "Mở Leader board đầu ngày" (Leader/MEDIA/DESIGN/QA/SALE board).

### ✅ Đã xử lý nhóm "Sửa nhỏ" (26/11)
PO README, po-board-create/README, po-feature-request (README + example), po-project-leave (3 file), team-chat-groups (2 file), 08-media, handbook README, metadata (tag `github-projects` → `google-sheet`), workflow/playbook (bảng Công cụ chuẩn + checklist), dev-project-onboarding (2 file), dev-project-offboarding (2 file). Giữ nguyên mọi chỗ nói về GitHub **repo / branch / PR / Issues** (bug chờ quyết định).

---

## Plan: Gộp `board-handbook/` vào `po-board-create/` + tạo `po-internal-daily/` (26/11, chờ duyệt)

### Bản đồ di chuyển tri thức từ `board-handbook.md`

| Nội dung gốc | Đi đâu | Cách xử lý |
|---|---|---|
| Quản lý dự án là gì? (Scope / Deadline / Resource / Responsibility) + Quản lý dự án tốt là | `board-create-handbook.md` — mục mở đầu | Giữ nguyên văn |
| Epic: 1 người chịu trách nhiệm, < 1 tuần, team < 5 người; thêm Epic = mở rộng scope → báo quản lý; khách thêm Epic = cơ hội mở rộng hợp đồng | `board-create-handbook.md` — mục Milestones | Giữ ý, đổi Epic → Milestone, link Feature Request |
| Epic phải có Feature ID (`BR-XXX`, `FR-XXX`) | ❓ Chờ Anderson | Sheet chưa có cột Feature ID |
| Milestone = mốc bàn giao weekly (`W33`, `Alpha`) | ❓ Chờ Anderson | Sheet hiện dùng Milestone = tên tính năng, mốc ngày nằm ở Upcoming Milestones |
| Tasks: < 4h, làm trong 1 ngày | Đã có trong Board Rule | — |
| Bugs: mô tả đủ để người đọc không cần hỏi lại; deadline nằm trong Milestone; fix càng sớm càng tốt; người giữ Epic giữ bug | `board-create-handbook.md` — mục Bugs | Giữ nguyên văn |
| Board: team nhìn vào biết tuần này làm gì, có trễ không | Đã có (Tiêu chí board tốt) | — |
| Về Tasks: luôn cập nhật task mới nhất, bỏ task outdated, task mới đủ thông tin | `internal-daily-handbook.md` — bước CHANGE | Giữ ý |
| 3 loại board cơ bản + nâng cao (Sprint / Bugs / Personal / Sprint Future / Gantt / Filter) | Đã thay bằng các tab | Bỏ phần GitHub |
| Tạo Board chuẩn (GitHub Projects) | — | Bỏ (đã có `po-board-create/`) |
| Tạo Task chuẩn (AI-driven, GH CLI, format body) | — | Bỏ, xử lý cùng `dev-tasks-logs/` |
| **Dấu hiệu quản lý dự án không tốt** — cấp team (12 dấu hiệu) & cấp cá nhân (6 dấu hiệu) | `internal-daily-handbook.md` — "Board đang ốm: nhận biết thế nào?" | Giữ nguyên văn, chỉ đổi thuật ngữ (In Progress → Doing, Personal Board → lọc tên mình, Epic → Milestone) |
| Đọc tab sprint mỗi sáng (✅/❌ thứ 2 – thứ 5) + Chuẩn bị sprint tiếp theo (đã gỡ khỏi board-create) | `internal-daily-handbook.md` | Giữ nguyên văn |

### Folder mới `05-product-owner/po-internal-daily/` (tạo template trống trước, duyệt cấu trúc rồi mới viết)

- `README.md`
- `internal-daily-process.md` — Luồng `DEMO → CHANGE → REPORT`
  - DEMO: show sản phẩm cả team đã làm hôm qua
  - CHANGE: đưa thay đổi, task mới phát hiện lên board, điều chỉnh task cho hợp lý, viết agile report ở đầu file Management
  - REPORT: export file Management ra PDF gửi khách, kèm tin nhắn summary
- `internal-daily-handbook.md` — cách nghĩ từng bước + dấu hiệu board ốm
- `internal-daily-example.md` — mẫu agile report đầu tab, mẫu tin nhắn summary kèm PDF (tốt/tồi)

### Sau khi chuyển xong
- Xoá folder `board-handbook/` (cần Anderson cho phép xoá) hoặc chuyển vào `_to_delete/`
- Đổi ~25 link trỏ tới `board-handbook/` → `po-board-create/board-create-handbook.md` hoặc `po-internal-daily/`
- `05-product-owner/README.md`: Chương 4 → Internal Daily Meeting
- Đánh giá trùng lặp với `04-developer/dev-daily/` và `04-developer/dev-daily-report/` (làm sau)

### Tiến độ (26/11)
- ✅ Đã chuyển vào `board-create-handbook.md`: Quản lý dự án là gì / Quản lý dự án tốt là (nguyên văn), kiến thức Epic → Milestones, kiến thức Bugs (nguyên văn).
- ✅ Đã tạo khung trống `po-internal-daily/` (README, process, handbook, example) — chờ duyệt cấu trúc.
- ⏳ Chưa xoá `board-handbook/`, chưa đổi link.
- Quyết định mặc định: bỏ yêu cầu Feature ID (Sheet chưa có cột); Milestone theo tên tính năng (theo Sheet).

### Tiến độ (26/11, chiều)
- ✅ `po-internal-daily/` đủ 4 file (process, handbook, example, README). Handbook sắp theo luồng DEMO → CHANGE → REPORT.
- ✅ Tạo `po-milestone-create/`: handbook + example đã có nội dung chuyển từ board-create và internal-daily; process còn khung trống, chờ thảo luận.
- ⏳ Chưa chốt: giờ họp Internal Daily / giờ gửi PDF; có thêm Board Rule "task xử lý lỗi" không; số ngày task treo `Doing` (2 hay 3); bug ở GitHub Issues hay Sheet; số phận `04-developer/dev-daily-report/`.
- ⏳ Chưa xoá `board-handbook/`, chưa sửa ~23 link.
