---
type: delivery
tags: [templates, communication, client-management]
created-date: 2026-11-19
updated-date: 2026-11-26
author: anderson
status: Nháp
---

# 💬 Mẫu Tin Nhắn Xử lý Feature Request — Không Tốt vs Tốt

**Người chịu trách nhiệm:** PO dự án
**Cập nhật lần cuối:** 2026-11-19
**Trạng thái:** Nháp

> **Quy tắc vàng:** Các tính năng mới thường được khách hàng nêu ra ngay **trong buổi họp (Daily Demo / Sync Call)** khi đang hào hứng nhìn sản phẩm chạy. Đừng dập tắt sự hào hứng đó bằng câu *"Ngoài hợp đồng rồi!"*, cũng đừng hứa miệng *"Để em làm luôn"*. **Ngay sau buổi họp**, hãy nhắn tin xác nhận kèm **BRD**, báo rõ **quy trình tiếp theo của Cyberk** và **mức phí mở rộng tiêu chuẩn `$25/giờ`** để khách biết chừng ngay từ đầu.

*(Bối cảnh thực tế xuyên suốt: dự án ứng dụng giao dịch & quản lý danh mục **Koto** của khách hàng **Jon**, đang chạy tới mốc Launch bản v1 vào **Thứ Sáu, 28/11**).*

---

## Bước 1: `UNDERSTAND` — Tiếp nhận & làm rõ yêu cầu

### 1.1. Jon nêu tính năng mới ngay trong buổi họp Daily Demo *(tình huống phổ biến nhất)*

> **Bối cảnh:** Trong buổi họp chiều nay, Jon hào hứng đề xuất thêm **Referral & 20% Fee Rebate Dashboard** để kéo user tự nhiên sau khi ra mắt, và hai bên đã trao đổi rõ luồng mong muốn ngay trong cuộc họp.

**❌ Mẫu KHÔNG TỐT (2 sai lầm kinh điển sau buổi họp):**

```
# Sai lầm A — Phủ đầu bằng hợp đồng làm khách cụt hứng:
Hi Jon, I checked our Proposal and Contract SoW after the meeting. Referral Dashboard is not included in the current scope, so we cannot build it unless we sign a paid Change Request at $25/hr.
```
```
# Sai lầm B — Trong họp gật gù rồi im lặng, hôm sau đùng cái đòi tiền:
Hi Jon, about the Referral idea you mentioned on the call yesterday — our team estimated 38 hours so you'll need to pay $950 extra before we start.
```

Tại sao tồi:
- **Sai lầm A** tạt thẳng chữ *"not included in Contract"* vào mặt khách lúc họ đang hào hứng nhất — nghe như luật sư chặn họng thay vì người đồng đội xây sản phẩm.
- **Sai lầm B** để khoảng trống im lặng sau buổi họp khiến Jon đinh ninh *"bàn trên call xong nghĩa là team tự làm luôn"*, đến hôm sau đột ngột bị đòi `$950` nên cảm thấy bị đánh úp.

👉 **Cách sửa đúng:** Ngay sau buổi họp, hãy bắt nhịp sự hào hứng của Jon, đính kèm **BRD** vừa viết, chỉ rõ **lộ trình tiếp theo của Cyberk** nhân danh việc bảo vệ ngày Launch `Nov 28`, và báo trước mức **`$25/hour`** một cách tự nhiên:

**✅ Mẫu TỐT:**

```
Hi Jon 👋 Great session earlier — really love the Referral & 20% Fee Rebate idea, it's a strong growth loop for bringing in organic traders right after launch!

Since this is a brand-new feature outside our v1 scope, here is how we'll handle the next steps on our side so your Nov 28 launch stays protected:

1️⃣ Requirements (Done): I've captured everything we discussed today into a clear BRD here so nothing gets lost:
📄 BRD — Referral & 20% Fee Rebate: https://github.com/Cyberk-Official/koto-docs/blob/main/docs/brd/referral-rebate.md
• Single-tier invite code & link for every verified user
• 20% trading fee rebate credited daily in USDC
• Self-referral & duplicate wallet protection included

2️⃣ Technical Estimate (Within 24h): Our Tech Lead is now reviewing the UX/UI screens, system architecture, and code side effects to calculate the exact team hours needed.

3️⃣ Proposal (Tomorrow's sync): For transparency, our standard rate for new feature expansions is $25/hour. Once the estimate is finalized tomorrow, I'll walk you through the full breakdown, total hours, and timeline options so you can decide how you'd like to proceed 🙏
```

