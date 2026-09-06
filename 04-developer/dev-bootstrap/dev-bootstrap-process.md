---
type: process
tags: [bootstrap, setup, project-kickoff, developer, cto]
created-date: 2026-09-06
updated-date: 2026-09-06
author: anderson
status: Nháp
---

# Bootstrap Dự Án — Quy trình

**Người chịu trách nhiệm:** CTO (điều phối) + Tech Lead (thực thi)
**Cập nhật lần cuối:** 2026-09-06
**Trạng thái:** Nháp

## Tại sao có trang này

### Vấn đề hiện tại

Sau khi proposal được ký, team thường mất **2–3 tuần đầu chỉ để setup**: tạo repo, cài framework, viết auth, setup database, tạo admin panel, vẽ ERD, viết API scaffold... Trong khi đó, client đã trả tiền và đang chờ thấy tiến độ thực sự.

Hậu quả: **Sprint 1 gần như không ra được feature nào có giá trị** — chỉ ra infrastructure. Client không thấy được gì. Team bị áp lực "không có gì để show".

### Giải pháp — Bootstrap Phase

Thay vì setup từng dự án từ con số 0, Cyberk chuẩn hóa một **Bootstrap Phase** diễn ra ngay sau khi ký hợp đồng và trước Sprint 1 chính thức:

> **Mục tiêu:** Đến ngày Kick-off với client, dự án đã có **50–80% infrastructure sẵn sàng** — authentication chạy được, database có schema, admin panel hoạt động, API scaffold có, frontend kết nối được backend. Developer nhảy vào là code business logic ngay, không phải mất thêm 2 tuần setup.

### Tại sao giao cho CTO quản lý?

Bootstrap là công việc kỹ thuật thuần túy — không cần nhiều giao tiếp với client, cần quyết định nhanh về kiến trúc, cần người đủ tầm nhìn để setup đúng từ đầu. CTO là người phù hợp nhất để:
- Chọn tech stack, template, framework đúng với dự án
- Đảm bảo naming convention, folder structure nhất quán
- Giao việc và track progress mà không cần họp nhiều
- Bàn giao lại cho team với documentation đầy đủ

---

## Khi nào áp dụng (Trigger)

- Hợp đồng đã ký, deposit đã nhận
- Internal Planning Meeting đã xong, có PRD/BRD
- **Trước** khi bắt đầu Sprint 1 chính thức

## Thời gian mục tiêu

**3–5 ngày làm việc** (tùy độ phức tạp của tech stack).
Nếu quá 7 ngày → escalate lên Anderson, xem xét lại scope Bootstrap.

---

## Vai trò & trách nhiệm

| Vai trò | Chịu trách nhiệm gì |
|---------|---------------------|
| **CTO** | Giao task, review kết quả từng milestone, duyệt kiến trúc, bàn giao cho team |
| **Tech Lead / Senior Dev** | Thực thi bootstrap, tạo repo, code các module nền tảng |
| **PO** | Cung cấp PRD, trả lời câu hỏi về business logic khi cần |
| **Anderson** | Nhận báo cáo hoàn thành, không can thiệp vào chi tiết kỹ thuật |

---

## Các bước

### Milestone 0 — Chuẩn bị (Ngày 1 sáng)

| # | Việc làm | Ai làm | Đầu ra |
|---|----------|--------|--------|
| 0.1 | Đọc PRD/BRD, liệt kê các entity chính (User, Product, Order...) | CTO + Tech Lead | Danh sách entities |
| 0.2 | Chọn tech stack dứt khoát — không thay đổi sau bước này | CTO | Tech stack document |
| 0.3 | Tạo repository theo chuẩn ([dev-new-repo](../dev-new-repo/dev-new-repo-process.md)) | Tech Lead | Repo live trên GitHub |
| 0.4 | Setup project từ template/boilerplate phù hợp | Tech Lead | App chạy được `Hello World` |

### Milestone 1 — Database & Architecture (Ngày 1–2)

| # | Việc làm | Ai làm | Đầu ra |
|---|----------|--------|--------|
| 1.1 | Vẽ **ERD** (Entity Relationship Diagram) — tất cả bảng, quan hệ, index | Tech Lead | ERD file (dbdiagram.io hoặc tương đương) |
| 1.2 | Review ERD với CTO — duyệt trước khi code | CTO | ERD đã duyệt |
| 1.3 | Viết **Database Schema** (migration files) từ ERD đã duyệt | Tech Lead | Migration files commit |
| 1.4 | Chạy migration thành công trên local | Tech Lead | DB local có đầy đủ bảng |
| 1.5 | Setup **seed data** tối thiểu — đủ để test | Tech Lead | Seed script hoạt động |

### Milestone 2 — Authentication (Ngày 2–3)

| # | Việc làm | Ai làm | Đầu ra |
|---|----------|--------|--------|
| 2.1 | Implement **Authentication** — Register / Login / Logout / Refresh Token | Tech Lead | Auth API chạy được |
| 2.2 | Setup **Role-based Access Control (RBAC)** — các role từ PRD | Tech Lead | Middleware phân quyền hoạt động |
| 2.3 | Test auth flow đầy đủ (happy path + error cases) | Tech Lead | Auth tested, không có lỗi cơ bản |

### Milestone 3 — Admin Panel (Ngày 3–4)

