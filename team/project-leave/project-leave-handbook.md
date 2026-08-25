---
type: team
tags: [offboarding, project]
created: 2026-08-25
updated: 2026-08-25
author: Brian
status: Đang dùng
---

# Rời Dự Án — Cẩm nang cho Team

**Người chịu trách nhiệm:** Product Lead
**Trạng thái:** Đang dùng

Sổ tay này cung cấp các hướng dẫn thực tế, giải thích cách xử lý trong từng tình huống cụ thể (chủ động rời đi, điều chuyển nội bộ, nghỉ đột xuất/bất khả kháng, hoặc chưa có người tiếp quản) để đảm bảo tính chuyên nghiệp và tính liên tục của dự án tại Cyberk.

---

## Tình huống 1 — Làm sao để chủ động xin rời dự án một cách chuyên nghiệp?

Khi bạn muốn rời dự án vì lý do cá nhân hoặc định hướng công việc, cách bạn giao tiếp quyết định sự chuyên nghiệp và uy tín cá nhân của bạn.

**✅ Cách tốt:**
> Thông báo sớm ít nhất 2 tuần, giải thích lý do rõ ràng, lịch sự và chủ động đề xuất kế hoạch bàn giao chi tiết.

```text
"Chào anh/chị [Product Lead], em xin phép được bàn giao công việc tại dự án X từ ngày [DD/MM]. Lý do là em cần tập trung hoàn thành [lý do cụ thể/định hướng mới].
Em đã chuẩn bị sẵn danh sách các task đang làm dở và đề xuất anh [Tên Receiver] là người tiếp nhận vì anh ấy nắm rõ phần module Y nhất.
Em gửi kèm link dự thảo kế hoạch bàn giao ở đây để anh/chị xem xét ạ."
```

Tại sao tốt: Giúp Product Lead ở thế chủ động sắp xếp người thay thế, giảm thiểu xung đột và giữ mối quan hệ tốt đẹp giữa các thành viên.

**❌ Cách tồi:**
> Thông báo sát ngày (hoặc đột ngột nghỉ) mà không có sự chuẩn bị hay bàn giao gì.

```text
"Chào anh, ngày mai em nghỉ dự án X nha anh. Code em đã push lên git rồi, mọi người tự lấy về chạy tiếp nha."
```

Tại sao tồi: Gây khó khăn cực kỳ lớn cho team, làm vỡ tiến độ dự án, vi phạm quy tắc ứng xử và có thể bị hủy thưởng dự án theo [[project-bonus-policy|Chính Sách Thưởng Dự Án]].

---

## Tình huống 2 — Được Ban Quản lý điều chuyển sang dự án khác thì cần làm gì?

Khi công ty yêu cầu bạn chuyển sang một dự án mới quan trọng hơn hoặc phù hợp hơn, bạn vẫn có trách nhiệm đóng gói và bàn giao dự án cũ một cách trọn vẹn.

**✅ Cách tốt:**
> Phối hợp cùng Product Lead dự án cũ và Product Lead dự án mới để thống nhất "Điểm cắt chuyển giao" (Transition Cutoff), tập trung hoàn thiện dứt điểm các task đang làm trước ngày switch hoàn toàn.

```text
"Chào anh [Product Lead Dự án cũ], theo quyết định điều chuyển của công ty, em sẽ bắt đầu sang dự án mới từ ngày [DD/MM].
Từ nay đến ngày đó, em sẽ tập trung dứt điểm 2 task quan trọng là CYB-101 và CYB-102, đồng thời dành 3 ngày cuối để hướng dẫn bàn giao lại toàn bộ tài liệu cho anh [Tên Receiver].
Em gửi kế hoạch chuyển giao chi tiết ở đây ạ."
```

Tại sao tốt: Đảm bảo dự án cũ không bị "gãy", bạn bước sang dự án mới với tâm thế thoải mái và vẫn được hưởng chính sách thưởng dự án theo tỷ lệ đóng góp (pro-rata).

