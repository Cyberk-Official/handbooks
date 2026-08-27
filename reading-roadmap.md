# Reading Roadmap — Đọc Handbook theo lộ trình

> Handbook có rất nhiều tài liệu. Trang này giúp bạn biết **nên đọc gì, theo thứ tự nào**, tuỳ thuộc bạn là ai và cần gì.

---

## 🗺️ Tổng quan — 4 tầng đọc

```
Tầng 1: Nền tảng        ← Ai cũng đọc (The Cyberk Way + Văn hoá)
Tầng 2: Vai trò          ← Đọc theo vị trí của bạn (Dev / QA / PL / HR)
Tầng 3: Tình huống       ← Đọc khi gặp case cụ thể (bàn giao, xử lý bug, onboard...)
Tầng 4: Đóng góp         ← Đọc khi muốn sửa/thêm handbook
```

---

## Tầng 1 — Nền tảng (Ai cũng đọc)

> Đọc lần lượt từ trên xuống. Đây là "la bàn" — không có nền tảng này, bạn sẽ không hiểu tại sao chúng ta làm theo cách mình đang làm.

| # | Đọc gì | File | Thời gian |
|---|--------|------|-----------|
| 1 | **Lời nói đầu** — Tại sao handbook tồn tại | [0.1-loi-noi-dau.md](./01-cyberk-way/0.1-loi-noi-dau.md) | 2 phút |
| 2 | **Câu chuyện Cyberk** — Lịch sử hình thành từ ngày đầu | [0.3-lich-su-hinh-thanh.md](./01-cyberk-way/0.3-lich-su-hinh-thanh.md) | 5 phút |
| 3 | **Sứ mệnh & Giá trị cốt lõi** — La bàn cho mọi quyết định | [2.1-su-menh.md](./01-cyberk-way/2.1-su-menh.md) → [2.2-gia-tri-cot-loi.md](./01-cyberk-way/2.2-gia-tri-cot-loi.md) | 5 phút |
| 4 | **Tổng quan & Cơ cấu tổ chức** — Cyberk làm gì, phục vụ ai, team tổ chức ra sao | [2.3-tong-quan.md](./01-cyberk-way/2.3-tong-quan-ve-cyberk.md) → [2.5-co-cau.md](./01-cyberk-way/2.5-co-cau-to-chuc.md) | 5 phút |
| 5 | **3 Bí quyết Cyberk** — Triết lý vận hành cốt lõi | [3.1](./01-cyberk-way/3.1-cham-hay-khong-bang-tay-quen.md) → [3.2](./01-cyberk-way/3.2-di-bat-bien-ung-van-bien.md) → [3.3](./01-cyberk-way/3.3-tram-nghe-khong-bang-mot-thay.md) | 10 phút |
| 6 | **Horenso** — Nghệ thuật giao tiếp nội bộ: Báo cáo · Liên lạc · Thảo luận | [horenso.md](./team/02-culture/horenso.md) | 10 phút |
| 7 | **Quy trình làm việc & Sprint một ngày** — Cách vận hành hàng ngày | [5.1-quy-trinh.md](./01-cyberk-way/5.1-quy-trinh.md) → [sprint-mot-ngay.md](./01-cyberk-way/5.1-sprint-mot-ngay.md) | 5 phút |

> ⏱ **Tổng: ~40 phút.** Đọc xong tầng này, bạn hiểu Cyberk là ai và cách chúng ta vận hành.

---

## Tầng 2 — Theo vai trò

### 🧑‍💻 Nếu bạn là Developer

