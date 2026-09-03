---
type: team
tags: [onboarding, project, team]
created: 2026-08-25
updated: 2026-09-03
author: Brian
status: Đang dùng
---

# Onboarding Dự Án — Cẩm nang cho Team

**Người chịu trách nhiệm:** Product Lead  
**Cập nhật lần cuối:** 2026-09-03  
**Trạng thái:** Đang dùng  

Sổ tay này cung cấp các hướng dẫn thực tế, giải thích cách tư duy, phương pháp giao tiếp và cách xử lý trong từng tình huống cụ thể khi tiếp nhận thành viên mới vào dự án tại Cyberk. 

Dưới sự dẫn dắt trực tiếp của **Product Lead**, kết hợp với việc **thành viên mới chủ động sử dụng công cụ AI** để tìm hiểu kiến trúc và mã nguồn, thời gian tiếp cận dự án được rút ngắn tối đa: **trong vòng 24 giờ cài đặt và chạy thành công ứng dụng trên máy cá nhân** và **đến ngày thứ 2 hoàn thành Pull Request đầu tiên**.

---

## Tình huống 1 — Ngày đầu vào dự án, tiếp cận thế nào để nắm bắt nhanh nhất mà không bị ngợp?

Một dự án phần mềm có thể có khối lượng mã nguồn rất lớn và nhiều luồng nghiệp vụ phức tạp. Nếu thành viên mới tự mở từng file code ra đọc từ trên xuống dưới mà không có định hướng, họ sẽ chìm trong chi tiết vụn vặt và mất phương hướng.

**✅ Cách tốt:**  
Product Lead tổ chức buổi định hướng tổng quan (30–45 phút), sau đó thành viên mới chủ động kết hợp công cụ AI để tìm hiểu dự án theo chiều từ trên xuống (Top-down):
1. **Lắng nghe Product Lead giới thiệu bối cảnh:** Hiểu rõ bài toán sản phẩm giải quyết cho khách hàng, đối tượng người dùng chính và luồng nghiệp vụ cốt lõi (Happy Path).
2. **Dùng AI phân tích kiến trúc dự án:** Đưa các file cấu hình (`package.json`, `go.mod`, thư mục repo) vào AI để yêu cầu tóm tắt cấu trúc module, các service chính và luồng dữ liệu giao tiếp.
3. **Cài đặt và trải nghiệm sản phẩm:** Dưới sự hướng dẫn của Product Lead, khởi động ứng dụng trên máy cá nhân và trực tiếp trải nghiệm thử các tính năng từ góc nhìn người dùng.
4. **Ghi chép có hệ thống:** Ghi chú lại các câu hỏi về logic nghiệp vụ sâu hoặc các góc khuất kiến trúc để trao đổi với Product Lead vào cuối ngày.

Tại sao tốt: Thành viên mới nắm được bức tranh tổng thể chỉ trong vài giờ đầu tiên, hiểu được mục đích của mã nguồn trước khi bắt tay vào code.

**❌ Cách tồi:**  
Mở ngay IDE và đọc từng dòng mã nguồn trong im lặng; hoặc ngược lại, vừa vào đã hỏi những chi tiết vụn vặt khi chưa buồn nghe giới thiệu tổng quan về sản phẩm.

```text
"Anh ơi hàm này ở file helper này làm gì vậy anh?"
(Trong khi chưa nắm được sản phẩm là hệ thống sàn giao dịch hay ứng dụng ví).
```

Tại sao tồi: Tốn thời gian của cả Product Lead lẫn bản thân, thiếu tư duy tổng thể và làm chậm tiến độ làm quen dự án.

---

## Tình huống 2 — Cài đặt môi trường máy cá nhân và giải mã biến môi trường với dotenvx gặp lỗi thì xử lý thế nào?

