---
type: process
tags: [hr, termination, offboarding, left]
created-date: 2026-09-06
updated-date: 2026-09-06
author: anderson
status: Nháp
---

# Member Left — Chấm dứt Hợp đồng

**Người chịu trách nhiệm:** Anderson (CEO)
**Cập nhật lần cuối:** 2026-09-06
**Trạng thái:** Nháp

## Tại sao có trang này

Chấm dứt hợp đồng là quyết định nặng nề — nhưng đôi khi là cần thiết để bảo vệ team, dự án và công ty. Quy trình này đảm bảo quyết định được thực hiện **đúng pháp luật, có phẩm giá cho cả hai bên, và không gây gián đoạn dự án**.

## Khi nào áp dụng (Trigger)

**Từ quy trình nội bộ:**
- Không vượt qua Retraining (hr-member-retraining) sau 30 ngày
- Sau Member Warning mà tiếp tục gây hậu quả nghiêm trọng
- Hiệu suất và thái độ không cải thiện sau toàn bộ các bước trước

**Trực tiếp (Zero-Tolerance — bỏ qua các bước trước):**
- Tiết lộ bí mật kinh doanh, mã nguồn, data client
- Gian lận tài chính, timesheet, báo cáo sai sự thật
- Vi phạm bảo mật nghiêm trọng
- Vi phạm lặp lại ≥ 5 lần / 30 ngày theo CYBERK-HR-001
- Bạo lực, quấy rối tại nơi làm việc

**Nhân viên tự nguyện rời đi:**
- Cũng dùng checklist offboarding này (bỏ qua Bước 1–3)

## Vai trò & trách nhiệm

| Vai trò | Chịu trách nhiệm gì |
|---------|---------------------|
| **Anderson (CEO)** | Quyết định duy nhất. Thông báo trực tiếp với nhân viên |
| **Brian / Hương (Leader)** | Lập kế hoạch bàn giao, thu hồi quyền truy cập, hỗ trợ thủ tục |
| **CTO** | Đánh giá rủi ro kỹ thuật khi nhân viên rời — đặc biệt với dev có quyền cao |
| **Nhân viên** | Bàn giao đầy đủ, hợp tác với quy trình |

## Các bước

### Phần A — Chuẩn bị (Trước khi thông báo)

| # | Việc làm | Ai làm | Đầu ra |
|---|----------|--------|--------|
| 1 | Anderson họp nội bộ với Leader + CTO: xác nhận quyết định, đánh giá rủi ro dự án | Anderson | Quyết định chính thức nội bộ |
| 2 | CTO lập danh sách quyền truy cập cần thu hồi: GitHub, server, tools, email, Telegram | CTO | Checklist thu hồi |
| 3 | Leader lập kế hoạch bàn giao: ai tiếp nhận task nào, timeline bàn giao | Leader | Kế hoạch bàn giao |

### Phần B — Thông báo với nhân viên

| # | Việc làm | Ai làm | Đầu ra |
|---|----------|--------|--------|
| 4 | Anderson gặp 1:1 riêng với nhân viên — thông báo quyết định, nêu lý do rõ ràng dựa trên hồ sơ đã có | Anderson | Nhân viên được thông báo trực tiếp |
| 5 | Lắng nghe nhân viên giải trình lần cuối — Anderson có thể điều chỉnh nếu có thông tin mới | Anderson | Công bằng đến cùng |
| 6 | Thống nhất ngày cuối làm việc và timeline bàn giao (thường 1–2 tuần) | Anderson + Nhân viên | Ngày cuối đã xác nhận |

### Phần C — Bàn giao & Offboarding (1–2 tuần)

| # | Việc làm | Ai làm | Đầu ra |
|---|----------|--------|--------|
| 7 | Nhân viên bàn giao task đang làm: document, code, context | Nhân viên + Leader | Tài liệu bàn giao |
| 8 | Nhân viên chuyển giao kiến thức dự án: họp với người tiếp nhận | Nhân viên + Người nhận | Session bàn giao |
| 9 | Kiểm tra không còn code WIP chưa push, không còn branch chưa merge | CTO | Codebase sạch |