| # | Đọc gì | File | Tại sao |
|---|--------|------|---------|
| 1 | Daily Report — Cách viết | [daily-report-handbook.md](./delivery/dev-daily-report/daily-report-handbook.md) | Viết mỗi ngày, cần đúng cách ngay từ đầu |
| 2 | Board & Task — Quản lý công việc | [board handbook.md](./delivery/board-handbook/handbook.md) | Hiểu cách tạo task chuẩn, board chuẩn |
| 3 | Bug Handling — Xử lý khi gặp bug | [bug-handling-process.md](./delivery/qa-bugs-handling/bug-handling-process.md) | Biết luồng xử lý, không tự ý fix mà không log |
| 4 | AI-Driven Development | [ai-driven-development.md](./delivery/dev/ai-driven-development.md) | Cách Cyberk tận dụng AI trong phát triển |
| 5 | Solo-dev Way | [solodev-way.md](./delivery/dev/solodev-way.md) | Tư duy dev độc lập, làm việc như CTO |
| 6 | Asimov Pipeline | [asimove-pipeline.md](./delivery/dev/asimove-pipeline.md) | Pipeline sản xuất phần mềm tiên tiến |

### 🧪 Nếu bạn là QA

| # | Đọc gì | File | Tại sao |
|---|--------|------|---------|
| 1 | Bug Handling — Quy trình đầy đủ | [bug-handling-process.md](./delivery/qa-bugs-handling/bug-handling-process.md) → [bug-handling-handbook.md](./delivery/qa-bugs-handling/bug-handling-handbook.md) | Luồng xử lý bug từ A→Z |
| 2 | Severity & SLA | [bug-severity-sla-handbook.md](./delivery/qa-bugs-handling/bug-severity-sla-handbook.md) | Phân loại bug, thời gian phản hồi cam kết |
| 3 | Mẫu tin nhắn tiếp nhận bug | [acknowledgment-messages-example.md](./delivery/qa-bugs-handling/acknowledgment-messages-example.md) | Copy-paste khi tiếp nhận bug |
| 4 | Bug Logging trên GitHub | [qa-bugs-logs-process.md](./delivery/qa-bugs-logs/qa-bugs-logs-process.md) | Format tạo issue chuẩn |

### 📋 Nếu bạn là Product Lead / PM

| # | Đọc gì | File | Tại sao |
|---|--------|------|---------|
| 1 | Board & Task Management | [board handbook.md](./delivery/board-handbook/handbook.md) | Quản lý dự án hiệu quả trên GitHub |
| 2 | Planning & Kickoff | [planning-instruction.md](./delivery/planning/planning-instruction.md) → [planning-template.md](./delivery/planning/planning-template.md) | Cách tổ chức kickoff meeting, lập kế hoạch |
| 3 | Bàn giao sản phẩm — Quy trình | [handover-process.md](./delivery/pl-hangover/handover-process.md) | 4 bước bàn giao cho client |
| 4 | Bàn giao sản phẩm — Cẩm nang | [handover-handbook.md](./delivery/pl-hangover/handover-handbook.md) | Cách nghĩ đúng ở từng giai đoạn |
| 5 | Bàn giao — Mẫu & Template | [handover-example.md](./delivery/pl-hangover/handover-example.md) | Slide outline, mẫu tin nhắn, email recap |
| 6 | Maintenance Policy | [maintenance-policy-reference.md](./delivery/pl-hangover/maintenance-policy-reference.md) | SLA, thời hạn bảo trì |
| 7 | Daily Report — Quy trình | [daily-report-process.md](./delivery/dev-daily-report/daily-report-process.md) | Đảm bảo team report đúng cách |

### 👔 Nếu bạn là HR / Manager

| # | Đọc gì | File | Tại sao |
|---|--------|------|---------|
| 1 | Đón người mới — Quy trình cho HR | [welcoming-newbie-process.md](./hr/welcoming-newbie/welcoming-newbie-process.md) → [welcoming-newbie-handbook.md](./hr/welcoming-newbie/welcoming-newbie-handbook.md) | Chuẩn bị đón newbie |
| 2 | Thành viên join dự án | [project-onboarding/](./team/project-onboarding/) | Quy trình đưa người mới vào dự án |
| 3 | Thành viên rời dự án | [project-leave/](./team/project-leave/) | Quy trình chuyển giao khi rời dự án |

### 🧑‍🎓 Nếu bạn là Newbie (vừa vào Cyberk)

