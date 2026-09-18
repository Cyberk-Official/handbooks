---
type: team
tags: [offboarding, project, developer, handbook]
created-date: 2026-09-17
updated-date: 2026-09-17
status: Nháp
---

# Bàn giao khi rời dự án — Cẩm nang cho Developer

**Người chịu trách nhiệm:** Product Owner của dự án

**Cập nhật lần cuối:** 2026-09-17

**Trạng thái:** Nháp

Bạn sắp rời dự án. Giá trị của lần bàn giao nằm ở việc người sau có thể tiếp tục công việc mà không phải đoán: **vì sao code như vậy, phần nào còn dở, kiểm tra bằng cách nào**. Hãy để lại bối cảnh bạn từng mong mình có khi mới vào dự án.

Lịch, vai trò và checklist thực hiện nằm trong [process](./dev-project-offboarding-process.md). Trang này giúp bạn chuẩn bị đầu ra dùng được.

---

## 1. Task chưa xong thì bàn giao thế nào?

Một task dở được mô tả rõ vẫn có thể tiếp quản tốt. Điều gây khó cho người nhận là code nằm ở local, trạng thái “gần xong” và không biết bước tiếp theo.

**✅ Cách tốt:** Cập nhật trực tiếp trên issue, gắn Draft PR và commit cụ thể:

```text
[FR-042] Payment webhook — bàn giao cho @receiver
- Đã làm: xác thực chữ ký; 3 test hợp lệ/sai chữ ký/thiếu header đã pass.
- Code: Draft PR #128, branch feat/FR-042-payment-webhook, commit abc1234.
- Còn thiếu: xử lý webhook gửi trùng; chưa test retry trên staging.
- Bước tiếp: bổ sung idempotency theo acceptance criteria trong FR-042.
- Blocker: thiếu quyền sandbox; PO đang làm việc với client.
- Receiver đã xác nhận nhận task; Target date được cập nhật trên board.
```

Tại sao tốt: Người nhận có điểm bắt đầu cụ thể và phân biệt được phần đã kiểm tra với phần còn thiếu. Hồ sơ bàn giao chỉ cần link tới issue này.

**❌ Cách tồi:** “Payment xong 90%, code trên máy em, cứ chuyển Done rồi người sau sửa nốt.”

Tại sao tồi: Board báo sai tiến độ; không có code để tiếp quản và không biết 10% còn lại là gì. Giữ task ở trạng thái thật, để PO và Receiver chốt phần chuyển tiếp.

---

## 2. Viết gì để người nhận không phải hỏi lại?

Hồ sơ bàn giao là bản đồ dẫn tới nguồn chính, không phải bản sao của toàn bộ repo. Tạo một file Markdown theo vị trí đã thống nhất với PO, ghi Developer, Receiver, ngày rời dự án và các mốc bàn giao đã chốt ở đầu file.

| Phần trong hồ sơ | Nội dung cần có | Nguồn chính để dẫn link |
|-----------------|------------------|------------------------|
| **1. Công việc và phạm vi** | Module phụ trách; việc đã xong, việc chuyển tiếp; người nhận; blocker và next step | Issue, PR, board dự án và Feature ID trong PRD/BRD |
| **2. Logic và quyết định kỹ thuật** | Entry point, luồng dữ liệu, dependency, lý do chọn giải pháp, edge case và lỗi đã biết | Code, ADR, ERD, API docs, BRD và issue lỗi |
| **3. Môi trường, vận hành và quyền** | Cách setup/test; deploy/rollback nếu thuộc phần phụ trách; tên dịch vụ, Owner, quyền cần chuyển, automation phụ thuộc và người xử lý | README, `.env.example`, hướng dẫn vận hành; vị trí item trong 1Password, không chứa giá trị secret |
| **4. Demo và xác nhận** | Luồng cần kiểm chứng, link video, commit đã chạy, kết quả test/Reverse Demo, phần cần bổ sung và xác nhận Receiver/PO | Video do PO lưu, bằng chứng kiểm thử và xác nhận trong hồ sơ |

**✅ Cách tốt:** “Webhook đi từ route → xác thực chữ ký → queue → cập nhật trạng thái. Xem ADR về retry và issue duplicate event. README đã bổ sung lệnh chạy worker; PR tài liệu đã được review.”

