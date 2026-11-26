---
type: delivery
tags: [handbook, dev-daily, board, google-sheet]
created-date: 2026-11-26
updated-date: 2026-11-26
author: anderson
status: Nháp
---

# Internal Daily Meeting — Cẩm nang cho PO

**Người chịu trách nhiệm:** PO dự án
**Cập nhật lần cuối:** 2026-11-26
**Trạng thái:** Nháp

Mỗi ngày, PO dẫn team đi qua 3 bước `DEMO → CHANGE → REPORT`: cả team xem sản phẩm đã làm hôm qua, PO sửa board theo những gì vừa thấy, rồi gửi khách bản PDF export từ board. Trang này nói cách dẫn từng bước, và các dấu hiệu cho thấy dự án đang được quản lý chưa tốt.

---

## Vì sao buổi DEMO phải mở sản phẩm ra xem?

Vì *"Trăm nghe không bằng một thấy"*. Chúng ta không nói "sắp xong rồi", chúng ta cho nhau thấy sản phẩm chạy được. Điều này triệt tiêu mọi hiểu lầm và đảm bảo chúng ta không bao giờ đi sai hướng quá một ngày.

Chất lượng không phải là trách nhiệm của riêng QA. Trong buổi Demo, cả team cùng đặt mình vào vị trí người dùng và trải nghiệm sản phẩm. Vấn đề được phát hiện và sửa ngay từ khi mới manh nha — mỗi tính năng trước khi đến tay khách hàng đã được chính chúng ta dùng đi dùng lại hàng chục lần.

Câu hay nghe nhất khi bỏ qua phần xem: *"Phần này mình làm, cả team biết rồi, cần gì xem nữa."* Nhưng người làm ra tính năng là người khó thấy lỗi của nó nhất. Mình biết phải bấm vào đâu, biết phải nhập gì, nên luồng nào mình thử cũng chạy. Bỏ qua phần xem là để sự chủ quan đó đi thẳng tới khách. Khách bấm theo cách khác, và lỗi lộ ra trước mặt khách thay vì trước mặt team. Vì vậy mỗi phần làm xong đều được mở ra trên sản phẩm đang chạy, để một người khác trong team bấm thử, kể cả khi nó chỉ là một nút bấm.

Demo không dừng ở luồng chạy đúng. Người dùng thật sẽ nhập sai, bấm nhầm, mất mạng giữa chừng. Mỗi tính năng khi demo, ngoài luồng chạy đúng, cả team thử thêm các trường hợp lỗi liên quan tới nó. Danh sách dưới đây là những trường hợp hay bị bỏ qua nhất:

| Nhóm | Thử gì trong buổi Demo |
|------|------------------------|
| Form & nhập liệu | Để trống rồi bấm submit · nhập sai định dạng (email thiếu `@`, số điện thoại có chữ) · nhập rất dài, có ký tự đặc biệt hoặc emoji · số âm, số `0`, số thập phân nhiều chữ số · bấm submit 2 lần liên tiếp |
| Đăng nhập & quyền | Sai mật khẩu · tài khoản không tồn tại · link quên mật khẩu đã hết hạn · session hết hạn khi đang thao tác · mở thẳng URL của trang cần đăng nhập |
| Mạng & server | Tắt mạng giữa chừng · server trả lỗi hoặc timeout: có thông báo không, bấm lại được không · mạng chậm: có trạng thái loading không |
| Dữ liệu | Danh sách rỗng · danh sách rất dài · reload trang giữa lúc đang điền form · bấm nút back của trình duyệt |
| Ví & giao dịch | Số dư không đủ · từ chối ký trên ví · ví đang ở sai chain · giao dịch pending lâu hoặc failed · lệnh bị sàn từ chối |
| Thiết bị | Mở trên điện thoại · xoay ngang màn hình · trình duyệt khác (Safari, Chrome) |

Không cần thử hết cả bảng cho mọi tính năng. Tính năng đăng nhập thì thử nhóm Đăng nhập. Tính năng rút tiền thì thử nhóm Ví & giao dịch và Mạng & server. Trường hợp nào chưa xử lý thì lên board thành task ở bước Change.

Cách tồi:

```
Shota: "Hôm qua em làm xong phần TP/SL rồi anh, chiều em push."
PO: "Ok, next."
```

Tại sao tồi: Cả team chỉ nghe Shota nói là xong, chưa ai thấy nó chạy thế nào. Hai ngày sau khách dùng thử và phát hiện lỗi.

Cách tốt:

```
Shota mở staging, đặt một lệnh Limit có TP/SL, kéo SL trên chart.
Kate: "Kéo SL xuống dưới giá entry mà vẫn cho đặt — cái này phải chặn."
PO ghi lại: bug [P1] cho Milestone Lighter Platform Integration.
```

Tại sao tốt: Lỗi bị bắt ngay trên sản phẩm, trong 1 phút, trước khi khách nhìn thấy.

---

## Sau buổi DEMO, cần sửa gì trên board?