| # | Việc làm | Ai làm | Đầu ra |
|---|----------|--------|--------|
| 3.1 | Setup **Admin Panel** — CRUD cho các entity chính | Tech Lead | Admin panel chạy được |
| 3.2 | Admin có thể login, quản lý users, xem data | Tech Lead | Admin flow hoạt động |
| 3.3 | Review với CTO | CTO | Duyệt hoặc feedback |

### Milestone 4 — API Scaffold (Ngày 3–4)

| # | Việc làm | Ai làm | Đầu ra |
|---|----------|--------|--------|
| 4.1 | Viết **API scaffold** cho tất cả entity trong ERD — CRUD cơ bản | Tech Lead | API endpoints tồn tại, trả về đúng format |
| 4.2 | Setup **API documentation** (Swagger / Postman Collection) | Tech Lead | Docs có thể share cho frontend/client |
| 4.3 | Không cần có business logic — chỉ cần đúng contract (request/response shape) | Tech Lead | Frontend có thể mock data từ API thật |

### Milestone 5 — Frontend Foundation (Ngày 4–5)

| # | Việc làm | Ai làm | Đầu ra |
|---|----------|--------|--------|
| 5.1 | Setup frontend project, routing, layout chính | Tech Lead | App frontend chạy được |
| 5.2 | Kết nối frontend với backend — auth flow chạy end-to-end | Tech Lead | Login từ UI → JWT → API hoạt động |
| 5.3 | Setup các trang skeleton cho từng major feature (chỉ cần UI khung, chưa cần data thật) | Tech Lead | Team frontend có thể làm việc ngay |

### Milestone 6 — Documentation & Handover (Ngày 5)

| # | Việc làm | Ai làm | Đầu ra |
|---|----------|--------|--------|
| 6.1 | Cập nhật `README.md` — setup guide đầy đủ, ai clone về cũng tự chạy được | Tech Lead | README hoàn chỉnh |
| 6.2 | Viết **Architecture Decision Record (ADR)** — ghi lại mọi quyết định kiến trúc quan trọng và lý do | CTO | ADR document |
| 6.3 | Tạo **Environment Setup Guide** — `.env.example` đầy đủ, mô tả từng key | Tech Lead | `.env.example` commit |
| 6.4 | CTO review toàn bộ codebase — check naming, structure, patterns | CTO | Review comment đã resolved |
| 6.5 | Demo ngắn cho team (15 phút) — clone, chạy, xem flow | CTO | Mọi developer biết cách chạy |
| 6.6 | Thông báo PO — Bootstrap xong, sẵn sàng Sprint 1 | CTO | PO cập nhật lịch |

---

## Quy tắc cứng

| Quy tắc | Lý do |
|---------|-------|
| **ERD phải được duyệt trước khi viết schema** | Đổi ERD sau khi có data = migration đau đầu, data loss risk |
| **Không code business logic trong Bootstrap** | Bootstrap chỉ làm nền tảng. Business logic = Sprint 1 trở đi |
| **Tech stack không được thay đổi sau Milestone 0** | Đổi giữa chừng = làm lại từ đầu |
| **README phải đủ để người mới tự setup trong 30 phút** | Nếu phải hỏi = README chưa đủ |
| **Không Bootstrap quá 7 ngày** | Bootstrap kéo dài = scope quá lớn hoặc team thiếu năng lực. Cần escalate |
| **CTO phải review trước khi Handover** | Không để technical debt ngay từ ngày đầu |

## Checklist tự kiểm — trước khi khai báo Bootstrap Done

- [ ] Repo tồn tại trên `github.com/Cyberk-Official/`, Private, đúng tên
- [ ] Nhánh `main` và `develop` đã có, Branch Protection đã bật
- [ ] ERD đã được CTO duyệt và lưu vào Wiki/README
- [ ] Database migrations chạy thành công từ migration files
- [ ] Auth (Register/Login/Logout/Refresh) hoạt động, có RBAC
- [ ] Admin panel CRUD được ít nhất 2 entity chính
- [ ] API scaffold đầy đủ cho tất cả entity trong ERD
- [ ] API Docs (Swagger/Postman) đã có và accessible
- [ ] Frontend chạy được, kết nối được backend, auth flow end-to-end
- [ ] `.env.example` đầy đủ, không thiếu key nào
- [ ] README: mô tả, tech stack, setup guide ≤ 30 phút
- [ ] ADR document ghi lại quyết định kiến trúc chính
- [ ] Đã demo cho team — mọi người tự clone + chạy được

## Ngoại lệ & escalation

| Tình huống | Xử lý |
|------------|--------|
| Bootstrap > 7 ngày | CTO báo Anderson ngay, giải thích lý do, đề xuất scope trim |
| PRD chưa đủ rõ để vẽ ERD | CTO mở meeting với PO giải quyết trong 1h, không chờ |
| Tech stack client yêu cầu team chưa biết | CTO báo Anderson ngay — không tự quyết |
| Client muốn xem tiến độ trong khi đang Bootstrap | PO handle, giải thích "đang setup nền tảng, Sprint 1 sẽ show feature" |

## Liên kết

- [Cẩm nang Bootstrap — cách nghĩ & các quyết định quan trọng](./dev-bootstrap-handbook.md)
- [Tạo Repository mới](../dev-new-repo/dev-new-repo-process.md)
- [Internal Planning — bước trước Bootstrap](../../05-product-owner/po-planning/planning-process.md)
- [Kick-off với client — bước sau Bootstrap](../../05-product-owner/po-kick-off/kick-off-process.md)
- [Onboarding developer mới vào dự án — sau Bootstrap](../dev-project-onboarding/dev-project-onboarding-process.md)
