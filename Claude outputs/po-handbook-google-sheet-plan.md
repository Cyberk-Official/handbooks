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

