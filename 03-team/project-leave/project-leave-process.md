---
type: team
tags: [offboarding, project, process]
created: 2026-08-25
updated: 2026-09-03
author: Brian
status: Đang dùng
---

# Rời Dự Án — Quy trình Chuẩn

**Người chịu trách nhiệm:** Product Lead  
**Cập nhật lần cuối:** 2026-09-03  
**Trạng thái:** Đang dùng  

## Tại sao có trang này

Quy trình này nhằm đảm bảo việc chuyển giao công việc, tài nguyên, mã nguồn và quyền hạn của một thành viên khi rời khỏi dự án diễn ra suôn sẻ, không làm gián đoạn tiến độ chung (Business Continuity), không thất thoát tri thức (Zero Knowledge Loss) và bảo vệ an toàn tuyệt đối tài sản/thông tin của Cyberk và khách hàng.

## Khi nào áp dụng (Trigger)

Quy trình được kích hoạt khi:
- Thành viên dự án chủ động đề xuất xin rời dự án.
- Có quyết định điều chuyển nhân sự sang dự án khác từ Ban Quản lý.
- Thành viên nghỉ việc tại công ty.

---

## Luồng chính

```mermaid
flowchart TD
    A["1. Đề xuất & Xác nhận timeline (T-14)"] --> B["2. Thiết lập Cutoff & Lập kế hoạch bàn giao (T-10)"]
    B --> C["3. Đóng gói mã nguồn & Soạn tài liệu (T-7 -> T-3)"]
    C --> D["4. Họp bàn giao & Live Verification (T-2)"]
    D --> E["5. Thu hồi quyền & Bảo mật Zero Trust (Last Day)"]
    E --> F["6. Đánh giá Thưởng & Sign-off hoàn tất (Last Day)"]
```

---

## Vai trò & trách nhiệm

| Vai trò | Chịu trách nhiệm gì |
|---------|---------------------|
| **Product Lead** | - Chịu trách nhiệm trực tiếp và toàn diện về quá trình offboarding thành viên khỏi dự án.<br>- Họp 1-1 xác nhận timeline, đánh giá rủi ro (Impact Assessment) và điểm nghẽn SPOF.<br>- Chỉ định Receiver và thiết lập Cutoff Date (T-7 dừng nhận task mới).<br>- Thẩm định và phê duyệt tài liệu bàn giao (Handover Doc).<br>- Chủ trì buổi họp bàn giao (Handover Session), giám sát Live & Reverse Demo và lưu trữ video record.<br>- Thực hiện thu hồi 100% quyền truy cập (GitHub, Cloud, Secrets, SaaS) và chuyển Owner dịch vụ.<br>- Đánh giá chất lượng bàn giao, đề xuất thưởng dự án theo [[project-bonus-policy\|Chính Sách Thưởng Dự Án]] và ký duyệt Sign-off. |
| **Thành viên rời đi (Outgoing Member)** | - Thông báo chính thức trước tối thiểu 2 tuần.<br>- Tập trung dứt điểm các task dở dang trước mốc Cutoff Date.<br>- Push 100% commit và branch cá nhân lên remote GitHub (không để code trên máy cá nhân).<br>- Soạn thảo tài liệu bàn giao chuẩn 4 trụ cột và quay video demo luồng chạy.<br>- Trình diễn Live Demo tại buổi họp bàn giao và giải đáp mọi khúc mắc kỹ thuật.<br>- Bàn giao quyền sở hữu (Owner) toàn bộ tài khoản/API key cho Product Lead. |
| **Thành viên nhận bàn giao (Receiver)** | - Đọc trước tài liệu bàn giao và mã nguồn liên quan trước buổi họp.<br>- Tham gia buổi họp bàn giao, chủ động đặt câu hỏi làm rõ logic ngầm và edge cases.<br>- **Tự tay clone mã nguồn, nạp key giải mã `dotenvx` và chạy ứng dụng thành công trên máy mình** dưới sự chứng kiến của PL và người rời đi.<br>- Tiếp quản chính thức các issue và module được phân công. |

---

## Các bước