Tốt vì: Giữ trọn lửa hào hứng của Jon, khóa chặt phạm vi bằng BRD ngay lập tức, cho thấy quy trình chuyên nghiệp trong 24h và neo sẵn đơn giá `$25/hour` để ngày mai nhận báo giá không bao giờ giật mình.

---

### 1.2. Jon bất chợt nhắn ý tưởng qua Telegram ngoài giờ họp (chưa đủ thông tin viết BRD)

> **Bối cảnh:** Tối muộn, Jon nhắn vào nhóm: *"Hey team! Just thought of something cool — what if we also build a Telegram Trading Bot so users can place limit orders right inside Telegram?"*

**❌ Mẫu KHÔNG TỐT:**

```
Awesome idea Jon! Shouldn't be too hard, let me ask the devs tomorrow how long it takes 👍
```

Tại sao tồi: Chưa họp làm rõ lệnh nào, ký ví ra sao, chưa có BRD mà đã vội hứa hẹn cảm tính và định ném thẳng câu hỏi mơ hồ sang cho Dev đoán mò.

👉 **Cách sửa đúng:** Khen ý tưởng sắc bén, hẹn 15 phút trong buổi họp ngày mai để làm rõ luồng lên BRD, đồng thời báo trước quy trình tiếp theo & đơn giá `$25/hour`:

**✅ Mẫu TỐT:**

```
Hi Jon 👋 That's a super sharp idea — a Telegram Trading Bot would make quick order execution way stickier for mobile traders!

Because this introduces a new product flow outside our current v1 build, here's our next step at Cyberk:
• Let's spend 15 mins in tomorrow's call (at 3:00 PM) to map out the exact bot commands and wallet signing flow so I can write up the BRD.
• Right after that, our Tech Lead will estimate the UX, architecture, and dev hours within 24 hours.
• Just so you have a ballpark early on, our feature expansion rate is $25/hour — once we have the exact hours, we'll review the full breakdown and schedule options together!
```

---

## Bước 2: `ESTIMATE` — Phối hợp Tech Lead & giữ nhịp 24h

### 2.1. PO chuyển yêu cầu cho Tech Lead ước lượng *(giao tiếp nội bộ)*

> **Bối cảnh:** PO cần Tech Lead đưa ra báo cáo Estimate trong vòng 24 giờ cho tính năng **Referral & 20% Fee Rebate**.

**❌ Mẫu KHÔNG TỐT:**

```
@hungdn Anh ơi, nay họp Jon bảo muốn làm thêm mục Referral nhận 20% phí giao dịch. Anh nhẩm nhanh giúp em mất khoảng bao nhiêu tiếng để mai em báo Jon nhé!
```

Tại sao tồi: Không có BRD, đẩy Tech Lead vào thế ước lượng bằng trí tưởng tượng → chắc chắn bỏ sót màn hình Admin Payout, sót worker đối soát phí và quên cộng buffer rủi ro.

👉 **Cách sửa đúng:** Viết xong BRD trước rồi mới bàn giao cho Tech Lead, nêu rõ 4 hạng mục bắt buộc + buffer 30%–50% + mốc 24h:

**✅ Mẫu TỐT:**

