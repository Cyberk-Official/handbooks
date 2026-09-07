---
type: team
tags: [onboarding, project, team]
created: 2026-08-25
updated: 2026-09-03
author: Brian
status: Đang dùng
---

# Onboarding Dự Án — Cẩm nang cho Team

**Người chịu trách nhiệm:** Product Owner  
**Cập nhật lần cuối:** 2026-09-03  
**Trạng thái:** Đang dùng  

Sổ tay này cung cấp các hướng dẫn thực tế, giải thích cách tư duy, phương pháp giao tiếp và cách xử lý trong từng tình huống cụ thể khi tiếp nhận thành viên mới vào dự án tại Cyberk. 

Dưới sự dẫn dắt trực tiếp của **Product Owner**, kết hợp với việc **thành viên mới chủ động sử dụng công cụ AI** để tìm hiểu kiến trúc và mã nguồn, thời gian tiếp cận dự án được rút ngắn tối đa: **trong vòng 24 giờ cài đặt và chạy thành công ứng dụng trên máy cá nhân** và **đến ngày thứ 2 hoàn thành Pull Request đầu tiên**.

---

## Tình huống 1 — Ngày đầu vào dự án, tiếp cận thế nào để nắm bắt nhanh nhất mà không bị ngợp?

Một dự án phần mềm có thể có khối lượng mã nguồn rất lớn và nhiều luồng nghiệp vụ phức tạp. Nếu thành viên mới tự mở từng file code ra đọc từ trên xuống dưới mà không có định hướng, họ sẽ chìm trong chi tiết vụn vặt và mất phương hướng.

**✅ Cách tốt:**  
Product Owner tổ chức buổi định hướng tổng quan (30–45 phút), sau đó thành viên mới chủ động dùng AI để tìm hiểu dự án từ bức tranh tổng thể trước rồi mới đi vào chi tiết:
1. **Lắng nghe Product Owner giới thiệu bối cảnh:** Hiểu rõ bài toán sản phẩm giải quyết cho khách hàng, đối tượng người dùng chính và các luồng sử dụng cơ bản của sản phẩm.
2. **Dùng AI phân tích kiến trúc dự án:** Đưa các file cấu hình (`package.json`, `go.mod`, thư mục repo) vào AI để yêu cầu tóm tắt cấu trúc module, các service chính và luồng dữ liệu giao tiếp.
3. **Cài đặt và trải nghiệm sản phẩm:** Dưới sự hướng dẫn của Product Owner, khởi động ứng dụng trên máy cá nhân và trực tiếp trải nghiệm thử các tính năng từ góc nhìn người dùng.
4. **Ghi chép lại các điểm chưa rõ:** Ghi chú lại những câu hỏi về logic nghiệp vụ hoặc các phần mã nguồn chưa hiểu để trao đổi với Product Owner vào cuối ngày.

Tại sao tốt: Thành viên mới nắm được bức tranh tổng thể chỉ trong vài giờ đầu tiên, hiểu được mục đích của mã nguồn trước khi bắt tay vào code.

**❌ Cách tồi:**  
Mở ngay IDE và đọc từng dòng mã nguồn trong im lặng; hoặc ngược lại, vừa vào đã hỏi những chi tiết vụn vặt khi chưa buồn nghe giới thiệu tổng quan về sản phẩm.

```text
"Anh ơi hàm này ở file helper này làm gì vậy anh?"
(Trong khi chưa nắm được sản phẩm là hệ thống sàn giao dịch hay ứng dụng ví).
```

Tại sao tồi: Tốn thời gian của cả Product Owner lẫn bản thân, thiếu tư duy tổng thể và làm chậm tiến độ làm quen dự án.

---

## Tình huống 2 — Cài đặt môi trường máy cá nhân và giải mã biến môi trường với dotenvx gặp lỗi thì xử lý thế nào?

