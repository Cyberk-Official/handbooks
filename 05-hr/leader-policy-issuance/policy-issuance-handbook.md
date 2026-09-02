---
type: handbook
tags: [policy, governance, decision-making, cyberk-way]
created: 2026-08-29
updated: 2026-08-29
author: anderson
---

# Ban hành Policy — Cẩm nang cho C-level & Leaders

**Người chịu trách nhiệm:** CEO
**Cập nhật lần cuối:** 2026-08-29
**Trạng thái:** Đang dùng

Bạn là CEO hoặc C-level, vừa nhận ra công ty cần một quy định mới. Bạn biết phải làm gì, nhưng **cách bạn ban hành** quyết định nhiều hơn bạn nghĩ — nó quyết định liệu mọi người sẽ tuân theo vì hiểu, hay tuân theo vì sợ (hoặc tệ hơn: không tuân theo vì không biết).

Trang này hướng dẫn cách nghĩ và cách làm đúng cho từng bước trong [quy trình ban hành policy](./policy-issuance-process.md).

---

## Bước 1 — Trình bày bản nháp cho Leaders: Nên làm thế nào?

### Soạn bản nháp: Viết cho người đọc, không viết cho mình

Sai lầm phổ biến nhất: soạn policy bằng ngôn ngữ của người ra quyết định ("Tôi muốn..."), thay vì ngôn ngữ của người phải tuân theo ("Bạn cần..."). Policy tốt phải trả lời được 3 câu hỏi:

1. **Vì sao** có policy này? (tinh thần)
2. **Ai** phải làm theo? (phạm vi)
3. **Cụ thể phải làm gì?** (điều khoản)

**✅ Cách tốt:**

```
Tinh thần: Source code là tài sản cốt lõi của công ty. Quản lý tốt giúp
team cộng tác hiệu quả, rollback an toàn khi có sự cố, và onboard 
người mới nhanh hơn.

Phạm vi: Áp dụng cho toàn bộ Developer và AI Agent tại Cyberk.

Điều khoản:
- Mỗi branch tương ứng đúng 1 Task trên Board
- Không push trực tiếp vào main/prod/dev
- Mọi thay đổi phải qua Pull Request
```

Tại sao tốt: Mở bằng lý do (người đọc hiểu *vì sao*), scope rõ ràng, điều khoản cụ thể đo được.

**❌ Cách tồi:**

```
Quyết định: Từ nay mọi người phải dùng Git đúng cách. Không được 
commit bừa bãi. Ai vi phạm sẽ bị nhắc nhở.
```

Tại sao tồi: Không có lý do, "đúng cách" là mơ hồ, "commit bừa bãi" không định nghĩa rõ, hình thức xử lý không cụ thể.

### Trình bày trong nhóm Leaders: Đừng "thả bom", hãy "mở cửa"

Khi gửi bản nháp cho Leaders trên Telegram, mục tiêu không phải "thông báo", mà là **mời cộng tác**. Leaders là người sẽ triển khai policy xuống team — nếu họ không hiểu hoặc không đồng ý, policy sẽ chết ngay khi ra khỏi phòng họp.

**✅ Cách tốt:**

```
📋 [Bản nháp] Quy chuẩn Quản lý Source Code & Git

Anh/chị em Leaders,

Mình đang soạn quy chuẩn Git cho toàn bộ dev team. Lý do: 
hiện tại mỗi dự án một kiểu, gây khó khăn khi review code 
chéo và onboard người mới.

Bản nháp ở đây: [link file HTML]

Mọi người xem giúp mình 2 điểm:
1. Có điều gì không khả thi với team mình không?
2. Còn thiếu gì cần bổ sung?

Mình thu thập ý kiến đến hết ngày [DD/MM] nhé.
```

Tại sao tốt: Giải thích vì sao, đặt câu hỏi cụ thể (không phải "mọi người xem thử"), có deadline rõ.

**❌ Cách tồi:**

```
Gửi mọi người quy định Git mới. Áp dụng từ tuần sau.
[đính kèm file]
```

Tại sao tồi: Không giải thích, không mời góp ý, ép thời hạn mà không thảo luận — Leaders cảm thấy bị ra lệnh thay vì được tham gia.

---

## Bước 2 — Thu thập phản hồi toàn công ty: Khi nào và làm thế nào?

### Câu hỏi mấu chốt: Policy này có "nhạy cảm" không?

Nhạy cảm = ảnh hưởng trực tiếp tới **quyền lợi, thói quen hàng ngày, hoặc cảm xúc** của nhân viên. Quy tắc ngón tay cái: nếu bạn tưởng tượng một nhân viên đọc policy này và nói "Sao không hỏi ý kiến tụi em trước?" — thì nó nhạy cảm.

**Ví dụ nhạy cảm:** Thay đổi nghỉ phép, WFH, lương thưởng, kỷ luật, giờ làm.
**Ví dụ không nhạy cảm:** Quy chuẩn Git, naming convention, template report.

### Thông báo bản nháp cho toàn công ty

**✅ Cách tốt:**

