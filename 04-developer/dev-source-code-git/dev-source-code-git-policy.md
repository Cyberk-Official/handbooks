---
type: policy
tags: [git, source-control, policy, developer, conventional-commits, semver]
created-date: 2026-09-17
updated-date: 2026-09-17
author: kane
status: Đang dùng
---

# Quy chuẩn Quản lý Source Code và Git

**Người chịu trách nhiệm:** Bùi Đắc Huy (Kane) — Giám đốc Công nghệ (CTO)
**Cập nhật lần cuối:** 2026-09-17
**Trạng thái:** Đang dùng — hiệu lực từ 21/10/2026

> ### ⚖️ Đây là bản sao để tra cứu, không phải văn bản gốc
>
> Nội dung dưới đây là Phụ lục 01 ban hành kèm Quyết định `CYBERK-DEV-001`. Văn bản gốc sống ở **policy repo**:
>
> | | |
> |---|---|
> | Quyết định ban hành | `CYBERK-DEV-001` — [dev-policy/CYBERK-DEV-001-quyet-dinh.md](https://github.com/Cyberk-Official/policy/blob/main/dev-policy/CYBERK-DEV-001-quyet-dinh.md) |
> | Phụ lục 01 (nội dung trang này) | `CYBERK-DEV-001-PL01` — [dev-policy/CYBERK-DEV-001-quy-chuan.md](https://github.com/Cyberk-Official/policy/blob/main/dev-policy/CYBERK-DEV-001-quy-chuan.md) |
> | Phiên bản | 1.0 — ban hành 17/09/2026, hiệu lực 21/10/2026 |
> | Người ký | Bùi Đắc Huy (Kane), Giám đốc Công nghệ |
>
> **Khi hai bản khác nhau, văn bản gốc thắng.** Mọi sửa đổi do CTO phê duyệt và ban hành bằng phiên bản mới tại policy repo, sau đó mới đồng bộ ngược về handbook. Đừng sửa trực tiếp trang này.

**Đối tượng áp dụng:** toàn bộ Developer, Tech Lead và các AI Agent tham gia viết code tại Cyberk, trên mọi repository thuộc sở hữu hoặc do Cyberk quản lý.

---

## Phần I. Sáu quy tắc Git bắt buộc

### 1.1. Một branch tương ứng một task

- Mỗi branch tương ứng đúng 1 Task trên Asimov Board. Một Task chỉ có 1 branch hoạt động.
- Không gộp nhiều task vào cùng một branch.
- Phát sinh việc mới (bug nhỏ, refactor, thêm tool) phải tạo Task trên Board trước khi tạo branch.

### 1.2. Không push hoặc merge trực tiếp vào nhánh chính

- Cấm push trực tiếp vào `main`, `prod`, `dev`.
- Mọi thay đổi phải đi qua branch riêng và Pull Request.
- Nhánh chính bắt buộc bật Protected Branch trên GitHub.

### 1.3. Mọi thay đổi phải qua Pull Request

- Tiêu đề PR theo chuẩn Conventional Commits.
- Mô tả PR bắt buộc gắn mã đóng task: `Closes #<issue-number>` hoặc `Fixes #<issue-number>`.
- PR chỉ được merge khi CI/CD pass (lint, test, build) và đủ số reviewer approve theo quy mô team:

| Quy mô team | Yêu cầu review |
| :--- | :--- |
| Từ 3 người trở lên | Tối thiểu 1 reviewer approve trước khi merge |
| 2 người | Review chéo, người còn lại là reviewer |
| 1 người (solo) | Được phép tự merge, bỏ qua quy tắc review |

### 1.4. Đồng bộ nhánh trước khi tạo PR

- Trước khi mở PR, chạy `git fetch origin` và rebase hoặc merge nhánh `dev` mới nhất để xử lý conflict tại local.

### 1.5. Xóa branch sau khi merge

- Xóa branch trên remote và local ngay sau khi PR được merge để tránh rác repository.

### 1.6. Không commit secrets

- Tuyệt đối không commit file `.env`, credentials, API key hoặc private token lên repository.

---

## Phần II. Tiêu chuẩn Atomic Commit

Atomic Commit là commit chỉ chứa duy nhất một thay đổi hoàn chỉnh và độc lập. Mỗi commit phải thỏa mãn đủ 3 tiêu chí:

1. **Đơn mục đích:** Chỉ giải quyết 1 việc (1 bugfix, 1 logic, 1 migration DB, hoặc 1 UI component).
2. **Luôn build được:** Mọi commit trong lịch sử khi checkout về đều build thành công và pass test. Không commit code gãy.
3. **Diff tối giản:** Chỉ stage những dòng liên quan trực tiếp đến commit. Không format file ngoài phạm vi.

---

## Phần III. Quy tắc đặt tên Branch

Cấu trúc: `<type>/<identifier>-<short-description>`

### 3.1. Ba cách định danh

| Trường hợp | Format | Ví dụ |
| :--- | :--- | :--- |
| Theo Issue trên Board (ưu tiên) | `<type>/<issue-number>-<description>` | `feat/143-receive-github-events` |
| Theo Roadmap Task Code | `<type>/<task-code>-<description>` | `feat/project-001-1-github-events` |
| Theo Module (hạ tầng, setup) | `<type>/<module>-<description>` | `infra/prod-stage` |

### 3.2. Bảng tiền tố

| Prefix | Mục đích | Ví dụ |
| :--- | :--- | :--- |
| `feat/` | Tính năng mới | `feat/143-receive-github-events` |
| `fix/` | Sửa lỗi | `fix/1363-competition-total-reward` |
| `hotfix/` | Sửa lỗi khẩn cấp trên Production | `hotfix/stripe-webhook-timeout` |
| `refactor/` | Tái cấu trúc code, không đổi tính năng | `refactor/1275-login-modal-state-machine` |
| `chore/` | Cập nhật config, dependencies, tool | `chore/upgrade-bun-v1.2` |
| `infra/` | Hạ tầng, CI/CD, Workers | `infra/prod-stage` |
| `docs/` | Viết hoặc sửa tài liệu | `docs/cli-command-specs` |
| `test/` | Thêm hoặc sửa test suite | `test/attendance-checkin-cases` |

### 3.3. Quy ước chung

Toàn bộ chữ thường, nối từ bằng dấu gạch ngang (kebab-case), không dấu tiếng Việt, không khoảng trắng, tối đa 45 ký tự.

---

## Phần IV. Quy tắc đặt tên Commit

Cú pháp: `<type>(<scope>): [task-code] <mô tả ngắn> [(#issue-number)]`

### 4.1. Ví dụ chuẩn

```text
feat(project): [PROJECT-001.1] receive and verify github events (#143)
fix(competition): correct prize pool calculation (#1363)
refactor(auth): convert login modal to state machine (#1275)
infra(cicd): make github token optional (#214)
```

### 4.2. Bảng type

| Type | Mục đích | Ví dụ |
| :--- | :--- | :--- |
| `feat` | Thêm tính năng mới | `feat(auth): add google oauth2 login` |
| `fix` | Sửa lỗi | `fix(cart): prevent duplicate item addition (#1351)` |
| `refactor` | Tái cấu trúc code | `refactor(db): optimize user query` |
| `perf` | Tối ưu hiệu năng | `perf(db): add index on orders.created_at` |
| `infra` | Cấu hình hạ tầng, CI/CD | `infra(cloudflare): configure worker routes` |
| `docs` | Thêm hoặc sửa tài liệu | `docs(readme): add setup guide` |
| `test` | Thêm hoặc sửa test | `test(auth): add expired token test cases` |
| `chore` | Cập nhật dependencies, build config | `chore(deps): update drizzle-orm to v0.38` |
| `style` | Sửa format code, không đổi logic | `style(ui): format navbar component` |

### 4.3. Quy ước chung

Viết thường chữ cái đầu sau dấu hai chấm; không đặt dấu chấm cuối tiêu đề; dùng động từ nguyên mẫu (`add`, `fix`, `update`, `remove`).

---

## Phần V. Quy trình đánh Tag Version

### 5.1. Chuẩn đặt tên Semantic Versioning

Sử dụng định dạng `vX.Y.Z`:

- **Major (X):** tăng khi có breaking change, phá vỡ tương thích ngược. Ví dụ `v2.0.0`.
- **Minor (Y):** tăng khi thêm tính năng mới, vẫn tương thích ngược. Ví dụ `v1.1.0`.
- **Patch (Z):** tăng khi chỉ sửa lỗi. Ví dụ `v1.0.1`.

### 5.2. Các bước đánh Tag và Release

1. Checkout nhánh phát hành và pull code mới nhất:
   ```bash
   git checkout main && git pull origin main
   ```
2. Tạo Annotated Tag (bắt buộc dùng cờ `-a`):
   ```bash
   git tag -a v1.2.0 -m "Release phien ban 1.2.0: them tinh nang gio hang"
   ```
3. Đẩy Tag lên remote (tag không tự push):
   ```bash
   git push origin v1.2.0
   ```
4. Tạo Release trên GitHub: vào *Releases*, chọn *Draft a new release*, chọn Tag vừa tạo, điền Release Notes và *Publish*.

---

## Phần VI. Chuẩn hóa Git Author Name và GitHub Username

### 6.1. Quy tắc

Toàn bộ thành viên thống nhất tên hiển thị theo format `english-name-cyberk`: dùng tên tiếng Anh hoặc tên Latin hóa, cộng hậu tố `-cyberk`, toàn bộ chữ thường, nối bằng dấu gạch ngang. Áp dụng cho cả Git Author Name và GitHub Username.

| Tên thật | Git Author Name / GitHub Username |
| :--- | :--- |
| Anderson | `anderson-cyberk` |
| Huy | `huy-cyberk` |
| Minh Tuan | `minh-tuan-cyberk` |
| Peter | `peter-cyberk` |

### 6.2. Cách cấu hình

```bash
git config --global user.name "anderson-cyberk"
```

GitHub Username đổi tại `github.com/settings/profile`, mục *Name* và *Username*. Bảo đảm Git Author Name khớp GitHub Username để commit liên kết đúng profile. Commit cũ với tên khác không cần rewrite history, chỉ cần cấu hình đúng từ thời điểm áp dụng.

---

## Phần VII. Quy tắc khi làm việc cùng AI Agent

1. **Commit theo từng mốc Spec:** yêu cầu AI hoàn thành từng task nhỏ trong Spec, chạy test xanh rồi mới tạo Atomic Commit. Không để AI code một mạch từ đầu đến cuối mới commit.
2. **Kiểm tra file rác:** luôn chạy `git status` trước khi commit, không để AI tự ý commit file `.env` hoặc file tạm.
3. **Trách nhiệm cuối cùng thuộc về Developer:** commit do AI tạo ra vẫn mang tên và trách nhiệm của Developer ký commit đó.
4. **Prompt mẫu:** *"Chạy test, sau đó tạo một atomic commit theo chuẩn conventional commits cho phần vừa làm: type(scope): message (#issue)."*

---

## Phần VIII. Đối chiếu Đúng và Sai

| Tiêu chí | SAI | ĐÚNG | Lý do |
| :--- | :--- | :--- | :--- |
| Đặt tên Branch | `feature/fix_bug_1363`, `peter/test`, `task1` | `fix/1363-competition-total-reward` | Đúng kebab-case, có type rõ ràng, map chính xác Task trên Board |
| Branch không có Task | Tự tạo branch code tự do | Tạo Issue `#1364` trên Board trước, rồi tạo branch `feat/1364-...` | Tuân thủ nguyên tắc một branch một task |
| Merge trực tiếp | `git push origin main` | Mở PR từ branch tính năng sang `dev` | Bảo vệ nhánh deploy và code base chung |
| Commit message mơ hồ | `update code`, `fix bug` | `fix(competition): fix total reward calculation (#1363)` | Rõ scope, hành động cụ thể, tự link Issue |
| Gom nhiều việc | 1 commit vừa thêm checkout, vừa sửa navbar, vừa sửa DB | 3 commit tách biệt theo từng mục đích | Tách biệt rủi ro, rollback độc lập khi có sự cố |
| Sửa bug kèm format | Sửa 1 dòng bug nhưng format lại 500 dòng | 2 commit riêng: `style(billing): format service` và `fix(billing): handle discount zero division` | Tránh nhiễu khi review code |
| Commit rác | `wip`, `fix again` | Squash hoặc amend thành 1 commit hoàn chỉnh trước khi push | Giữ lịch sử Git sạch, không gãy build |
| Release Tag | `git tag 1.2`, `git tag "release"` | `git tag -a v1.2.0 -m "Release v1.2.0"` | Tuân thủ SemVer và là Annotated Tag |

---

## Phần IX. Hiệu lực, giám sát và xử lý vi phạm

### 9.1. Checklist bắt buộc trước khi push

- [ ] Branch đã map 1-1 với 1 Task trên Asimov Board.
- [ ] Mọi thay đổi đi qua Pull Request, không push thẳng vào `main`, `prod`, `dev`.
- [ ] Mỗi commit chỉ làm đúng 1 nhiệm vụ và build thành công, pass test.
- [ ] Commit message đúng format `type(scope): description (#issue)`.
- [ ] Đã dọn dẹp các commit rác (`wip`, `temp`).
- [ ] Khi có Release mới, đã đánh Annotated Tag đúng chuẩn SemVer và push lên remote.

### 9.2. Giám sát

Tech Lead mỗi dự án chịu trách nhiệm cấu hình Protected Branch, rule CI/CD và kiểm tra việc tuân thủ Quy chuẩn trong quá trình review PR. Bộ phận Công nghệ rà soát định kỳ hàng quý.

### 9.3. Xử lý vi phạm

| Mức độ | Hành vi | Xử lý |
| :--- | :--- | :--- |
| Nhắc nhở | Sai format branch hoặc commit message, commit không atomic | Reviewer yêu cầu sửa trước khi merge |
| Cảnh cáo | Push trực tiếp vào nhánh chính, merge PR không qua review khi team từ 2 người trở lên | Tech Lead ghi nhận, báo cáo Bộ phận Công nghệ; tái phạm xử lý theo Nội quy lao động |
| Nghiêm trọng | Commit secrets, credentials, API key hoặc private token lên repository | Thu hồi và xoay vòng toàn bộ khóa bị lộ ngay lập tức; xử lý kỷ luật theo Nội quy lao động và Cam kết bảo mật thông tin |

### 9.4. Sửa đổi

Mọi sửa đổi, bổ sung Quy chuẩn này do CTO phê duyệt và ban hành bằng phiên bản mới.

---

## Liên kết

- [Tạo Repository Mới](../dev-new-repo/) — đặt tên repo, branch protection, quyền team khi khởi tạo
- [Quản lý công việc cá nhân hàng ngày](../dev-daily/) — lấy task từ board trước khi tạo branch
- [Tạo & quản lý task trên board](../dev-tasks-logs/) — nguồn của issue number dùng trong tên branch và commit
- [Ban hành Policy](../../07-hr/leader-policy-issuance/) — quy trình ban hành và sửa đổi văn bản như Quy chuẩn này