```
@hungdn Em vừa họp với Jon về yêu cầu mới: Referral & 20% Fee Rebate (dự kiến > 20h, ngoài SoW v1).
📄 BRD em đã viết xong ở đây: https://github.com/Cyberk-Official/koto-docs/blob/main/docs/brd/referral-rebate.md

Nhờ anh review và cho em Báo cáo Estimate trước 2:00 PM chiều mai (trong khung 24h trước giờ sync với Jon) gồm đủ 4 mục nhé:
1. Thiết kế UX/UI cần mở rộng
2. Thiết kế hệ thống cần thay đổi (DB, cronjob/worker...)
3. Source code & side effects chạm vào luồng hiện tại
4. Tổng số giờ của cả team (anh cộng sẵn buffer 30%–50% giúp em nhé)

Nếu anh thấy ca này phức tạp vượt quá 24h nghiên cứu thì báo em sớm để em escalate anh Anderson luôn ạ!
```

---

### 2.2. Khi tính năng đụng *side effects* lớn, Estimate vượt quá 24 giờ *(báo khách hàng)*

> **Bối cảnh:** Jon đề xuất thêm **Auto Copy-Trading Vault** (tự động sao chép lệnh theo ví chuyên gia). Tech Lead soi thấy đụng sâu vào cơ chế ký lệnh, trượt giá (*slippage*) và an toàn vốn nên vượt mốc 24h. PO đã báo Anderson nội bộ, giờ cần nhắn cho Jon.

**❌ Mẫu KHÔNG TỐT:**

> PO im lặng luôn qua buổi chiều hôm sau vì nghĩ *"chưa có số giờ thì nhắn làm gì"*, để Jon phải chủ động hỏi trước: *"Hey any update on the Copy-Trading estimate?"*

Tại sao tồi: Phá vỡ nhịp routine 24h hằng ngày, đánh mất tinh thần *responsive* và làm Jon nghĩ team thiếu chuyên nghiệp.

👉 **Cách sửa đúng:** Chủ động nhắn trước khi hết 24h, giải thích lý do cần thêm 1 ngày là để **kiểm tra kỹ *side effects* bảo vệ an toàn vốn cho hệ thống của Jon**:

**✅ Mẫu TỐT:**

```
Hi Jon 👋 Quick heads-up on the Auto Copy-Trading Vault estimate we discussed yesterday!

Our Tech Lead has been mapping out how automated order mirroring interacts with our current trade execution engine and wallet custody rules. Because this touches user funds and real-time slippage handling, we're taking one extra day with Anderson and our senior architect to check all side effects carefully — so we give you an accurate hour count with zero hidden risks.

I'll have the complete breakdown and proposal ready for you tomorrow by 4:00 PM GMT+8 👍
```

---

## Bước 3: `APPROVAL` — Xin AM (Anderson / Brian) duyệt ngân sách & mức phí

> **Bối cảnh:** Tech Lead đã gửi báo cáo Estimate 24 giờ (đã gộp buffer) cho tính năng **Portfolio Tax & PnL Export** mà Jon cần gấp cho buổi demo với quỹ đầu tư tuần tới. PO trình AM duyệt trước khi báo khách.

**❌ Mẫu KHÔNG TỐT:**

```
Anh @anderson ơi, Jon xin làm thêm cái xuất file PDF/CSV lịch sử PnL, anh Hưng tính hết 24 tiếng. Ca này mình thu tiền $600 hay làm free cho khách hả anh?
```

Tại sao tồi: Thiếu link BRD, thiếu bối cảnh tại sao khách cần gấp, thiếu đánh giá ảnh hưởng lên ngày Launch 28/11 → AM phải hỏi ngược lại 3–4 câu mới quyết được.

👉 **Cách sửa đúng:** Cung cấp trọn gói **BRD + 4 hạng mục Estimate + Giá trị chuẩn theo mức `$25/h` + Bối cảnh kinh doanh của khách + Ảnh hưởng lịch trình** trong đúng 1 tin nhắn để AM chốt ngay:

**✅ Mẫu TỐT:**

