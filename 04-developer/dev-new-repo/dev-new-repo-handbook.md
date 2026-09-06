---
type: handbook
tags: [github, repository, setup, developer]
created-date: 2026-09-06
updated-date: 2026-09-06
author: anderson
status: Nháp
---

# Tạo Repository Mới — Cẩm nang cho Developer

**Người chịu trách nhiệm:** PO dự án
**Cập nhật lần cuối:** 2026-09-06
**Trạng thái:** Nháp

Bạn vừa được giao tạo repo cho dự án mới. Trang này giúp bạn hiểu **tại sao** mỗi quyết định trong quá trình setup lại quan trọng — không chỉ "làm gì", mà "làm vậy để tránh gì".

---

## 1. Đặt tên repo — đừng tưởng là nhỏ

Tên repo là thứ tồn tại suốt vòng đời dự án. Đổi tên về sau rất đau: link gãy, clone path thay đổi, CI/CD cần cấu hình lại.

**Quy ước:** `[client]-[module]` — ví dụ `relmo-backend`, `koto-mobile`, `atlantis-smart-contract`

✅ **Tên tốt:**
```
relmo-backend
koto-mobile
atlantis-smart-contract
cyberk-internal-tools
```
Tại sao tốt: rõ client, rõ module. Nhìn tên là biết repo này của ai, làm gì.

❌ **Tên tồi:**
```
backend          ← backend của ai? dự án gì?
RelmoBackend     ← camelCase không nhất quán với standard
relmo_backend    ← underscore không phải kebab-case chuẩn
newproject       ← hoàn toàn vô nghĩa
```
Tại sao tồi: mơ hồ, không tìm được bằng keyword, dễ nhầm lẫn khi có nhiều dự án.

---

## 2. Private hay Public — không phải tuỳ thích

**Mặc định: Private.** Mọi repo chứa code dự án, code internal tool, hoặc bất kỳ thứ gì liên quan đến client đều phải Private.

Tại sao? Code Cyberk là tài sản của Cyberk và client. Public repo có thể bị:
- Crawled bởi bot tìm secrets bị commit nhầm
- Cạnh tranh đọc được approach kỹ thuật
- Client phát hiện và không vui

**Public chỉ khi:** Anderson phê duyệt, và mục đích rõ ràng (open source library, demo dự án portfolio đã xong...).

---

## 3. Nhánh `main` và `develop` — tại sao cần 2 nhánh ngay từ đầu

Nhiều team chỉ dùng `main` từ đầu rồi sau mới tách `develop`. Điều này sai vì: ngay từ ngày đầu, đã có push thẳng lên `main` — thói quen xấu hình thành và rất khó sửa sau.

**Vai trò của từng nhánh:**

| Nhánh | Mục đích | Ai được push |
|-------|----------|-------------|
| `main` | Code đã deploy lên production, luôn ổn định | Không ai push trực tiếp — chỉ merge qua PR |
| `develop` | Integration branch — code đã review, sẵn sàng test | Merge từ feature branch qua PR |
| `feature/*` | Nhánh làm việc của từng developer | Developer tự tạo, tự push |

✅ **Flow đúng:**
```
feature/login-page → PR → develop → PR → main
```

❌ **Flow sai:**
```
developer push thẳng lên main → "chắc nhỏ thôi" → một ngày production break
```
Tại sao tồi: không có review, không có audit trail, không có rollback plan.

---

## 4. `.gitignore` — cấu hình trước khi commit bất cứ thứ gì

`.gitignore` phải là **file đầu tiên được commit**, trước cả code. Nếu bạn commit file `.env` một lần dù sau đó xóa đi, nó vẫn tồn tại trong git history và có thể bị lộ.

✅ **Tốt:**
```bash
# Tạo repo → thêm .gitignore NGAY → commit → mới bắt đầu code
echo "node_modules/" >> .gitignore
echo ".env" >> .gitignore
echo ".DS_Store" >> .gitignore
git add .gitignore && git commit -m "chore: init gitignore"
```