### Phần D — Thu hồi quyền truy cập (Ngày cuối cùng)

| # | Việc làm | Ai làm | Đầu ra |
|---|----------|--------|--------|
| 10 | Thu hồi GitHub access — remove khỏi org và tất cả repo | CTO / Leader | GitHub ✅ |
| 11 | Remove khỏi Telegram group dự án và nội bộ | Leader | Telegram ✅ |
| 12 | Vô hiệu hóa email công ty (nếu có) | Leader | Email ✅ |
| 13 | Thu hồi quyền cloud/server (AWS, Fly.io, Railway...) | CTO | Cloud ✅ |
| 14 | Đổi mật khẩu các shared account mà nhân viên biết | CTO | Security ✅ |
| 15 | Thu hồi thiết bị công ty (nếu có) | Leader | Thiết bị ✅ |

### Phần E — Thủ tục pháp lý & tài chính

| # | Việc làm | Ai làm | Đầu ra |
|---|----------|--------|--------|
| 16 | Tính toán và thanh toán đầy đủ: lương còn lại, phép chưa nghỉ, bất kỳ khoản nào theo hợp đồng | Anderson | Thanh toán hoàn tất |
| 17 | Ký biên bản thanh lý hợp đồng lao động | Anderson + Nhân viên | Biên bản ký 2 bên |
| 18 | Cấp xác nhận thôi việc nếu nhân viên yêu cầu | Anderson | Giấy xác nhận |

### Phần F — Nội bộ sau khi nhân viên rời

| # | Việc làm | Ai làm | Đầu ra |
|---|----------|--------|--------|
| 19 | Anderson thông báo ngắn gọn cho team — không chia sẻ lý do chi tiết | Anderson | Team biết, không đồn đoán |
| 20 | Lưu hồ sơ toàn bộ (từ Issue/Warning/Retraining đến Termination) | Leader | Hồ sơ đầy đủ |
| 21 | Đánh giá nội bộ: vấn đề này có thể ngăn chặn từ đầu không? Cập nhật quy trình nếu cần | Anderson + Leader | Lesson learned |

## Quy tắc cứng

| Quy tắc | Lý do |
|---------|-------|
| **Chỉ Anderson thông báo quyết định — không để Leader làm thay** | Đây là quyết định cấp CEO, không thể uỷ quyền |
| **Không thông báo qua Telegram hay email — phải 1:1** | Phẩm giá con người. Không ai xứng đáng bị sa thải qua tin nhắn |
| **Thu hồi quyền truy cập ĐÚNG ngày cuối — không sớm hơn, không muộn hơn** | Sớm hơn = thiếu tôn trọng; Muộn hơn = rủi ro bảo mật |
| **Không nói lý do sa thải với team** | Tôn trọng quyền riêng tư, tránh gây chia rẽ |
| **Thanh toán đầy đủ trước hoặc cùng ngày cuối** | Nghĩa vụ pháp lý và đạo đức |

## Checklist tự kiểm — trước ngày cuối

- [ ] Anderson đã thông báo 1:1 với nhân viên
- [ ] Ngày cuối và timeline bàn giao đã thống nhất
- [ ] Bàn giao task và kiến thức đã hoàn tất
- [ ] Checklist thu hồi quyền truy cập đã hoàn tất (tất cả ô đã tick)
- [ ] Biên bản thanh lý hợp đồng đã ký
- [ ] Thanh toán đầy đủ đã thực hiện
- [ ] Team đã được thông báo ngắn gọn
- [ ] Hồ sơ đầy đủ đã lưu trữ

## Liên kết

- [Thường đến từ → Member Retraining](../hr-member-retraining/hr-member-retraining-process.md)
- [Hoặc từ → Member Warning](../hr-member-warning/hr-member-warning-process.md)
- [Nội quy lao động CYBERK-HR-001](../../../policy/base-policy/01-noi-quy-lao-dong.pdf)