```
Anh @anderson ơi, em xin Approval cho Feature Request mới của Jon (dự án Koto):

1. Yêu cầu: Portfolio Tax & PnL Export (PDF/CSV) — ngoài SoW v1.
📄 BRD: https://github.com/Cyberk-Official/koto-docs/blob/main/docs/brd/tax-pnl-export.md

2. Tóm tắt Estimate từ TL (đã gộp buffer): Tổng 24 giờ
• UX/UI: Modal lọc kỳ báo cáo + layout PDF
• System: Worker xuất báo cáo bất đồng bộ
• Code & side effects: Sửa query lịch sử giá & cộng phí giao dịch + QA test số liệu

3. Chi phí chuẩn ($25/h): 24h × $25 = $600.
4. Bối cảnh dự án: Tuần sau Jon có buổi demo gọi vốn rất quan trọng với quỹ institutional investor nên cần tính năng này. Nếu làm ngay sẽ lùi staging freeze 2 ngày (từ T2 sang T4 26/11), vẫn kịp trước ngày Launch 28/11.

Anh duyệt giúp em ca này mình thu $600 hay hỗ trợ miễn phí cho Jon để em lên Proposal chiều nay nhé ạ!
```

---

## Bước 4: `PROPOSAL` — Trình bày BRD, 4 hạng mục & chi phí cho khách hàng

### 4.1. Trường hợp **CÓ tính phí mở rộng** (`38h × $25/hr = $950` → làm tròn xuống `$800`)

> **Bối cảnh:** Quay lại tính năng **Referral & 20% Fee Rebate Dashboard**. Tech Lead ước lượng tổng **38 giờ** (đã gộp kín buffer 30%–50%), tính theo mức chuẩn `$25/giờ = $950`. AM duyệt làm tròn xuống **`$800`** (~15%) kèm một câu nói vui để Jon thấy thoải mái và "được hời".

**❌ Mẫu KHÔNG TỐT (Báo giá trần trụi hoặc lộ dòng Buffer):**

```
# Sai lầm A — Quăng cục tiền lẻ trơ trọi, khô khốc như đòi nợ:
Hi Jon, I talked to the tech team. Adding the Referral feature will take 38 hours ($950). Let me know if you approve.
```
```
# Sai lầm B — Thật thà ghi lộ dòng chữ "Buffer" cho khách mặc cả:
Hi Jon, here is the estimate for the Referral system:
- UI + Backend/Frontend + QA: 26 hours
- Risk buffer (45%): 12 hours
Total: 38 hours × $25/hr = $950
```

Tại sao tồi:
- **Sai lầm A** vừa thiếu 4 hạng mục giải thích, vừa giữ con số lẻ cứng nhắc khiến khách dễ nảy sinh cảm giác bị đối tác đếm từng giờ để *"bào tiền"*.
- **Sai lầm B** tự mời Jon gạch bỏ dòng buffer: *"Team em quen code rồi, bỏ 12 tiếng dự phòng đi, tính anh 26 tiếng thôi nhé!"*.

👉 **Cách sửa đúng:** Mở rõ **BRD + đủ 4 hạng mục kỹ thuật cụ thể**, tính minh bạch `38 hours × $25/hour = $950`, rồi **chủ động làm tròn xuống `$800`** kèm một lý do vui vẻ, thân tình và trao 2 lựa chọn lịch trình:

**✅ Mẫu TỐT:**

```
Hi Jon — we've completed the technical review for the Referral & Fee Rebate system! Based on the BRD we aligned on yesterday, here is the full breakdown:

🔍 Scope & Technical Impact:
1. UX/UI Design: 4 new screens — Referral Hub, Share Invite Modal, Rebate Earnings Table, and Admin Payout Overview.
2. System Architecture: New `referrals` & `rebate_ledgers` tables + a daily 00:00 UTC settlement worker to calculate fee shares.
3. Source Code & Side Effects: Updates to onboarding signup flow, trade fee matching logic (splitting 20% rebate cleanly), and anti-wash-trading checks on existing auth.
4. Team Effort: 38 hours total across UX/UI Design, Backend/Frontend Dev, and QA verification.

💡 Expansion Cost & Delivery Options:
• Standard calculation: 38 hours × $25/hour = $950 — let's round that down to an even $800 for you (just owe our team a round of iced coffee next time you're in Vietnam ☕😄).
• Option A (Recommended): Keep your v1 launch locked on Friday, Nov 28, and ship the Referral system right after as v1.1 on Thursday, Dec 4.
• Option B: Include it directly in the v1 build, moving our launch date by 4 working days to Dec 4.

Let me know which option fits your go-to-market plan best — happy to walk through every line item on our call today!
```

