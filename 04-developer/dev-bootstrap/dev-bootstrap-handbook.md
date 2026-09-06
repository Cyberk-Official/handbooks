---
type: handbook
tags: [bootstrap, setup, project-kickoff, developer, cto]
created-date: 2026-09-06
updated-date: 2026-09-06
author: anderson
status: Nháp
---

# Bootstrap Dự Án — Cẩm nang cho CTO & Tech Lead

**Người chịu trách nhiệm:** CTO
**Cập nhật lần cuối:** 2026-09-06
**Trạng thái:** Nháp

Hợp đồng vừa ký. PRD đã có. Và bạn có **3–5 ngày** để biến một repo trống thành nền tảng đủ vững để cả team nhảy vào làm business logic ngay từ Sprint 1.

Trang này giúp bạn hiểu **cách nghĩ đúng** ở từng quyết định trong Bootstrap — không chỉ làm gì, mà tại sao làm vậy, và những gì thường đi sai.

---

## 1. Bootstrap không phải "setup nhanh cho có" — đó là đầu tư kiến trúc

Lỗi tư duy phổ biến nhất: Bootstrap = làm nhanh, kịp deadline Sprint 1.

Sai. Bootstrap là thời điểm duy nhất bạn có thể **quyết định kiến trúc mà không phải trả giá ngay**. Một quyết định sai về naming convention, folder structure, hay database schema ở giai đoạn này sẽ ám ảnh cả dự án 6 tháng sau.

> **Nguyên tắc:** Làm đúng từ đầu quan trọng hơn làm nhanh từ đầu. 3 ngày cẩn thận tiết kiệm được 3 tuần refactor sau.

**Những quyết định không thể hoàn tác sau Bootstrap:**
- Tên entity trong database (đổi sau = migration phức tạp, data risk)
- Cấu trúc folder chính (đổi sau = tất cả import path thay đổi)
- Auth strategy (JWT vs Session vs OAuth — đổi sau = viết lại)
- Tech stack (đổi sau = làm lại từ đầu)

---

## 2. ERD — không được bỏ qua, dù "dự án nhỏ"

ERD (Entity Relationship Diagram) là bản vẽ của database. Nhiều team bỏ qua vì "dự án nhỏ, tôi nhớ trong đầu".

Vấn đề: khi bạn nhớ trong đầu, team còn lại không biết. Và khi bạn quên (3 tháng sau), không có gì để reference.

✅ **ERD tốt:**
- Có tất cả bảng từ PRD
- Quan hệ giữa bảng rõ ràng (1-n, n-n)
- Cột quan trọng đã có — đặc biệt `created_at`, `updated_at`, `deleted_at` (soft delete)
- Index đã được nghĩ tới cho các query thường xuyên

❌ **ERD tồi:**
```
"Tôi sẽ thêm bảng sau nếu cần"
→ Team frontend không biết data shape
→ API không nhất quán
→ Sprint 3 mới phát hiện thiếu bảng trung gian cho quan hệ n-n
→ Migration lúc đã có data production = đau đầu
```

**Quy tắc:** ERD phải được CTO **ký duyệt bằng comment trên PR hoặc message Telegram** trước khi tech lead viết một dòng migration. Không có exception.

---

## 3. Scope Bootstrap — cái gì làm, cái gì không

Đây là ranh giới dễ bị vi phạm nhất. Developer có xu hướng muốn làm nhiều hơn — "tiện thể làm luôn feature X".

### Làm trong Bootstrap ✅

| Module | Mức độ hoàn thiện |
|--------|------------------|
| Repo setup, CI/CD cơ bản | 100% |
| Database schema (tất cả entity) | 100% |
| Authentication (register/login/logout/refresh) | 100% |
| RBAC — roles và permissions cơ bản | 100% |
| Admin panel — CRUD entity chính | 80% (đủ dùng) |
| API scaffold — tất cả endpoints, đúng contract | 70% (có thể trả 404 với message rõ ràng) |
| Frontend skeleton — routing, layout, auth flow | 60% (chạy được, chưa đẹp) |
| Documentation (README, ERD, ADR) | 100% |

### Không làm trong Bootstrap ❌

- Business logic cụ thể (tính toán, workflow phức tạp)
- UI polish, animations, responsive
- Edge cases và error handling nâng cao
- Performance optimization
- Feature từ backlog chưa được PO ưu tiên Sprint 1