Buổi Demo luôn sinh ra việc: một màn hình cần sửa, một luồng còn thiếu, một bug vừa thấy. Nếu những việc đó chỉ nằm trong đầu PO hoặc trong tin nhắn, board sẽ không còn đúng với thực tế.

Sau mỗi buổi Demo, PO đi qua board với 3 việc:

- Luôn cập nhật task mới nhất lên board. Việc mới, bug mới phát hiện trong buổi Demo lên tab sprint trong ngày.
- Bỏ các tasks đã outdate. Task không còn đúng với sản phẩm hiện tại thì bỏ, đừng để board phình ra bằng những việc không ai làm nữa.
- Task/Bugs mới được tạo luôn đầy đủ thông tin: đủ 8 cột, đúng Board Rule *(xem [Cẩm nang Board](../po-board-create/board-create-handbook.md))*.

Rồi điều chỉnh các task đang có cho hợp lý: task trễ thì đổi Expected done date, người quá tải thì chuyển bớt, việc không kịp tuần này thì đưa sang sprint sau với ngày cụ thể.

Cách tồi:

```
PO nhắn riêng Shota: "Nhớ fix cái SL nhé."
Board không đổi gì.
```

Tại sao tồi: Việc không lên board thì không có Estimate, QA cũng không biết để test lại. Khách đọc PDF không biết team đã thấy lỗi này.

Một lỗi hay gặp khác: cả buổi họp xong mà không ai đụng vào board, vì ai cũng đã biết việc của mình. Task xong vẫn để `Doing`, việc mới nằm trong đầu PO. Khách chỉ thấy bản PDF, và nếu PDF hôm nay giống hệt hôm qua thì khách hiểu là team không làm gì, dù thực tế cả team vừa có một ngày làm việc tốt. Hai ba ngày như vậy là khách bắt đầu hỏi dồn, rồi nghĩ team lười.

Cách tốt:

```
Sau Demo, PO thêm 2 dòng vào sprint_2:
  Lighter Platform Integration | [P1] Block stop-loss below entry price | Shota | Todo | 0% | 2 | 2026-11-19
  Lighter Platform Integration | QA: retest TP/SL drag on chart          | Kate  | Todo | 0% | 1 | 2026-11-20
Task "Leverage presets" của Shota dời Expected done date sang thứ 5.
```

Tại sao tốt: Board phản ánh đúng những gì vừa thấy trong buổi Demo. Bản PDF gửi khách hôm nay đã có cả bug và kế hoạch sửa.

### Đọc board mỗi sáng thế nào?

PO mở tab sprint ra mỗi sáng — 10 giây biết:
- Còn bao nhiêu task `Todo`? (chưa ai bắt đầu)
- Task `Doing` nào kéo dài bất thường? (đang nghẽn)
- Số task `Done` có đang tăng? (team đang tiến triển)

Nếu thứ 4 mà chưa có task nào `Done` — sprint đang có vấn đề. Không cần ai nói, board tự nói.

Thứ 2 có 8 task `Todo`, chưa task nào `Doing` hay `Done`. Đến thứ 5 còn 2 `Todo`, 3 `Doing`, 3 `Done`. Sprint này đang ổn.

Một sprint khác, đến thứ 5 có 1 `Todo`, 7 `Doing`, 0 `Done`. Bảy task đang làm dở mà chưa cái nào xong, nên gần như chắc chắn sprint này trễ.

### Những dấu hiệu khi quản lý dự án không tốt

Ở mỗi buổi Change, PO đi qua danh sách dưới đây. Gặp dấu hiệu nào thì xử lý ngay trong buổi đó.

#### Dấu hiệu ở cấp team / dự án

- Bạn không rõ, mơ hồ, hoặc không biết mục tiêu cuối cùng của dự án là gì (Scope)? Tháng này phải bàn giao tính năng nào cho khách hàng, tại sao?
- Không rõ việc cần làm và chờ người quản lý giao việc cho bạn? hoặc bạn không biết mình cần phải làm gì.
- Bạn không biết đâu là task quan trọng nhất cần phải làm ngay trong hôm nay?
- Bạn không rõ rủi ro, tính năng nào có rủi ro gì cần lưu ý. Chỗ nào là điểm nóng cần phải giải quyết ngay?
- Bạn là "Tôn Ngộ Không" gánh team, trong khi những người còn lại là Trư Bát Giới, Sa Tăng.
- Bạn không có task nào, hoặc task của bạn chỉ có đủ đến hết tuần, và bạn không rõ mình cần làm gì về mặt dài hạn.
- Bạn được assign task-by-task thay vì theo một Milestone cụ thể.
- Task tạo ra không có Estimate, Expected done date, Milestone.
- Task của bạn treo từ tuần này qua tuần khác.
- Todo bị Abandoned, không có ai làm, hoặc có quá nhiều / quá ít Todo.
- **Task không gắn Milestone** — không ai biết nó thuộc tính năng nào, không verify được scope.

#### Dấu hiệu ở cấp cá nhân

