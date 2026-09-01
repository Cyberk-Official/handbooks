---
type: delivery
tags: [board, github-projects, project-management, handbook, setup]
created: 2026-09-01
updated: 2026-09-01
author: anderson
status: Nháp
---

# Khởi tạo Board dự án — Cẩm nang cho PM / Tech Lead

**Người chịu trách nhiệm:** [PM / Tech Lead]
**Cập nhật lần cuối:** 2026-09-01
**Trạng thái:** Nháp

## Kanban Board là gì?

Kanban Board là bảng trực quan chia công việc thành các cột theo **trạng thái**: `Backlog → Todo → In Progress → Done`. Mỗi task là một thẻ, di chuyển từ trái sang phải khi tiến triển. Nhìn vào board, bạn thấy ngay: bao nhiêu việc đang chờ, bao nhiêu đang làm, bao nhiêu đã xong.

Tại Cyberk, board dùng **GitHub Projects** — mỗi dự án một board, mỗi bộ phận một board.

## Tại sao board quan trọng?

Board giải quyết 3 vấn đề cốt lõi:

1. **PM không ngồi cạnh dev cả ngày** — nhưng mở board ra, dưới 10 giây phải biết: tuần này team đang ở đâu, ai đang kẹt, task nào trễ. Không cần hỏi, không cần họp.

2. **Dev không cần chờ ai giao việc** — mở Personal Board, thấy ngay task nào cần làm hôm nay. Tự chủ, không phụ thuộc.

3. **Vấn đề tự lộ ra** — task kẹt `In Progress` quá 3 ngày? Cột `Done` trống đến thứ 5? Board tự nói cho bạn biết sprint đang có vấn đề — trước khi bất kỳ ai kịp báo cáo.

> **Tiêu chí board tốt:** Một người chưa biết gì về dự án, mở board ra, **10 giây** biết được: team đang ở sprint nào, ai đang làm gì, có task nào đang kẹt không, deadline tuần này có kịp không.

---

## Đặt tên Board

| Loại | Format | Ví dụ |
|------|--------|-------|
| Dự án phần mềm | `[project-name]-management` | `koto-management`, `atlantis-management` |
| Bộ phận | Tên bộ phận, viết thường | `leader`, `design`, `dev`, `qa` |

---

## 8 Fields — Tại sao mỗi trường đều cần, không thiếu không thừa?

Board có 8 fields. Không phải con số ngẫu nhiên — mỗi field giải quyết một câu hỏi cụ thể. Thiếu 1 field = board không trả lời được 1 câu hỏi. Thêm 1 field = team phải điền thêm 1 thứ mà có thể không ai dùng.

### Status — Tại sao chỉ 5?

`Backlog → Todo → In Progress → Testing → Done`

Năm. Không hơn.

Sẽ có người hỏi: "Thêm `Review` được không? Task đang chờ review mà." Hoặc: "Thêm `Blocked` đi, để biết task nào đang bị chặn."

Không. Lý do:

- **"Review"** — Ai review? Code review hay design review? Chờ review của PM hay client? Mỗi người hiểu khác nhau → task kẹt cột "Review" cả tuần mà không ai biết nó đang chờ ai.
- **"Blocked"** — Blocked bởi cái gì? Đã report cho ai chưa? "Blocked" trở thành nơi task đến rồi nằm chết. Thay vì thêm cột, **comment trong issue** nói rõ blocked bởi gì → đó là thông tin hữu ích, không phải một cái cột.

5 trạng thái đủ rõ để **ai nhìn cũng hiểu giống nhau.** Thêm cột thứ 6 trở đi = thêm tranh cãi "task này nên ở cột nào."

✅ Tốt: Dev xong → chuyển `Testing` → QA verify → chuyển `Done`.

❌ Tồi: Task treo ở `Review` 4 ngày. PM hỏi: "Ai đang review?" Không ai biết.

### Epic — Task không có Epic = task trôi nổi

Epic là tên tính năng: `Authentication`, `Dashboard`, `Payment`.

Tại sao bắt buộc? Vì **Sprint Board** chỉ cho bạn thấy tuần này làm gì. Nhưng nếu task không gắn Epic, bạn không biết task đó phục vụ tính năng nào. 10 task trên board — nhìn vào không biết "feature Payment đã xong bao nhiêu phần trăm?"

Task không có Epic giống hàng trong kho không gắn nhãn — có đó, nhưng không biết thuộc đơn hàng nào.

### Milestone — Biết mốc bàn giao

`W33`, `W34`, `Alpha`, `Beta`.

Milestone trả lời: "Tuần 34 phải bàn giao cái gì cho khách?" Nếu task không gắn Milestone, PM phải tự nhớ — hoặc mở file khác tra — board không tự trả lời được.

### Week — Động cơ của Sprint Board

`33`, `34`, `35`...

Sprint Board filter theo Week. **Thiếu Week → Sprint Board hiển thị trống.** Đây là field ít ai nghĩ tới nhưng thiếu nó thì view quan trọng nhất vô dụng.

Đầu mỗi tuần, PM đổi filter `Week = [tuần mới]` → Sprint Board tự cập nhật. Nhanh, sạch, không cần tạo board mới mỗi sprint.

### Estimate — Không phải để đo giờ, mà để phát hiện overload

`2`, `3`, `4` (giờ)

Estimate **không phải** để theo dõi dev làm mấy giờ. Estimate để trả lời 1 câu hỏi duy nhất:

> **Sprint này có bị nhồi quá không?**

