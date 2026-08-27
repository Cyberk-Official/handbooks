# Cyberk Handbook

> **"Làm thế nào để vấn đề này không lặp lại?"**
>
> Mỗi trang trong handbook này tồn tại vì ai đó đã từng vấp, đã rút ra bài học, và đã viết xuống — để người tiếp theo không phải trả cùng một cái giá.

---

## Tại sao bạn nên đọc handbook này?

Đây là nơi lưu lại kinh nghiệm và cách làm tốt của Cyberk. Từ cách tổ chức buổi planning, cách giao tiếp với khách hàng, đến cách viết daily report — tất cả đã được đúc kết thành quy trình và sổ tay hướng dẫn.

Đọc hiểu handbook, bạn có thể từ newbie nhanh chóng tạo ra output của một professional.

Mỗi quy trình trong đây tồn tại vì đã có người làm sai trước bạn Đọc handbook thì bạn không phải lặp lại sai lầm đó.
---

## Handbook giải quyết vấn đề gì?

- **Quy trình từng bước** (Process) — Các bước rõ ràng, cần làm theo
- **Chỉ dẫn thực hiện** (Handbook) — Giải thích tại sao cần làm từng bước, cách nghĩ đúng ở từng giai đoạn
- **Ví dụ tốt và không tốt** — Sẽ thấy các trường hợp không nên làm theo, và tại sao
- **Các mẫu** (Example) — Mẫu tốt để bắt chước, copy-paste được, tiết kiệm thời gian học

---

## Đọc thế nào?

- Mỗi folder có 3 loại file:
  - `*-process.md` — Các bước, checklist, diagram
  - `*-handbook.md` — Cách nghĩ, ví dụ tốt/tồi
  - `*-example.md` — Mẫu copy-paste
- **Người mới:** đọc [01-cyberk-way/](./01-cyberk-way/) + [Giao tiếp](./03-team/team-communicate/) + [Getting Started](./05-hr/getting-started/), rồi đọc theo vai trò
- **Dev:** [Daily Report](./04-delivery/dev-daily-report/) → [Board](./04-delivery/board-handbook/) → [Bug Handling](./04-delivery/qa-bugs-handling/)
- **QA:** [Bug Handling](./04-delivery/qa-bugs-handling/) → [Bug Logging](./04-delivery/qa-bugs-logs/)
- **PL/PM:** [Planning](./04-delivery/pl-planning/) → [Kick-off](./04-delivery/pl-kick-off/) → [Bàn giao](./04-delivery/pl-hangover/)
- **HR:** [Đón newbie](./05-hr/welcoming-newbie/) → [Getting Started](./05-hr/getting-started/)

---

## Cấu trúc handbook

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
└── 🛠 workflow/                # Playbook & Template
    ├── playbook.md             #   "Hiến pháp" hướng dẫn viết handbook
    ├── process-template.md     #   Template trang quy trình
    └── handbook-template.md    #   Template trang cẩm nang
```

---

## Muốn đóng góp?

Handbook là tài liệu sống — không bao giờ "xong". Nếu bạn thấy điều gì chưa đúng, thiếu, hoặc có thể tốt hơn: đó là lúc bạn đóng góp.

- [Cách nghĩ khi viết handbook](./02-about-handbook/contributing-handbook.md)
- [Quy trình đề xuất & duyệt](./02-about-handbook/contributing-process.md)
- [Playbook — hướng dẫn viết chi tiết](./workflow/playbook.md)

> *Thấy sai? Sửa ngay. Đó là tinh thần Cyberk.*
