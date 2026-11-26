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

## Board là gì?

Tại Cyberk, board là một **Google Sheet** copy từ [`TEMPLATE`](https://docs.google.com/spreadsheets/d/1PA2c5UgSfVdYbqnafB0_hLelpRm8gluAt0MIA2W8vlg), nằm trong folder [Project Management](https://drive.google.com/drive/folders/1Yo-AivRaa4vDYkOE9-UEP5W3nNjzlj5S) — mỗi dự án một board, mỗi bộ phận một board.

## Tại sao board quan trọng?

Board giải quyết 2 vấn đề cốt lõi:

1. **Dev không cần chờ ai giao việc** — mở tab sprint, lọc theo tên mình ở cột Assignee, thấy ngay task nào cần làm hôm nay. Tự chủ, không phụ thuộc.

2. **Vấn đề tự lộ ra** — task kẹt `Doing` quá 3 ngày? Đến thứ 5 vẫn chưa có task nào `Done`? Expected done date đã qua mà Progress mới 50%? Board tự nói cho bạn biết sprint đang có vấn đề — trước khi bất kỳ ai kịp báo cáo.

> **Tiêu chí board tốt:** Một người chưa biết gì về dự án — kể cả khách hàng — mở board ra, **10 giây** biết được: team đang ở sprint nào, ai đang làm gì, có task nào đang kẹt không, deadline tuần này có kịp không.

---

## Đặt tên Board

| Loại | Format | Ví dụ |
|------|--------|-------|
| Dự án phần mềm | `[Project]-Management` | `Koto-Management`, `Precept-Management` |
| Bộ phận | Tên bộ phận, viết thường | `leader`, `design`, `dev`, `qa` |

---

## 8 cột bắt buộc — Tại sao mỗi cột đều cần?

Bảng task trên mỗi tab sprint có **8 cột**: `Milestones · Tasks · Assignee · Status · Progress · Estimate (h) · Expected done date · Notes`. Mỗi cột giải quyết một câu hỏi cụ thể. Thiếu 1 cột = board không trả lời được 1 câu hỏi. Thêm cột không cần = team phải điền thêm 1 thứ mà không ai dùng.

### Milestones — Task không có Milestone = task trôi nổi

Milestone là mốc bàn giao hoặc tên tính năng trong proposal: `Lighter - Trading`, `Monochrome Trading Competition`, `Trading Audit`.

Tại sao bắt buộc? Vì tab sprint chỉ cho bạn thấy tuần này làm gì. Nhưng nếu task không gắn Milestone, bạn không biết task đó phục vụ tính năng nào. 30 task trên board — nhìn vào không biết "Lighter Trading đã xong bao nhiêu phần trăm, kịp release ngày 20 không?"

Task không có Milestone giống hàng trong kho không gắn nhãn — có đó, nhưng không biết thuộc đơn hàng nào.

Tên Milestone cũng phải để khách đọc là hiểu — trong bản PDF, khách đọc tên Milestone trước khi đọc từng task.

✅ Tốt: `Lighter - Trading`, `Custom Referral Link`

❌ Tồi: `M3`, `BE phase 2`

### Tasks — Viết cho khách đọc, không phải cho dev đọc

Mỗi ngày board được export PDF gửi khách. Khách đọc cột Tasks để biết sản phẩm của họ đang đi tới đâu. Task viết bằng ngôn ngữ của dev thì khách không hiểu — rồi lại nhắn hỏi PO.

✅ Tốt: `Show the amount actually sent after step rounding, with a round-up to the next step`

❌ Tồi: `fix rounding util + refactor hook`

### Assignee — Mỗi task đúng 1 người

2 người assign = không ai chịu trách nhiệm. "Tôi tưởng anh làm" — câu nói kinh điển khi task có 2 assignees.

### Status — Tại sao chỉ 4?

`Todo → Doing → Done`, cộng thêm `Pending`.

Bốn. Không hơn.

Sẽ có người hỏi: "Thêm `Review` được không? Task đang chờ review mà." Hoặc: "Thêm `Blocked` đi, để biết task nào đang bị chặn."

Không. Lý do:

- **"Review"** — Ai review? Code review hay design review? Chờ review của PO hay client? Mỗi người hiểu khác nhau → task kẹt ở "Review" cả tuần mà không ai biết nó đang chờ ai.
- **"Blocked"** — Blocked bởi cái gì? Đã report cho ai chưa? "Blocked" trở thành nơi task đến rồi nằm chết. Đã có `Pending` — và **mọi task `Pending` phải ghi rõ ở cột Notes đang chờ cái gì, chờ ai** → đó là thông tin hữu ích, không phải một trạng thái mới.

4 trạng thái đủ rõ để **ai nhìn cũng hiểu giống nhau.** Thêm trạng thái thứ 5 trở đi = thêm tranh cãi "task này nên để trạng thái nào."

✅ Tốt: Task `Pending`, Notes ghi `Waiting for client API key — asked Jon on Nov 24`.

❌ Tồi: Task `Pending` 4 ngày, Notes trống. PO hỏi: "Đang chờ gì?" Không ai biết.

### Progress — Xong bao nhiêu phần trăm?

`0%` → `100%`. Status cho biết task đang ở đâu, Progress cho biết còn bao xa. Task `Doing` 20% ngày thứ Năm mà Expected done date là thứ Sáu = sắp trễ, biết trước để xử lý. `Done` thì phải `100%`.

### Estimate (h) — Không phải để đo giờ, mà để phát hiện overload

`2`, `3`, `4` (giờ). **Bắt buộc**, không quá 4 giờ một task.

Estimate **không phải** để theo dõi dev làm mấy giờ. Estimate để trả lời 1 câu hỏi duy nhất:

> **Sprint này có bị nhồi quá không?**

Cộng estimate của tất cả task trong sprint → so với capacity team (VD: 3 dev × 6h productive/ngày × 5 ngày = 90h). Estimate tổng > 90h = sprint sẽ trễ, chắc chắn. Biết sớm → cắt scope, đừng chờ thứ 6 mới biết.

Và vì sao Estimate luôn đi trước Assign? Chưa biết task bao nhiêu giờ thì không biết giao cho ai là vừa sức. Giao theo cảm giác = người ôm 50 giờ, người ngồi chơi.

### Expected done date — Biết task nào trễ

Task có ngày xong = nhìn vào là biết trễ hay chưa. Thiếu ngày xong = task "sống mãi" mà không ai hỏi.

Ngày phải là **một ngày cụ thể** — "tuần sau", "khi nào xong backend" không phải là ngày.

### Notes — Những gì cần biết thêm

Lý do `Pending`, task chuyển từ sprint trước (`Moved from sprint_1`), link tài liệu liên quan. Notes trống là bình thường — Notes sai mới là vấn đề.

---

## Estimate cùng ai? — Tại sao PO không estimate một mình?

PO hiểu khách cần gì. Dev hiểu hệ thống cần gì. Estimate một mình thì chỉ thấy một nửa bức tranh.

- **PO estimate một mình** sẽ sót hạng mục kỹ thuật — rồi giữa sprint mới nghe *"cái này phải viết thêm migration nữa anh ơi"*, *"phải cấu hình lại server mới chạy được"*.
- **Dev estimate một mình** sẽ sót hạng mục khách cần — màn hình trạng thái lỗi, email thông báo, trang hướng dẫn — những thứ không nằm trong code nhưng khách nhìn thấy đầu tiên.

✅ Cách tốt:

```
PO mở Planning Report, đi qua từng Milestone cùng Tech Lead.
PO: "Milestone Withdraw có 3 task: form rút tiền, xác nhận, lịch sử giao dịch."
TL: "Thiếu task xử lý rút tiền bị treo ở bridge, cái đó mất 4h. Form rút tiền cũng phải tách đôi — 6h là quá 4h rồi."
→ Board có đủ hạng mục, không task nào quá 4 tiếng.
```

Tại sao tốt: Dev chỉ ra phần PO không thấy. Task được tách nhỏ ngay khi estimate, không phải đợi tới lúc làm mới biết.

❌ Cách tồi:

```
PO tự điền Estimate cho 30 task trong 15 phút, gửi link board vào group:
"Mọi người xem task tuần này nhé."
→ Thứ Tư Dev báo: "Task deposit này phải 2 ngày chứ không phải 4h đâu anh."
```

Tại sao tồi: Estimate theo cảm giác. Sprint vỡ ngay giữa tuần.

---

## Các tab — Mỗi tab trả lời một câu hỏi

Nếu dồn **tất cả** task vào một chỗ — cả tuần trước, tuần sau, task đã done, task chưa ai làm — nhìn vào = nhiễu. Mỗi tab chỉ hiện đúng thứ bạn cần.

| Tab | Câu hỏi |
|-----|---------|
| 📌 `sprint_1`, `sprint_2`... | Tuần này team làm gì? |
| 📊 `Members` | Mỗi người đang làm bao nhiêu, tuần này so với tuần trước ra sao? |
| 📖 `README` | Luật chơi của board là gì? |
| 🗂️ `data` *(ẩn)* | Tự gom task từ các tab sprint bằng công thức QUERY để `Members` tính số. **Không sửa tay** |

### Tab sprint — "Tuần này team làm gì?"

Mỗi sprint là một tuần, mỗi tuần một tab: `sprint_1`, `sprint_2`... Đầu tab là **Daily Report** (Upcoming Milestones, Completed Tasks, Today's Focus, Risks), bên dưới là bảng task 8 cột.

Đây là tab **quan trọng nhất** — và cũng chính là trang khách nhận được dưới dạng PDF mỗi ngày.

### Việc chưa kịp làm thì đi đâu?

Sang sprint tiếp theo — với người nhận và ngày cụ thể. Tên tab luôn đặt theo sprint: `sprint_1`, `sprint_2`... nên mọi task luôn thuộc về một tuần nào đó.

✅ Cách tốt:

```
Tab: sprint_1 | sprint_2 | Members | README

Thứ 6 chốt sprint, task "Withdraw: Lighter → Koto" chưa xong
→ copy sang sprint_2, Notes ghi "Moved from sprint_1",
  Expected done date thứ 3 tuần sau.
```

Tại sao tốt: Task vẫn có người, có ngày, và thứ 3 tuần sau sẽ có người hỏi tới.

❌ Cách tồi:

```
Tab: Backlog | sprint_1 | Members | README

Thứ 6 chốt sprint, task chưa xong bị kéo về tab Backlog "lúc nào rảnh làm".
```

Tại sao tồi: Tab Backlog là nơi task đến rồi nằm chết. *"Cái này để sau làm"* — rồi không ai nhớ tới, cho đến ngày khách hỏi *"Cái anh nhờ tháng trước đâu rồi em?"*.

### Tab Members — "Ai đang quá tải?"

Tab `Members` cho PO bức tranh toàn team: mỗi người đang có bao nhiêu task, xong bao nhiêu, tuần này so với tuần trước.

### Bugs — Nằm ở đâu?

Bug cũng là một task: nằm trong tab sprint, dưới Milestone mà nó thuộc về, có Estimate, Assignee, Expected done date như mọi task khác. Gắn mức độ ở đầu tên task để nhìn là biết gấp hay không — VD Milestone `Trading Audit` của Koto: `[P0] O-1: Start the order form with an empty size...`, `[P1] P-3: Type any leverage directly...`.

Người chịu trách nhiệm Milestone thì chịu trách nhiệm luôn các bug thuộc Milestone đó.

---

## Tại sao mỗi Milestone phải có task UX/UI, QA, Code Refactor?

Đây là 3 luật đầu tiên trong Board Rule *(nằm ở tab `README` của mọi board, xem đủ ở phần quy tắc cứng của [quy trình](./board-create-process.md))*. Ba luật này là ba việc **dễ bị quên nhất** — không có dòng trên board thì không ai làm:

- **UX/UI** — Dev code xong mới phát hiện chưa có design cho trạng thái lỗi, trạng thái rỗng. Có task UX/UI ngay từ đầu Milestone = design đi trước code.
- **QA** — Không có task QA, đến ngày bàn giao mới thấy chưa ai test. Có task QA với Expected done date sau các task dev = QA có chỗ đứng trong kế hoạch, không phải "làm thêm nếu còn thời gian".
- **Code Refactor** — Refactor là nợ kỹ thuật mà **chỉ dev biết** — code cũ cần viết lại, performance cần tối ưu, dependency cần cập nhật. Không có task riêng, refactor sẽ luôn bị đẩy xuống cuối vì không "gấp" bằng feature mới — rồi nợ chồng nợ cho đến khi hệ thống quá chậm hoặc quá khó maintain. Mỗi Milestone một task refactor = trả nợ đều đặn, không để dồn.

---

## Lọc theo Milestone — Milestone này xong bao nhiêu phần trăm?

*Dữ liệu → Tạo chế độ xem lọc*, lọc cột Milestones.

Cần khi: Dự án có ≥ 5 Milestone chạy song song. PO muốn biết "Lighter Trading hoàn thành bao nhiêu phần trăm?" → lọc Milestone = Lighter - Trading, đếm Done/Total.

---

## Tóm lại

| Câu hỏi | Trả lời |
|---------|---------|
| Board là gì? | Bản mô phỏng trạng thái dự án — 10 giây biết có vấn đề |
| Dùng gì? | Google Sheet, copy từ `TEMPLATE`, nằm trong folder Project Management |
| Đặt tên? | `[Project]-Management` hoặc tên bộ phận |
| Bao nhiêu cột? | 8 — không thiếu, không thừa. Estimate bắt buộc |
| Tab chính? | Mỗi sprint một tab: `sprint_1`, `sprint_2`... |
| Ai tạo? | PO, Estimate cùng Dev, Assign cùng team |
| Status bao nhiêu? | 4. Không hơn. |

---

## Liên kết

- [Quy trình tạo Board](./board-create-process.md) — Luồng `TEMPLATE → ESTIMATE → ASSIGN → PLAN`, Board Rule, quy tắc cứng, checklist
- [AI Instruction](./board-create-ai-instruction/board-create-instruction.md) — AI soạn nháp task & Estimate từ Planning Report
- [Board Handbook — Quản lý board hằng ngày](../board-handbook/board-handbook.md) — Cập nhật tiến độ, Daily Report, export PDF gửi khách