Tại Cyberk, biến môi trường của dự án được mã hóa bảo mật trực tiếp trong Git bằng [dotenvx](https://github.com/dotenvx/dotenvx). Thành viên mới không cần xin file `.env` plain text thô, mà chỉ cần nhận **key giải mã (`DOTENV_PRIVATE_KEY`)** do Product Lead cấp để khởi chạy ứng dụng (`dotenvx run -- ...`).

Nếu gặp lỗi trong quá trình cài đặt hoặc giải mã, nguyên tắc xử lý được định nghĩa bằng **Quy tắc 30 phút Horenso**.

> **Quy tắc 30 phút:**  
> Khi gặp lỗi cài đặt hoặc lỗi giải mã env: Thành viên mới kiểm tra lại cú pháp lệnh `dotenvx`, đọc log lỗi, kết hợp dùng AI phân tích nguyên nhân và thử khắc phục trong **tối đa 30 phút**.  
> Nếu sau 30 phút vẫn chưa giải quyết được: **Bắt buộc phải báo cáo cho Product Lead** để được hỗ trợ trực tiếp. Tuyệt đối không ngồi im lặng mò mẫm cả ngày làm trôi qua mốc 24h chạy local.

**✅ Cách tốt:**  
Báo cáo cho Product Lead qua Telegram theo đúng cấu trúc Horenso: nêu rõ bước đang làm, log lỗi chi tiết, chẩn đoán từ AI và các cách bản thân đã thử.

```text
"Chào anh [Product Lead], em đang thực hiện chạy ứng dụng với dotenvx theo README nhưng gặp lỗi kết nối PostgreSQL:
- Lỗi cụ thể: [dotenvx] Decryption successful, nhưng app báo ECONNREFUSED 127.0.0.1:5432 khi kết nối DB.
- AI chẩn đoán: có thể container Docker postgres chưa sẵn sàng hoặc sai port mapping.
- Em đã kiểm tra: container postgres đang running, port 5432 đã mở.
Nhờ anh xem giúp em cấu hình database trong env mã hóa này có trỏ tới port nào khác không ạ? (Em gửi kèm ảnh chụp log bên dưới)."
```

Tại sao tốt: Product Lead nắm được ngay nguyên nhân và chỉ điểm cách sửa trong 1 phút, tiết kiệm thời gian cho cả hai và đảm bảo tiến độ cài đặt trong 24 giờ.

**❌ Cách tồi:**  
Nhắn tin cụt lủn, hỏi xin file `.env` thô không mã hóa qua chat, hoặc im lặng chịu trận cả ngày:

```text
"Anh ơi gửi em file .env với, máy em không chạy được."
(Đến tận buổi họp cuối ngày mới thông báo: "Hôm nay em chưa làm được gì vì máy lỗi...")
```

Tại sao tồi: Vi phạm quy định an toàn bảo mật khi yêu cầu gửi secrets dạng text trần; thể hiện sự thiếu chủ động và làm gián đoạn kế hoạch onboarding của dự án.

---

## Tình huống 3 — Bạn là Product Lead, làm sao để hướng dẫn thành viên mới hiệu quả mà không bị ngốn hết thời gian?

Product Lead có trách nhiệm trực tiếp hướng dẫn thành viên mới, nhưng không có nghĩa là phải ngồi kèm cặp từng thao tác suốt cả ngày làm việc.

**✅ Cách tốt:**  
Thiết lập khuôn khổ rõ ràng và chủ động chuẩn bị tài nguyên từ trước:
1. **Chuẩn bị sẵn quyền truy cập trước Ngày 1:** Phân quyền GitHub repo, thêm vào nhóm Telegram, chuẩn bị sẵn key giải mã `dotenvx` (`DOTENV_PRIVATE_KEY`), và chuẩn bị sẵn một task nhỏ trên GitHub Projects.
2. **Gửi key giải mã an toàn:** Gửi key giải mã `dotenvx` qua kênh tin nhắn riêng cho thành viên mới, nhắc nhở thành viên tuyệt đối không commit file `.env.keys` lên Git.
3. **Tổ chức buổi định hướng ngắn gọn (30 phút):** Giới thiệu bức tranh lớn của sản phẩm, giải thích kiến trúc và chỉ dẫn các tài liệu quan trọng.
4. **Thiết lập 2 mốc trao đổi cố định trong ngày (15 phút mỗi mốc):**
   - **Đầu ngày (09:15):** Thống nhất mục tiêu trong ngày (Day 1: Chạy local; Day 2: Hoàn thành First PR).
   - **Cuối ngày (17:00):** Nghiệm thu kết quả chạy local hoặc review PR, tháo gỡ khó khăn nếu có.
5. **Định hướng thành viên dùng AI làm trợ lý cấp 1:** Khuyến khích thành viên dùng AI để giải đáp các câu hỏi về cú pháp, thư viện hoặc đọc log lỗi trước khi hỏi Product Lead.

Tại sao tốt: Thành viên mới được định hướng rõ ràng, nhận được sự hỗ trợ kịp thời nhưng vẫn rèn luyện tính độc lập. Product Lead vẫn bảo vệ được thời gian tập trung xử lý các công việc quản lý và kỹ thuật quan trọng của mình.

**❌ Cách tồi:**  
- Bỏ mặc thành viên mới tự xoay xở với repo mà không có buổi giới thiệu, quên cấp key `dotenvx` khiến thành viên không thể chạy app.
- Hoặc ngược lại, ngồi kèm cặp trực tiếp từng câu lệnh terminal, làm hộ thành viên mới mỗi khi gặp lỗi nhỏ.

Tại sao tồi: Bỏ mặc khiến nhân sự mới mất niềm tin và làm chậm tiến độ dự án; kèm cặp quá mức triệt tiêu khả năng tư duy độc lập của thành viên và khiến Product Lead trễ deadline cá nhân.

---

## Tình huống 4 — Thành viên mới tiếp nhận bàn giao từ người rời dự án (Project Leave) cần làm gì để đảm bảo an toàn?

Khi tiếp nhận dự án để thay thế một nhân sự chuyển đi, mục tiêu là tiếp thu toàn bộ kiến thức nghiệp vụ và quyền hạn mà không để sót lỗ hổng kỹ thuật.

**✅ Cách tốt:**  
Dưới sự chủ trì của Product Lead, thực hiện đối soát và kiểm chứng thực tế:
1. **Yêu cầu Live Demo:** Đề nghị người rời đi chia sẻ màn hình và chạy thử toàn bộ luồng nghiệp vụ họ đang phụ trách trên môi trường staging/local.
2. **Tự tay chạy lại mã nguồn:** Thành viên mới tự clone code về máy cá nhân, dùng key giải mã `dotenvx` chạy thử nghiệm thu dưới sự chứng kiến của người bàn giao và Product Lead.
3. **Kiểm tra quyền truy cập và secrets:** Xác nhận key `dotenvx` giải mã đầy đủ mọi môi trường cần thiết; đảm bảo toàn bộ quyền truy cập cloud/server cá nhân của người cũ đã được chuyển giao cho Product Lead hoặc thu hồi.
4. **Hỏi rõ các điểm lưu ý kỹ thuật:** Làm rõ các logic phức tạp, điểm yếu của hệ thống hoặc những vấn đề thường phát sinh khi vận hành.

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
3. **Kết hợp công cụ AI:** Dùng AI hỗ trợ rà soát edge cases, viết unit test tự động và tối ưu hóa đoạn code vừa viết.
4. **Tự kiểm tra (Self-review):** Tự xem lại toàn bộ diff trước khi commit, loại bỏ code thừa, log debug hoặc biến không sử dụng.
5. **Mở Pull Request hoàn chỉnh trước cuối Day 2:**
   - Đặt tiêu đề rõ ràng kèm mã task: `[CYB-101] Fix auth token refresh issue`.
   - Mô tả ngắn gọn: Nội dung thay đổi là gì? Đã kiểm thử như thế nào?
   - Đính kèm bằng chứng kiểm thử (ảnh chụp hoặc video/GIF minh họa).
   - Tag Product Lead vào review và chủ động tiếp thu, chỉnh sửa feedback để merge code.

Tại sao tốt: Khẳng định tính kỷ luật và sự chuyên nghiệp ngay từ những ngày đầu. Product Lead dễ dàng review và phê duyệt nhanh chóng.

**❌ Cách tồi:**  
Commit một khối code lớn với thông điệp sơ sài (`update`, `fix bug`), mở PR trống trơn không có mô tả, chưa tự test trên local và hối thúc Product Lead merge gấp.

Tại sao tồi: Làm tăng nguy cơ lỗi cho hệ thống, thể hiện tác phong thiếu trách nhiệm và vi phạm quy chuẩn chất lượng của Cyberk.

---

## Tình huống 6 — Phát hiện tài liệu hướng dẫn (README.md) của dự án bị sai hoặc thiếu bước thì làm gì?

Codebase thay đổi liên tục nhưng tài liệu hướng dẫn thường bị chậm cập nhật. Khi cài đặt môi trường trong Day 1, thành viên mới là người có điều kiện tốt nhất để phát hiện các điểm sai sót này.

**✅ Cách tốt:**  
Áp dụng **Nguyên tắc Hướng đạo sinh (Boy Scout Rule):** Luôn để bãi trại sạch sẽ hơn khi bạn đến.
- Trong quá trình cài đặt dưới sự hướng dẫn của Product Lead, ghi chép lại chính xác các câu lệnh hoặc biến môi trường cần bổ sung.
- Sau khi ứng dụng chạy thành công, mở ngay một Pull Request nhỏ: `docs: update setup instructions in README`.
- Nêu rõ trong PR: *"Cập nhật bổ sung lệnh cài đặt và hướng dẫn nạp key dotenvx trong quá trình setup máy mới"*.

Tại sao tốt: Giúp các nhân sự gia nhập sau này cài đặt suôn sẻ, biến trải nghiệm thực tế của bản thân thành giá trị chung cho toàn đội ngũ.

**❌ Cách tồi:**  
Tự sửa lỗi trên máy mình rồi giữ kín, hoặc lên nhóm chat Telegram phàn nàn chê bai tài liệu mà không có hành động cải tiến cụ thể.

Tại sao tồi: Tạo tâm lý tiêu cực cho tập thể và bỏ lỡ cơ hội đóng góp tích cực cho chất lượng dự án.

---

## Tóm lại

| Tiêu chí | Chuyên nghiệp (Nên làm) | Không chuyên nghiệp (Tránh làm) |
|---|---|---|
| **Vai trò hướng dẫn** | Product Lead trực tiếp định hướng, hướng dẫn cài đặt và đồng hành trong 3 ngày đầu. | Để thành viên mới tự xoay xở một mình hoặc bỏ rơi không có hướng dẫn. |
| **Bảo mật biến môi trường** | Sử dụng `dotenvx`, Product Lead cấp key giải mã an toàn; cấm commit `.env.keys` lên Git. | Xin gửi file `.env` plain text qua chat, hoặc vô tình commit private key lên repo. |
| **Ứng dụng công cụ AI** | Thành viên mới chủ động dùng AI tìm hiểu kiến trúc, giải mã log lỗi và sinh test để tăng tốc. | Không tận dụng công cụ hỗ trợ, hoặc ỷ lại copy-paste code từ AI mà không hiểu. |
| **Mục tiêu thời gian** | Trong 24h chạy thành công local; Ngày thứ 2 merge First PR; Ngày thứ 3 vào Sprint chính thức. | Kéo dài thời gian làm quen cả tuần, không có mục tiêu cụ thể theo từng ngày. |
| **Xử lý sự cố kỹ thuật** | Tự tìm hiểu cùng AI tối đa 30 phút; nếu kẹt, báo cáo ngay Product Lead theo chuẩn Horenso. | Ngồi im lặng mò mẫm cả ngày hoặc vừa gặp lỗi nhỏ đã kêu ca không chịu suy nghĩ. |
| **Bàn giao từ người rời đi** | Product Lead chủ trì, kiểm tra giải mã `dotenvx`, Live Demo và tự tay chạy lại code trước khi xác nhận. | Chỉ nghe giải thích qua loa, gật đầu thụ động khi bản thân chưa chạy được code. |
| **Thực hiện First PR** | Nhận task trên Board, branch chuẩn, code sạch có test, PR có ảnh bằng chứng kiểm thử. | Commit cẩu thả, mở PR không mô tả, chưa tự test kỹ lưỡng trên local. |
| **Tài liệu dự án bị thiếu/sai** | Mở ngay PR cập nhật lại `README.md` sau khi cài đặt thành công trên máy mình. | Phàn nàn chê bai trên nhóm chat hoặc sửa được cho máy mình rồi thôi. |

---

## Liên kết

- [Quy trình Onboarding Dự Án (Process)](project-onboarding-process.md)
- [Cẩm nang Giao tiếp trong Team (Horenso)](../team-communicate/team-communicate-handbook.md)
- [Quy trình Quản lý Công việc Hàng ngày (Dev Daily)](../dev-daily/dev-daily-process.md)
- [Cẩm nang Quản lý Board Cá nhân & Dự Án](../../04-delivery/board-handbook/board-handbook.md)
- [Quy trình Rời Dự Án (Project Leave)](../project-leave/project-leave-process.md)