Tại sao tốt: Có đường đi, có lý do và có nguồn để kiểm tra. Khi phát hiện thiếu hướng dẫn, bạn sửa ngay tại nguồn để người onboard sau cũng dùng được.

**❌ Cách tồi:** Copy README sang file bàn giao, viết thêm vài bước khác vào Telegram rồi nhắn “có gì hỏi em”.

Tại sao tồi: Người nhận phải đoán bản nào đúng; bối cảnh quan trọng vẫn phụ thuộc trí nhớ người cũ. Có thể nhờ AI rà cấu trúc tài liệu, nhưng bạn phải kiểm tra nội dung với code và kết quả chạy thật.

---

## 3. Demo thế nào để biết đã bàn giao được?

Live Demo giúp người nhận thấy cách hoạt động. **Reverse Demo** mới kiểm tra được họ có thể tự làm: Receiver thao tác, bạn quan sát và giải thích điểm còn thiếu.

**✅ Cách tốt:** Thống nhất với PO luồng cần kiểm chứng theo module bàn giao. Ví dụ với payment webhook: Receiver setup theo README, chạy test chữ ký, gửi một webhook sandbox và chỉ ra nơi xem log khi lỗi. Receiver dùng quyền riêng; bạn ghi commit, kết quả và bổ sung bước thiếu vào tài liệu. Video được kiểm tra để không lộ secrets trước khi chia sẻ.

Tại sao tốt: Kiểm chứng cả code, tài liệu, quyền và khả năng debug. Người nhận có bằng chứng thực tế để xác nhận tiếp quản.

**❌ Cách tồi:** Bạn chạy hết trên máy mình, Receiver chỉ xem video rồi xác nhận “đã hiểu”.

Tại sao tồi: Có thể máy bạn đang có config chưa ghi lại hoặc quyền riêng mà người nhận không có. Khi Reverse Demo lỗi, coi đó là phần cần hoàn thiện trước khi chốt bàn giao.

---

## 4. Chuyển quyền dịch vụ mà không làm gián đoạn hệ thống thế nào?

Kiểm kê cả quyền trực tiếp lẫn công việc chạy bằng danh tính của bạn: repo, board, kho secrets, server/cloud, database, SaaS, CI/CD, scheduled job và bot nếu có. Với mỗi mục, ghi phạm vi dự án/môi trường, Owner hiện tại, người nhận, phụ thuộc và kết quả chuyển giao.

**✅ Cách tốt:** Phát hiện deploy dùng token cá nhân → ghi tên workflow và vị trí cấu hình cho PO → người quản trị thay bằng credentials do dự án quản lý → Receiver kiểm tra pipeline bằng quyền mới → người quản trị thu hồi token/quyền cũ và ghi xác nhận. Secrets được xử lý trong 1Password hoặc nguồn PO phê duyệt.

Tại sao tốt: Đổi người chịu trách nhiệm mà hệ thống vẫn hoạt động; việc thu hồi có người thực hiện và bằng chứng. Nếu chỉ chuyển dự án, liệt kê rõ quyền của dự án rời đi để PO xác định đúng phạm vi thu hồi.

**❌ Cách tồi:** Gửi `.env` qua Telegram cho người nhận, hoặc tự xóa tài khoản đang sở hữu pipeline trước khi kiểm tra phụ thuộc.

Tại sao tồi: Gửi mật khẩu không chuyển được trách nhiệm sở hữu; xóa tài khoản có thể làm deploy dừng hoạt động. Khi cần khóa quyền khẩn cấp, báo PO xử lý theo Project Leave thay vì tự thay đổi hệ thống.

---

## 5. Báo blocker bàn giao trên Telegram thế nào?

Cập nhật issue/hồ sơ trước, sau đó gửi link kèm ảnh hưởng và việc cần người khác hỗ trợ. Vẫn giữ nhịp [Dev Daily](../dev-daily/dev-daily-process.md) và cung cấp dữ liệu cho [Daily Report](../dev-daily-report/daily-report-process.md) đến khi đã chuyển trách nhiệm.

**✅ Cách tốt — mẫu chat:**

```text
Anh @PO ơi, em đã cập nhật hồ sơ bàn giao: <link> 📋
- Code webhook: Draft PR #128; @receiver đã nhận task trên board.
- Reverse Demo còn kẹt quyền sandbox nên chưa kiểm chứng được callback.
- Nhờ anh xác nhận quyền với client trước 15:00 hôm nay;
  em và @receiver dự kiến chạy lại lúc 16:00 nếu đã được cấp quyền.
- Nếu chưa có quyền, mốc nghiệm thu bàn giao ngày mai có nguy cơ trễ.
```