---

### 4.2. Trường hợp AM duyệt **MIỄN PHÍ** (hỗ trợ chiến lược cho khách)

> **Bối cảnh:** Với tính năng **Portfolio Tax & PnL Export (`24h`)**, AM (Anderson) quyết định **miễn phí** để tiếp sức cho Jon chốt deal với quỹ đầu tư tuần tới.

**❌ Mẫu KHÔNG TỐT:**

```
No worries Jon, we'll add the PDF/CSV export for free! Should be easy 👍
```

Tại sao tồi: Một câu nói vô tình xóa sạch giá trị 24 giờ cày cuốc (trị giá `$600`) của cả team, và tập cho Jon thói quen nghĩ rằng mọi tính năng xuất báo cáo về sau đều "dễ ợt và miễn phí".

👉 **Cách sửa đúng:** Vẫn trình bày đầy đủ **4 hạng mục tác động & giá trị tương đương (`24h × $25/hr = $600`)** trước để Jon thấy rõ sức nặng công việc, rồi mới thông báo Cyberk tài trợ (*on the house*):

**✅ Mẫu TỐT:**

```
Hi Jon — we finished reviewing the Portfolio Tax & PnL Export feature from yesterday's meeting!

To make sure the numbers are institutional-grade accurate without slowing down the live dashboard, here's the work required from our team:
1. UX/UI Design: Export filter modal (date range, asset filter, realized vs. unrealized PnL view) + branded PDF report layout.
2. System Architecture: Async report-generation worker so heavy trade histories don't block live user requests.
3. Source Code & Side Effects: Refactoring historical price lookup and fee aggregation queries, plus QA cross-checking math edge cases.
4. Team Effort: 24 hours across Design, Dev, and QA.

At our standard $25/hour expansion rate, this 24-hour module comes out to $600. However, since we know how important next week's institutional investor demo is for you, Cyberk is happy to cover this one on the house 🙌

Just one quick note on schedule: adding this cleanly will move our staging freeze by 2 days from Monday to Wednesday, Nov 26 — still well ahead of your investor demo. Shall we lock this in?
```

---

### 4.3. Gửi Email chốt confirm sau khi khách gật đầu đồng ý chi phí

> **Bối cảnh:** Sau khi xem Proposal hệ thống **Referral & 20% Fee Rebate (`$800`)**, Jon hào hứng nhắn trên Telegram: *"Haha deal, coffees are on me! Option A looks great, let's go ahead with $800 and ship it on Dec 4!"*.

**❌ Mẫu KHÔNG TỐT:**

```
# Chỉ thả tim hoặc nhắn lại trên Telegram rồi xua quân đi code luôn:
Awesome, thanks Jon! Team is starting on it right away 🚀
```

Tại sao tồi: Một tháng sau khi gửi hóa đơn thu thêm `$800`, dòng chat Telegram đã trôi dưới hàng nghìn tin nhắn khác (hoặc người phụ trách thanh toán bên phía Jon không nằm trong nhóm Telegram). Không có Email xác nhận chính thức rất dễ nảy sinh hiểu lầm và tranh cãi không đáng có.

👉 **Cách sửa đúng:** Nhắn nhẹ trên Telegram báo đã gửi Email xác nhận, đồng thời gửi ngay **1 Email formal** (CC AM Anderson / Brian) ghi rõ phạm vi BRD, 4 hạng mục, mức phí đã chốt `$800`, mốc bàn giao và đề nghị Jon reply chữ **"Confirmed"** để lưu hồ sơ:

**✅ Mẫu TỐT (Email gửi khách hàng):**

