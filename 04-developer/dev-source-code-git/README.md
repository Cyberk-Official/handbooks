# 🔀 Quản lý Source Code & Git

> **Đối tượng:** Toàn bộ Developer, Tech Lead và AI Agent viết code tại Cyberk
> **Mục đích:** Chuẩn hóa cách dùng Git — branch, commit, PR, tag release — trên mọi repo của Cyberk

---

## Tài liệu

| File | Nội dung | Đọc khi |
|------|----------|---------|
| [dev-source-code-git-policy.md](./dev-source-code-git-policy.md) | Quy chuẩn chính thức: 6 quy tắc Git bắt buộc, Atomic Commit, đặt tên branch/commit, tag SemVer, Git Author Name, làm việc cùng AI Agent, bảng Đúng/Sai, giám sát & chế tài | Trước khi tạo branch đầu tiên, và mỗi khi không chắc format |

---

## Quan trọng — đây không phải văn bản gốc

Quy chuẩn này được ban hành bằng **Quyết định `CYBERK-DEV-001`** (CTO ký ngày 17/09/2026, hiệu lực **21/10/2026**). Bản trong handbook là bản sao để tra cứu cho tiện; văn bản gốc nằm ở **policy repo**:

- [CYBERK-DEV-001 — Quyết định ban hành](https://github.com/Cyberk-Official/policy/blob/main/dev-policy/CYBERK-DEV-001-quyet-dinh.md)
- [CYBERK-DEV-001-PL01 — Phụ lục 01: Quy chuẩn](https://github.com/Cyberk-Official/policy/blob/main/dev-policy/CYBERK-DEV-001-quy-chuan.md)

Khi hai bản khác nhau, **văn bản gốc thắng**. Muốn sửa quy chuẩn thì sửa ở policy repo và xin CTO phê duyệt phiên bản mới, rồi mới đồng bộ về đây — đừng sửa thẳng trong handbook.

---

## Tra nhanh

| Cần gì | Xem mục |
|--------|---------|
| Đặt tên branch | [Phần III](./dev-source-code-git-policy.md#phần-iii-quy-tắc-đặt-tên-branch) |
| Viết commit message | [Phần IV](./dev-source-code-git-policy.md#phần-iv-quy-tắc-đặt-tên-commit) |
| Cần bao nhiêu reviewer | [Mục 1.3](./dev-source-code-git-policy.md#13-mọi-thay-đổi-phải-qua-pull-request) |
| Đánh tag release | [Phần V](./dev-source-code-git-policy.md#phần-v-quy-trình-đánh-tag-version) |
| Đặt Git Author Name | [Phần VI](./dev-source-code-git-policy.md#phần-vi-chuẩn-hóa-git-author-name-và-github-username) |
| Để AI commit hộ | [Phần VII](./dev-source-code-git-policy.md#phần-vii-quy-tắc-khi-làm-việc-cùng-ai-agent) |
| Checklist trước khi push | [Mục 9.1](./dev-source-code-git-policy.md#91-checklist-bắt-buộc-trước-khi-push) |
