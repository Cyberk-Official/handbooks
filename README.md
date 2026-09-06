# Cyberk Handbook

> **"Làm thế nào để vấn đề này không lặp lại?"**
>
> Mỗi trang trong handbook này tồn tại vì ai đó đã từng vấp, đã rút ra bài học, và đã viết xuống — để người tiếp theo không phải trả cùng một cái giá.

---

## Tại sao bạn nên đọc handbook này?

Đây là nơi lưu lại kinh nghiệm và cách làm tốt của Cyberk. Từ cách tổ chức buổi planning, cách giao tiếp với khách hàng, đến cách viết daily report — tất cả đã được đúc kết thành quy trình và sổ tay hướng dẫn.

Đọc hiểu handbook, bạn có thể từ newbie nhanh chóng tạo ra output của một professional.

Mỗi quy trình trong đây tồn tại vì đã có người làm sai trước bạn. Đọc handbook thì bạn không phải lặp lại sai lầm đó.

---

## Handbook giải quyết vấn đề gì?

- **Quy trình từng bước** (Process) — Các bước rõ ràng, cần làm theo
- **Chỉ dẫn thực hiện** (Handbook) — Giải thích tại sao cần làm từng bước, cách nghĩ đúng ở từng giai đoạn
- **Ví dụ tốt và không tốt** — Sẽ thấy các trường hợp không nên làm theo, và tại sao
- **Các mẫu** (Example) — Mẫu tốt để bắt chước, copy-paste được, tiết kiệm thời gian học

---

## Đọc thế nào?

- Mỗi folder có thể chứa tối đa 7 loại file (xem [Playbook](./workflow/playbook.md)):
  - `*-process.md` — Các bước, checklist, diagram
  - `*-handbook.md` — Cách nghĩ, ví dụ tốt/tồi
  - `*-example.md` — Mẫu copy-paste
  - `*-reference.md` — Bảng tra cứu nhanh (SLA, phân loại...)
  - `*-policy.md` — Chính sách, quy định
  - `*-role.md` — Vai trò, trách nhiệm
  - `*-ai-instruction/` — Hướng dẫn cho AI sinh nội dung
- **Người mới:** đọc [01-cyberk-way/](./01-cyberk-way/) + [Giao tiếp](./03-team/team-communicate/) + [Getting Started](./07-hr/newbie-getting-started/), rồi đọc theo vai trò
- **Dev:** [Daily Report](./04-developer/dev-daily-report/) → [Board](./05-product-owner/board-handbook/) → [Bug Handling](./06-qa/qa-bugs-handling/)
- **QA:** [Bug Handling](./06-qa/qa-bugs-handling/) → [Bug Logging](./06-qa/qa-bugs-logs/)
- **PO:** [Planning](./05-product-owner/po-planning/) → [Kick-off](./05-product-owner/po-kick-off/) → [Bàn giao](./05-product-owner/po-handover/)
- **HR:** [Đón newbie](./07-hr/admin-welcoming-newbie/) → [Getting Started](./07-hr/newbie-getting-started/)

---

## Cấu trúc handbook

```
handbook/
│
├── 📖 01-cyberk-way/           # Triết lý, bí quyết, cách vận hành
├── 📋 02-about-handbook/        # Cách đóng góp, owners, quy trình viết
├── 🤝 03-team/                  # Văn hoá & giao tiếp chung (mọi role)
│   └── team-communicate/        #   Horenso — báo cáo, liên lạc, thảo luận
│
├── 💻 04-developer/             # Dành cho Developer
│   ├── dev-daily/               #   Quản lý công việc cá nhân hàng ngày
│   ├── dev-project-onboarding/  #   Tham gia dự án mới
│   ├── dev-daily-report/        #   Viết Daily Report gửi khách hàng
│   ├── dev-tasks-logs/          #   Tạo & quản lý task trên board (AI-driven)
│   └── dev-write-brd/           #   Viết BRD khi phát sinh yêu cầu mới
│
├── 🎯 05-product-owner/         # Dành cho Product Owner
│   ├── po-project-leave/        #   Quy trình thành viên rời dự án
│   ├── po-planning/             #   Internal Planning Meeting (nội bộ)
│   ├── po-kick-off/             #   Kick-off Meeting (với khách hàng)
│   ├── po-board-create/         #   Khởi tạo Board dự án
│   ├── po-handover/             #   Bàn giao sản phẩm
│   └── board-handbook/          #   Quản lý board GitHub Projects
│
├── 🔍 06-qa/                    # Dành cho QA
│   ├── qa-bugs-handling/        #   Xử lý & phân loại bugs
│   ├── qa-bugs-logs/            #   Logging bugs trên GitHub
│   └── blameless-postmortem.md  #   Quy trình Postmortem
│
├── 👥 07-hr/                    # Con người & onboarding
│   ├── newbie-getting-started/  #   Ngày đầu tiên cho newbie
│   ├── admin-welcoming-newbie/  #   Chuẩn bị đón người mới (cho HR)
│   └── leader-policy-issuance/  #   Ban hành chính sách
│
├── 🎬 08-media/                 # Media & VJ
└── 🛠 workflow/                 # Playbook & Template
    ├── playbook.md              #   "Hiến pháp" hướng dẫn viết handbook
    ├── process-template.md      #   Template trang quy trình
    └── handbook-template.md     #   Template trang cẩm nang
```


---

## Muốn đóng góp?

Handbook là tài liệu sống — không bao giờ "xong". Nếu bạn thấy điều gì chưa đúng, thiếu, hoặc có thể tốt hơn: đó là lúc bạn đóng góp.

- [Cách nghĩ khi viết handbook](./02-about-handbook/contributing-handbook.md)
- [Quy trình đề xuất & duyệt](./02-about-handbook/contributing-process.md)
- [Playbook — hướng dẫn viết chi tiết](./workflow/playbook.md)

> *Thấy sai? Sửa ngay. Đó là tinh thần Cyberk.*
