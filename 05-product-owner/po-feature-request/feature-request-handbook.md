---
type: delivery
tags: [handbook, project-management, client-management, communication]
created-date: 2026-11-19
updated-date: 2026-11-26
author: anderson
status: Nháp
---

# Xử lý Feature Request — Cẩm nang cho Product Owner

**Người chịu trách nhiệm:** PO dự án
**Cập nhật lần cuối:** 2026-11-19
**Trạng thái:** Nháp

Khi khách hàng nảy ra ý tưởng mới và muốn thêm tính năng, **PO là người đầu tiên tiếp nhận.** Cách bạn phản hồi trong 5 phút đầu tiên quyết định dự án giữ được cam kết đúng hạn hay sa lầy vào *scope creep* — và khách hào hứng mở rộng hợp đồng hay tụt hứng vì cảm thấy bị dội nước lạnh.

Cuốn cẩm nang này giúp bạn hiểu **cách nghĩ đúng** và **cách dẫn dắt khách hàng** đi qua 4 bước `UNDERSTAND → ESTIMATE → APPROVAL → PROPOSAL` một cách tự nhiên, chuyên nghiệp.

---

## Thế nào là một Yêu cầu tính năng (Feature Request)?

Không phải mọi lời đề xuất của khách đều xử lý giống nhau. Một yêu cầu được xác định là **Yêu cầu tính năng mới (Feature Request)** khi hội tụ đủ **3 dấu hiệu**:

1. **Là một tính năng mới:** Hoàn toàn mới, **không nằm trong user flow đã có** của sản phẩm.
2. **Ngoài phạm vi cam kết:** **Chưa được mô tả** trong tài liệu **Scope of Work (SoW)** của Proposal, hoặc trong **Hợp đồng** đã ký.
3. **Tốn công sức đáng kể của team (`> 20h`):** Việc thực hiện đòi hỏi nguồn lực lớn — **lớn hơn 20 giờ làm việc** của team.

> ⚡ **Phân tầng nhanh theo giờ công:**
> - **Dưới 8 giờ (`< 8h`):** Các yêu cầu đơn giản *(như màn hình Terms & Policy)* hoặc tính năng nền tảng hầu như ứng dụng nào cũng có *(Forgot Password, 2FA cơ bản...)* → **Bỏ qua quy trình 4 bước**, đưa thẳng lên board làm luôn cho khách.
> - **Từ 8 đến 20 giờ (`8h – 20h`):** Vẫn chạy **đủ quy trình 4 bước** và lên báo giá cụ thể (`số giờ × $25/giờ`). Ở lần phát sinh đầu tiên, có thể cân nhắc **offer miễn phí**, nhưng **nhắc trước khách hàng rằng các lần phát sinh sau có thể phải tính phí**.
> - **Trên 20 giờ (`> 20h`):** Bắt buộc đi trọn quy trình 4 bước dưới đây.

---

## Tư duy gốc: Khách xin thêm tính năng là tín hiệu TỐT

**Kết luận thẳng: Khách hàng muốn thêm yêu cầu mới luôn là một tín hiệu tốt.** Đây là chuyện hoàn toàn bình thường ở mọi dự án phần mềm, và nó **sẽ xảy ra thường xuyên** khi khách hàng nhìn thấy sản phẩm của họ dần thành hình mỗi ngày.

Nó tốt vì ba lý do rất thực tế:
- Khách hàng còn muốn mở rộng tính năng nghĩa là họ **đang tin tưởng năng lực của team** và tâm huyết với sản phẩm.
- Tạo cơ hội trực tiếp để **công ty có thêm doanh thu** từ việc mở rộng hợp đồng.
- Mang lại cho **anh em thành viên trong team thêm việc làm, thêm nguồn thu nhập** gắn bó lâu dài với dự án.

Vì vậy, ở vị trí PO, hãy luôn đối xử với mọi yêu cầu mới như **một cơ hội**, thay vì nhìn nó như một *"việc phiền hà"* làm xáo trộn kế hoạch của bạn.

---

## Tại sao bạn lại thấy phiền khi khách mở rộng yêu cầu?