```
📢 [Bản nháp - Xin ý kiến] Chính sách làm việc từ xa (WFH)

Hi all,

Công ty đang chuẩn bị ban hành chính sách WFH mới. Trước khi 
chính thức, mình muốn mọi người cùng xem bản nháp và góp ý.

👉 Bản nháp: [link file HTML]

Mọi ý kiến đóng góp, mình thu thập đến hết ngày [DD/MM].
Các bạn có thể reply trực tiếp trong nhóm này.

Lưu ý: đây là BẢN NHÁP, chưa có hiệu lực. Nội dung có thể 
thay đổi dựa trên phản hồi của mọi người.
```

Tại sao tốt: Ghi rõ là BẢN NHÁP, có thời hạn góp ý, mời mọi người tham gia — tạo cảm giác được tôn trọng.

**❌ Cách tồi:**

```
Mọi người đọc chính sách WFH mới nhé. 
Có gì thắc mắc thì hỏi HR.
```

Tại sao tồi: Không phân biệt nháp/chính thức, không mời góp ý — chỉ "thông báo xong" rồi thôi. Nhân viên cảm thấy bị áp đặt.

### Xử lý phản hồi: Không phải mọi góp ý đều phải thay đổi

Thu thập phản hồi không có nghĩa là phải chiều theo tất cả. Nhưng phải **ghi nhận** tất cả. Quy tắc:

| Loại phản hồi | Hành động |
|---------------|----------|
| Góp ý hợp lý, có thể điều chỉnh | Cập nhật bản nháp, ghi chú "đã điều chỉnh theo ý kiến của..." |
| Góp ý hợp lý nhưng không phù hợp lúc này | Reply cảm ơn, giải thích lý do chưa áp dụng |
| Phản đối không có lý do cụ thể | Reply cảm ơn, giữ nguyên. Không cần tranh luận |
| Nhiều người cùng phản đối một điểm | Tổ chức meeting nhỏ hoặc poll để quyết định |

---

## Bước 3 — Phân phối qua Admin: Tại sao không tự gửi?

### Lý do đi qua Admin

1. **Kênh chính thức:** Email là kênh chính thức duy nhất cho policy. Telegram dùng để thảo luận, không dùng để ban hành. Policy gửi trên Telegram sẽ bị cuốn trôi trong chat.
2. **Đầu mối duy nhất:** Admin quản lý danh sách email toàn công ty, đảm bảo không ai bị sót. CEO gửi từ email cá nhân có thể bị thiếu người.
3. **Lưu trữ:** Admin lưu trữ có hệ thống. Khi nhân viên mới vào, có thể tra lại toàn bộ policy đã ban hành.

### Chuyển giao cho Admin

**✅ Cách tốt:**

```
Gửi Admin,

Policy [POL-DEV-001] "Quy chuẩn Quản lý Source Code & Git" 
đã được duyệt. File PDF đính kèm.

Nhờ em gửi email cho toàn bộ công ty với nội dung:
- Subject: [Cyberk] Ban hành Quy chuẩn Quản lý Source Code & Git
- Body: "Kính gửi toàn thể nhân viên, công ty ban hành quy chuẩn 
  mới về quản lý source code & Git, có hiệu lực từ ngày [DD/MM/YYYY]. 
  Chi tiết trong file đính kèm."
- Đính kèm: file PDF

Xác nhận lại khi đã gửi xong nhé. Cảm ơn em.
```

Tại sao tốt: Cung cấp đầy đủ thông tin (mã số, tên, file, nội dung email gợi ý), có yêu cầu xác nhận.

**❌ Cách tồi:**

```
Gửi cái này cho mọi người giúp anh.
[đính kèm file]
```

Tại sao tồi: Admin không biết gửi kênh nào, viết subject gì, body ra sao. Kết quả: email thiếu context, nhân viên đọc không hiểu.

---

## Tóm lại

| Bước | Làm gì | Nguyên tắc cốt lõi |
|------|--------|-------------------|
| **1. Trình Leaders** | Soạn nháp → gửi nhóm Leaders → thu thập phản hồi | "Mời cộng tác, không thả bom" |
| **2. Hỏi ý kiến** *(nếu nhạy cảm)* | Gửi bản nháp toàn công ty → mở cửa sổ góp ý | "Hỏi trước, ban hành sau" |
| **3. Phân phối** | Duyệt → PDF → Admin gửi email | "Kênh chính thức, đầu mối duy nhất" |

### Ba anti-pattern cần tránh

1. **"CEO nói là luật"** — Policy ra mà không qua Leaders → team bị động, Leaders mất mặt
2. **"Hỏi cho có"** — Thu thập ý kiến nhưng không ghi nhận, không phản hồi → mất tin tưởng
3. **"Gửi Telegram là xong"** — Policy trôi trong chat, 2 tuần sau không ai nhớ → vô hiệu hóa

---

## Liên kết

- [Quy trình ban hành Policy](./policy-issuance-process.md) — Flowchart, bảng bước, checklist
- [Skill soạn Policy](../skills/create-decision/SKILL.md) — Pipeline MD → HTML → PDF
- [Template HTML quyết định](../skills/create-decision/cyberk-decision-template.html)
- [Playbook viết Handbook](../../workflow/playbook.md) — Nguyên tắc viết tài liệu CyberK
