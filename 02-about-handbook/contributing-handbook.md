---
type: handbook
tags: [contributing, handbook]
created-date: 2026-09-02
updated-date: 2026-09-02
author: anderson
status: Nháp
---

# Đóng góp Handbook — Cẩm nang cho mọi thành viên

**Người chịu trách nhiệm:** Anderson (CEO)
**Cập nhật lần cuối:** 2026-08-25
**Trạng thái:** Đang dùng

> **"Làm thế nào để vấn đề này không lặp lại?"**

Đây là câu hỏi quan trọng nhất tại Cyberk. Không phải "ai gây ra lỗi?", không phải "sao lại để xảy ra?" — mà là **"làm gì để lần sau không vấp lại chỗ này?"**

Handbook và process chính là **trái tim của Cyberk** — nơi ghi lại cách làm, kinh nghiệm từ những sai lầm đi trước, và cách sửa sai. Mỗi trang trong handbook tồn tại vì ai đó đã từng vấp, đã rút ra bài học, và đã **viết xuống** để người đi sau không phải trả giá lần nữa.

Vì vậy, viết vào handbook không phải là "làm tài liệu" — đó là **hành động quan trọng nhất** bạn có thể làm cho đồng đội của mình.

---

## Khi nào nên viết vào handbook?

Mỗi khi bạn tự hỏi: **"Làm thế nào để vấn đề này không lặp lại?"** — câu trả lời luôn là viết xuống.

Cụ thể hơn:
- Bạn vừa **mắc lỗi hoặc chứng kiến sự cố** — và đã tìm ra cách tránh lần sau
- Bạn vừa **trả lời cùng một câu hỏi** cho người thứ hai trở lên
- Một **quyết định vừa được chốt** trong cuộc họp — nhưng chưa ai ghi lại
- Bạn **phát hiện handbook sai** so với cách team đang làm thực tế
- Bạn là **người mới** và thấy thiếu thông tin khi onboard — góc nhìn của bạn là vô giá

> Tài liệu giá trị nhất thường sinh ra từ thất bại. Sau mỗi sự cố, viết lại thành trang — đó là cách Cyberk biến đau thương thành trí tuệ tập thể.

✅ Cách tốt:
> Sprint vừa rồi deploy bị lỗi vì quên chạy migration. Sau khi fix xong, dev viết ngay vào `delivery/deploy/deploy-process.md` thêm bước "Kiểm tra migration trước khi deploy" + lý do, rồi gửi Telegram:
> *"Đã cập nhật quy trình deploy — thêm bước kiểm tra migration. Xem ở đây: [link]"*

Tại sao tốt: Biến sai lầm thành bài học cho toàn bộ team. Viết-trước, thông báo-sau. Lần deploy sau, ai cũng có checklist.

❌ Cách tồi:
> Deploy lỗi → fix xong → meeting nói "lần sau nhớ chạy migration nhé" → ai cũng gật → 2 tháng sau lặp lại y hệt.

Tại sao tồi: Lời nói bay đi. Không ai ghi lại = bài học không tồn tại. Vấn đề **chắc chắn** sẽ lặp lại.

---

## Viết file gì? — Hiểu hệ thống 7 loại tài liệu

Trước khi viết, hỏi: **"Mình đang viết CÁI GÌ?"**

| Bạn muốn... | Viết file loại | Hậu tố |
|-------------|---------------|--------|
| Ghi luồng xử lý từ A→Z, ai làm gì | **Process** | `-process.md` |
| Giải thích cách nghĩ, mẫu tốt/tồi | **Handbook** | `-handbook.md` |
| Ghi quy định chính thức | **Policy** | `-policy.md` |
| Cho mẫu copy-paste | **Example** | `-example.md` |
| Cho bảng tra nhanh con số/tiêu chuẩn | **Reference** | `-reference.md` |
| Mô tả vai trò/team | **Role** | `-role.md` |
| Cho AI prompt để sinh nội dung | **AI Instruction** | `-instruction.md` |

> **Combo tối thiểu cho mỗi chủ đề: Process + Handbook.** Thêm loại khác khi thật sự cần.

