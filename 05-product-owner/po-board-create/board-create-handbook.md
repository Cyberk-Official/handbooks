---
type: delivery
tags: [board, google-sheet, project-management, handbook, setup]
created-date: 2026-09-01
updated-date: 2026-11-26
author: anderson
status: Nháp
---

# Khởi tạo Board dự án — Cẩm nang cho PO / Tech Lead

**Người chịu trách nhiệm:** PO dự án
**Cập nhật lần cuối:** 2026-11-26
**Trạng thái:** Nháp

## Quản lý dự án là gì?

Tại Cyberk quản lý dự án bao gồm 4 thành phần:

- **Scope:** Đề bài, tổng khối lượng công việc.
- **Deadline:** Deadline cho mỗi phần công việc đó.
- **Resource:** Nguồn lực, effort, số lượng nhân sự dành cho dự án đó.
- **Responsibility:** Trách nhiệm công việc, tinh thần hoàn thành công việc của từng cá nhân.

## Quản lý dự án tốt là:

- Scope rõ ràng, được cập nhật liên tục, và không bị out-dated
- Deadline là cố định, và hiếm khi bị trễ. Luôn bàn giao đúng hạn
- Resource hợp lý. Anh em hiếm khi phải overtime
- Team đoàn kết. Anh em luôn sẵn sàng hỗ trợ nhau để hoàn thành dự án

Board là nơi 4 thành phần này hiện ra trên cùng một trang: Scope là các Milestone và task, Deadline là Expected done date, Resource là Estimate, Responsibility là Assignee.

---

## Board là gì?

