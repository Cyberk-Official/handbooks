---
type: process
tags: [github, repository, setup, developer]
created-date: 2026-09-06
updated-date: 2026-09-06
author: anderson
status: Nháp
---

# Tạo Repository Mới — Quy trình

**Người chịu trách nhiệm:** PO dự án (tạo repo) + Developer (setup local)
**Cập nhật lần cuối:** 2026-09-06
**Trạng thái:** Nháp

## Tại sao có trang này

Mỗi dự án tại Cyberk bắt đầu bằng một repository. Tạo sai cấu trúc từ đầu — tên không chuẩn, thiếu nhánh `develop`, thiếu `.gitignore` — gây lộn xộn về sau rất khó sửa. Trang này chuẩn hóa quy trình để mọi repo của Cyberk nhất quán ngay từ ngày đầu.

## Khi nào áp dụng (Trigger)

- Dự án mới ký hợp đồng và cần khởi động
- Tách module lớn thành repo riêng
- Tạo repo phục vụ internal tool / automation

## Vai trò & trách nhiệm

| Vai trò | Chịu trách nhiệm gì |
|---------|---------------------|
| **PO / Tech Lead** | Quyết định tên repo, visibility, team permission |
| **Developer (người tạo)** | Thực hiện các bước tạo và cấu hình trên GitHub |
| **Mọi Developer** | Clone, setup local, chạy được trên máy mình |

## Các bước

### Phần A — Tạo Repository trên GitHub

| # | Việc làm | Ai làm | Đầu ra |
|---|----------|--------|--------|
| 1 | **Đặt tên repo** — theo quy ước `[client]-[project]` (VD: `relmo-backend`, `koto-mobile`). Dùng kebab-case, không dùng camelCase hay underscore. | PO / Tech Lead | Tên repo đã chốt |
| 2 | **Tạo repo** trên GitHub tại `github.com/Cyberk-Official/` — **Private** mặc định. Không tạo repo Public trừ khi đã được Anderson duyệt. | Developer | Repo tồn tại trên GitHub |
| 3 | **Cấu hình Repository Settings** — (xem chi tiết ở Bước 3 của handbook) | Developer | Settings đã đúng chuẩn |
| 4 | **Khởi tạo nhánh chuẩn** — tạo `main` (production) và `develop` (integration). Set `develop` làm default branch. | Developer | 2 nhánh đã tồn tại |
| 5 | **Thêm `.gitignore`** — chọn đúng ngôn ngữ/framework. Bổ sung thêm các entry đặc thù dự án. | Developer | `.gitignore` commit đầu tiên |
| 6 | **Tạo `README.md` khởi đầu** — theo template chuẩn (xem example). Tối thiểu: mô tả dự án, tech stack, hướng dẫn setup local. | Developer | README commit đầu tiên |
| 7 | **Thêm `AGENTS.md`** (nếu dự án có AI agent làm việc) — quy tắc cho AI agents trong repo này. | Developer | AGENTS.md commit đầu tiên |
| 8 | **Cấu hình Branch Protection Rules** cho nhánh `main` và `develop` | Developer | Không ai push thẳng được vào main |
| 9 | **Add team members** — thêm đúng nhân sự vào repo với đúng permission level | PO / Tech Lead | Mọi người vào được |
| 10 | **Thông báo team** qua Telegram — gửi link repo, mô tả ngắn, ai làm gì | PO | Team nhận thông báo |

### Phần B — Setup Local (mỗi Developer)

| # | Việc làm | Ai làm | Đầu ra |
|---|----------|--------|--------|
| 1 | `git clone [repo-url]` và `cd [project-name]` | Developer | Code về máy |
| 2 | Copy `.env.example` → `.env`, điền giá trị thật (lấy từ PO hoặc 1Password) | Developer | `.env` đã đủ key |
| 3 | Cài dependencies (`npm install` / `bun install` / `pip install`...) | Developer | Dependencies installed |
| 4 | Chạy dự án lần đầu, xác nhận không có lỗi | Developer | App chạy được trên local |
| 5 | Tạo nhánh cá nhân đầu tiên từ `develop`, commit nhỏ để test flow | Developer | Đã biết workflow Git |

## Quy tắc cứng

| Quy tắc | Lý do |
|---------|-------|
| **Tên repo dùng kebab-case** (`relmo-backend`, không phải `RelmoBackend`) | Nhất quán, dễ tìm kiếm, tránh lỗi case-sensitive trên Linux server |
| **Mặc định Private** — không Public trừ khi có lệnh | Bảo vệ code và thông tin client |
| **Không push thẳng vào `main`** — mọi thay đổi qua PR | Đảm bảo code review, tránh bug lên production |
| **`develop` là default branch** | Developer clone về mặc định ở nhánh đúng, không phải main |
| **`.env` không bao giờ commit** — phải trong `.gitignore` từ ngày đầu | Tránh lộ secrets lên GitHub |
| **README tối thiểu phải có setup guide** | Người mới vào dự án tự setup được mà không cần hỏi |

## Checklist tự kiểm

**Sau khi tạo xong, kiểm tra:**
- [ ] Tên repo đúng quy ước `[client]-[project]`, kebab-case
- [ ] Repo để **Private**
- [ ] Có nhánh `main` và `develop`, `develop` là default
- [ ] `.gitignore` đã có và commit
- [ ] `.env` **không** có trong git (phải có `.env.example` thay thế)
- [ ] `README.md` có đủ: mô tả, tech stack, setup guide
- [ ] Branch Protection bật cho `main` (ít nhất require PR)
- [ ] Team members đã được add với đúng permission
- [ ] Team đã nhận thông báo qua Telegram

## Ngoại lệ & escalation

| Tình huống | Xử lý |
|------------|--------|
| Client yêu cầu repo Public | Hỏi Anderson trước khi tạo. Không tự quyết |
| Tech Lead muốn dùng org khác (không phải `Cyberk-Official`) | Thảo luận với Anderson |
| Không có `.env.example` từ template cũ | Tự tạo, liệt kê tất cả key cần thiết (để trống giá trị) |

## Liên kết

- [Cẩm nang tạo repo — cách nghĩ & tốt/tồi](./dev-new-repo-handbook.md)
- [Ví dụ tốt — mẫu README, .gitignore, cấu trúc folder](./dev-new-repo-example.md)
- [Onboarding dự án cho Developer](../dev-project-onboarding/dev-project-onboarding-process.md)
- [Board Create — PO khởi tạo board sau khi có repo](../../05-product-owner/po-board-create/board-create-process.md)