❌ **Tồi:**
```bash
# Code vài ngày → nhớ ra chưa có .gitignore → thêm sau
# .env đã bị commit ở commit trước → cần rewrite history (đau đầu)
```

**Những thứ luôn phải có trong `.gitignore`:**
- `.env` và mọi biến thể (`.env.local`, `.env.production`)
- `node_modules/`, `.venv/`, vendor dependency folders
- Build artifacts (`dist/`, `build/`, `.next/`, `__pycache__/`)
- Editor configs cá nhân (`.idea/`, `.vscode/settings.json`)
- OS files (`.DS_Store`, `Thumbs.db`)

---

## 5. README — không phải formality, là cứu cánh

Nhìn vào repo 6 tháng sau khi bạn đã quên hết, hoặc khi developer mới join — README là thứ đầu tiên họ mở. README tồi = mất 1-2 ngày hỏi lung tung để setup.

**README tối thiểu phải có:**

```markdown
## Mô tả
[1-2 câu: dự án này làm gì, cho ai]

## Tech Stack
- Backend: Node.js 20, Hono, Drizzle ORM
- Database: PostgreSQL 16
- Deploy: Fly.io

## Setup Local
1. Clone repo
2. cp .env.example .env  # điền giá trị từ PO/1Password
3. bun install
4. bun run db:migrate
5. bun run dev  # → localhost:3000

## Cấu trúc thư mục
[Mô tả ngắn các folder quan trọng]

## Quy ước Git
- Branch: feature/[tên-tính-năng]
- Commit: [type]: [mô tả ngắn]
```

✅ **README tốt:** Người mới clone về, đọc README, chạy được app trong 30 phút.

❌ **README tồi:**
```markdown
# Relmo Backend
To run: npm start
```
Tại sao tồi: không biết cần `.env` gì, không biết cần migrate DB không, không biết port mặc định là bao nhiêu.

---

## 6. Branch Protection — lưới an toàn không thể thiếu

Branch Protection ngăn push trực tiếp lên `main`. Thiết lập ngay khi tạo repo, đừng đợi đến khi có sự cố.

**Cấu hình tối thiểu cho `main`:**
- ✅ `Require a pull request before merging`
- ✅ `Require approvals: 1` (ít nhất 1 người khác review)
- ✅ `Do not allow bypassing the above settings` (kể cả admin)

**Cấu hình cho `develop`** (linh hoạt hơn, nhưng nên có):
- ✅ `Require a pull request before merging`
- ❌ Không cần require approvals (team nhỏ, để linh hoạt)

---

## 7. Team permission — nguyên tắc least privilege

Không phải ai cũng cần `Admin` permission. Dùng quyền tối thiểu cần thiết.

| Role | Permission | Ghi chú |
|------|-----------|---------|
| PO / Tech Lead | `Maintain` | Tạo release, quản lý settings |
| Senior Developer | `Write` | Push branch, tạo PR, merge PR |
| Junior Developer | `Write` | Push branch, tạo PR |
| QA | `Triage` | Đọc code, tạo issue |
| Client (nếu cần xem) | `Read` | Chỉ xem |

---

## Tóm lại

| Việc | Làm ngay | Đừng bao giờ |
|------|----------|--------------|
| Đặt tên | `client-module`, kebab-case | camelCase, tên chung chung |
| Visibility | Private mặc định | Public mà không hỏi |
| Nhánh | `main` + `develop` từ ngày 1 | Chỉ dùng `main`, push thẳng |
| `.gitignore` | File commit đầu tiên | Commit `.env` rồi mới thêm |
| README | Setup guide đủ để tự chạy | "To run: npm start" |
| Branch protection | Ngay sau khi tạo repo | "Thêm sau cũng được" |

## Liên kết

- [Quy trình các bước chi tiết](./dev-new-repo-process.md)
- [Mẫu README, .gitignore, cấu trúc folder](./dev-new-repo-example.md)
- [Onboarding khi tham gia dự án đã có sẵn](../dev-project-onboarding/dev-project-onboarding-handbook.md)