Tại sao tốt: PO thấy chính xác phần cần hỗ trợ, ảnh hưởng và kế hoạch kiểm tra lại. Trạng thái đã nằm trong hồ sơ nên không bị mất trong chat.

**❌ Cách tồi:** “Em bàn giao gần xong rồi, đang chờ bên kia.”

Tại sao tồi: Không biết ai cần hành động, chờ gì hoặc khi nào ảnh hưởng deadline. Không chờ đến ngày cuối mới báo một blocker đã biết.

---

## 6. Rời dự án rồi, nghĩa vụ bảo mật còn gì?

Khi off-boarding, bạn cần ký NDA về bảo mật thông tin dự án sau khi rời đi theo [yêu cầu trong Project Leave](../../05-product-owner/po-project-leave/po-project-leave-process.md#yêu-cầu-ký-nda-khi-off-boarding). HR cung cấp mẫu được phê duyệt; bạn đọc rõ dự án áp dụng, thông tin được bảo vệ, thời hạn, ngoại lệ và cách xử lý bản sao dữ liệu. Nếu đã có NDA trước đó, gửi HR đối chiếu để chuẩn bị văn bản ký xác nhận phù hợp cho lần off-boarding này.

**✅ Cách tốt:** Nhận mẫu ngay khi chốt kế hoạch, hỏi HR/PO các điều khoản chưa rõ, ký trước sign-off và nhận xác nhận HR đã lưu bản ký. Hồ sơ bàn giao chỉ ghi trạng thái, ngày ký, mã tham chiếu. Sau khi rời dự án, muốn dùng hình ảnh hoặc đoạn code trong portfolio thì kiểm tra NDA và xin chấp thuận theo quy định trong văn bản trước khi sử dụng.

Tại sao tốt: Bạn hiểu rõ nghĩa vụ còn tiếp tục sau khi rời đi, có bằng chứng hoàn tất và không phát tán bản ký chứa dữ liệu cá nhân.

**❌ Cách tồi:** “Em đã bị xóa quyền repo nên hết trách nhiệm bảo mật”, bỏ qua bước ký hoặc tự đưa code/dữ liệu dự án sang dự án mới.

Tại sao tồi: Thu hồi quyền không xóa thông tin bạn đã tiếp cận; việc tiết lộ hoặc tái sử dụng vẫn phải tuân thủ NDA. Nếu chưa ký được, báo PO/HR để xử lý; việc thu hồi quyền vẫn diễn ra đúng lịch.

---

## Tóm lại

| Câu hỏi tự kiểm | Bằng chứng nên có |
|-----------------|--------------------|
| Người sau tìm được phần đang dở không? | Issue dẫn tới branch/commit/PR trên remote |
| Người sau hiểu vì sao và làm gì tiếp không? | Tài liệu tại nguồn, next step, blocker, Assignee và ETA |
| Người sau tự chạy được không? | Reverse Demo, kết quả test và xác nhận Receiver |
| Dịch vụ còn hoạt động sau khi đổi người không? | Xác nhận chuyển Owner, kiểm tra automation và thu hồi quyền |
| Nghĩa vụ bảo mật sau khi rời đi đã được xác nhận chưa? | NDA đã ký đầy đủ, HR xác nhận lưu và mã tham chiếu trong hồ sơ |
| Ai chốt hoàn tất? | Sign-off của PO trong hồ sơ bàn giao |

**Bắt đầu ngay:** mở Personal Board, rà task/PR còn mở và gửi PO link phạm vi cần bàn giao để chốt kế hoạch.

---

## Liên kết

- [Quy trình off-boarding — Các bước và checklist](./dev-project-offboarding-process.md)
- [Project Leave — Lịch và điều phối bàn giao](../../05-product-owner/po-project-leave/po-project-leave-process.md)
- [Project Onboarding — Cách Receiver tiếp nhận dự án](../dev-project-onboarding/dev-project-onboarding-process.md)
- [Dev Write BRD — Ghi lại requirement còn thiếu](../dev-write-brd/dev-write-brd-process.md)
- [Dev Bootstrap — Các tài liệu nền tảng cần dẫn link](../dev-bootstrap/dev-bootstrap-process.md)