```
Subject: [Koto] Scope & Cost Confirmation — Referral & 20% Fee Rebate Expansion
To: jon@koto.xyz
Cc: anderson@cyberk.ai

Hi Jon,

Thank you for confirming the Referral & 20% Fee Rebate expansion during our sync today!

To keep everything crystal clear for both teams' records, I'm summarizing the agreed scope, effort, cost, and delivery schedule below:

1. Approved Requirements (BRD)
• Document: Referral & 20% Fee Rebate v1.0 (attached PDF & GitHub link)

2. Technical Scope Summary
• UX/UI Design: 4 new screens (Referral Hub, Share Invite Modal, Rebate Earnings Table, Admin Payout Overview)
• System Architecture: `referrals` & `rebate_ledgers` tables + daily 00:00 UTC settlement worker
• Source Code & Side Effects: Signup attribution update, 20% trade fee rebate split, and anti-self-referral checks
• Total Team Effort: 38 hours

3. Agreed Expansion Cost & Payment
• Standard Expansion Estimate: $950 USD (38 hours × $25/hour)
• Agreed Rounded-Down Fee: $800 USD
• Billing: To be included in the next project invoice

4. Agreed Delivery Schedule (Option A)
• Current v1 Launch: Remains unchanged on Friday, Nov 28
• Referral Expansion (v1.1) Delivery: Thursday, Dec 4

Could you please reply "Confirmed" to this email so we have formal sign-off on file and can schedule the team right away?

Best regards,
Anna
Product Owner — Cyberk
```

---

### 4.3. Gửi Email chốt confirm sau khi khách gật đầu đồng ý chi phí

> **Bối cảnh:** Sau khi xem Proposal hệ thống **Referral & 20% Fee Rebate (`$800`)**, Jon hào hứng nhắn trên Telegram: *"Haha deal, coffees are on me! Option A looks great, let's go ahead with $800 and ship it on Dec 4!"*.

**❌ Mẫu KHÔNG TỐT:**

```
# Chỉ thả tim hoặc nhắn lại trên Telegram rồi xua quân đi code luôn:
Awesome, thanks Jon! Team is starting on it right away 🚀
```

Tại sao tồi: Một tháng sau khi gửi hóa đơn thu thêm `$800`, dòng chat Telegram đã trôi dưới hàng nghìn tin nhắn khác (hoặc người phụ trách thanh toán bên phía Jon không nằm trong nhóm Telegram). Không có Email xác nhận chính thức rất dễ nảy sinh hiểu lầm và tranh cãi không đáng có.

👉 **Cách sửa đúng:** Nhắn nhẹ trên Telegram báo đã gửi Email xác nhận, đồng thời gửi ngay **1 Email formal** (CC AM Anderson / Brian) ghi rõ phạm vi BRD, 4 hạng mục, mức phí đã chốt `$800`, mốc bàn giao và đề nghị Jon reply chữ **"Confirmed"** để lưu hồ sơ:

**✅ Mẫu TỐT (Email gửi khách hàng):**

```
Subject: [Koto] Scope & Cost Confirmation — Referral & 20% Fee Rebate Expansion
To: jon@koto.xyz
Cc: anderson@cyberk.ai

Hi Jon,

Thank you for confirming the Referral & 20% Fee Rebate expansion during our sync today!

To keep everything crystal clear for both teams' records, I'm summarizing the agreed scope, effort, cost, and delivery schedule below:

1. Approved Requirements (BRD)
• Document: Referral & 20% Fee Rebate v1.0 (attached PDF & GitHub link)

2. Technical Scope Summary
• UX/UI Design: 4 new screens (Referral Hub, Share Invite Modal, Rebate Earnings Table, Admin Payout Overview)
• System Architecture: `referrals` & `rebate_ledgers` tables + daily 00:00 UTC settlement worker
• Source Code & Side Effects: Signup attribution update, 20% trade fee rebate split, and anti-self-referral checks
• Total Team Effort: 38 hours

3. Agreed Expansion Cost & Payment
• Standard Expansion Estimate: $950 USD (38 hours × $25/hour)
• Agreed Rounded-Down Fee: $800 USD
• Billing: To be included in the next project invoice

4. Agreed Delivery Schedule (Option A)
• Current v1 Launch: Remains unchanged on Friday, Nov 28
• Referral Expansion (v1.1) Delivery: Thursday, Dec 4

Could you please reply "Confirmed" to this email so we have formal sign-off on file and can schedule the team right away?

Best regards,
Anna
Product Owner — Cyberk
```