✅ Cách tốt:
> Viết về quy trình xử lý bug? Tạo folder `qa-bugs-handling/`:
> - `bug-handling-process.md` — luồng: ai báo bug → ai phân loại → ai fix → ai verify
> - `bug-handling-handbook.md` — cách nghĩ khi phân loại severity, mẫu báo bug tốt/tồi
> - `bug-severity-sla-handbook.md` — bảng tra severity + SLA

Tại sao tốt: Người cần biết luồng tổng → đọc process. Người cần hiểu sâu → đọc handbook. Cần tra số → đọc reference. Mỗi file một mục đích.

❌ Cách tồi:
> Nhồi tất cả vào 1 file `bug-handling.md` dài 30 trang — lẫn lộn quy trình, ví dụ, bảng tra, chính sách.

Tại sao tồi: Không ai muốn đọc 30 trang để tìm 1 thông tin. Khó cập nhật — sửa SLA phải lội qua hết phần process.

---

## Cách viết một trang tốt

### Luôn mở bằng "Tại sao"

Mọi trang đều bắt đầu bằng lý do tồn tại — giúp người đọc hiểu bối cảnh và quyết định đúng trong tình huống trang chưa lường tới.

✅ Cách tốt:
> *"Tại sao có trang này: Daily report không chỉ để báo cáo — nó là công cụ để team đồng bộ tiến độ mỗi ngày mà không cần họp."*

❌ Cách tồi:
> Nhảy thẳng vào "Bước 1: Mở board..."

### Cụ thể, đo được

Mọi con số, thời hạn, tiêu chuẩn phải **cụ thể**. Tránh từ mơ hồ.

| ❌ Mơ hồ | ✅ Cụ thể |
|----------|----------|
| "Báo sớm" | "Báo trước ít nhất 1 ngày làm việc" |
| "Xử lý nhanh" | "Phản hồi trong 2 giờ làm việc" |
| "Team phù hợp" | "Gán cho reviewer thuộc cùng Epic" |

### Link, đừng copy

Khi cần nhắc lại thông tin từ trang khác → **đặt link**. Tuyệt đối không copy nội dung — vì bản copy sẽ lỗi thời khi bản gốc cập nhật.

### Giữ hồn khi migrate tài liệu cũ

Handbook cũ của Cyberk (The Cyberk Way) chứa rất nhiều triết lý, câu chuyện, lý do — đó là **hồn**. Khi chuyển sang format mới:
- Giữ lại những câu có "tại sao", có triết lý
- Chỉ đổi cấu trúc (heading, bảng, naming), không giết nội dung
- Đọc bản gốc kỹ trước khi viết lại

---

## Quy ước đặt tên

### Tên file
```
[chủ-đề]-[loại].md
```
VD: `bug-handling-process.md`, `code-review-handbook.md`, `maintenance-policy-reference.md`

### Tên folder
```
handbook/[mục-lớn]/[chủ-đề]/
```
VD: `handbook/delivery/qa-bugs-handling/`, `handbook/hr/getting-started/`

### Branch name (khi tạo PR)
```
handbook/[mô-tả-ngắn]
```
VD: `handbook/add-code-review-guidelines`, `handbook/fix-onboarding-typo`

---

## Tóm lại

| Nguyên tắc | Ghi nhớ |
|-----------|---------|
| Viết-trước, thông báo-sau | Chat là kênh thông báo, handbook là nơi lưu trữ |
| Một thông tin, một nơi | Link thay vì copy |
| Tách đúng loại file | Process ≠ Handbook ≠ Example |
| Mở bằng "Tại sao" | Người đọc hiểu bối cảnh trước khi đọc chi tiết |
| Cụ thể, đo được | Không "sớm", không "hợp lý" |
| Giữ hồn | Migrate format, không giết triết lý |
| Ai cũng đề xuất được | Mở PR, owner duyệt |

---

## Liên kết

- [Quy trình đề xuất & duyệt](./contributing-process.md)
- [Bảng tra: ai chịu trách nhiệm mục nào](./owners-reference.md)
- [Playbook — Bộ hướng dẫn chi tiết](../workflow/playbook.md)
