---
type: dev
tags: [git, source-control, cyberk-way, best-practices]
alias: [source-code-and-git, git-standard, atomic-commit, git-workflow]
---

# Quy Chuẩn Quản Lý Source Code & Git

Tài liệu quy định cách quản lý Git và Source Code tại Cyberk, áp dụng cho toàn bộ Developer và AI Agents.

---

## 1. 6 Quy Tắc Git Bắt Buộc

### 1. 1 Branch = 1 Task (No Task, No Branch)
- Mỗi branch tương ứng với đúng 1 Task trên Asimov Board.
- 1 Task chỉ có 1 branch hoạt động. Không gộp nhiều task vào 1 branch.
- Nếu phát sinh việc mới (bug nhỏ, refactor, thêm tool), hãy tạo Task trên Board trước khi tạo branch.

### 2. Không Push/Merge trực tiếp vào nhánh chính
- Cấm push trực tiếp vào `main`, `prod`, `dev`.
- Mọi thay đổi đều phải tạo Branch riêng và mở Pull Request (PR).
- Nhánh chính được cài đặt Protected Branch trên GitHub.

### 3. Mọi thay đổi phải qua Pull Request (PR)
- Tiêu đề PR theo chuẩn Conventional Commits.
- Phần mô tả bắt buộc gắn mã đóng task: `Closes #<issue-number>` (hoặc `Fixes #<issue-number>`).
- PR chỉ được merge khi: CI/CD pass (lint, test, build) và có **tối thiểu 1 reviewer approve**.
- **Quy tắc review theo quy mô team:**
  - **Team >= 3 người:** Bắt buộc tối thiểu 1 reviewer approve trước khi merge.
  - **Team 2 người:** Review chéo, người còn lại là reviewer.
  - **Team 1 người (solo):** Bỏ qua quy tắc review, được phép tự merge.

### 4. Đồng bộ nhánh trước khi tạo PR
- Trước khi mở PR, chạy `git fetch origin` và rebase/merge nhánh `dev` mới nhất để xử lý xung đột (conflict) tại local.

### 5. Xóa Branch sau khi Merge
- Xóa branch trên remote và local ngay sau khi PR được merge để tránh rác repository.

### 6. Không Commit Secrets và `.env`
- Tuyệt đối không commit file `.env`, credentials, API key hoặc private token lên repository.

---

## 2. Tiêu Chuẩn Atomic Commit

Atomic Commit là một commit chỉ chứa **duy nhất một thay đổi hoàn chỉnh và độc lập**.

3 tiêu chí bắt buộc của một commit:
1. **Đơn mục đích (Single Purpose):** Mỗi commit chỉ giải quyết 1 việc (1 bugfix, 1 logic, 1 migration DB, hoặc 1 UI component).
2. **Luôn build được (Always Green):** Mọi commit trong lịch sử khi checkout về đều phải build thành công và pass test. Không commit code gãy.
3. **Diff tối giản (Minimal Diff):** Chỉ stage những dòng code liên quan trực tiếp đến commit. Không format file ngoài phạm vi.

---

## 3. Quy Tắc Đặt Tên Branch

### Cấu trúc:
```bash
<type>/<identifier>-<short-description>
```

### 3 trường hợp định danh:

1. **Theo Issue trên Board (Ưu tiên sử dụng):**
   - Format: `<type>/<issue-number>-<description>`
   - Ví dụ: `feat/143-receive-github-events`, `fix/1363-competition-total-reward`

2. **Theo Roadmap Task Code (Task thuộc Milestone lớn):**
   - Format: `<type>/<task-code>-<description>`
   - Ví dụ: `feat/project-001-1-github-events`, `feat/org-003-1-checkin-rules`

3. **Theo Module (Task hạ tầng, setup môi trường):**
   - Format: `<type>/<module>-<description>`
   - Ví dụ: `infra/prod-stage`, `chore/rename-package-scope`

### Bảng tiền tố (Prefix Types):