| # | Việc làm | Ai làm | Đầu ra | Timeline |
|---|----------|--------|--------|----------|
| 1 | **Gửi yêu cầu rời dự án**<br>- Gửi thông báo chính thức và lý do. | Outgoing Member | Email/Tin nhắn chính thức gửi Product Lead | **T-14 ngày** (Trước ngày rời dự án ít nhất 2 tuần) |
| 2 | **Họp 1-1, Đánh giá rủi ro & Chỉ định Receiver**<br>- Product Lead họp 1-1, rà soát SPOF và lên kế hoạch chuyển giao. | Product Lead + Outgoing Member | Kế hoạch chuyển giao & Người nhận (Receiver) được chỉ định | Trong vòng **24–48 giờ** sau khi nhận yêu cầu |
| 3 | **Thiết lập Cutoff Date & Đóng gói công việc**<br>- Dừng nhận task mới, dứt điểm task cũ.<br>- Push 100% remote branch, đóng gói Draft PRs. | Outgoing Member + Product Lead | Git sạch, PR được merge hoặc đóng gói, Board cập nhật | **T-7 ngày** đến **T-3 ngày** |
| 4 | **Soạn thảo & Phê duyệt tài liệu bàn giao**<br>- Outgoing Member soạn Handover Doc chuẩn 4 phần kèm video demo.<br>- Product Lead thẩm định tính tự giải thích (Self-explanatory). | Outgoing Member (Soạn) + Product Lead (Duyệt) | Handover Doc hoàn thiện được Product Lead phê duyệt | Hoàn thành trước **T-3 ngày** |
| 5 | **Chủ trì Họp bàn giao & Live Verification**<br>- Live Demo luồng tính năng.<br>- Receiver tự tay chạy local (Reverse Demo).<br>- Record video buổi họp và lưu vào Wiki. | Product Lead (Chủ trì) + Outgoing Member + Receiver | Buổi họp hoàn tất, video được lưu trữ, Receiver chạy được app | **T-2 ngày** |
| 6 | **Thu hồi quyền truy cập & Bảo mật Zero Trust**<br>- Thu hồi quyền GitHub, Cloud SSH/IAM, rotate secret nếu cần, transfer Owner SaaS, thu hồi key `dotenvx`. | Product Lead | Bảng kiểm định quyền hạn thu hồi 100% | **Ngày làm việc cuối cùng** (Trước 18:00) |
| 7 | **Đánh giá Thưởng, Tri ân & Ký duyệt Sign-off**<br>- Đánh giá thưởng pro-rata theo chính sách.<br>- Gửi lời cảm ơn trên nhóm team và ký duyệt hoàn tất. | Product Lead | Checklist hoàn tất 100%, Sign-off đóng quy trình | **Ngày làm việc cuối cùng** |

---

## Quy tắc cứng (không được vi phạm) + lý do

| Quy tắc | Lý do |
|---------|-------|
| Bắt buộc thông báo trước tối thiểu 2 tuần (trừ bất khả kháng) | Đảm bảo Product Lead có đủ thời gian sắp xếp người thay thế và lên kế hoạch chuyển giao không làm vỡ tiến độ chung. |
| Dừng nhận task mới từ mốc Cutoff Date (T-7 ngày) | Dành trọn vẹn thời gian cho việc dứt điểm task dở, dọn dẹp Git, viết tài liệu và kiểm thử chuyển giao. |
| Tuyệt đối không để mã nguồn dở dang trên máy local cá nhân | Toàn bộ commit và branch phải được push lên remote GitHub trước ngày cuối cùng để tránh mất mát dữ liệu khi thu hồi máy/tài khoản. |
| Tài liệu bàn giao phải đạt chuẩn "Self-explanatory" và được Product Lead phê duyệt | Đảm bảo người mới vào sau đọc là có thể tự chạy và vận hành được ngay mà không cần liên hệ lại người cũ. |
| Receiver bắt buộc phải tự tay chạy thành công mã nguồn trên máy mình trong buổi họp | Kiểm chứng thực tế tri thức đã được tiếp thu, loại bỏ tình trạng bàn giao hình thức một chiều. |
| Áp dụng bảo mật Zero Trust: Thu hồi 100% quyền truy cập và secrets trong ngày cuối cùng | Ngăn chặn triệt để rủi ro rò rỉ dữ liệu của Cyberk và khách hàng. Tuyệt đối không để sót SSH keys hay quyền Admin sau khi rời đi. |
| Tự ý bỏ việc (Ghosting) hoặc không hoàn thành bàn giao sẽ bị hủy thưởng dự án | Đồng bộ với [[project-bonus-policy\|Chính Sách Thưởng Dự Án]] nhằm đảm bảo tính kỷ luật và cam kết trách nhiệm. |

---

## Ngoại lệ & Escalation

| Tình huống | Hành động |
|-----------|----------|
| **Nghỉ đột xuất (lý do bất khả kháng: sức khỏe nặng, biến cố gia đình)** | - Product Lead lập tức khóa mọi quyền truy cập trong vòng 1 giờ để bảo vệ hệ thống.<br>- Kéo toàn bộ code mới nhất từ remote Git về kiểm tra commit cuối cùng; rà soát task trên GitHub Projects.<br>- Chỉ định Interim Receiver tiếp quản khẩn cấp để giữ nhịp Sprint.<br>- Đề xuất phân chia thưởng pro-rata theo đóng góp thực tế (cần Anderson duyệt). |
| **Thành viên cố tình ngắt liên lạc (Ghosting) hoặc bất hợp tác** | - Khóa ngay lập tức mọi quyền truy cập Git, Cloud, Server, Database, SaaS.<br>- Thu hồi toàn bộ quyền lợi thưởng dự án theo quy chế kỷ luật.<br>- Báo cáo ngay lên Anderson để có phương án pháp lý/hành chính nếu cần. |
| **Dự án chưa tuyển được Receiver thay thế (Team neo người)** | - Product Lead tạm thời đóng vai trò Receiver trung gian, lưu trữ toàn bộ Handover Doc và Video record vào Wiki dự án.<br>- Khi có nhân sự mới, áp dụng trực tiếp [[project-onboarding-process\|Quy trình Onboarding Dự Án]] để chuyển giao lại trong 24h. |

