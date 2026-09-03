---
type: team
tags: [offboarding, project, team, lead]
created: 2026-09-03
updated: 2026-09-03
author: Brian
status: Đang dùng
---

# Rời Dự Án — Cẩm nang cho Product Lead

**Người chịu trách nhiệm:** Product Lead  
**Cập nhật lần cuối:** 2026-09-03  
**Trạng thái:** Đang dùng  

Sổ tay này cung cấp hướng dẫn thực chiến, giải thích cách tư duy quản trị rủi ro, phương pháp điều phối chuyển giao và cách xử lý từng tình huống cụ thể dành riêng cho **Product Lead** khi có thành viên rời khỏi dự án (chủ động xin nghỉ, điều chuyển nội bộ, hoặc nghỉ đột xuất/bất khả kháng) tại Cyberk.

Mục tiêu tối thượng của Product Lead là: **Đảm bảo tính liên tục của dự án (Business Continuity), tri thức không bị gián đoạn (Zero Knowledge Loss), và bảo mật hệ thống an toàn tuyệt đối (Zero Security Risk).**

---

## Tình huống 1 — Tiếp nhận thông báo xin rời dự án: Product Lead cần phản hồi và đánh giá rủi ro ban đầu thế nào?

Khi nhận được tin nhắn hoặc email xin rời dự án từ một thành viên, phản ứng ban đầu của Product Lead sẽ quyết định toàn bộ thái độ hợp tác và sự suôn sẻ của cả quá trình chuyển giao sau đó.

**✅ Cách tốt:**  
1. **Phản hồi chuyên nghiệp và bình tĩnh:** Ghi nhận thông tin, gửi lời cảm ơn đóng góp ban đầu và hẹn một buổi gặp 1-1 nhanh (15–30 phút) trong vòng 24 giờ.
2. **Thực hiện Đánh giá Tác động & Rủi ro (Impact Assessment):** Trước buổi gặp 1-1, Product Lead tự rà soát:
   - Thành viên đang nắm giữ những module cốt lõi nào?
   - Có điểm nghẽn đơn lẻ (Single Point of Failure - SPOF) nào mà chỉ thành viên đó biết cách vận hành không?
   - Các mốc Milestone/Sprint sắp tới bị ảnh hưởng ra sao?
   - Thành viên đang nắm giữ quyền Admin/Owner các tài nguyên nào (Cloud, GitHub, Domain, SaaS)?
3. **Thấu hiểu và thống nhất mục tiêu trong buổi 1-1:** Lắng nghe nguyện vọng, thống nhất ngày làm việc cuối cùng trên dự án (Last Working Day) và xác lập cam kết đóng gói bàn giao trọn vẹn.

```text
"Chào [Tên Member], anh đã nhận được tin nhắn của em. Cảm ơn em vì những đóng góp tích cực cho dự án trong thời gian qua.
Anh em mình set một buổi trao đổi 1-1 ngắn lúc 14:00 chiều nay để cùng rà soát lại các đầu việc dở dang, thống nhất ngày bàn giao (Cutoff Date) và lên kế hoạch chuyển giao cho người tiếp quản nhé."
```

Tại sao tốt: Thể hiện sự tôn trọng, giữ tinh thần làm việc tích cực cho thành viên và giúp Product Lead ngay lập tức nắm thế chủ động trong việc quản trị rủi ro nhân sự.

**❌ Cách tồi:**  
- Tỏ thái độ khó chịu, trách móc, tra khảo hoặc im lặng không phản hồi nhiều ngày.
- Hoặc ngược lại, đồng ý ngay lập tức mà không rà soát lại khối lượng công việc và quyền truy cập thành viên đang nắm giữ.

```text
"Sao lại nghỉ lúc này? Dự án đang gấp thế này em nghỉ là vỡ hết tiến độ đấy!"
(Hoặc: "Ok em, chừng nào nghỉ thì bảo anh.")
```