Tại Cyberk, biến môi trường của dự án được mã hóa bảo mật trực tiếp trong Git bằng [dotenvx](https://github.com/dotenvx/dotenvx). Thành viên mới không cần xin file `.env` thông thường (chưa mã hóa), mà chỉ cần nhận **key giải mã (`DOTENV_PRIVATE_KEY`)** do Product Owner cấp để chạy ứng dụng (`dotenvx run -- ...`).

Nếu gặp lỗi trong quá trình cài đặt hoặc giải mã, áp dụng **Quy tắc 30 phút**: tự tìm cách xử lý trong tối đa 30 phút, nếu không được thì phải hỏi ngay.

> **Quy tắc 30 phút:**  
> Khi gặp lỗi cài đặt hoặc lỗi giải mã env: Thành viên mới kiểm tra lại cú pháp lệnh `dotenvx`, đọc log lỗi, kết hợp dùng AI phân tích nguyên nhân và thử khắc phục trong **tối đa 30 phút**.  
> Nếu sau 30 phút vẫn chưa giải quyết được: **Bắt buộc phải báo cáo cho Product Owner** để được hỗ trợ trực tiếp. Tuyệt đối không ngồi im lặng mò mẫm cả ngày làm trôi qua mốc 24h chạy local.

**✅ Cách tốt:**  
Nhắn tin báo cáo rõ ràng cho Product Owner qua Telegram: nêu rõ bước đang làm, gửi đoạn log lỗi, phân tích từ AI và các cách mình đã tự thử.

```text
"Chào anh [Product Owner], em đang thực hiện chạy ứng dụng với dotenvx theo README nhưng gặp lỗi kết nối PostgreSQL:
- Lỗi cụ thể: [dotenvx] Decryption successful, nhưng app báo ECONNREFUSED 127.0.0.1:5432 khi kết nối DB.
- AI chẩn đoán: có thể container Docker postgres chưa sẵn sàng hoặc sai port mapping.
- Em đã kiểm tra: container postgres đang running, port 5432 đã mở.
Nhờ anh xem giúp em cấu hình database trong env mã hóa này có trỏ tới port nào khác không ạ? (Em gửi kèm ảnh chụp log bên dưới)."
```

Tại sao tốt: Product Owner nắm được ngay nguyên nhân và chỉ điểm cách sửa trong 1 phút, tiết kiệm thời gian cho cả hai và đảm bảo tiến độ cài đặt trong 24 giờ.

**❌ Cách tồi:**  
Nhắn tin cụt lủn, hỏi xin file `.env` thô không mã hóa qua chat, hoặc im lặng chịu trận cả ngày:

```text
"Anh ơi gửi em file .env với, máy em không chạy được."
(Đến tận buổi họp cuối ngày mới thông báo: "Hôm nay em chưa làm được gì vì máy lỗi...")
```

Tại sao tồi: Vi phạm quy định bảo mật khi yêu cầu gửi thông tin mật khẩu/khóa bí mật ở dạng văn bản thô; thể hiện sự thiếu chủ động và làm gián đoạn kế hoạch onboarding của dự án.

---

## Tình huống 3 — Bạn là Product Owner, làm sao để hướng dẫn thành viên mới hiệu quả mà không bị ngốn hết thời gian?

Product Owner có trách nhiệm trực tiếp hướng dẫn thành viên mới, nhưng không có nghĩa là phải ngồi kèm cặp từng thao tác suốt cả ngày làm việc.

**✅ Cách tốt:**  
Thiết lập khuôn khổ rõ ràng và chủ động chuẩn bị tài nguyên từ trước:
1. **Chuẩn bị sẵn quyền truy cập trước Ngày 1:** Phân quyền GitHub repo, thêm vào nhóm Telegram, chuẩn bị sẵn key giải mã `dotenvx` (`DOTENV_PRIVATE_KEY`), và chuẩn bị sẵn một task nhỏ trên GitHub Projects.
2. **Gửi key giải mã an toàn:** Gửi key giải mã `dotenvx` qua kênh tin nhắn riêng cho thành viên mới, nhắc nhở thành viên tuyệt đối không commit file `.env.keys` lên Git.
3. **Tổ chức buổi định hướng ngắn gọn (30 phút):** Giới thiệu bức tranh lớn của sản phẩm, giải thích kiến trúc và chỉ dẫn các tài liệu quan trọng.
4. **Thiết lập 2 mốc trao đổi cố định trong ngày (15 phút mỗi mốc):**
   - **Đầu ngày (09:15):** Thống nhất mục tiêu trong ngày (Day 1: Chạy local; Day 2: Hoàn thành First PR).
   - **Cuối ngày (17:00):** Nghiệm thu kết quả chạy local hoặc review PR, tháo gỡ khó khăn nếu có.
5. **Khuyến khích dùng AI tra cứu trước khi hỏi:** Hướng dẫn thành viên chủ động hỏi AI về cú pháp code, cách dùng thư viện hoặc nhờ AI giải thích log lỗi trước khi hỏi Product Owner.

Tại sao tốt: Thành viên mới được định hướng rõ ràng, nhận được sự hỗ trợ kịp thời nhưng vẫn rèn luyện tính độc lập. Product Owner vẫn bảo vệ được thời gian tập trung xử lý các công việc quản lý và kỹ thuật quan trọng của mình.

**❌ Cách tồi:**  
- Bỏ mặc thành viên mới tự xoay xở với repo mà không có buổi giới thiệu, quên cấp key `dotenvx` khiến thành viên không thể chạy app.
- Hoặc ngược lại, ngồi kèm cặp trực tiếp từng câu lệnh terminal, làm hộ thành viên mới mỗi khi gặp lỗi nhỏ.

Tại sao tồi: Bỏ mặc khiến nhân sự mới mất niềm tin và làm chậm tiến độ dự án; kèm cặp quá mức triệt tiêu khả năng tư duy độc lập của thành viên và khiến Product Owner trễ deadline cá nhân.

---

## Tình huống 4 — Thành viên mới tiếp nhận bàn giao từ người rời dự án (Project Leave) cần làm gì để đảm bảo an toàn?

Khi tiếp nhận dự án để thay thế một nhân sự chuyển đi, mục tiêu là tiếp thu toàn bộ kiến thức nghiệp vụ và quyền hạn mà không để sót lỗ hổng kỹ thuật.

**✅ Cách tốt:**  
Dưới sự chủ trì của Product Owner, thực hiện đối soát và kiểm chứng thực tế:
1. **Yêu cầu chạy thử trực tiếp (Demo):** Đề nghị người bàn giao chia sẻ màn hình và chạy thử các chức năng họ phụ trách trên môi trường staging hoặc máy cá nhân.
2. **Tự tay chạy thử mã nguồn:** Thành viên mới tự clone code về máy mình, dùng key giải mã `dotenvx` chạy thử trực tiếp dưới sự chứng kiến của người bàn giao và Product Owner.
3. **Kiểm tra quyền truy cập và biến môi trường:** Xác nhận key `dotenvx` giải mã được đầy đủ các môi trường cần thiết; đảm bảo toàn bộ quyền truy cập hệ thống của người cũ đã được chuyển giao cho Product Owner hoặc thu hồi.
4. **Hỏi rõ các điểm lưu ý khi vận hành:** Làm rõ các phần code phức tạp, lỗi hay gặp hoặc những điểm cần chú ý khi chạy thực tế.

Tại sao tốt: Đảm bảo chuyển giao thông suốt, phát hiện sớm các khúc mắc trước khi người cũ hoàn tất thủ tục rời dự án.

**❌ Cách tồi:**  
Chỉ nghe giải thích qua loa bằng miệng, gật đầu đồng ý mà chưa từng tự tay chạy thử mã nguồn hoặc chưa kiểm tra khả năng giải mã env trên máy mình.

Tại sao tồi: Khi người cũ rời đi, mọi rủi ro kỹ thuật và lỗi phát sinh sẽ đè nặng lên vai thành viên mới mà không còn ai hỗ trợ giải thích.

---

## Tình huống 5 — Thực hiện và hoàn thành First PR trong Ngày thứ 2 như thế nào để đạt chuẩn?

Task đầu tiên trong Ngày thứ 2 là cơ hội để thành viên mới làm quen với toàn bộ chu trình phát triển mã nguồn của Cyberk: từ quản lý board, tạo branch, viết code, kiểm thử đến mở Pull Request.

**✅ Cách tốt:**  
Tuân thủ chuẩn mực kỹ thuật và quy trình của team:
1. **Tiếp nhận task trên GitHub Projects:** Chuyển trạng thái task sang `In Progress`.
2. **Đặt tên nhánh đúng quy ước:** Ví dụ: `fix/CYB-101-update-auth-flow` hoặc `feature/CYB-105-user-list-api`.
3. **Dùng AI hỗ trợ:** Nhờ AI kiểm tra các trường hợp lỗi có thể xảy ra (ngoại lệ), viết test tự động (unit test) và gợi ý viết code gọn hơn.
4. **Tự kiểm tra lại code trước khi commit:** Xem lại những chỗ mình vừa thay đổi, xóa bỏ code thừa, câu lệnh in log thử nghiệm và các biến không dùng.
5. **Mở Pull Request hoàn chỉnh trước cuối Day 2:**
   - Đặt tiêu đề rõ ràng kèm mã task: `[CYB-101] Fix auth token refresh issue`.
   - Mô tả ngắn gọn: Nội dung thay đổi là gì? Đã kiểm thử như thế nào?
   - Đính kèm bằng chứng kiểm thử (ảnh chụp hoặc video/GIF minh họa).
   - Tag Product Owner vào review và chủ động tiếp thu, chỉnh sửa feedback để merge code.

Tại sao tốt: Khẳng định tính kỷ luật và sự chuyên nghiệp ngay từ những ngày đầu. Product Owner dễ dàng review và phê duyệt nhanh chóng.

**❌ Cách tồi:**  
Commit một khối code lớn với thông điệp sơ sài (`update`, `fix bug`), mở PR trống trơn không có mô tả, chưa tự test trên local và hối thúc Product Owner merge gấp.

Tại sao tồi: Làm tăng nguy cơ lỗi cho hệ thống, thể hiện tác phong thiếu trách nhiệm và vi phạm quy chuẩn chất lượng của Cyberk.

---

## Tình huống 6 — Phát hiện tài liệu hướng dẫn (README.md) của dự án bị sai hoặc thiếu bước thì làm gì?

Codebase thay đổi liên tục nhưng tài liệu hướng dẫn thường bị chậm cập nhật. Khi cài đặt môi trường trong Day 1, thành viên mới là người có điều kiện tốt nhất để phát hiện các điểm sai sót này.

**✅ Cách tốt:**  
**Thấy chỗ nào sai hoặc thiếu thì tiện tay sửa luôn và mở PR cập nhật:**
- Trong lúc cài đặt, ghi chú lại những câu lệnh hoặc bước cấu hình còn thiếu trong tài liệu.
- Sau khi ứng dụng chạy thành công trên máy mình, mở ngay một Pull Request nhỏ để cập nhật lại file `README.md` (ví dụ: `docs: update setup instructions in README`).
- Nêu rõ trong PR: *"Bổ sung lệnh cài đặt và hướng dẫn nạp key dotenvx còn thiếu trong README"* để người vào sau cài đặt dễ dàng hơn.

Tại sao tốt: Giúp các nhân sự gia nhập sau này cài đặt suôn sẻ, biến trải nghiệm thực tế của bản thân thành giá trị chung cho toàn đội ngũ.

**❌ Cách tồi:**  
Tự sửa lỗi trên máy mình rồi giữ kín, hoặc lên nhóm chat Telegram phàn nàn chê bai tài liệu mà không có hành động cải tiến cụ thể.

Tại sao tồi: Tạo tâm lý tiêu cực cho tập thể và bỏ lỡ cơ hội đóng góp tích cực cho chất lượng dự án.

---

## Tóm lại

| Tiêu chí | Chuyên nghiệp (Nên làm) | Không chuyên nghiệp (Tránh làm) |
|---|---|---|
| **Vai trò hướng dẫn** | Product Owner trực tiếp định hướng, hướng dẫn cài đặt và đồng hành trong 3 ngày đầu. | Để thành viên mới tự xoay xở một mình hoặc bỏ rơi không có hướng dẫn. |
| **Bảo mật biến môi trường** | Sử dụng `dotenvx`, Product Owner cấp key giải mã an toàn; cấm commit `.env.keys` lên Git. | Xin gửi file `.env` chưa mã hóa qua chat, hoặc vô tình commit private key lên repo. |
| **Ứng dụng công cụ AI** | Thành viên mới chủ động dùng AI tìm hiểu kiến trúc, giải mã log lỗi và sinh test để tăng tốc. | Không tận dụng công cụ hỗ trợ, hoặc ỷ lại copy-paste code từ AI mà không hiểu. |
| **Mục tiêu thời gian** | Trong 24h chạy thành công local; Ngày thứ 2 merge First PR; Ngày thứ 3 vào Sprint chính thức. | Kéo dài thời gian làm quen cả tuần, không có mục tiêu cụ thể theo từng ngày. |
| **Xử lý sự cố kỹ thuật** | Tự tìm hiểu cùng AI tối đa 30 phút; nếu kẹt, báo ngay Product Owner kèm log lỗi và cách đã thử. | Ngồi im lặng mò mẫm cả ngày hoặc vừa gặp lỗi nhỏ đã kêu ca không chịu suy nghĩ. |
| **Bàn giao từ người rời đi** | Product Owner chủ trì, kiểm tra giải mã `dotenvx`, xem demo trực tiếp và tự tay chạy lại code trước khi xác nhận. | Chỉ nghe giải thích qua loa, gật đầu thụ động khi bản thân chưa chạy được code. |
| **Thực hiện First PR** | Nhận task trên Board, branch chuẩn, code sạch có test, PR có ảnh bằng chứng kiểm thử. | Commit cẩu thả, mở PR không mô tả, chưa tự test kỹ lưỡng trên local. |
| **Tài liệu dự án bị thiếu/sai** | Tiện tay mở ngay PR cập nhật lại `README.md` sau khi cài đặt thành công trên máy mình. | Phàn nàn chê bai trên nhóm chat hoặc sửa được cho máy mình rồi thôi. |

---

## Liên kết

- [Quy trình Onboarding Dự Án (Process)](dev-project-onboarding-process.md)
- [Cẩm nang Giao tiếp trong Team (Horenso)](../../03-team/team-communicate/team-communicate-handbook.md)
- [Quy trình Quản lý Công việc Hàng ngày (Dev Daily)](../dev-daily/dev-daily-process.md)
- [Cẩm nang Quản lý Board Cá nhân & Dự Án](../../05-product-owner/board-handbook/board-handbook.md)
- [Quy trình Rời Dự Án (Project Leave)](../../05-product-owner/po-project-leave/po-project-leave-process.md)