Nếu đó là cơ hội tốt, tại sao phản xạ tự nhiên của nhiều PO và Dev vẫn là thở dài ngao ngán mỗi khi nghe khách nói *"Anh muốn làm thêm cái này..."*?

Cảm giác "phiền" đó thực ra không đến từ khách hàng, mà đến từ **3 nỗi sợ ngầm khi làm việc không có quy trình**:

1. **Sợ vỡ kế hoạch cũ vì tưởng phải "nhét chung vào rổ hiện tại":** Bạn nhìn bảng Sprint đã kín mít và hoảng hốt nghĩ rằng nhận thêm yêu cầu mới đồng nghĩa với việc bắt team thức đêm để kịp ngày Launch cũ. *Sự thật:* Yêu cầu mới `> 20h` có thời gian và nguồn lực tính riêng — khách hàng sẽ là người chọn hoặc làm ở milestone kế tiếp, hoặc dời ngày Launch tương ứng.
2. **Sợ kẹt giữa hai làn đạn tiền bạc (Khách hàng vs Anh em Dev):** Bạn ngại mở lời chuyện thu phí vì sợ khách phật lòng, nhưng nếu nhận làm không công thì áy náy vì anh em trong team phải gánh thêm việc. *Sự thật:* Bạn không phải tự đi mặc cả hay gồng một mình — đơn giá mở rộng **`$25/giờ`** là chuẩn minh bạch của công ty, và người quyết định tính phí hay tài trợ miễn phí là **AM (Anderson / Brian)** ở bước Approval.
3. **Sợ cảnh làm mò, sửa đi sửa lại không hồi kết:** Trước đây thấy mệt là vì khách mới nói vài câu trên cuộc họp đã vội giao dev code ngay, dẫn đến hiểu sai ý, đụng *side effects* dây chuyền. *Sự thật:* Khi bắt buộc đi qua **BRD** và **Estimate kèm buffer 30%–50%**, mọi rủi ro đã được soi sáng trước khi viết dòng code đầu tiên.

Hiểu rõ 3 điều này, bạn sẽ thấy quy trình 4 bước dưới đây chính là bộ giáp giải phóng bạn khỏi mọi sự "phiền hà" đó.

---

## Bước 1: `UNDERSTAND` — Khách nêu ý tưởng ngay trong buổi họp, bạn xử lý sao?

Tại Cyberk, phần lớn tính năng mới không đến từ email trang trọng, mà bật ra ngay **giữa buổi họp Daily Demo** khi khách nhìn thấy sản phẩm đang chạy thật trên màn hình.

Sai lầm lớn nhất của PO nằm ở **lời phản hồi ngay trên cuộc họp** và **sự im lặng sau khi tắt máy**.

**❌ Cách tồi (Ngay trong buổi họp với Jon):**

```
Jon: "Hey, watching the trading screen gave me an idea — can we add a Referral & 20% Fee Rebate dashboard so early users invite their friends?"

PO (Sai lầm 1 — Coi như việc phiền hà, chặn bằng hợp đồng):
"Hmm, Referral isn't in our v1 contract SoW Jon. If you want that, it'll be an extra paid request."

PO (Sai lầm 2 — Hứa ẩu không qua quy trình):
"Oh nice idea! Referral links are pretty simple, let me tell the devs to add it!"
```

Tại sao tồi: Sai lầm 1 biến cơ hội mở rộng doanh thu thành cuộc cãi vã hợp đồng. Sai lầm 2 tự trói tay cả team khi chưa biết logic chia phí 20% phức tạp cỡ nào. Và nguy hiểm không kém: trong họp chỉ ậm ừ *"Let me check"* rồi tắt máy im lặng — khiến Jon mặc định team đã nhận làm miễn phí!

👉 **Cách làm đúng của PO Cyberk:**
1. **Ngay trên buổi call:** Đón nhận cơ hội bằng sự hào hứng, rồi dành 10–15 phút hỏi rõ luồng mong muốn (*Ai được mời? Tính 20% trên phí nào? Trả thưởng lúc nào?*) để lấy đủ nguyên liệu viết **BRD** bằng skill viết BRD.
2. **Ngay sau buổi họp:** Gửi tin nhắn trên Telegram đính kèm **BRD** vừa viết, báo rõ **quy trình tiếp theo của Cyberk** (Tech Lead estimate trong 24h → Trình bày Proposal ngày mai) và **báo trước mức phí mở rộng tiêu chuẩn `$25/giờ`** để khách biết chừng.