Tại sao tồi: Gây ức chế tâm lý, khiến thành viên có tâm lý buông xuôi, bàn giao qua loa hoặc thậm chí bỏ ngang công việc gây khủng hoảng cho team.

---

## Tình huống 2 — Thiết lập Kế hoạch Chuyển giao (Handover Plan) & Điểm cắt công việc (Cutoff Date)

Một sai lầm phổ biến là để thành viên sắp rời đi tiếp tục ôm đồm tính năng mới cho đến tận ngày cuối cùng, dẫn đến việc không còn thời gian viết tài liệu và kiểm thử chuyển giao.

**✅ Cách tốt:**  
Product Lead thiết lập **Điểm cắt công việc (Cutoff Date - thường là T-7 ngày làm việc)** và chia giai đoạn chuyển giao rõ ràng:
1. **Từ T-14 đến T-7 ngày (Giai đoạn Dứt điểm):** Dừng nhận toàn bộ tính năng lớn mới. Tập trung dứt điểm các task đang làm dở, fix các bug quan trọng còn tồn đọng.
2. **Từ T-6 đến T-3 ngày (Giai đoạn Đóng gói & Soạn tài liệu):** Member dành 100% thời gian để viết tài liệu bàn giao chuẩn (`Handover Doc`), dọn dẹp Git branch, chuẩn bị video demo. Product Lead review bản thảo tài liệu.
3. **Từ T-2 đến T-1 ngày (Giai đoạn Họp bàn giao & Live Verification):** Tổ chức họp bàn giao chính thức với Receiver, Receiver tự tay chạy lại code dưới sự chứng kiến của PL.
4. **Ngày cuối cùng (Last Day - Giai đoạn Thu hồi & Sign-off):** Thu hồi toàn bộ quyền truy cập, đối soát secrets, nghiệm thu hoàn tất và ký duyệt Sign-off.

```markdown
# Kế hoạch Chuyển giao Dự án X — [Tên Member]
- **Người bàn giao:** [Tên Member]
- **Người tiếp nhận (Receiver):** [Tên Receiver]
- **Giám sát & Phê duyệt:** Product Lead
- **Mốc Cutoff dừng nhận task mới:** [DD/MM]
- **Hạn chót hoàn thành Handover Doc:** [DD/MM]
- **Thời gian họp Handover Session:** [Giờ, DD/MM]
- **Ngày thu hồi quyền & Sign-off:** [DD/MM]
```

Tại sao tốt: Phân bổ thời gian khoa học, đảm bảo công việc không bị dồn ứ vào ngày cuối và tài liệu bàn giao đạt chất lượng thực tế.

**❌ Cách tồi:**  
Giao thêm task mới sát ngày nghỉ: *"Còn 3 ngày nữa em ráng code nốt màn hình này đi rồi hôm cuối gửi tài liệu qua chat sau."*

Tại sao tồi: Thành viên không kịp viết tài liệu, code vội vàng sinh nhiều lỗi tiềm ẩn, và khi họ rời đi không ai trong team hiểu logic để bảo trì tiếp.

---

## Tình huống 3 — Chỉ định và định hướng nhiệm vụ cho Người nhận bàn giao (Receiver)

Nếu Product Lead chỉ định Receiver một cách hời hợt theo kiểu "ngồi nghe cho biết", buổi bàn giao sẽ trở thành hình thức và người ở lại vẫn không thể tiếp quản được hệ thống.

**✅ Cách tốt:**  
1. **Tiêu chí chọn Receiver:** Chọn nhân sự có chuyên môn tương đồng, hoặc đang phụ trách module liên quan. Nếu khối lượng công việc quá lớn, PL có thể tách làm 2 Receiver (ví dụ: 1 người nhận mảng Frontend, 1 người nhận Backend/Infra).
2. **Định hướng rõ trách nhiệm cho Receiver:**
   - Đọc trước mã nguồn và tài liệu bàn giao trước buổi họp.
   - Chuẩn bị danh sách các câu hỏi về những điểm chưa rõ.
   - **Bắt buộc tự tay chạy lại mã nguồn trên máy mình** dưới sự hướng dẫn trực tiếp của người rời đi.