Cộng estimate của tất cả task trong sprint → so với capacity team (VD: 3 dev × 6h productive/ngày × 5 ngày = 90h). Estimate tổng > 90h = sprint sẽ trễ, chắc chắn. Biết sớm → cắt scope, đừng chờ thứ 6 mới biết.

### Start date & Target date — Biết task nào trễ

Không cần giải thích nhiều. Task có target date = board tự highlight khi trễ hạn. Thiếu target date = task "sống mãi" mà không ai hỏi.

### Assignees — Mỗi task đúng 1 người

2 người assign = không ai chịu trách nhiệm. "Tôi tưởng anh làm" — câu nói kinh điển khi task có 2 assignees.

### Labels — Phân loại nhanh

`operations`, `dev`, `design`, `qa`, `bug`.

Labels cho phép filter nhanh. Đặc biệt `bug` — Bugs Board filter theo label này. Không gắn label `bug` = bug lẫn vào task thường, không ai theo dõi riêng.

---

## 3 Views — Mỗi view trả lời một câu hỏi

Board mặc định hiện **tất cả** task — cả tuần trước, tuần sau, task đã done, task chưa ai làm. Nhìn vào = nhiễu. Views filter bớt nhiễu, chỉ hiện đúng thứ bạn cần.

### Sprint Board — "Tuần này team làm gì?"

Filter: `Week = [tuần hiện tại]`. Group by: `Status`.

Đây là view **quan trọng nhất**. PM mở Sprint Board ra mỗi sáng — 10 giây biết:
- Cột `Todo` còn bao nhiêu? (chưa ai bắt đầu)
- Cột `In Progress` có task nào kéo dài bất thường? (đang nghẽn)
- Cột `Done` có đang tăng? (team đang tiến triển)

Nếu thứ 4 mà `Done` trống — sprint đang có vấn đề. Không cần ai nói, board tự nói.

✅ Sprint Board tốt: Thứ 2 — 8 task Todo, 0 In Progress, 0 Done. Thứ 5 — 2 Todo, 3 In Progress, 3 Done. → Đang ổn.

❌ Sprint Board tệ: Thứ 5 — 1 Todo, 7 In Progress, 0 Done. → 7 task đang làm dở, không cái nào xong. Sprint sẽ vỡ.

### Bugs Board — "Nợ kỹ thuật đang ở đâu?"

Filter: `Labels = bug`. Group by: `Status`.

Bugs có đặc thù: chúng thường kéo dài qua nhiều sprint. Một bug phát hiện tuần 33, fix tuần 35 — nếu chỉ nhìn Sprint Board tuần 35, bạn không biết bug đó tồn tại từ bao giờ.

Bugs Board cho bạn **bức tranh toàn bộ nợ kỹ thuật** — bao nhiêu bug chưa fix, bug nào gần deadline, bug nào đã kéo dài quá lâu. Client hỏi "Còn bao nhiêu bug?" — bạn mở Bugs Board, trả lời trong 5 giây.

### Personal Board — "Tôi phải làm gì?"

Filter: `Assignees = [github-id]`. Mỗi member 1 view.

Đây là view dành cho **dev, không phải cho PM.** Mỗi sáng dev mở Personal Board — thấy ngay task nào cần làm hôm nay, không cần chờ standup, không cần hỏi Lead.

Nếu member mở board mà phải search, scroll, filter thủ công mới thấy task của mình — board đã thất bại. Personal Board giải quyết chuyện đó.

> **Quy tắc:** Tạo board xong, nếu bất kỳ member nào không thấy task của mình trong **1 click** — quay lại sửa Personal Board view.

---

## 3 Views nâng cao — Khi nào mới cần?

Không phải dự án nào cũng cần. Thêm view khi **có nhu cầu thật**, không thêm cho đủ.

### Sprint Future Board

Filter: `Week = [tuần tới]`.

Cần khi: PM muốn chuẩn bị sprint tiếp — kiểm tra tuần sau đã có đủ task chưa, assign chưa, estimate chưa. Không cần ngay khi mới tạo board.

### Gantt Chart

GitHub Projects hỗ trợ Roadmap view (dạng timeline). Cần Start date + Target date.

Cần khi: Dự án > 2 tháng, có nhiều milestone, cần nhìn tổng thể timeline. Dự án ngắn < 1 tháng → Sprint Board đủ.

### Filter Boards theo Epic

Filter: `Epic = [tên Epic]`.

Cần khi: Dự án có ≥ 5 Epic chạy song song. PM muốn biết "Feature Payment hoàn thành bao nhiêu phần trăm?" → mở view filter Epic = Payment, đếm Done/Total.

---

## Tóm lại

| Câu hỏi | Trả lời |
|---------|---------|
| Board là gì? | Bản mô phỏng trạng thái dự án — 10 giây biết có vấn đề |
| Đặt tên? | `[project]-management` hoặc tên bộ phận |
| Bao nhiêu fields? | 8 — không thiếu, không thừa |
| Bao nhiêu views? | 3 chuẩn + thêm nâng cao khi cần |
| Ai tạo? | PM / Tech Lead + AI (GH CLI) |
| Khi nào? | Sau planning, trước task đầu tiên |
| Status bao nhiêu cột? | 4. Không hơn. |

---

## Liên kết

- [Quy trình tạo Board](./board-create-process.md) — Luồng từng bước, quy tắc cứng, checklist
- [AI Instruction](./board-create-ai-instruction/board-create-instruction.md) — GH CLI commands cho AI tự tạo board
- [Board Handbook — Tổng quan quản lý dự án](../board-handbook/board-handbook.md)
- [Dev Tasks Logs](../dev-tasks-logs/dev-tasks-logs-process.md) — Bước tiếp theo: tạo task trên board