> **Nếu developer hỏi "làm thêm X không?"** → câu trả lời luôn là "backlog Sprint 1" trừ khi X là nền tảng bắt buộc.

---

## 4. Authentication — quyết định strategy trước khi code

Auth là module quan trọng nhất và khó refactor nhất. Quyết định sai = viết lại hoàn toàn.

**Các lựa chọn phổ biến và khi nào dùng:**

| Strategy | Khi nào phù hợp | Khi nào không phù hợp |
|----------|----------------|----------------------|
| **JWT (stateless)** | API-first, mobile app, microservices | Cần revoke token ngay lập tức (banking, high security) |
| **Session-based** | Web app thuần, không cần API public | Mobile app, microservices |
| **OAuth (Google/GitHub)** | B2C product, user không muốn tạo account | B2B enterprise, client muốn control user |

✅ **Cyberk default:** JWT với Access Token (15 phút) + Refresh Token (7 ngày) stored in httpOnly cookie. Phù hợp với hầu hết dự án web + mobile.

**Những thứ Auth phải cover trong Bootstrap:**
- Đăng ký, đăng nhập, đăng xuất
- Refresh token
- Forgot/Reset password (ít nhất là API, UI có thể sau)
- Middleware xác thực đúng cho tất cả protected routes

---

## 5. Admin Panel — không phải "nice to have"

Nhiều team để Admin Panel sang Sprint 2-3 vì nghĩ là "sau tính". Sai lầm.

**Tại sao Admin cần có từ Bootstrap:**
1. Team cần seed data để test — admin panel là cách nhanh nhất
2. Client muốn xem data thật khi demo Sprint 1 — không có admin = không có gì để show
3. QA cần tool để tạo test case — không có admin = tạo data bằng SQL thủ công
4. Sau Sprint 1 mới làm admin = đã có user data thật, rủi ro cao hơn

**Admin tối thiểu trong Bootstrap:**
- Login riêng (hoặc dùng role Admin từ RBAC)
- CRUD User (xem, khóa, đổi role)
- CRUD 2–3 entity chính từ PRD
- Không cần đẹp — cần chạy được và đủ dùng

---

## 6. Handover — cách bàn giao đúng cho team

Bootstrap xong mà handover không tốt = team vẫn mất 2 ngày để hiểu codebase.

✅ **Handover tốt:**
```
1. README đủ để ai clone về tự chạy trong 30 phút
2. Demo session 15 phút: CTO live-clone, live-setup, live-chạy
3. ADR document: giải thích 3–5 quyết định kiến trúc lớn nhất và lý do
4. Mọi câu hỏi của team phải được hỏi và trả lời TRONG demo — không "hỏi sau"
```

❌ **Handover tồi:**
```
CTO: "Repo đó trên GitHub nhé, tự xem"
Team: [clone về, lỗi, không biết cần .env gì, không biết port mặc định]
→ Mất 2 ngày mỗi người setup
→ Mỗi người hỏi CTO 5 lần
→ CTO mất 1 ngày trả lời slack
```

> **Nguyên tắc:** Nếu ai đó phải hỏi CTO để setup local, README chưa đủ. Sửa README, đừng trả lời câu hỏi.

---

## Tóm lại — Bootstrap checklist tư duy

| Câu hỏi | Câu trả lời đúng |
|---------|-----------------|
| Làm Bootstrap để làm gì? | Để Sprint 1 làm được business logic ngay, không mất thời gian setup |
| Scope Bootstrap đến đâu? | Infrastructure 50–80%, không có business logic |
| ERD phải làm khi nào? | Trước khi viết một dòng migration |
| Ai duyệt ERD? | CTO — bắt buộc, không có exception |
| Bootstrap bao lâu? | 3–5 ngày. Quá 7 ngày → escalate |
| Handover thế nào? | Demo live + README đủ tự setup + ADR document |

## Liên kết

- [Quy trình các bước chi tiết](./dev-bootstrap-process.md)
- [Tạo repo mới — Milestone 0](../dev-new-repo/dev-new-repo-process.md)
- [Planning nội bộ — bước trước Bootstrap](../../05-product-owner/po-planning/planning-handbook.md)