**❌ Cách tồi:**
> Ngay khi có lệnh chuyển là lập tức bỏ bê dự án cũ, dồn toàn bộ sự chú ý sang dự án mới hoặc ôm đồm cả 2 mà không làm rõ giới hạn năng lực.

```text
"Em nhận lệnh sang dự án mới rồi nên dự án này em không làm tiếp được nữa nha, anh kiếm ai làm nốt giùm em."
```

Tại sao tồi: Gây ách tắc cho dự án cũ, tạo ấn tượng thiếu trách nhiệm và làm mất uy tín cá nhân với cả hai team.

---

## Tình huống 3 — Xử lý thế nào khi gặp trường hợp bất khả kháng / nghỉ đột xuất (sức khỏe, sự cố gia đình)?

Khi xảy ra biến cố bất khả kháng, ưu tiên hàng đầu là sự an toàn và sức khỏe của bạn. Tuy nhiên, hãy cố gắng cung cấp thông tin tối thiểu cần thiết để team có thể vận hành tiếp.

**✅ Cách tốt:**
> Báo ngay cho Product Lead càng sớm càng tốt qua điện thoại hoặc tin nhắn ngắn gọn. Gửi thông tin truy cập khẩn cấp và vị trí code/tài liệu đang dở dang.

```text
"Chào anh [Product Lead], em gặp sự cố sức khỏe/gia đình đột xuất nên xin phép vắng mặt từ hôm nay.
Tình trạng công việc hiện tại:
1. Task CYB-200: Em đang làm dở ở branch `feature/payment-v2`, đã push commit mới nhất lên remote lúc sáng nay.
2. Tài khoản/mật khẩu server test em đã lưu trong 1Password của team.
Em ủy quyền cho anh tiếp quản task này giúp em. Khi sức khỏe ổn định em sẽ nhắn lại ngay ạ."
```

Tại sao tốt: Giúp team có ngay phương án ứng phó khẩn cấp, tiếp quản code kịp thời, và vẫn được xem xét bảo lưu quyền lợi thưởng pro-rata theo chính sách bất khả kháng.

**❌ Cách tồi:**
> Biến mất hoàn toàn không một lời nhắn (Ghosting), giữ mã nguồn dở dang trên máy cá nhân mà không push lên Git, hoặc giữ tài khoản độc quyền khiến team không thể truy cập.

Tại sao tồi: Làm tê liệt toàn bộ luồng công việc của đồng đội, team phải viết lại từ đầu hoặc mất quyền truy cập tài nguyên của khách hàng.

---

## Tình huống 4 — Khi dự án chưa tìm được Receiver (Người nhận bàn giao) thay thế thì làm sao?

Nếu thời điểm bạn rời đi mà công ty chưa tuyển hoặc chưa sắp xếp được nhân sự mới vào thay thế ngay, người nhận bàn giao mặc định là **Product Lead**.

**✅ Cách tốt:**
> Soạn tài liệu bàn giao dưới dạng "Tự giải thích" (Self-explanatory Documentation) để bất kỳ nhân sự nào vào sau đọc cũng có thể tự chạy và hiểu được mà không cần bạn giải thích lại.

```markdown
# Hướng dẫn chạy và bảo trì Module Payment (Self-explanatory Guide)

## 1. Môi trường & Thiết lập
- Cần Node v20+, cài đặt bằng `npm install`.
- File env mẫu đã được lưu tại `.env.example`.

## 2. Luồng xử lý chính
- Request vào đi qua Middleware `AuthGuard` -> Controller `PaymentController` -> Service `StripeProvider`.
- Nếu gặp lỗi Timeout từ cổng thanh toán, xem cách debug tại Wiki `troubleshooting-payment`.
```

Tại sao tốt: Giúp Product Lead dễ dàng lưu trữ và bàn giao lại cho người mới bất cứ lúc nào trong tương lai.