---

## Checklist

### Dành cho Product Lead

- [ ] **T-14:** Đã tiếp nhận thông báo, họp 1-1 xác nhận timeline và đánh giá rủi ro (Impact Assessment).
- [ ] **T-10:** Đã chỉ định Receiver và ban hành kế hoạch chuyển giao (Handover Plan).
- [ ] **T-7:** Đã thiết lập Cutoff Date, chốt danh sách task dở dang trên GitHub Projects.
- [ ] **T-3:** Đã thẩm định và phê duyệt tài liệu bàn giao (Handover Doc) đạt chuẩn 4 trụ cột.
- [ ] **T-2:** Đã chủ trì buổi họp Handover Session, xác nhận Receiver chạy thành công local, và lưu trữ video record.
- [ ] **Last Day:** Đã thu hồi quyền GitHub Repo/Org của thành viên.
- [ ] **Last Day:** Đã xóa SSH keys trên server, xóa IAM User/Service Account, thu hồi quyền Database.
- [ ] **Last Day:** Đã tiếp nhận chuyển giao quyền sở hữu (Owner) các tài khoản SaaS (Figma, Sentry, Vercel, Domain...).
- [ ] **Last Day:** Đã xoay vòng (rotate) API keys nhạy cảm (nếu cần) và thu hồi key `dotenvx`.
- [ ] **Last Day:** Đã xóa khỏi các nhóm/topic Telegram bảo mật của dự án.
- [ ] **Last Day:** Đã đánh giá thưởng dự án pro-rata theo chính sách, gửi lời cảm ơn trên nhóm team và ký duyệt Sign-off.

### Dành cho Thành viên rời đi (Outgoing Member)

- [ ] **T-14:** Đã gửi thông báo chính thức trước ít nhất 2 tuần và tham gia họp 1-1 với Product Lead.
- [ ] **T-7:** Đã ngừng nhận task mới, tập trung dứt điểm các task đang làm dở.
- [ ] **T-5:** Đã push 100% commit và branch cá nhân lên remote GitHub (không giữ code local).
- [ ] **T-3:** Đã hoàn thành Handover Doc chuẩn 4 phần kèm video quay màn hình demo luồng code.
- [ ] **T-2:** Đã trình diễn Live Demo trong buổi họp và hướng dẫn Receiver chạy thành công mã nguồn.
- [ ] **Last Day:** Đã chuyển giao quyền Owner tài khoản dịch vụ và secrets cho Product Lead.
- [ ] **Last Day:** Đã cập nhật trạng thái toàn bộ issues cá nhân trên GitHub Projects sang Closed hoặc reassign.

### Dành cho Người nhận bàn giao (Receiver)

- [ ] **T-3:** Đã đọc trước tài liệu bàn giao và chuẩn bị danh sách câu hỏi làm rõ.
- [ ] **T-2:** Đã tham gia buổi họp, tự tay clone code, nạp key `dotenvx` và chạy ứng dụng thành công trên máy mình.
- [ ] **T-2:** Đã nắm rõ luồng xử lý của module, các edge cases và cách debug khi có sự cố.
- [ ] **Last Day:** Đã tiếp nhận chính thức các issue và task được phân công trên GitHub Projects.

---

## Liên kết

- [Cẩm nang Rời Dự Án cho Product Lead (Lead Handbook)](project-leave-lead-handbook.md)
- [Cẩm nang Rời Dự Án cho Thành viên (Member Handbook)](project-leave-member-handbook.md)
- [Quy trình Onboarding Dự Án (Process)](../project-onboarding/project-onboarding-process.md)
- [Cẩm nang Onboarding Dự Án (Handbook)](../project-onboarding/project-onboarding-handbook.md)
- [Cẩm nang Giao tiếp trong Team (Horenso)](../team-communicate/team-communicate-handbook.md)
- [Quy trình Quản lý Công việc Hàng ngày (Dev Daily)](../dev-daily/dev-daily-process.md)
- [Cẩm nang Quản lý Board Dự Án](../../04-delivery/board-handbook/board-handbook.md)
- [Chính Sách Thưởng Dự Án](../../04-delivery/bonus-policy/project-bonus-policy.md)