3. **Cam kết đồng hành từ PL:** Nhắc nhở Receiver rằng PL luôn đồng hành hỗ trợ, tránh tạo áp lực tâm lý quá tải cho người nhận.

```text
"Chào [Tên Receiver], từ tuần sau em sẽ tiếp nhận module Payment từ bạn [Tên Member]. 
Anh đã gửi link Handover Doc do bạn soạn thảo. Em dành 2 tiếng chiều nay đọc trước và ghi lại các chỗ chưa rõ nhé.
Sáng mai anh em mình sẽ có buổi họp bàn giao 3 bên, em sẽ trực tiếp clone code về máy chạy thử dưới sự hỗ trợ của bạn ấy."
```

Tại sao tốt: Receiver có sự chuẩn bị chủ động, tiếp thu tri thức có chiều sâu và sẵn sàng làm chủ mã nguồn ngay sau buổi bàn giao.

**❌ Cách tồi:**  
Chỉ định Receiver sát giờ họp mà không thông báo trước, hoặc để Receiver ngồi nghe thụ động suốt buổi họp mà không yêu cầu thao tác thực tế trên máy tính.

Tại sao tồi: Receiver nghe xong nhưng không nhớ, không chạy được code trên máy mình và để lại lỗ hổng tri thức nghiêm trọng cho dự án.

---

## Tình huống 4 — Quản trị mã nguồn & Board: Dọn dẹp Git Branch và dứt điểm Pull Request

Mã nguồn dở dang nằm trên máy cá nhân của người rời đi là một trong những rủi ro kỹ thuật lớn nhất khi nhân sự nghỉ việc.

**✅ Cách tốt:**  
Product Lead trực tiếp rà soát và kiểm soát theo 3 bước:
1. **Rà soát GitHub Projects Board:**
   - Lọc toàn bộ issue gán cho member (`assignee:@member`).
   - Task đã hoàn thành: yêu cầu member hoàn thiện kiểm thử và mở PR.
   - Task đang làm dở không kịp xong trước Cutoff: yêu cầu member viết ghi chú chi tiết vào issue (đã làm đến đâu, còn vướng chỗ nào) và reassign sang cho Receiver hoặc Product Lead.
2. **Kiểm tra và dọn dẹp Git Branches:**
   - **Quy tắc bắt buộc:** Yêu cầu member push 100% các commit và branch cá nhân lên remote repo trên GitHub. Tuyệt đối không để code dở dang trên máy local cá nhân.
   - Đối với các PR đang mở: Product Lead review và merge các PR đạt chuẩn; đối với PR dở dang, chuyển thành **Draft PR** và giao lại cho Receiver theo dõi tiếp.
   - Xóa các branch tạm (stale branches) đã cũ hoặc không còn sử dụng.

Tại sao tốt: Không bị thất thoát bất kỳ dòng code nào, giữ cho Git repository và Board dự án luôn sạch sẽ, rõ ràng.

**❌ Cách tồi:**  
Không kiểm tra Git remote trước khi member rời đi, chỉ tin vào lời hứa *"code em để trên máy, có gì em gửi sau"*.

Tại sao tồi: Sau khi member rời đi hoặc bị khóa tài khoản, mã nguồn quan trọng bị kẹt trên máy cá nhân không thể thu hồi được.

---

## Tình huống 5 — Thẩm định & Phê duyệt Tài liệu Bàn giao (Handover Doc Review)

Product Lead là người chịu trách nhiệm cuối cùng về chất lượng tài liệu bàn giao. Không phê duyệt các tài liệu viết chung chung, sơ sài.