| Prefix | Mục đích | Ví dụ |
| :--- | :--- | :--- |
| `feat/` | Tính năng mới | `feat/143-receive-github-events` |
| `fix/` | Sửa lỗi | `fix/1363-competition-total-reward` |
| `hotfix/` | Sửa lỗi khẩn cấp trên Production | `hotfix/stripe-webhook-timeout` |
| `refactor/` | Tái cấu trúc code (không đổi tính năng) | `refactor/1275-login-modal-state-machine` |
| `chore/` | Cập nhật configs, dependencies, tool | `chore/upgrade-bun-v1.2` |
| `infra/` | Hạ tầng, CI/CD, Workers | `infra/prod-stage` |
| `docs/` | Viết hoặc sửa tài liệu | `docs/cli-command-specs` |
| `test/` | Thêm/sửa test suite | `test/attendance-checkin-cases` |

**Quy ước:** Toàn bộ chữ thường (`lowercase`), nối từ bằng dấu gạch ngang (`kebab-case`), không dấu tiếng Việt, không khoảng trắng, tối đa 45 ký tự.

---

## 4. Quy Tắc Đặt Tên Commit (Conventional Commits)

### Cú pháp:
```text
<type>(<scope>): [task-code] <mô tả ngắn> [optional (#issue-number)]
```

### Ví dụ chuẩn:
```text
feat(project): [PROJECT-001.1] receive and verify github events (#143)
fix(competition): correct prize pool calculation (#1363)
refactor(auth): convert login modal to state machine (#1275)
infra(cicd): make github token optional (#214)
```

### Bảng Types:

| Type | Mục đích | Ví dụ |
| :--- | :--- | :--- |
| `feat` | Thêm tính năng mới | `feat(auth): add google oauth2 login` |
| `fix` | Sửa lỗi | `fix(cart): prevent duplicate item addition (#1351)` |
| `refactor` | Tái cấu trúc code | `refactor(db): optimize user query` |
| `perf` | Tối ưu hiệu năng | `perf(db): add index on orders.created_at` |
| `infra` | Cấu hình hạ tầng, CI/CD | `infra(cloudflare): configure worker routes` |
| `docs` | Thêm/sửa tài liệu | `docs(readme): add setup guide` |
| `test` | Thêm/sửa test | `test(auth): add expired token test cases` |
| `chore` | Cập nhật dependencies, build configs | `chore(deps): update drizzle-orm to v0.38` |
| `style` | Sửa format code (không đổi logic) | `style(ui): format navbar component` |

**Quy ước:**
- Viết thường chữ cái đầu sau dấu hai chấm.
- Không đặt dấu chấm ở cuối tiêu đề.
- Dùng động từ nguyên mẫu: `add`, `fix`, `update`, `remove`.

---

## 5. Bảng So Sánh: Đúng vs Sai

| Tiêu chí | ❌ SAI | ✅ ĐÚNG | Lý do |
| :--- | :--- | :--- | :--- |
| **Đặt tên Branch** | `feature/fix_bug_1363`<br>`peter/test`<br>`task1` | `fix/1363-competition-total-reward`<br>`feat/project-001-1-github-events` | Đúng kebab-case, có type rõ ràng, map chính xác với Task trên Board. |
| **Branch không có Task** | Tự tạo branch code tự do | Tạo Issue `#1364` trên Board trước -> tạo branch `feat/1364-...` | Tuân thủ 1 Branch = 1 Task. |
| **Merge trực tiếp** | `git push origin main`<br>`git push origin dev` | Mở PR từ branch tính năng sang `dev` | Bảo vệ nhánh deploy và code base chung. |
| **Commit Message mơ hồ** | `git commit -m "update code"`<br>`git commit -m "fix bug"` | `fix(competition): fix total reward calculation (#1363)` | Rõ scope, hành động cụ thể, tự link Issue. |
| **Gom nhiều việc** | 1 commit vừa thêm checkout, vừa sửa navbar, vừa sửa DB | 3 commits tách biệt:<br>1. `chore(db): add status column`<br>2. `fix(ui): fix navbar overflow`<br>3. `feat(checkout): create checkout page` | Tách biệt rủi ro, rollback độc lập khi có sự cố. |
| **Sửa bug kèm format** | Sửa 1 dòng bug nhưng format lại 500 dòng cả file | 2 commits riêng:<br>1. `style(billing): format service`<br>2. `fix(billing): handle discount zero division` | Tránh nhiễu khi review code. |
| **Commit rác (WIP)** | `git commit -m "wip"`<br>`git commit -m "fix again"` | Squash/amend lại thành 1 commit hoàn chỉnh trước khi push: `fix(auth): correct token signature` | Giữ lịch sử Git sạch, không gãy build. |