**✅ Cách tốt (Lời đáp trực tiếp ngay trên buổi họp):**

```
PO: "Love that idea Jon — a 20% fee rebate loop right after launch will be huge for organic trader growth! Since this is a brand-new flow outside our v1 scope, let's take 10 minutes right now to map out how you want the rebate rules to work. Right after this call, I'll write up a clean BRD and have our Tech Lead estimate the hours within 24 hours so we keep your Nov 28 launch safe!"
```

> 📋 Xem mẫu tin nhắn gửi ngay sau buổi họp kèm mức `$25/hour`: [Bước 1 — Mẫu tin nhắn Understand](./feature-request-example.md#bước-1-understand--tiếp-nhận--làm-rõ-yêu-cầu)

---

## Bước 2: `ESTIMATE` — Làm sao lấy được con số chuẩn từ Tech Lead trong 24 giờ?

Sau khi có BRD, bạn chuyển sang cho Tech Lead ước lượng với **deadline tiêu chuẩn là 24 giờ**.

### Tại sao bắt buộc là 24 giờ?
Nhịp vận hành giữa khách hàng và team tại Cyberk xoay theo chu kỳ **24 giờ mỗi ngày** (họp chiều nay → chiều mai gặp lại). Phản hồi ngay trong phiên làm việc ngày kế tiếp giúp giữ nóng cảm hứng của khách, giữ tinh thần *responsive* của team và cho khách cảm nhận trực tiếp chất lượng dịch vụ cao cấp.

### Tại sao báo cáo của Tech Lead phải có đủ 4 hạng mục + Buffer 30%–50%?
Trong mắt khách hàng, tính năng mới đôi khi chỉ là *"thêm 1 màn hình lấy link mời bạn bè — chắc mất 4 tiếng"*. Họ không nhìn thấy phần chìm dưới mặt nước: thiết kế bảng dữ liệu mới, viết cronjob đối soát phí mỗi đêm, chặn gian lận tự tạo 2 ví mời nhau, kiểm thử lại toàn bộ luồng khớp lệnh cũ.

Vì vậy, đừng bao giờ nhận từ Tech Lead một con số trơ trọi kiểu *"Khoảng 30 tiếng em nhé"*. Con số đó đến từ danh sách task chi tiết của Milestone mới, làm theo [Tạo Milestone](../po-milestone-create/milestone-create-process.md). Danh sách task giữ nội bộ; khi trình khách, Tech Lead gom task lại thành **4 hạng mục**:
1. **Thiết kế UX/UI cần mở rộng**
2. **Thiết kế hệ thống cần thay đổi** *(nếu có)*
3. **Source code và side effects cần chỉnh sửa**
4. **Team effort** — Tổng số giờ của cả team, **đã cộng buffer 30%–50%** cho các phát sinh liên quan.

- **Chưa có BRD → Không bắt Tech Lead nhẩm mò:** Bắt ước lượng qua vài câu kể miệng chắc chắn sẽ bỏ sót *side effects* và hụt giờ thực tế.
- **Quá 24 giờ chưa xong → Báo ngay cho Anderson:** Đừng ép Tech Lead chốt đại một con số cho kịp giờ. Việc ước lượng vượt quá 24h là dấu hiệu cảnh báo một feature rất lớn chạm sâu vào kiến trúc lõi — hãy báo cáo Anderson để cùng đánh giá kỹ *side effects*, đồng thời chủ động nhắn hẹn lại khách trước khi hết 24h.

### Kinh nghiệm thực chiến: Làm tròn xuống 10%–15% kèm một lý do vui vẻ

Vì Tech Lead đã cộng sẵn **buffer 30%–50%** ở bước Estimate, team đã có vùng đệm an toàn cho các rủi ro phát sinh. Khi tính ra thành tiền (ví dụ `38 giờ × $25/giờ = $950`), thay vì giữ khư khư con số lẻ cứng nhắc, kinh nghiệm thực chiến là **chủ động làm tròn xuống khoảng 10%–15%** (từ `$950` xuống chẵn **`$800`** — thống nhất trước với AM ở bước Approval) kèm một lý do hài hước, thân tình: *"giảm vì hôm nay anh đẹp trai"*, hoặc *"làm tròn còn `$800`, lần tới sang Việt Nam nhớ mời team chầu cafe nhé!"*.

Mẹo nhỏ này giải quyết triệt để tâm lý nhạy cảm khi nói chuyện tiền nong:
- Khách hàng lập tức **cảm thấy mình được "hời"** ngay cả khi chưa mở lời mặc cả.
- Xóa tan cảm giác nặng nề rằng agency đang cố đếm từng giờ lẻ để **"bào tiền"** khách.
- Không khí buổi họp trở nên gần gũi như những người bạn làm sản phẩm cùng nhau, giúp khách gật đầu chốt phương án nhẹ nhàng hơn rất nhiều.

> 📋 Xem mẫu bàn giao cho Tech Lead và mẫu báo khách khi quá 24h: [Bước 2 — Mẫu tin nhắn Estimate](./feature-request-example.md#bước-2-estimate--phối-hợp-tech-lead--giữ-nhịp-24h)

---

## Bước 3: `APPROVAL` — Mang đến cho AM bức tranh đủ để quyết trong 2 phút

Trước khi trình bày với khách, bạn gửi BRD + Báo cáo Estimate cho **AM (Anderson / Brian)** duyệt ngân sách mở rộng và chốt mức chi phí. Tuỳ hoàn cảnh từng dự án, công ty có thể áp dụng mức phí mở rộng chuẩn **`$25/giờ`**, hoặc quyết định **tài trợ miễn phí** như một khoản đầu tư thiện chí cho khách hàng.

AM không ngồi họp hằng ngày với khách như bạn. Đừng đẩy lên một câu hỏi trống không kiểu *"24 tiếng này tính tiền hay free anh?"*. Hãy dọn sẵn đủ **4 dữ kiện** trong một lần trình duyệt:
1. **Link BRD** của tính năng mới.
2. **Tóm tắt 4 hạng mục Estimate** từ Tech Lead và tổng số giờ (đã gộp buffer).
3. **Chi phí quy đổi chuẩn** theo mức `$25/giờ`.
4. **Bối cảnh thực tế tại mặt trận:** Khách đang cần tính năng này vì mục tiêu kinh doanh gì (VD: sắp demo gọi vốn với quỹ đầu tư, hay chỉ là ý tưởng thêm thắt)? Nếu làm ngay có ảnh hưởng mốc Launch hiện tại không?

Đủ 4 mảnh này, AM có thể duyệt ngay lập tức để bạn kịp quay lại với khách trong nhịp 24h.

> 📋 Xem mẫu tin nhắn xin Approval chuẩn gửi AM: [Bước 3 — Mẫu tin nhắn Approval](./feature-request-example.md#bước-3-approval--xin-am-anderson--brian-duyệt-ngân-sách--mức-phí)

---

## Bước 4: `PROPOSAL` — Minh bạch 4 hạng mục trước khi nói đến tiền & Khóa sổ bằng Email

Khi bước vào buổi trình bày Proposal cho khách hàng, sự tự tin của bạn đến từ tính minh bạch. Dù hôm đó bạn báo thu phí hay báo tin vui được công ty miễn phí, hãy giữ vững **4 nguyên tắc**:

1. **Mở BRD và giải thích 4 hạng mục tác động TRƯỚC — Nói chi phí SAU:** Hãy dẫn khách đi qua từng màn hình UX/UI cần vẽ thêm, thay đổi kiến trúc hệ thống, những đoạn source code & *side effects* phải sửa để không làm hỏng luồng cũ, rồi mới chốt tổng giờ công của team. Khi khách thấy rõ khối lượng kỹ thuật đồ sộ bên dưới, phép nhân `số giờ × $25/giờ` trở nên hoàn toàn hợp lý.
2. **Chỉ công bố 1 con số tổng giờ duy nhất (đã gộp kín buffer 30%–50%):** Buffer là công cụ quản trị rủi ro nội bộ. Tách riêng dòng chữ *"buffer dự phòng"* trên màn hình trình bày chẳng khác nào mời khách gạch bỏ nó.
3. **Dù công ty duyệt Miễn phí, vẫn phải trình bày đủ 4 hạng mục và giá trị tương đương:** Đừng bao giờ nói *"Việc này nhỏ, bọn em làm giúp anh luôn"*. Hãy để khách thấy rõ đây là gói công việc 24 giờ trị giá `$600`, và Cyberk quyết định tài trợ trọn gói để tiếp sức cho cột mốc kinh doanh của họ. Khách sẽ trân trọng món quà đó gấp bội và không bao giờ xem nhẹ công sức của team ở các lần sau.
4. **Sau cái gật đầu của khách về chi phí → Bắt buộc gửi 1 Email chốt confirm:** Trên cuộc họp hay trong nhóm Telegram, khách nói *"Ok duyệt nhé, làm luôn đi em"* nghe rất nhanh gọn — nhưng 1 tháng sau đến kỳ thanh toán, tin nhắn trôi mất và bộ phận tài chính của khách có thể thắc mắc khoản phí phát sinh này ở đâu ra. Vì vậy, ngay khi khách vừa gật đầu đồng ý, bạn phải gửi **1 Email xác nhận chính thức** (đính kèm BRD, 4 hạng mục, mức phí đã thống nhất, lịch bàn giao và CC AM) để khách bấm reply *"Confirmed"*. Có email đó trong tay, tuyệt đối không bao giờ xảy ra tranh cãi về sau.

Cuối buổi trình bày, luôn trao cho khách **quyền tự quyết về lịch trình**: giữ nguyên ngày Launch hiện tại và làm tính năng mới ngay ở bản kế tiếp, hoặc gộp vào bản hiện tại và dời ngày Launch tương ứng với số giờ mở rộng.

> 📋 Xem mẫu trình bày Proposal (Tính phí / Miễn phí) và mẫu Email chốt confirm: [Bước 4 — Mẫu Proposal & Email Confirm](./feature-request-example.md#bước-4-proposal--trình-bày-brd-4-hạng-mục--chi-phí-cho-khách-hàng)

---

## Ngoại lệ nhạy cảm: Khi yêu cầu bị sai do khách mô tả nhầm hoặc hiểu lệch lúc giao tiếp

Trong thực tế làm dự án, chắc chắn sẽ có lúc team code đúng như những gì đã bàn ban đầu, nhưng khi lên buổi Demo khách hàng mới thốt lên: *"Chết rồi, lúc đầu anh diễn đạt nhầm ý..."* — hoặc giữa khách và team hiểu lệch nhau một khái niệm nghiệp vụ dẫn tới luồng làm ra không dùng được.

Xét thuần về giấy tờ, lỗi không nằm ở code của team. Nhưng nếu ở tình huống này bạn áp nguyên đơn giá thay đổi 100% như một tính năng mới bình thường, khách hàng sẽ cực kỳ dễ rơi vào cảm giác **"ấm ức"**: trong thâm tâm họ nghĩ đây là sự cố giao tiếp của cả hai phía (*"Mình không rành kỹ thuật nên nói chưa rõ, lẽ ra PO phải hỏi kỹ hơn chứ sao giờ bắt mình chịu phạt hết tiền sửa?"*) — từ đó mất sạch thiện cảm với cả đội ngũ.

**❌ Cách tồi (Tranh thắng thua trên câu chữ cũ):**

```
"Hi Jon, the team built this exact flow based on what you described in week 1. Rebuilding it will take 24 hours, so it will cost $600."
```

Tại sao tồi: Bạn thắng về lý nhưng thua đứt mối quan hệ. Khách trả `$600` trong sự ấm ức và cảm thấy team vô cảm, chỉ chăm chăm đổ lỗi để thu tiền.

👉 **Cách làm đúng của PO Cyberk:**
1. **Tuyệt đối không đôi co tìm người có lỗi** (*"tại anh nói thế"* hay *"tại em nghe nhầm"*). Tập trung ngay vào việc làm rõ lại luồng đúng trong **BRD** và nhờ Tech Lead tính số giờ cần chỉnh sửa (**Estimate**).
2. Khi trình **AM (Anderson / Brian)** ở bước **Approval**, hãy báo rõ nguồn gốc đến từ độ vênh giao tiếp và đề xuất một trong hai phương án thiện chí:
   - **Giảm giá sâu 50%:** Hai bên cùng chia sẻ mỗi bên một nửa công sức để sửa lại sản phẩm cho trọn vẹn.
   - **Hoặc miễn phí lần đầu (`$0`):** Hỗ trợ trọn gói ở lần lệch ý đầu tiên (kèm thống nhất cách xác nhận kỹ BRD cho các chặng sau).

**✅ Cách tốt (Lời dẫn thấu tình đạt lý với khách):**

```
"Hi Jon — glad we caught this gap early during today's demo! Misalignments like this can happen when translating a complex flow into screens. Reworking the settlement logic and UI takes 24 hours of team effort ($600 at our standard rate), but since we're in this together as partners, we'd like to split it 50/50 and cover half on our side — so just $300 to get it rebuilt exactly the way you envisioned."
```

Tại sao tốt: Khách vẫn thấy rõ khối lượng 24 giờ công team phải bỏ ra làm lại, nhưng hành động chủ động chịu một nửa (hoặc miễn phí lần đầu) xóa tan 100% sự ấm ức — biến một pha hiểu nhầm thành khoảnh khắc khách nể phục sự tử tế của Cyberk.

---

## Tóm lại

Toàn bộ cẩm nang xử lý Feature Request (`> 20h`) gói gọn trong bảng sau:

| Chặng | Cách nghĩ & hành động đúng của PO | Sai lầm cần tránh |
|-------|-----------------------------------|-------------------|
| **Tâm thế gốc** | Xem yêu cầu mới là **cơ hội tốt** (thêm doanh thu cho công ty, thêm việc cho anh em) | Coi yêu cầu mới của khách là *"việc phiền hà"* |
| **Ngoại lệ `< 8h`** | Các mục rất nhanh (*Terms & Policy, Forgot Password, 2FA cơ bản...*) → Đưa lên board làm luôn | Máy móc bắt khách họp viết BRD và thu phí lặt vặt |
| **1. UNDERSTAND** | Hào hứng làm rõ trong họp → Viết **BRD** → Nhắn sau họp báo quy trình tiếp theo & mức **`$25/giờ`** | Phủ đầu *"Ngoài hợp đồng"* hoặc họp xong im lặng không nhắn gì |
| **2. ESTIMATE** | Giao BRD để Tech Lead tính đủ **4 hạng mục + buffer 30%–50%** trong **≤ 24h** *(quá 24h báo Anderson)* | Bắt Tech Lead nhẩm mò khi chưa có BRD; quá 24h để khách tự hỏi |
| **3. APPROVAL** | Trình **AM (Anderson / Brian)** đủ BRD + 4 mục Estimate + mức phí `$25/h` + bối cảnh khách hàng | Hỏi trống không *"Ca này thu tiền hay free anh?"* |
| **4. PROPOSAL** | Trình bày **BRD + 4 hạng mục + tổng giờ** + chi phí → Khi khách gật đầu, **gửi Email chốt confirm** chờ khách reply xác nhận | Báo cục giá trơ trọi, lộ chữ *"buffer"*, hoặc chỉ chốt miệng trên call/chat mà không có Email lưu bằng chứng |
| **Lệch ý do giao tiếp** | Không đổ lỗi → Đề xuất với AM **giảm giá sâu 50%** (cùng san sẻ) hoặc **miễn phí lần đầu** để khách không thấy ấm ức | Đôi co *"anh đã duyệt spec cũ"* và bắt khách chịu 100% phí sửa đổi |

---

## Liên kết

- [Quy trình Tiếp nhận & Xử lý Feature Request](./feature-request-process.md) — Flowchart, vai trò, quy tắc cứng & checklist
- [Mẫu BRD & Báo giá mở rộng](./template/feature-request-brd-template.md) — File mẫu BRD kèm báo giá mở rộng cho PO copy sử dụng ngay
- [Mẫu tin nhắn Không Tốt vs Tốt](./feature-request-example.md) — Toàn bộ mẫu tin nhắn copy-paste với Jon qua 4 bước