**✅ Cách tốt:**  
Product Lead thẩm định tài liệu dựa trên **Bộ tiêu chuẩn 4 Trụ Cột & Tính tự giải thích (Self-explanatory)**:
1. **Trụ cột 1 — Bức tranh tổng quan & Module phụ trách:** Sơ đồ cấu trúc, luồng nghiệp vụ cốt lõi, công nghệ đặc thù.
2. **Trụ cột 2 — Danh mục công việc dở dang (Pending Tasks):** Mã issue trên GitHub Projects, tên branch tương ứng, trạng thái hiện tại và hướng xử lý tiếp theo.
3. **Trụ cột 3 — Tài nguyên, Secrets & Cấu hình:** Danh sách tài khoản dịch vụ, biến môi trường đặc biệt, key giải mã `dotenvx`.
4. **Trụ cột 4 — Kinh nghiệm vận hành & Edge cases:** Những lỗi hay gặp (known issues), cách khắc phục sự cố khẩn cấp (troubleshooting).
5. **Yêu cầu Walkthrough Video:** Đối với các luồng nghiệp vụ phức tạp, yêu cầu member quay một video ngắn (10–15 phút quay màn hình giải thích luồng code) đính kèm vào tài liệu.

```text
"Anh đã xem bản thảo Handover Doc của em. Nội dung phần module Payment viết rất rõ, nhưng phần tích hợp Webhook bên thứ 3 còn thiếu thông tin debug khi nhận callback thất bại.
Em bổ sung thêm mục giải thích log lỗi Webhook và đính kèm video quay nhanh luồng test trên Sandbox trước 16:00 chiều nay nhé."
```

Tại sao tốt: Đảm bảo tài liệu có tính ứng dụng cao, bất kỳ dev mới nào vào sau đọc cũng có thể tiếp quản được ngay mà không cần liên hệ lại người cũ.

**❌ Cách tồi:**  
Đọc lướt qua tài liệu 2 trang A4 chỉ toàn gạch đầu dòng ngắn ngủn (`Code ở branch main, task trên board`) rồi bấm duyệt ngay.

Tại sao tồi: Tài liệu vô giá trị, gây lãng phí thời gian của người tiếp quản sau này.

---

## Tình huống 6 — Chủ trì Buổi họp Bàn giao (Handover Session & Live Verification)

Buổi họp bàn giao không phải là buổi thuyết trình một chiều, mà là phiên **nghiệm thu và kiểm chứng thực tế (Verification Session)** do Product Lead chủ trì.

**✅ Cách tốt:**  
Product Lead điều phối buổi họp theo kịch bản 3 bước:
1. **Bước 1 — Live Demo (20 phút):** Thành viên rời đi chia sẻ màn hình, trình diễn luồng chạy của các tính năng và module do mình phụ trách trên môi trường staging/local.
2. **Bước 2 — Reverse Demo / Live Setup (25 phút):** **Receiver trực tiếp chia sẻ màn hình**, tự clone repo, nạp key giải mã `dotenvx`, khởi chạy dự án và chạy thử test case dưới sự quan sát của Member và Product Lead. Mọi thắc mắc được giải đáp trực tiếp ngay tại chỗ.
3. **Bước 3 — Ghi âm & Đóng gói (5 phút):** Product Lead ghi âm/quay video (Record) toàn bộ buổi họp, lưu link record vào Wiki dự án để làm tài liệu đào tạo cho các nhân sự gia nhập sau này.

Tại sao tốt: Xác thực 100% việc người mới đã cài đặt và hiểu được mã nguồn; lưu trữ tư liệu sống động cho dự án.

**❌ Cách tồi:**  
Product Lead vắng mặt trong buổi họp để 2 thành viên tự trao đổi với nhau, không quay video lưu trữ, không có bước nghiệm thu chạy code thực tế.

Tại sao tồi: Hai thành viên trao đổi qua loa, bỏ qua các góc khuất kỹ thuật, và khi phát sinh lỗi Product Lead không nắm được nguyên nhân để xử lý.

---

## Tình huống 7 — Thu hồi Quyền truy cập (Access Revocation) & Bảo mật Zero Trust

Bảo mật thông tin dự án là trách nhiệm sống còn của Product Lead. Sau ngày làm việc cuối cùng, không được để sót bất kỳ quyền truy cập nào.