- **Quá nhiều Todo (> 10 tasks)** — Board thành danh sách mong ước, không phải kế hoạch. Developer bị choáng ngợp, không biết bắt đầu từ đâu.
- **Quá ít Todo (0–1 tasks)** — Developer đang reactive, chờ ai đó giao việc. Thiếu chủ động review Milestone và tự kéo task.
- **`Doing` > 3 tasks cùng lúc** — Multitasking giả. Context switching giết năng suất. Thực tế không task nào được tập trung.
- **Task treo `Doing` > 2 ngày liên tục** — Task quá lớn cần breakdown, hoặc bị block mà không báo. PO bôi đỏ dòng task đó ngay ở bước Change.
- **Không có task `Done` trong cả tuần** — Hoặc không cập nhật board, hoặc task quá lớn chưa xong. Cả hai đều là vấn đề.
- **Board không được mở đầu ngày** — Developer code theo quán tính, không theo ưu tiên. Đây là dấu hiệu nghiêm trọng nhất.

> 📖 **Xem chi tiết:** [Dev Daily — Quản lý công việc cá nhân](../../04-developer/dev-daily/dev-daily-process.md) — quy trình hàng ngày, ma trận ưu tiên, và cách tự kiểm tra board cá nhân.

### Chuẩn bị sprint tiếp theo

Ở buổi họp thứ 5 – thứ 6, sau bước Change, PO mở sẵn tab sprint tuần tới: kiểm tra đã có đủ task chưa, estimate chưa, assign chưa. Việc chưa kịp xong của tuần này cũng chuyển sang đây, với ngày cụ thể.

---

## Daily Report và tin nhắn summary cần có gì?

Khách không ngồi trong buổi Demo. Thứ khách nhận được mỗi ngày là **bản PDF export từ tab sprint**, với Daily Report ở đầu trang và bảng tiến độ bên dưới, cùng một tin nhắn summary ngắn.

Daily Report trả lời 4 câu hỏi:

1. Team đã làm xong những gì?
2. Team đang gặp vấn đề gì?
3. Có những giải pháp nào?
4. Team chọn giải pháp nào, tại sao?

Câu 1 cho khách thấy tiến độ. Ba câu sau cho khách thấy team đang suy nghĩ thế nào. Khách đọc được vấn đề cùng các phương án và lý do chọn, thì khi cần quyết, khách quyết được ngay trong ngày thay vì phải hẹn một buổi họp.

Mỗi dòng ở câu 1 là một việc khách nhìn thấy được trên sản phẩm. *"Worked on frontend"* hay *"Fixed some bugs"* thì khách đọc xong vẫn phải nhắn hỏi PO là frontend nào, bug nào.

Viết vấn đề thật, kể cả khi đó là tin xấu. Mục vấn đề để trống cả tuần vì sợ khách lo, rồi đến ngày bàn giao Milestone trễ 3 ngày và khách nghe tin lần đầu, thì mất niềm tin rất khó lấy lại. Khách chấp nhận được một vấn đề khi biết sớm.

Tin nhắn summary không lặp lại cả bản PDF. Nó là 3–5 dòng để khách đọc trên điện thoại là biết hôm nay có gì quan trọng, và có cần mở PDF ra xem kỹ không. Gửi mỗi file PDF thì khách phải mở ra mới biết có gì, mà đọc trên điện thoại nhiều khi khách không mở. Summary dài 3 đoạn, có lời chào và lời kết như email, thì khách đọc lướt rồi bỏ qua đúng câu quan trọng.

> 📖 Mẫu Daily Report và tin nhắn summary: xem [Internal Daily — Mẫu](./internal-daily-example.md)

---

## Tóm lại

| Câu hỏi | Trả lời |
|---------|---------|
| Buổi họp để làm gì? | Xem sản phẩm hôm qua, sửa board cho đúng, gửi khách báo cáo từ board |
| DEMO show gì? | Sản phẩm đang chạy — không phải code, không phải lời kể |
| CHANGE làm gì? | Cập nhật task mới nhất, bỏ task outdate, điều chỉnh task cho hợp lý, viết Daily Report |
| REPORT gửi gì? | PDF export từ tab sprint + tin nhắn summary 3–5 dòng |
| Khi nào soi dấu hiệu quản lý chưa tốt? | Mỗi buổi Change, 17 dấu hiệu ở cấp team và cá nhân |
| Khi nào chuẩn bị sprint tới? | Buổi họp thứ 5 – thứ 6 |

---

## Liên kết

- [Quy trình Internal Daily](./internal-daily-process.md) — Luồng `DEMO → CHANGE → REPORT`, quy tắc cứng, checklist
- [Internal Daily — Mẫu](./internal-daily-example.md) — Mẫu Daily Report, tin nhắn summary
- [Cẩm nang Board](../po-board-create/board-create-handbook.md) — 8 cột, Board Rule, các tab
- [Tạo Milestone](../po-milestone-create/milestone-create-handbook.md) — Đặt tên Milestone, tách task, estimate khi có việc mới
- [Trăm nghe không bằng một thấy](../../01-cyberk-way/3.3-tram-nghe-khong-bang-mot-thay.md) — Gốc triết lý của Daily Demo & Daily Meeting
