# Đóng góp Handbook — Cẩm nang cho mọi thành viên

**Người chịu trách nhiệm:** Anderson (CEO)
**Cập nhật lần cuối:** 2026-08-25
**Trạng thái:** Đang dùng

Bạn muốn sửa hoặc thêm nội dung vào handbook nhưng không biết bắt đầu từ đâu? Trang này hướng dẫn bạn **cách nghĩ** khi viết — không chỉ format, mà tại sao chúng ta viết theo cách đó.

> Handbook không bao giờ "xong". Một sửa đổi nhỏ hôm nay tốt hơn một kế hoạch viết đầy đủ ngày mai mà không bao giờ thực hiện.

---

## Khi nào nên viết vào handbook?

Câu hỏi kiểm tra nhanh: **"Mình vừa trả lời câu hỏi này cho ai đó trên chat chưa?"** Nếu rồi — và nó không phải câu hỏi chỉ áp dụng 1 lần — thì nó cần vào handbook.

Dấu hiệu cụ thể:
- Cùng một câu hỏi được hỏi lại ≥ 2 lần bởi những người khác nhau
- Bạn vừa giải quyết xong một sự cố và rút ra bài học
- Có quyết định mới vừa được chốt trong cuộc họp
- Bạn phát hiện handbook thiếu hoặc sai so với thực tế

✅ Cách tốt:
> Sau buổi họp chốt quy trình code review mới, PL viết ngay vào `delivery/code-review/code-review-process.md`, rồi gửi Slack:
> *"Đã cập nhật quy trình code review mới vào handbook: [link]. Mọi người review giúp nhé."*

Tại sao tốt: Viết-trước, thông báo-sau. Thông tin sống ở một nơi duy nhất. Slack chỉ là kênh thông báo, không phải nơi lưu trữ.

❌ Cách tồi:
> PL thông báo trên Slack: *"Từ giờ code review phải có ít nhất 2 reviewer approve nhé."*
> → 3 tháng sau không ai nhớ quy tắc này. Người mới vào hỏi lại. Không ai biết post ở đâu.

Tại sao tồi: Thông tin chết trong luồng chat. Không có nguồn thông tin duy nhất. Câu hỏi bị hỏi đi hỏi lại.

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
- [Playbook — Bộ hướng dẫn chi tiết](../playbook.md)