| # | Đọc gì | File | Tại sao |
|---|--------|------|---------|
| 1 | ⬆️ **Tầng 1 trước** | Xem bảng ở trên | Hiểu Cyberk là ai |
| 2 | Getting Started — Ngày đầu tiên | [getting-started-process.md](./hr/getting-started/getting-started-process.md) → [getting-started-handbook.md](./hr/getting-started/getting-started-handbook.md) | Checklist ngày đầu, cần làm gì |
| 3 | Ăn trưa ở đâu? | [lunch-handbook.md](./hr/getting-started/lunch-handbook.md) | Cơm nhà, quán quanh văn phòng |
| 4 | Trang phục | [outfit-handbook.md](./hr/getting-started/outfit-handbook.md) | Cyberk mặc gì đi làm |
| 5 | Daily Report | [daily-report-handbook.md](./delivery/dev-daily-report/daily-report-handbook.md) | Bắt đầu viết từ ngày đầu tiên |
| 6 | Đọc thêm theo vai trò | Xem mục Dev / QA / PL ở trên | Chọn đúng track của bạn |

---

## Tầng 3 — Theo tình huống

> Không cần đọc hết. Đọc khi gặp case cụ thể.

| Tôi đang cần... | Đọc |
|-----------------|-----|
| Viết daily report | [delivery/dev-daily-report/](./delivery/dev-daily-report/) |
| Xử lý 1 con bug | [delivery/qa-bugs-handling/](./delivery/qa-bugs-handling/) |
| Tạo bug trên GitHub | [delivery/qa-bugs-logs/](./delivery/qa-bugs-logs/) |
| Quản lý board/task | [delivery/board-handbook/](./delivery/board-handbook/) |
| Kickoff dự án mới | [delivery/planning/](./delivery/planning/) |
| Bàn giao sản phẩm cho client | [delivery/pl-hangover/](./delivery/pl-hangover/) |
| Đón newbie vào công ty | [hr/welcoming-newbie/](./hr/welcoming-newbie/) |
| Đưa người mới vào dự án | [team/project-onboarding/](./team/project-onboarding/) |
| Chuyển giao khi rời dự án | [team/project-leave/](./team/project-leave/) |
| Tìm hiểu AI-driven dev | [delivery/dev/](./delivery/dev/) |
| Hiểu cách giao tiếp nội bộ | [team/02-culture/horenso.md](./team/02-culture/horenso.md) |

---

## Tầng 4 — Đóng góp vào Handbook

> Đọc khi bạn muốn **sửa, thêm, hoặc cải thiện** handbook.

| # | Đọc gì | File |
|---|--------|------|
| 1 | Tại sao viết handbook quan trọng | [contributing-handbook.md](./05-about-handbook/contributing-handbook.md) |
| 2 | Quy trình đề xuất & duyệt (PR) | [contributing-process.md](./05-about-handbook/contributing-process.md) |
| 3 | Ai chịu trách nhiệm mục nào | [owners-reference.md](./05-about-handbook/owners-reference.md) |
| 4 | Playbook — Hướng dẫn viết chi tiết | [playbook.md](./playbook.md) |
| 5 | Template Process | [process-template.md](./workflow/process-template.md) |
| 6 | Template Handbook | [handbook-template.md](./workflow/handbook-template.md) |

---

## Tips đọc hiệu quả

1. **Đừng đọc hết một lần.** Đọc Tầng 1 → đọc theo vai trò → tra theo tình huống khi cần.
2. **Process trước, Handbook sau.** Process cho biết *luồng tổng thể*; Handbook giải thích *cách nghĩ*.
3. **Example là bạn.** Khi cần làm gì đó lần đầu, tìm file `-example.md` để copy-paste.
4. **Thấy sai? Sửa ngay.** Đọc → thấy thiếu/sai → mở PR. Đó là cách handbook sống.

> *"Làm thế nào để vấn đề này không lặp lại?"*
> — Câu hỏi khởi nguồn cho mọi trang trong handbook.
