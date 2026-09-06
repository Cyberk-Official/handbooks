---
type: example
tags: [github, repository, setup, developer]
created-date: 2026-09-06
updated-date: 2026-09-06
author: anderson
status: Nháp
---

# Tạo Repository Mới — Mẫu tốt & không tốt

**Người chịu trách nhiệm:** Anderson
**Cập nhật lần cuối:** 2026-09-06

> Quy tắc: Copy-paste các mẫu dưới đây, thay `[placeholder]` bằng thông tin thực. Không xoá phần nào mà không có lý do.

---

## Mẫu 1 — Tên Repository

### ✅ Tên tốt

```
relmo-backend
relmo-mobile
koto-smart-contract
atlantis-web
cyberk-internal-analytics
asimov-sage
```

### ❌ Tên không tốt

```
backend          ← quá chung, không biết của dự án nào
newProject       ← camelCase, tên tạm
test123          ← tên test không bao giờ được dùng cho repo thật
RelmoBackend     ← PascalCase
relmo_mobile     ← underscore thay vì kebab
```

---

## Mẫu 2 — README.md khởi đầu

Copy toàn bộ template dưới đây, điền thông tin thực:

```markdown
# [Tên Dự Án]

> [1 câu mô tả: dự án này làm gì và phục vụ ai]

## Tech Stack

- **Runtime:** [Node.js 20 / Bun 1.x / Python 3.12...]
- **Framework:** [Hono / Express / FastAPI / Next.js...]
- **Database:** [PostgreSQL 16 / MySQL 8 / MongoDB...]
- **ORM:** [Drizzle / Prisma / SQLAlchemy...]
- **Deploy:** [Fly.io / Railway / AWS EC2...]

## Prerequisites

- [Node.js >= 20](https://nodejs.org/) hoặc [Bun >= 1.0](https://bun.sh/)
- [Docker Desktop](https://www.docker.com/) (để chạy database local)
- Quyền truy cập vào 1Password team vault `[Tên vault]`

## Setup Local

```bash
# 1. Clone repo
git clone git@github.com:Cyberk-Official/[repo-name].git
cd [repo-name]

# 2. Cài dependencies
bun install

# 3. Cấu hình environment
cp .env.example .env
# Mở .env, điền các giá trị từ 1Password > [Tên vault] > [Tên entry]

# 4. Khởi tạo database
docker compose up -d   # khởi động PostgreSQL local
bun run db:migrate     # chạy migration

# 5. Chạy dev server
bun run dev
# → http://localhost:3000
```

## Cấu trúc thư mục

```
src/
├── routes/      # API endpoints
├── services/    # Business logic
├── db/          # Database schema & migrations
│   └── schema/
└── lib/         # Shared utilities
```

## Quy ước Git

**Nhánh:**
- `main` — production, chỉ merge qua PR
- `develop` — integration, merge feature vào đây
- `feature/[tên-tính-năng]` — nhánh làm việc cá nhân

**Commit message:**
```
feat: thêm API tạo user
fix: sửa lỗi validate email
chore: cập nhật dependencies
docs: thêm hướng dẫn setup
```

## Liên hệ

- **PO:** [Tên] — Telegram `@[handle]`
- **Tech Lead:** [Tên] — Telegram `@[handle]`
```

---

## Mẫu 3 — `.gitignore` chuẩn Cyberk (Node.js / Bun)

```gitignore
# Dependencies
node_modules/
.pnp
.pnp.js

# Environment variables — KHÔNG BAO GIỜ COMMIT
.env
.env.local
.env.*.local
.env.development
.env.test
.env.production

# Build outputs
dist/
build/
.next/
out/

# Database
*.db
*.sqlite
*.sqlite3

# Logs
logs/
*.log
npm-debug.log*

# OS
.DS_Store
Thumbs.db

# Editor
.idea/
.vscode/settings.json
*.swp
*.swo

# Testing
coverage/
.nyc_output/

# Misc
.cache/
tmp/
```

---

## Mẫu 4 — `.env.example` (template cho developer khác)

File này được commit vào git — không có giá trị thật, chỉ có key và mô tả:

```bash
# Application
NODE_ENV=development
PORT=3000
APP_SECRET=your-secret-key-here

# Database
DATABASE_URL=postgresql://user:password@localhost:5432/dbname
# Local: postgresql://postgres:postgres@localhost:5432/[project]_dev

# External APIs
STRIPE_SECRET_KEY=sk_test_...         # Lấy từ 1Password > Relmo > Stripe Test Key
TELEGRAM_BOT_TOKEN=                   # Lấy từ 1Password > Relmo > Telegram Bot

# Storage
AWS_ACCESS_KEY_ID=
AWS_SECRET_ACCESS_KEY=
AWS_S3_BUCKET=
```

---

## Mẫu 5 — Commit messages đầu tiên (sau khi tạo repo)

```bash
# Commit 1: khởi tạo
git commit -m "chore: init repository"

# Commit 2: gitignore
git commit -m "chore: add .gitignore"

# Commit 3: README và env example
git commit -m "docs: add README and .env.example"

# Commit 4: cấu trúc folder ban đầu
git commit -m "chore: scaffold project structure"
```

❌ **Commit message không tốt:**
```bash
git commit -m "first commit"       ← không biết chứa gì
git commit -m "aaa"                ← vô nghĩa
git commit -m "fix"                ← fix cái gì?
git commit -m "WIP"                ← không commit WIP lên develop/main
```

---

## Mẫu 6 — Thông báo Telegram khi tạo xong repo

Gửi vào group dự án khi hoàn tất setup:

```
🚀 Repo mới đã sẵn sàng!

📦 [relmo-backend](https://github.com/Cyberk-Official/relmo-backend)
🔒 Private | Default branch: develop

**Setup:**
1. Clone: git clone git@github.com:Cyberk-Official/relmo-backend.git
2. Xem README để setup local (15-20 phút)
3. .env values lấy từ 1Password > Relmo vault

cc @[tech-lead] @[developer-1] @[developer-2]
```

---

## Nguyên tắc chung

| Không nên | Nên |
|-----------|-----|
| Tên repo chung chung (`backend`, `app`) | Tên cụ thể theo client-module (`relmo-backend`) |
| Bắt đầu code trước khi có `.gitignore` | `.gitignore` là commit đầu tiên |
| README copy từ dự án cũ, quên sửa | README mới viết, đặc thù cho dự án này |
| Dùng `main` một mình | Tạo `develop` ngay từ đầu |
| Add tất cả vào `Admin` | Dùng đúng permission level (Write/Triage/Read) |
| Push thẳng lên `main` "vì chỉ một chữ" | Mọi thay đổi qua PR, không có ngoại lệ |