**✅ Cách tốt:**  
Product Lead áp dụng nguyên tắc **Zero Trust Offboarding**, thực hiện rà soát và thu hồi quyền theo bảng kiểm định trước 18:00 ngày làm việc cuối cùng:

| Kênh / Tài nguyên | Hành động của Product Lead |
|---|---|
| **GitHub Repository / Org** | Xóa khỏi Collaborators/Team trên GitHub Repo của dự án (hoặc hạ quyền xuống Read-only nếu member vẫn làm dự án khác trong công ty). |
| **Cloud & Servers (AWS/GCP/VPS)** | Xóa SSH public keys cá nhân trên server; vô hiệu hóa/xóa IAM User, Service Account; thu hồi quyền truy cập Database production/staging. |
| **Biến môi trường & Secrets** | Nếu member từng nắm giữ master secret/root credentials: **thực hiện xoay vòng (rotate) toàn bộ API keys và secrets liên quan**; cập nhật lại file env mã hóa qua `dotenvx`. |
| **Công cụ SaaS & Quản lý** | Thu hồi quyền trên Figma, Postman Workspace, Sentry, Vercel, Supabase, 1Password vault của dự án. |
| **Giao tiếp & Trao đổi** | Xóa khỏi Topic/Group Telegram bảo mật của dự án (nếu member nghỉ việc hoặc chuyển sang dự án không liên quan). |
| **Chuyển quyền sở hữu (Ownership Transfer)** | Kiểm tra và chuyển toàn bộ các dịch vụ/domain/bot Telegram do member đăng ký sang email quản trị của Product Lead. |

Tại sao tốt: Ngăn chặn triệt để rủi ro rò rỉ dữ liệu khách hàng, đảm bảo tính toàn vẹn và tuân thủ tiêu chuẩn an toàn thông tin của Cyberk.

**❌ Cách tồi:**  
Quên không xóa SSH keys trên server production hoặc để member tiếp tục ở lại nhóm Telegram dự án sau khi đã rời đi hàng tháng trời.

Tại sao tồi: Vi phạm nghiêm trọng chính sách bảo mật, tạo nguy cơ lộ dữ liệu khách hàng và mất an toàn mã nguồn.

---

## Tình huống 8 — Xử lý tình huống Bất khả kháng / Nghỉ đột xuất / Thành viên Ghosting

Trong trường hợp thành viên gặp sự cố sức khỏe nặng, biến cố gia đình đột xuất hoặc cố tình ngắt liên lạc (Ghosting) mà không bàn giao:

**✅ Cách tốt:**  
Product Lead kích hoạt **Quy trình Ứng phó Khẩn cấp 4 bước**:
1. **Khóa quyền truy cập tức thì (Trong vòng 1 giờ):** Lập tức thu hồi mọi quyền truy cập Git, Cloud, Server và Secrets của thành viên để bảo vệ an toàn hệ thống.
2. **Thu hồi và khôi phục mã nguồn:** Kéo toàn bộ branch mới nhất trên remote Git về máy; kiểm tra lịch sử commit gần nhất; rà soát GitHub Projects Board để tổng hợp danh sách task đang dang dở.
3. **Chỉ định Interim Receiver:** Product Lead trực tiếp tiếp quản tạm thời hoặc phân công một Senior Dev có năng lực đứng ra gánh vác các task critical path để không làm trễ tiến độ Sprint.
4. **Báo cáo và xử lý chế tài:** Báo cáo tình hình cho Quản lý cấp cao (Anderson); căn cứ quy định tại [[project-bonus-policy|Chính Sách Thưởng Dự Án]] để xem xét bảo lưu quyền lợi pro-rata (nếu có lý do bất khả kháng chính đáng) hoặc hủy thưởng và kỷ luật (nếu cố tình tự ý bỏ việc/ghosting).

Tại sao tốt: Giữ cho dự án đứng vững trước khủng hoảng nhân sự, xử lý minh bạch và đúng quy định công ty.