Tại Cyberk, board là một **Google Sheet** copy từ [`TEMPLATE`](https://docs.google.com/spreadsheets/d/1PA2c5UgSfVdYbqnafB0_hLelpRm8gluAt0MIA2W8vlg), nằm trong folder [Project Management](https://drive.google.com/drive/folders/1Yo-AivRaa4vDYkOE9-UEP5W3nNjzlj5S) — mỗi dự án một board, mỗi bộ phận một board.

## Tại sao board quan trọng?

Board giải quyết 2 vấn đề cốt lõi:

1. **Dev không cần chờ ai giao việc** — mở tab sprint, lọc theo tên mình ở cột Assignee, thấy ngay task nào cần làm hôm nay. Tự chủ, không phụ thuộc.

2. **Vấn đề tự lộ ra** — task kẹt `Doing` quá 2 ngày *(bôi đỏ)*? Đến thứ 5 vẫn chưa có task nào `Done`? Expected done date đã qua mà Progress mới 50%? Board tự nói cho bạn biết sprint đang có vấn đề — trước khi bất kỳ ai kịp báo cáo.

> **Tiêu chí board tốt:** Một người chưa biết gì về dự án — kể cả khách hàng — mở board ra, **10 giây** biết được: team đang ở sprint nào, ai đang làm gì, có task nào đang kẹt không, deadline tuần này có kịp không.

---

## Đặt tên Board

| Loại | Format | Ví dụ |
|------|--------|-------|
| Dự án phần mềm | `[Project]-Management` | `Koto-Management`, `Precept-Management` |
| Bộ phận | Tên bộ phận, viết thường | `leader`, `design`, `dev`, `qa` |

---

## 8 cột bắt buộc

Bảng task trên mỗi tab sprint có **8 cột**: `Milestones · Tasks · Assignee · Status · Progress · Estimate (h) · Expected done date · Notes`. Mỗi cột giải quyết một câu hỏi cụ thể. Thiếu 1 cột = board không trả lời được 1 câu hỏi. Thêm cột không cần = team phải điền thêm 1 thứ mà không ai dùng.

### Milestones

Milestone là mốc bàn giao hoặc một đợt việc trong proposal: `Lighter Platform Integration`, `Monochrome Trading Competition Launch`, `Smart Contract Audit Report Cover`.

Tại sao bắt buộc? Vì tab sprint chỉ cho bạn thấy tuần này làm gì. Nhưng nếu task không gắn Milestone, bạn không biết task đó phục vụ tính năng nào. 30 task trên board — nhìn vào không biết "Lighter Platform Integration đã xong bao nhiêu phần trăm, kịp release ngày 20 không?"

Task không có Milestone giống hàng trong kho không gắn nhãn — có đó, nhưng không biết thuộc đơn hàng nào.

Cách đặt tên, độ lớn của một Milestone và cách tách Milestone thành task: xem [Tạo Milestone](../po-milestone-create/milestone-create-handbook.md).

### Tasks

Mỗi ngày board được export PDF gửi khách. Khách đọc cột Tasks để biết sản phẩm của họ đang đi tới đâu. Task viết bằng ngôn ngữ của dev thì khách không hiểu — rồi lại nhắn hỏi PO.

Ví dụ, cùng một việc:

```
Khách đọc là hiểu:   Show the amount actually sent after step rounding, with a round-up to the next step
Chỉ dev hiểu:        fix rounding util + refactor hook
```

### Assignee

2 người assign = không ai chịu trách nhiệm. "Tôi tưởng anh làm" — câu nói kinh điển khi task có 2 assignees.

### Status

`Todo → Doing → Done`, cộng thêm `Pending`.

Bốn. Không hơn.

Sẽ có người hỏi: "Thêm `Review` được không? Task đang chờ review mà." Hoặc: "Thêm `Blocked` đi, để biết task nào đang bị chặn."

Không. Lý do:

- **"Review"** — Ai review? Code review hay design review? Chờ review của PO hay client? Mỗi người hiểu khác nhau → task kẹt ở "Review" cả tuần mà không ai biết nó đang chờ ai.
- **"Blocked"** — Blocked bởi cái gì? Đã report cho ai chưa? "Blocked" trở thành nơi task đến rồi nằm chết. Đã có `Pending` — và **mọi task `Pending` phải ghi rõ ở cột Notes đang chờ cái gì, chờ ai** → đó là thông tin hữu ích, không phải một trạng thái mới.

4 trạng thái đủ rõ để **ai nhìn cũng hiểu giống nhau.** Thêm trạng thái thứ 5 trở đi = thêm tranh cãi "task này nên để trạng thái nào."

Một task `Pending` có Notes ghi `Waiting for client API key — asked Jon on Nov 24` thì ai đọc cũng biết đang chờ gì và đã hỏi ai. Một task `Pending` 4 ngày với Notes trống thì PO phải đi hỏi từng người.

### Progress

`0%` → `100%`. Status cho biết task đang ở đâu, Progress cho biết còn bao xa. Task `Doing` 20% ngày thứ Năm mà Expected done date là thứ Sáu = sắp trễ, biết trước để xử lý. `Done` thì phải `100%`.

### Estimate (h)

`2`, `3`, `4` (giờ). **Bắt buộc**, không quá 4 giờ một task.

Estimate **không phải** để theo dõi dev làm mấy giờ. Estimate để trả lời 1 câu hỏi duy nhất:

> **Sprint này có bị nhồi quá không?**

Cộng estimate của tất cả task trong sprint → so với capacity team (VD: 3 dev × 6h productive/ngày × 5 ngày = 90h). Estimate tổng > 90h = sprint sẽ trễ, chắc chắn. Biết sớm → cắt scope, đừng chờ thứ 6 mới biết.

Và vì sao Estimate luôn đi trước Assign? Chưa biết task bao nhiêu giờ thì không biết giao cho ai là vừa sức. Giao theo cảm giác = người ôm 50 giờ, người ngồi chơi.

### Expected done date

Task có ngày xong = nhìn vào là biết trễ hay chưa. Thiếu ngày xong = task "sống mãi" mà không ai hỏi.

Ngày phải là **một ngày cụ thể** — "tuần sau", "khi nào xong backend" không phải là ngày.

### Notes

Lý do `Pending`, task chuyển từ sprint trước (`Moved from sprint_1`), link tài liệu liên quan. Không có gì cần ghi thì để trống.

---

## Các tab

Nếu dồn **tất cả** task vào một chỗ — cả tuần trước, tuần sau, task đã done, task chưa ai làm — nhìn vào = nhiễu. Mỗi tab chỉ hiện đúng thứ bạn cần.

| Tab | Câu hỏi |
|-----|---------|
| 📌 `sprint_1`, `sprint_2`... | Tuần này team làm gì? |
| 📊 `Members` | Mỗi người đang làm bao nhiêu, tuần này so với tuần trước ra sao? |
| 📖 `README` | Luật chơi của board là gì? |
| 🗂️ `data` *(ẩn)* | Tự gom task từ các tab sprint bằng công thức QUERY để `Members` tính số. **Không sửa tay** |

### Tab sprint

Mỗi sprint là một tuần, mỗi tuần một tab: `sprint_1`, `sprint_2`... Đầu tab là **Daily Report** *(xem [Internal Daily](../po-internal-daily/internal-daily-handbook.md))*, bên dưới là bảng task 8 cột.

Đây là tab **quan trọng nhất** — và cũng chính là trang khách nhận được dưới dạng PDF mỗi ngày.

### Việc chưa kịp làm thì đi đâu?

Sang sprint tiếp theo — với người nhận và ngày cụ thể. Tên tab luôn đặt theo sprint: `sprint_1`, `sprint_2`... nên mọi task luôn thuộc về một tuần nào đó.

Cách tồi:

```
Tab: Backlog | sprint_1 | Members | README

Thứ 6 chốt sprint, task chưa xong bị kéo về tab Backlog "lúc nào rảnh làm".
```

Tại sao tồi: Tab Backlog là nơi task đến rồi nằm chết. *"Cái này để sau làm"* — rồi không ai nhớ tới, cho đến ngày khách hỏi *"Cái anh nhờ tháng trước đâu rồi em?"*.

Cách tốt:

```
Tab: sprint_1 | sprint_2 | Members | README

Thứ 6 chốt sprint, task "Withdraw: Lighter → Koto" chưa xong
→ copy sang sprint_2, Notes ghi "Moved from sprint_1",
  Expected done date thứ 3 tuần sau.
```

Tại sao tốt: Task vẫn có người, có ngày, và thứ 3 tuần sau sẽ có người hỏi tới.

### Tab Members

Tab `Members` cho PO bức tranh toàn team: mỗi người đang có bao nhiêu task, xong bao nhiêu, tuần này so với tuần trước.

### Bugs

Bug là các issue của dự án. Cần được phát hiện càng sớm càng tốt.

- Mô tả đầy đủ, rõ ràng sao cho người đọc không cần hỏi lại cũng hiểu được vấn đề.
- Deadline luôn nằm trong Milestones, và Fix càng sớm càng tốt.

Thấy bug ở đâu *(buổi Demo, khách báo, QA test)* thì chụp ảnh và đưa thẳng lên **GitHub Issue** theo chuẩn của [QA Bugs Logs](../../06-qa/qa-bugs-logs/qa-bugs-logs-process.md) — có severity, bước tái hiện, ảnh chụp. GitHub Issue là nơi duy nhất lưu bug. Board không có danh sách bug riêng.

Khi **sửa** bug nào, PO tạo task tương ứng cho đúng bug đó trong tab sprint, như mọi task khác: nằm trong tab sprint, dưới Milestone mà bug thuộc về, có Estimate, Assignee, Expected done date, và link GitHub Issue ở cột Notes. Gắn mức độ ở đầu tên task để nhìn là biết gấp hay không — VD Milestone `Trading UI Audit Fixes` của Koto: `[P0] O-1: Start the order form with an empty size...`, `[P1] P-3: Type any leverage directly...`. Nhờ vậy bug có giờ trong Estimate, có người nhận, và khách thấy được trong bản PDF.

Một task là một bug. Task tên `Fix bugs` hay `Fix UI issues` thì khách đọc không biết bug nào đã sửa, QA không biết test lại cái gì, và Estimate không có cơ sở.

Người chịu trách nhiệm cho Milestone, thì sẽ chịu trách nhiệm cho bugs thuộc về Milestone đó.

---

## Xem tiến độ một Milestone

*Dữ liệu → Tạo chế độ xem lọc*, lọc cột Milestones.

Cần khi: Dự án có ≥ 5 Milestone chạy song song. PO muốn biết "Lighter Platform Integration hoàn thành bao nhiêu phần trăm?" → lọc Milestone = Lighter Platform Integration, đếm Done/Total.

---

## Tóm lại

| Câu hỏi | Trả lời |
|---------|---------|
| Board là gì? | Bản mô phỏng trạng thái dự án — 10 giây biết có vấn đề |
| Dùng gì? | Google Sheet, copy từ `TEMPLATE`, nằm trong folder Project Management |
| Đặt tên? | `[Project]-Management` hoặc tên bộ phận |
| Bao nhiêu cột? | 8 — không thiếu, không thừa. Estimate bắt buộc |
| Tab chính? | Mỗi sprint một tab: `sprint_1`, `sprint_2`... |
| Ai tạo? | PO, estimate cùng Tech Lead *(xem [Tạo Milestone](../po-milestone-create/milestone-create-handbook.md))*. Team nhận việc trong buổi [Planning](../po-planning/planning-process.md) |
| Status bao nhiêu? | 4. Không hơn. |

---

## Liên kết

- [Quy trình tạo Board](./board-create-process.md) — Luồng `TEMPLATE → ESTIMATE → PLAN`, Board Rule, quy tắc cứng, checklist
- [Tạo Milestone](../po-milestone-create/milestone-create-handbook.md) — Đặt tên Milestone, tách task, estimate cùng Dev
- [Internal Daily Meeting](../po-internal-daily/internal-daily-process.md) — Cập nhật board hằng ngày, Daily Report, export PDF gửi khách