**❌ Cách tồi:**
> Bàn giao theo kiểu nói miệng một chiều cho Product Lead mà không lưu lại tài liệu thành văn bản, vì nghĩ "dù sao Lead cũng biết code/quản lý rồi".

Tại sao tồi: Product Lead quản lý nhiều đầu việc sẽ nhanh chóng quên các chi tiết kỹ thuật nhỏ, dẫn đến việc người mới vào sau vẫn bị bế tắc.

---

## Tình huống 5 — Viết tài liệu bàn giao (Handover Document) như thế nào là đạt chuẩn?

Tài liệu bàn giao là di sản bạn để lại cho dự án. Một tài liệu tốt giúp người sau làm việc tiếp mà không phải liên tục nhắn tin hỏi bạn sau khi bạn đã rời đi.

**✅ Cách tốt:**
> Tài liệu rõ ràng, chia làm 3 phần: (1) Danh sách task dở dang và trạng thái hiện tại, (2) Sơ đồ cấu trúc/logic cốt lõi do bạn chịu trách nhiệm, (3) Thông tin tài khoản/API key và cách setup môi trường đặc biệt.

```markdown
# Tài liệu Bàn giao Dự án X - [Tên của bạn]

## 1. Công việc dở dang (Pending Tasks)
- Task CYB-123 (Feature Login): Đã làm xong API, đang viết Frontend. Người tiếp quản cần tiếp tục ở branch `feature/login`.
- Task CYB-124 (Fix bug Payment): Đã reproduce được bug, ghi chú cách fix tại [Link comment].

## 2. Tài nguyên & Quyền truy cập
- Quyền Admin GCP: Đã transfer cho anh [Product Lead Name] (email: ...).
- API Key test tích hợp Sandbox: Lưu trong Vault 1Password của dự án.
```

Tại sao tốt: Tiết kiệm hàng giờ đồng hồ cho người tiếp quản và giữ vững chất lượng dự án.

**❌ Cách tồi:**
> Viết tài liệu qua loa, chung chung, không có tính định hướng hành động.

```text
- Code ở trên GitHub branch main.
- Các task cần làm đều ở trên Jira.
- Có gì không hiểu thì cứ ping Slack cho em (mặc dù đã rời dự án).
```

Tại sao tồi: Người tiếp quản sẽ không biết bắt đầu từ đâu, branch nào là branch mới nhất, và dễ dẫn đến việc làm sai logic cũ.

---

## Tóm lại

| Tiêu chí | Chuyên nghiệp (Nên làm) | Không chuyên nghiệp (Tránh làm) |
|---|---|---|
| **Chủ động xin nghỉ** | Báo trước tối thiểu 2 tuần, chủ động lập kế hoạch bàn giao. | Báo sát ngày, đột ngột xin off không lý do. |
| **Công ty điều chuyển** | Thống nhất Cutoff Date, dứt điểm task cũ, chuyển giao có trật tự. | Bỏ dở dự án cũ ngay khi có lệnh điều chuyển. |
| **Bất khả kháng (ốm/việc gấp)** | Báo khẩn cấp ngay, push commit mới nhất, gửi quyền truy cập. | Biến mất không báo trước (Ghosting), giữ code dở trên local. |
| **Chưa có Receiver** | Viết tài liệu tự giải thích (Self-explanatory) gửi Product Lead. | Chỉ nói miệng qua loa cho Product Lead rồi thôi. |
| **Bàn giao code & quyền** | Code sạch, push branch rõ ràng, transfer owner tài khoản. | Code dở dang không push, vẫn giữ quyền admin sau khi rời đi. |

---

## Liên kết

- [Quy trình Rời Dự Án](project-leave-process.md)
- [Project Onboarding](../project-onboarding/project-onboarding-process.md)
- [Chính Sách Thưởng Dự Án](../../delivery/dev/bonus-policy/project-bonus-policy.md)