**❌ Cách tồi:**  
Hoảng loạn, đổ lỗi cho thành viên trước mặt khách hàng/team, hoặc bỏ mặc các task dở dang làm ảnh hưởng dây chuyền đến cả hệ thống.

Tại sao tồi: Làm mất uy tín của cả công ty với khách hàng và gây suy sụp tinh thần của các thành viên còn lại trong team.

---

## Tình huống 9 — Khi dự án chưa có nhân sự thay thế: Product Lead đóng vai trò "Knowledge Vault"

Khi dự án neo người hoặc chưa kịp tuyển nhân sự mới thay thế ngay, Product Lead chính là "chiếc cầu nối tri thức" lưu trữ mọi thông tin.

**✅ Cách tốt:**  
1. **Tiếp nhận vai trò Receiver trung gian:** Product Lead trực tiếp đứng ra nhận bàn giao từ thành viên rời đi, yêu cầu tài liệu đạt chuẩn Self-explanatory tối đa.
2. **Lưu trữ tập trung có cấu trúc (Knowledge Hub):** Lưu toàn bộ Handover Doc, sơ đồ kiến trúc, link video record và danh sách credentials vào thư mục Wiki dự án.
3. **Sẵn sàng kịch bản Onboarding người mới:** Khi có nhân sự mới gia nhập dự án, Product Lead sử dụng trực tiếp bộ tài liệu này kết hợp với [[project-onboarding-process|Quy trình Onboarding Dự Án]] để hướng dẫn người mới cài đặt local trong 24h và hoàn thành First PR trong Ngày 2 mà không bị mất dấu tri thức.

Tại sao tốt: Dự án không bị phụ thuộc vào một cá nhân cụ thể, tri thức được thể chế hóa và dễ dàng chuyển giao cho bất kỳ ai trong tương lai.

**❌ Cách tồi:**  
Nghĩ rằng "chưa có người mới thì bàn giao làm gì", cho phép member rời đi mà không cần viết tài liệu chi tiết.

Tại sao tồi: Đến khi tuyển được người mới vào thì toàn bộ tri thức kỹ thuật cũ đã biến mất, team phải mò mẫm hoặc viết lại code từ đầu.

---

## Tình huống 10 — Đánh giá Hoàn tất (Sign-off), Phân bổ Thưởng dự án & Giữ gìn văn hóa

Kết thúc quá trình rời dự án bằng một buổi nghiệm thu rõ ràng và lời cảm ơn chân thành khẳng định văn hóa chuyên nghiệp của Cyberk.

**✅ Cách tốt:**  
1. **Ký duyệt hoàn tất (Sign-off):** Product Lead kiểm tra lại toàn bộ checklist: mã nguồn đã dọn dẹp, PR đã xử lý, tài liệu đã lưu trữ, quyền hạn đã thu hồi 100%.
2. **Đánh giá Thưởng dự án (Bonus Evaluation):** Căn cứ vào thời gian cống hiến thực tế và tinh thần trách nhiệm trong quá trình bàn giao để đề xuất phân bổ thưởng dự án theo tỷ lệ đóng góp (pro-rata) theo đúng [[project-bonus-policy|Chính Sách Thưởng Dự Án]].
3. **Gửi lời cảm ơn và chúc mừng công khai:** Đăng lời cảm ơn trang trọng trên nhóm Telegram chung của team, ghi nhận những đóng góp của thành viên và chúc thành viên gặt hái thành công ở chặng đường tiếp theo.

```text
"Thay mặt dự án [Tên Dự Án], anh xin gửi lời cảm ơn chân thành đến bạn [Tên Member] vì những cống hiến rất giá trị trong suốt [Số Tháng] vừa qua.
Bạn đã hoàn tất xuất sắc toàn bộ quy trình bàn giao công việc và mã nguồn cho team.
Chúc em luôn nhiều sức khỏe, năng lượng và gặt hái nhiều thành công rực rỡ trên hành trình mới nhé! 🚀👏"
```