---

## Ngoại lệ: Yêu cầu đơn giản hoặc tính năng cơ bản `< 8 giờ`

> **Bối cảnh:** Cuối buổi họp, Jon sực nhớ: *"Oh, we don't have a Forgot Password flow and a Terms & Privacy screen on the login page yet — can we add those?"* — Tổng công sức chưa tới 6 giờ.

**❌ Mẫu KHÔNG TỐT:**

```
Hi Jon, Forgot Password and Terms & Privacy weren't listed in our initial flow. Let me write a BRD, ask our Tech Lead to estimate, and send you a quote at $25/hour tomorrow.
```

Tại sao tồi: Quá máy móc và cứng nhắc! Bắt khách chờ 24h và đòi thu trăm bạc lẻ cho trang *Terms & Privacy* hay *Forgot Password* sẽ khiến khách cảm thấy công ty chi li, thiếu tinh thần đồng hành.

👉 **Cách sửa đúng:** Nhận diện ngay đây là ngoại lệ `< 8 giờ` — bỏ qua quy trình 4 bước, đưa thẳng lên board làm luôn để ghi điểm tuyệt đối:

**✅ Mẫu TỐT:**

```
Hi Jon 👋 Following up from our call — great catch on Forgot Password and the Terms & Privacy page!

Since both are essential baseline flows and take less than 8 hours in total, we'll skip the expansion process and build them right away for you at no extra charge. I've added both to our GitHub board — you'll see them live in tomorrow afternoon's demo! 🚀
```

---

## Tóm tắt nhanh: Phản xạ sai vs Phản xạ chuẩn

| Chặng | ❌ Phản xạ sai thường gặp | ✅ Phản xạ chuẩn của PO Cyberk |
|-------|---------------------------|--------------------------------|
| **1. Understand** | Phủ đầu *"Out of contract"* hoặc họp xong im lặng không nhắn gì | **Nhắn ngay sau buổi họp**: gửi BRD + báo quy trình tiếp theo + báo trước mức **`$25/hour`** |
| **2. Estimate** | Ném câu chat cụt ngủn cho TL đoán mò; quá 24h thì im thin thít | Giao **BRD** để TL tính đủ 4 hạng mục (+ buffer 30%–50%) trong **24h**; quá 24h báo Anderson & update khách chủ động |
| **3. Approval** | Hỏi AM trống không *"thu tiền hay free anh?"* | Trình đủ **BRD + 4 mục Estimate + mức phí `$25/h` + bối cảnh khách** trong 1 tin nhắn |
| **4. Proposal** | Báo cục tiền trơ trọi, lộ chữ *"buffer"*, hoặc khách gật đầu trên chat là đi code luôn không lưu Email | Trình bày **BRD + 4 hạng mục + tổng giờ** → Khách đồng ý xong **gửi ngay Email chốt confirm** (CC AM) chờ khách reply *"Confirmed"* |
| **Ngoại lệ `< 8h`** | Máy móc bắt làm BRD & thu phí lẻ tẻ cho *Forgot Password, 2FA, Terms...* | Bỏ qua quy trình 4 bước, đưa lên board làm luôn cho khách |

---

## Liên kết

- [Quy trình Tiếp nhận & Xử lý Feature Request](./feature-request-process.md) — Luồng 4 bước `UNDERSTAND → ESTIMATE → APPROVAL → PROPOSAL`
- [Mẫu BRD & Báo giá mở rộng](./template/feature-request-brd-template.md) — File mẫu đính kèm trong tin nhắn & Email chốt confirm
- [Xử lý Feature Request — Cẩm nang cho PO](./feature-request-handbook.md) — Cách nghĩ chi tiết của PO ở từng bước