---

## 6. Ví Dụ Kịch Bản: Triển Khai 1 Tính Năng

**Tác vụ:** Nhận Task `#145` từ Board để làm tính năng *Đổi mật khẩu*.

**Quy trình chuẩn:**
1. Tạo branch: `feat/145-user-change-password`
2. Chia nhỏ thành chuỗi Atomic Commits:
   ```text
   commit 1: feat(crypto): add password hashing helper
   commit 2: test(crypto): add unit tests for hashing helper
   commit 3: feat(api): add post change-password endpoint (#145)
   commit 4: test(api): add test for change-password route
   commit 5: feat(ui): create password change form on profile (#145)
   ```
3. Mở Pull Request vào `dev`: Tiêu đề `feat(auth): implement user change password (#145)`, gắn `Closes #145`.
4. Sau khi CI/CD pass và có Approve -> Merge PR (Task `#145` tự động chuyển sang `Done`).

---

## 7. Chuẩn Hoá Git Author Name & Username

Toàn bộ thành viên Cyberk phải thống nhất tên hiển thị trên Git và GitHub theo format:

```
english-name-cyberk
```

### Quy tắc:
- Dùng **tên tiếng Anh** (hoặc tên Latin hoá) + hậu tố `-cyberk`.
- Toàn bộ chữ thường (`lowercase`), nối bằng dấu gạch ngang (`kebab-case`).
- Áp dụng cho cả **Git Author Name** (hiển thị trên commit) và **GitHub Username**.

### Ví dụ:

| Tên thật | Git Author Name / GitHub Username |
| :--- | :--- |
| Anderson | `anderson-cyberk` |
| Huy | `huy-cyberk` |
| Minh Tuan | `minh-tuan-cyberk` |
| Peter | `peter-cyberk` |

### Cách cấu hình Git Author Name:

```bash
# Cấu hình global (áp dụng cho toàn bộ repo trên máy)
git config --global user.name "anderson-cyberk"

# Cấu hình cho 1 repo cụ thể
git config user.name "anderson-cyberk"
```

### Lưu ý:
- **GitHub Username:** Đổi tại [github.com/settings/profile](https://github.com/settings/profile), mục "Name" và "Username".
- Đảm bảo Git Author Name khớp với GitHub Username để commit được liên kết đúng profile.
- Nếu đã có commit cũ với tên khác, không cần rewrite history, chỉ cần cấu hình đúng từ thời điểm áp dụng.

---

## 8. Kỹ Thuật Git Hàng Ngày

- **Stage từng đoạn code:** `git add -p <file>`
- **Sửa nhanh commit gần nhất:** `git commit --amend --no-edit`
- **Gộp commit rác trước khi mở PR:** `git rebase -i HEAD~<n>` (dùng `squash` hoặc `fixup`)

---

## 9. Quy Tắc Khi Làm Việc Cùng AI Agent

1. **Commit theo từng mốc Spec:** Yêu cầu AI hoàn thành từng task nhỏ trong Spec, chạy test xanh rồi mới tạo Atomic Commit. Không để AI code một mạch từ đầu đến cuối mới commit.
2. **Kiểm tra file rác:** Luôn kiểm tra `git status` trước khi commit, không để AI tự ý commit file `.env` hoặc file tạm.
3. **Prompt mẫu cho AI:**
   > *"Chạy test, sau đó tạo một atomic commit theo chuẩn conventional commits cho phần vừa làm: type(scope): message (#issue)."*

---

## 10. Checklist Trước Khi Push

- [ ] Branch đã map 1-1 với 1 Task trên Asimov Board (`#Issue` hoặc `Task Code`)?
- [ ] Mọi thay đổi đều đi qua Pull Request, không push thẳng vào `main`, `prod`, `dev`?
- [ ] Mỗi commit chỉ làm đúng 1 nhiệm vụ (Atomic)?
- [ ] Tất cả commit đều build thành công và pass test?
- [ ] Commit message đúng format `type(scope): description (#issue)`?
- [ ] Đã dọn dẹp các commit rác (`wip`, `temp`) trước khi push?