Tại sao tốt: Tạo kết thúc đẹp, giữ gìn mối quan hệ đồng nghiệp tốt đẹp, khích lệ tinh thần trách nhiệm của toàn thể đội ngũ còn ở lại.

**❌ Cách tồi:**  
- Âm thầm kick member ra khỏi nhóm chat không một lời thông báo, hoặc tìm cách cắt giảm thưởng vô lý dù thành viên đã bàn giao chu đáo.
- Hoặc ký duyệt bừa bãi khi chưa kiểm tra checklist khiến rủi ro kỹ thuật còn treo lơ lửng.

Tại sao tồi: Phá vỡ văn hóa công ty, tạo hình ảnh xấu về năng lực quản trị của Product Lead và gây bất an cho các nhân sự ở lại.

---

## Bảng Tóm Tắt Thực Chiến Dành Cho Product Lead

| Giai đoạn | Việc Product Lead NÊN làm | Điều Product Lead TRÁNH làm |
|---|---|---|
| **Tiếp nhận thông báo (T-14)** | Bình tĩnh, hẹn 1-1 trong 24h, đánh giá rủi ro (Impact Assessment) và các điểm nghẽn SPOF. | Trách móc, khó chịu hoặc im lặng không phản hồi. |
| **Lập kế hoạch (T-10 đến T-7)** | Thiết lập Cutoff Date (T-7 dừng nhận task mới), chỉ định Receiver và lập timeline bàn giao rõ ràng. | Tiếp tục giao task mới sát ngày nghỉ khiến không có thời gian viết tài liệu. |
| **Quản trị Git & Task (T-5 đến T-3)** | Yêu cầu push 100% remote branch, đóng gói Draft PRs, reassign task dở dang trên GitHub Projects. | Để code dở dang nằm trên máy local của member. |
| **Duyệt Handover Doc (T-3)** | Thẩm định theo 4 trụ cột, kiểm tra tính tự giải thích (Self-explanatory), yêu cầu video demo. | Duyệt qua loa tài liệu sơ sài chỉ có vài gạch đầu dòng. |
| **Chủ trì họp Handover (T-2)** | Điều phối Live Demo, yêu cầu Receiver tự tay chạy local (Reverse Demo), quay video lưu trữ. | Vắng mặt trong buổi họp hoặc chỉ để hai bên nói chuyện miệng. |
| **Bảo mật & Thu hồi quyền (Last Day)** | Thu hồi toàn bộ quyền GitHub, Cloud SSH/IAM, rotate secret, chuyển Owner SaaS, thu hồi key `dotenvx`. | Bỏ quên SSH keys trên server hoặc giữ nguyên quyền Admin SaaS. |
| **Xử lý sự cố / Ghosting** | Khóa quyền tức thì trong 1h, kéo remote branch về, kích hoạt Interim Receiver, báo cáo quản lý. | Hoảng loạn, than phiền với khách hàng và bỏ mặc tiến độ Sprint. |
| **Sign-off & Tri ân (Last Day)** | Kiểm tra checklist 100%, đề xuất thưởng pro-rata công tâm, gửi lời cảm ơn trang trọng trên nhóm team. | Cắt thưởng vô lý hoặc âm thầm kick member ra khỏi nhóm chat. |

---

## Liên kết

- [Quy trình Rời Dự Án (Process)](project-leave-process.md)
- [Cẩm nang Rời Dự Án cho Thành viên (Member Handbook)](project-leave-member-handbook.md)
- [Quy trình Onboarding Dự Án](../project-onboarding/project-onboarding-process.md)
- [Cẩm nang Onboarding Dự Án](../project-onboarding/project-onboarding-handbook.md)
- [Cẩm nang Giao tiếp trong Team (Horenso)](../team-communicate/team-communicate-handbook.md)
- [Cẩm nang Quản lý Board Dự Án](../../04-delivery/board-handbook/board-handbook.md)
- [Chính Sách Thưởng Dự Án](../../04-delivery/bonus-policy/project-bonus-policy.md)
