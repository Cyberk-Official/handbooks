# Cyberk Handbook

> **"Làm thế nào để vấn đề này không lặp lại?"**
>
> Handbook là trái tim của Cyberk — nơi ghi lại cách làm, kinh nghiệm từ những sai lầm đi trước, và cách sửa sai. Mỗi trang tồn tại vì ai đó đã từng vấp, đã rút ra bài học, và đã viết xuống.

Nếu bạn là thành viên của Cyberk, đây là nơi bạn tìm thấy câu trả lời. Nếu bạn là người mới, bắt đầu từ [Tầng 1 — Nền tảng](#tầng-1--nền-tảng-ai-cũng-đọc).

---

## Bắt đầu từ đâu? — 4 tầng đọc

```
Tầng 1: Nền tảng        ← Ai cũng đọc (The Cyberk Way + Văn hoá)
Tầng 2: Vai trò          ← Đọc theo vị trí của bạn (Dev / QA / PL / HR)
Tầng 3: Tình huống       ← Đọc khi gặp case cụ thể (bàn giao, xử lý bug, onboard...)
Tầng 4: Đóng góp         ← Đọc khi muốn sửa/thêm handbook
```

> **Tips:** Đừng đọc hết một lần. Đọc Tầng 1 → đọc theo vai trò → tra theo tình huống khi cần. Process cho biết *luồng tổng thể*; Handbook giải thích *cách nghĩ*. Khi cần làm gì đó lần đầu, tìm file `-example.md` để copy-paste.

---

## Tầng 1 — Nền tảng (Ai cũng đọc)

> Đọc lần lượt từ trên xuống. Đây là "la bàn" — không có nền tảng này, bạn sẽ không hiểu tại sao chúng ta làm theo cách mình đang làm.

| # | Đọc gì | File | Thời gian |
|---|--------|------|-----------|
| 1 | **Lời nói đầu** — Tại sao handbook tồn tại | [0.1-loi-noi-dau.md](./01-cyberk-way/0.1-loi-noi-dau.md) | 2 phút |
| 2 | **Câu chuyện Cyberk** — Lịch sử hình thành từ ngày đầu | [0.3-lich-su-hinh-thanh.md](./01-cyberk-way/0.3-lich-su-hinh-thanh.md) | 5 phút |
| 3 | **Sứ mệnh & Giá trị cốt lõi** — La bàn cho mọi quyết định | [2.1-su-menh.md](./01-cyberk-way/2.1-su-menh.md) → [2.2-gia-tri-cot-loi.md](./01-cyberk-way/2.2-gia-tri-cot-loi.md) | 5 phút |
| 4 | **Tổng quan & Cơ cấu tổ chức** — Cyberk làm gì, phục vụ ai | [2.3-tong-quan.md](./01-cyberk-way/2.3-tong-quan-ve-cyberk.md) → [2.5-co-cau.md](./01-cyberk-way/2.5-co-cau-to-chuc.md) | 5 phút |
| 5 | **3 Bí quyết Cyberk** — Triết lý vận hành cốt lõi | [3.1](./01-cyberk-way/3.1-cham-hay-khong-bang-tay-quen.md) → [3.2](./01-cyberk-way/3.2-di-bat-bien-ung-van-bien.md) → [3.3](./01-cyberk-way/3.3-tram-nghe-khong-bang-mot-thay.md) | 10 phút |
| 6 | **Giao tiếp trong team** — Horenso: Báo cáo · Liên lạc · Thảo luận | [communicate-handbook.md](./03-team/team-communicate/communicate-handbook.md) | 10 phút |
| 7 | **Quy trình làm việc & Sprint một ngày** — Cách vận hành hàng ngày | [5.1-quy-trinh.md](./01-cyberk-way/5.1-quy-trinh.md) → [sprint-mot-ngay.md](./01-cyberk-way/5.1-sprint-mot-ngay.md) | 5 phút |

> ⏱ **Tổng: ~40 phút.** Đọc xong tầng này, bạn hiểu Cyberk là ai và cách chúng ta vận hành.

---

## Tầng 2 — Theo vai trò

### 🧑‍🎓 Nếu bạn là Newbie (vừa vào Cyberk)

| # | Đọc gì | File |
|---|--------|------|
| 1 | ⬆️ **Tầng 1 trước** | Xem bảng ở trên |
| 2 | Getting Started — Ngày đầu tiên | [getting-started/](./05-hr/getting-started/) |
| 3 | Daily Report — Bắt đầu viết từ ngày đầu | [daily-report-handbook.md](./04-delivery/dev-daily-report/daily-report-handbook.md) |
| 4 | Đọc thêm theo vai trò | Xem mục Dev / QA / PL bên dưới |

### 🧑‍💻 Nếu bạn là Developer

| # | Đọc gì | File |
|---|--------|------|
| 1 | Daily Report — Cách viết | [daily-report-handbook.md](./04-delivery/dev-daily-report/daily-report-handbook.md) |
| 2 | Board & Task — Quản lý công việc | [board-handbook/](./04-delivery/board-handbook/) |
| 3 | Bug Handling — Xử lý khi gặp bug | [qa-bugs-handling/](./04-delivery/qa-bugs-handling/) |

### 🧪 Nếu bạn là QA

| # | Đọc gì | File |
|---|--------|------|
| 1 | Bug Handling — Quy trình đầy đủ | [qa-bugs-handling/](./04-delivery/qa-bugs-handling/) |
| 2 | Severity & SLA | [bug-severity-sla-handbook.md](./04-delivery/qa-bugs-handling/bug-severity-sla-handbook.md) |
| 3 | Bug Logging trên GitHub | [qa-bugs-logs/](./04-delivery/qa-bugs-logs/) |

### 📋 Nếu bạn là Product Lead / PM

| # | Đọc gì | File |
|---|--------|------|
| 1 | Internal Planning — Họp nội bộ lập kế hoạch | [pl-planning/](./04-delivery/pl-planning/) |
| 2 | Kick-off với khách hàng | [pl-kick-off/](./04-delivery/pl-kick-off/) |
| 3 | Bàn giao sản phẩm | [pl-hangover/](./04-delivery/pl-hangover/) |
| 4 | Board & Task Management | [board-handbook/](./04-delivery/board-handbook/) |
| 5 | Daily Report — Đảm bảo team report đúng | [dev-daily-report/](./04-delivery/dev-daily-report/) |

### 👔 Nếu bạn là HR / Manager

| # | Đọc gì | File |
|---|--------|------|
| 1 | Đón người mới — Quy trình cho HR | [welcoming-newbie/](./05-hr/welcoming-newbie/) |
| 2 | Thành viên join dự án | [project-onboarding/](./03-team/project-onboarding/) |
| 3 | Thành viên rời dự án | [project-leave/](./03-team/project-leave/) |

---

## Tầng 3 — Theo tình huống

> Không cần đọc hết. Tra khi gặp case cụ thể.

| Tôi đang cần... | Đọc |
|-----------------|-----|
| Viết daily report | [04-delivery/dev-daily-report/](./04-delivery/dev-daily-report/) |
| Xử lý 1 con bug | [04-delivery/qa-bugs-handling/](./04-delivery/qa-bugs-handling/) |
| Tạo bug trên GitHub | [04-delivery/qa-bugs-logs/](./04-delivery/qa-bugs-logs/) |
| Quản lý board/task | [04-delivery/board-handbook/](./04-delivery/board-handbook/) |
| Lập kế hoạch dự án (nội bộ) | [04-delivery/pl-planning/](./04-delivery/pl-planning/) |
| Kick-off với khách hàng | [04-delivery/pl-kick-off/](./04-delivery/pl-kick-off/) |
| Bàn giao sản phẩm cho client | [04-delivery/pl-hangover/](./04-delivery/pl-hangover/) |
| Đón newbie vào công ty | [05-hr/welcoming-newbie/](./05-hr/welcoming-newbie/) |
| Đưa người mới vào dự án | [03-team/project-onboarding/](./03-team/project-onboarding/) |
| Chuyển giao khi rời dự án | [03-team/project-leave/](./03-team/project-leave/) |
| Hiểu cách giao tiếp nội bộ | [03-team/team-communicate/](./03-team/team-communicate/) |

---

## Tầng 4 — Đóng góp vào Handbook

> Đọc khi bạn muốn **sửa, thêm, hoặc cải thiện** handbook.

| # | Đọc gì | File |
|---|--------|------|
| 1 | Tại sao viết handbook quan trọng | [contributing-handbook.md](./02-about-handbook/contributing-handbook.md) |
| 2 | Quy trình đề xuất & duyệt (PR) | [contributing-process.md](./02-about-handbook/contributing-process.md) |
| 3 | Ai chịu trách nhiệm mục nào | [owners-reference.md](./02-about-handbook/owners-reference.md) |
| 4 | Playbook — Hướng dẫn viết chi tiết | [playbook.md](./workflow/playbook.md) |
| 5 | Template Process & Handbook | [process-template.md](./workflow/process-template.md) · [handbook-template.md](./workflow/handbook-template.md) |

---

## Cấu trúc thư mục

```
handbook/
│
├── 📖 01-cyberk-way/          # Triết lý, bí quyết, cách vận hành
├── 📋 02-about-handbook/       # Cách đóng góp, owners, quy trình viết
├── 🤝 03-team/                 # Văn hoá, giao tiếp, join/leave dự án
│   ├── team-communicate/       #   Horenso — báo cáo, liên lạc, thảo luận
│   ├── project-onboarding/     #   Thành viên mới tham gia dự án
│   └── project-leave/          #   Thành viên rời khỏi dự án
├── 🔧 04-delivery/             # Quy trình làm sản phẩm
│   ├── pl-planning/            #   Internal Planning Meeting (nội bộ)
│   ├── pl-kick-off/            #   Kick-off Meeting (với khách hàng)
│   ├── pl-hangover/            #   Bàn giao sản phẩm
│   ├── dev-daily-report/       #   Daily report
│   ├── board-handbook/         #   Quản lý board GitHub Projects
│   ├── qa-bugs-handling/       #   Xử lý bugs
│   └── qa-bugs-logs/           #   Logging bugs trên GitHub
├── 👥 05-hr/                   # Con người
│   ├── getting-started/        #   Ngày đầu tiên cho newbie
│   └── welcoming-newbie/       #   Chuẩn bị đón người mới (cho HR)
└── 🛠 workflow/                # Template & Playbook
    ├── playbook.md             #   "Hiến pháp" hướng dẫn viết handbook
    ├── process-template.md     #   Template trang quy trình
    └── handbook-template.md    #   Template trang cẩm nang
```

---

> Handbook là tài liệu sống. Không bao giờ "xong". Nếu bạn thấy điều gì chưa đúng hoặc có thể tốt hơn — [đề xuất sửa](./02-about-handbook/contributing-process.md). Đó cũng là tinh thần Cyberk.
