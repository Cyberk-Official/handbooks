# CyberK Handbook Playbook v2.0
### Bộ hướng dẫn để viết Handbook cho CyberK

> **Playbook này là gì:** hướng dẫn *CÁCH* viết một handbook tốt cho CyberK — nguyên tắc, template, và cách duy trì.
> **Playbook này KHÔNG phải:** handbook của CyberK. Handbook thật sẽ được viết SAU, dựa trên playbook này.

---

## Phần 0 — Cách dùng playbook này

Đọc Phần 1 (triết lý) trước để hiểu *tại sao*. Sau đó dùng Phần 3–4 (template + checklist) làm công cụ hằng ngày khi viết từng trang. Phần 6 (duy trì) đọc một lần rồi thiết lập. Phần 7 là lộ trình bắt đầu.

Nguyên tắc bao trùm, nhớ trước mọi thứ khác:

> **Bắt đầu nhỏ, lớn dần.**
> CyberK là công ty phần mềm sáng tạo quy mô nhỏ. Handbook không cần đồ sộ.
> Cái đáng có là *cơ chế tư duy đúng*, không phải *số lượng trang*.
> Một handbook 10 trang được dùng thật tốt hơn 200 trang nằm chết.

---

## Phần 1 — Bốn nguyên tắc nền tảng

Đây là "linh hồn" khiến handbook sống được. Thiếu chúng, handbook chỉ là một đống file Word chết.

### 1.1. Viết xuống TRƯỚC, thông báo SAU
Đảo ngược thói quen thông thường. Cách làm phổ biến: quyết định → thông báo qua họp/Slack → (thỉnh thoảng) mới viết tài liệu — và bước cuối hay bị bỏ quên. CyberK làm ngược: **viết giải pháp vào handbook trước, rồi mới thông báo bằng cách dẫn link**. Nhờ vậy không tồn tại bước "làm tài liệu sau" để mà quên.
- *Thực hành:* Khi có quyết định/quy trình mới, người phụ trách viết vào handbook trước, rồi mới gửi Slack kèm link. Câu cửa miệng: "Đã cập nhật handbook, xem ở đây."

### 1.2. Một nguồn thông tin duy nhất
Mỗi thông tin chỉ sống ở đúng một nơi. Mục tiêu: **không bao giờ tồn tại hai "phiên bản" của cùng một thứ** để phải phân vân bản nào mới. Mọi trùng lặp là kẻ thù. Khi phát hiện hai nơi cùng nói về một chuyện, gộp về một, và chỗ khác chỉ **link tới**, không copy lại.
- *Thực hành:* Không có "bản Google Doc riêng của team A" song song với handbook. Cần nhắc lại thông tin ở trang khác thì đặt link.

### 1.3. Không bao giờ hoàn thành (cải tiến liên tục)
Handbook là tài liệu sống, lớn dần. Sai lầm chết người là cố viết cho "đủ" rồi mới ra mắt — sẽ không bao giờ ra mắt. Thay vào đó: ra mắt sớm với vài trang, rồi bồi đắp từng quy trình một. Đa số mục sẽ trống lúc đầu, và **thế là bình thường**. Đừng chê một mục vì nó sơ sài; hãy ghi nhận người làm nó tốt hơn hôm qua một chút. Ghi chú riêng: tài liệu giá trị nhất thường sinh ra từ thất bại — sau mỗi sự cố, viết lại thành trang để lần sau không vấp.
- *Thực hành:* Ra mắt handbook trong tuần này với 3–5 trang, không đợi "xong". Mỗi tuần thêm/sửa vài trang.

### 1.4. Nói cả lý do, không chỉ nói làm gì
Mỗi trang không chỉ ghi "làm X" mà giải thích "vì sao làm X". Lý do giúp người đọc quyết định đúng trong tình huống mới mà trang chưa lường tới, và giúp người sau hiểu bối cảnh khi muốn sửa.
- *Thực hành:* Mọi quy trình/chính sách đều có một dòng "Tại sao có trang này".

### Kèm theo: Ai cũng được đề xuất sửa
Đây là điểm phân biệt handbook sống và tài liệu chết. Nếu chỉ vài người được sửa, nội dung sẽ lỗi thời và tạo tâm lý "phải hỏi mới chắc". Giải pháp: **tách vai trò người ĐỀ XUẤT và người DUYỆT**. Ai cũng đề xuất được (kể cả người mới); người chịu trách nhiệm trang mới là người duyệt. Mở cho đề xuất không nguy hiểm, vì luôn có người gác cổng. Người mới đề xuất còn mang lại góc nhìn tươi mới.
- *Thực hành:* Bất kỳ ai cũng đề xuất sửa được (qua Pull Request nếu dùng Git). Người phụ trách trang duyệt.

---

## Phần 2 — Nguyên tắc viết (giọng văn & hình thức)

- **Ngôn ngữ:** Tiếng Việt cho vận hành nội bộ/HR/quy trình; giữ nguyên thuật ngữ kỹ thuật tiếng Anh (code review, deploy, sprint, handoff...) thay vì dịch gượng.
- **Ngắn, trực tiếp, hành động được:** Câu ngắn. Động từ hành động. Tránh văn hoa.
- **Một trang = một chủ đề:** Đừng nhồi. Nếu một trang phình to, tách ra và đặt link.
- **Nhất quán định dạng:** Mọi trang cùng thể loại dùng chung template (Phần 3). Người đọc quen một trang là đọc được tất cả.
- **Mặc định mọi người đọc được:** Trong công ty, mặc định mọi người xem được mọi trang, trừ số ít thật sự nhạy cảm (lương, dữ liệu cá nhân). Minh bạch tạo tin tưởng và giảm việc hỏi đi hỏi lại.
- **Đúng tone kênh giao tiếp:** Mẫu tin nhắn cho Telegram viết kiểu chat — ngắn, thân thiện, có emoji. Mẫu cho email viết formal hơn. Không dùng lẫn.
- **Đặt tên file theo quy ước:** `[chủ-đề]-[loại].md` — VD `bug-handling-process.md`, `bug-handling-handbook.md`, `bug-severity-sla-handbook.md`. Nhìn tên file là biết nội dung gì và thuộc loại nào.

### Hệ thống 6 loại tài liệu

Mỗi trang trong handbook thuộc một trong 6 loại. Mỗi loại có mục đích và lúc đọc khác nhau:

| Loại | Ý nghĩa | Khi nào đọc | Hậu tố file |
|------|---------|-------------|-------------|
| **Process** | Quy trình chính thức — chart, bảng bước, vai trò, quy tắc cứng | Cần biết **luồng tổng thể** và ai làm gì | `-process.md` |
| **Handbook** | Cẩm nang — giải thích cách nghĩ, cách làm, mẫu tốt/tồi | Cần hiểu **cách thực hiện cụ thể** | `-handbook.md` |
| **Policy** | Chính sách — quy định, điều khoản, phạm vi áp dụng | Cần biết **quy định chính thức** | `-policy.md` |
| **Example** | Mẫu sẵn — tin nhắn, template, ví dụ tốt vs tồi | Cần **copy-paste** hoặc học cách làm đúng | `-example.md` |
| **Reference** | Bảng tra cứu — phân loại, SLA, deadline, labels | Cần **tra nhanh** một con số hoặc tiêu chuẩn | `-reference.md` |
| **Role** | Vai trò / team — trách nhiệm, handoff, cách cộng tác | Cần biết **ai làm gì** và phối hợp ra sao | `-role.md` |

> Không phải chủ đề nào cũng cần đủ 6 loại. Viết cái nào cần trước, bổ sung dần.

### Cấu trúc folder cho mỗi chủ đề

Một chủ đề phức tạp (nhiều file) nên gom thành folder:

```
handbook/[mục-lớn]/[chủ-đề]/
├── README.md                     ← Mục lục + giải thích các loại tài liệu
├── [chủ-đề]-process.md           ← Flowchart, bảng bước, quy tắc cứng
├── [chủ-đề]-handbook.md          ← Cẩm nang cách nghĩ, mẫu tốt/tồi
├── [chủ-đề]-example.md           ← Mẫu sẵn để copy-paste
└── [tên-cụ-thể]-reference.md     ← Bảng tra cứu
```

VD thực tế đã triển khai:

```
handbook/delivery/qa-bugs-handling/
├── README.md
├── bug-handling-process.md
├── bug-handling-handbook.md
├── acknowledgment-messages-example.md
└── bug-severity-sla-handbook.md
```

---

## Phần 3 — Bộ Page Template (dùng lại cho từng trang)

Sáu template tương ứng 6 loại tài liệu. Copy nguyên khối khi tạo trang mới.

### 3.1. Template — Trang QUY TRÌNH (Process / Workflow)
```
# [Tên quy trình — bắt đầu bằng động từ]

**Người chịu trách nhiệm:** [tên/vai trò — đúng MỘT người]
**Cập nhật lần cuối:** [ngày]
**Trạng thái:** [Nháp / Đang dùng / Ngừng dùng]

## Tại sao có trang này
[1–2 câu: quy trình này giải quyết vấn đề gì]

## Khi nào áp dụng (Trigger)
[Điều gì kích hoạt quy trình này]

## Vai trò & trách nhiệm
| Vai trò | Chịu trách nhiệm gì |
|---------|---------------------|
| ...     | ...                 |
[Định nghĩa vai trò TRƯỚC khi liệt kê bước]

## Các bước
| # | Việc làm | Ai làm | Đầu ra/Ghi chú |
|---|----------|--------|-----------------|
| 1 | ...      | ...    | ...             |

## Quy tắc cứng (không được vi phạm) + lý do
[Các quy tắc bất di bất dịch, mỗi cái KÈM lý do. VD: "người viết không tự duyệt việc của mình — để đảm bảo khách quan"]

## Checklist tự kiểm (nhúng ngay đây)
- [ ] ...

## Ngoại lệ & escalation
[Lệch khỏi luồng chính thì làm gì, hỏi ai]

## Liên kết
[Link tới template, trang liên quan — KHÔNG copy lại nội dung]
```

### 3.2. Template — Trang CHÍNH SÁCH (Policy)
```
# [Tên chính sách]

**Người chịu trách nhiệm:** [...]
**Cập nhật lần cuối:** [ngày]

## Tinh thần / Tại sao có chính sách này
[Mở bằng TINH THẦN trước điều khoản. Gắn với giá trị công ty nếu có]

## Phạm vi áp dụng (áp dụng cho ai)

## Nội dung chính sách
[Mọi con số phải CỤ THỂ, đo được: thời hạn báo trước, hạn mức... Tránh "sớm", "hợp lý"]

## Câu hỏi thường gặp (FAQ)

## Liên kết
[Trỏ sang chính sách liên quan thay vì nhồi nội dung]
```

### 3.3. Template — Trang VAI TRÒ / TEAM (Role / Team page)
```
# [Tên vai trò hoặc team]

**Người chịu trách nhiệm:** [...]
**Cập nhật lần cuối:** [ngày]

## Mục đích của vai trò/team
## Trách nhiệm chính
## Ai chịu trách nhiệm cho việc gì (bảng)
## Cách cộng tác / điểm giao tiếp với team khác (handoff)
## Liên kết
```

### 3.4. Template — Trang CẨM NANG (Handbook)

Dùng khi cần giải thích *cách nghĩ* và *cách làm* — không phải liệt kê bước khô khan mà nói chuyện trực tiếp với người đọc.

```
# [Tên chủ đề] — Cẩm nang cho [đối tượng]

**Người chịu trách nhiệm:** [...]
**Cập nhật lần cuối:** [ngày]
**Trạng thái:** [Nháp / Đang dùng / Ngừng dùng]

[1–2 câu mở đầu: người đọc đang ở đâu, tại sao cần đọc trang này]

## [Tình huống 1 — viết dạng câu hỏi]
[Giải thích cách nghĩ + hành động cụ thể]

✅ Cách tốt:
[Mẫu / ví dụ tốt]
Tại sao tốt: [...]

❌ Cách tồi:
[Mẫu / ví dụ tồi]
Tại sao tồi: [...]

## [Tình huống 2...]

## Tóm lại
[Bảng tóm tắt nhanh hoặc vài dòng gói gọn]

## Liên kết
[Link tới process, example, reference liên quan]
```

### 3.5. Template — Trang MẪU (Example)

Tập hợp mẫu sẵn để copy-paste. Mỗi mẫu có cặp tốt/tồi kèm giải thích.

```
# [Mẫu gì] — Tốt vs Không Tốt

**Người chịu trách nhiệm:** [...]
**Cập nhật lần cuối:** [ngày]

> Quy tắc: [nguyên tắc chung khi dùng mẫu — VD "viết kiểu chat, không kiểu email"]

## ✅ Mẫu TỐT

### 1. [Tình huống]
[Mẫu]
Tốt vì: [...]

### 2. [Tình huống...]

## ❌ Mẫu KHÔNG TỐT

### 1. [Anti-pattern]
[Mẫu tồi]
Tại sao tồi: [...]

## Nguyên tắc chung
[Bảng tóm tắt: Không nên → Nên]
```

### 3.6. Template — Trang TRA CỨU (Reference)

Bảng tra nhanh — con số, phân loại, tiêu chuẩn. Tối thiểu text, tối đa bảng và chart.

```
# [Tên bảng tra cứu] — Sổ tay cho [đối tượng]

**Người chịu trách nhiệm:** [...]
**Cập nhật lần cuối:** [ngày]

[1–2 câu: bảng này dùng để tra gì]

## Bảng phân loại
[Bảng chính — gom TẤT CẢ thông tin vào 1 bảng, tiết kiệm không gian]

## Chart phân loại (nếu cần)
[Mermaid flowchart giúp ra quyết định nhanh]

## Quy tắc đặc biệt
[Nâng/hạ/tạm dừng...]

## Liên kết
```

---

## Phần 4 — Checklist "một trang tốt" (tự kiểm trước khi publish)

- [ ] Tiêu đề rõ, (nếu là quy trình) bắt đầu bằng động từ
- [ ] Có **người chịu trách nhiệm** — đúng một người
- [ ] Có ngày cập nhật lần cuối
- [ ] Có mục "Tại sao có trang này" hoặc context mở đầu
- [ ] Không trùng lặp nội dung với trang khác — nếu trùng thì link, đừng copy
- [ ] Người mới đọc là làm được, không cần hỏi thêm
- [ ] Đủ chi tiết để dùng, nhưng không rườm rà
- [ ] Đã đặt link tới các trang liên quan
- [ ] Mẫu tin nhắn/template viết đúng tone kênh giao tiếp (chat ≠ email)
- [ ] Mỗi hướng dẫn quan trọng có cặp **tốt + tồi** kèm giải thích
- [ ] Tên file đúng quy ước `[chủ-đề]-[loại].md`

---

## Phần 4B — Công thức viết từng thể loại trang

Ba thể loại trang, mỗi loại có công thức riêng đã được kiểm chứng.

### 4B.1. Trang QUY TRÌNH
1. **Mở bằng mục đích, nêu tiêu chí chất lượng:** ngay đầu trang cho biết quy trình này hướng tới cái gì (VD: "để code hiệu quả, dễ hiểu, dễ bảo trì, an toàn"). Người đọc biết ngay *đích đến*.
2. **Phân vai rạch ròi TRƯỚC khi liệt kê bước:** một quy trình tốt định nghĩa vai trò, không chỉ liệt kê bước. VD với code review: Author (người viết) → Reviewer (soát domain) → người duyệt cuối (lo kiến trúc tổng thể, tính nhất quán). Mỗi vai một trách nhiệm khác nhau.
3. **Luồng tuần tự rõ:** ai làm gì ở mỗi chặng đều rõ.
4. **Quy tắc cứng tách khỏi hướng dẫn mềm, luôn kèm lý do:** VD "người viết code không được tự duyệt việc của mình" — và ghi rõ vì sao (đảm bảo khách quan). Khi có quy tắc bất di bất dịch, tách riêng.
5. **Nhúng checklist ngay trong trang:** để người thực hiện tự xác nhận đã cân nhắc các rủi ro. Đừng để checklist rời.
6. **Nhất quán tinh thần "nói lý do":** VD hướng dẫn viết comment code nên "giải thích *vì sao*, không giải thích *cái gì*".

### 4B.2. Trang CHÍNH SÁCH
1. **Mở bằng tinh thần/lý do, không mở bằng luật lệ:** VD chính sách nghỉ phép nên bắt đầu bằng *vì sao* nghỉ ngơi quan trọng, rồi mới tới quy tắc. Chính sách nêu *tinh thần* trước *điều khoản*.
2. **Overview ngắn trước, chi tiết sau.**
3. **Quy tắc cụ thể, đo được:** VD thời hạn báo trước rõ ràng ("báo trước số tuần tương ứng số ngày nghỉ"), tránh mơ hồ kiểu "báo sớm".
4. **Link tới chính sách liên quan thay vì nhồi:** một chính sách trỏ sang chính sách khác, không copy nội dung.
5. **Chính sách cũng được cải tiến như code:** ghi ngày cập nhật, sửa khi thấy chưa hợp lý, kèm lý do sửa.

### 4B.3. Trang VAI TRÒ / KHÁI NIỆM
1. **Định nghĩa một câu, sắc gọn:** VD "người chịu trách nhiệm chính là người ra quyết định cuối cùng cho một việc — *không phải* người làm hết mọi việc". Định nghĩa loại bỏ hiểu lầm ngay.
2. **Nêu rõ nó khác cách cũ thế nào:** khi giới thiệu khái niệm mới, giải thích vì sao nó tốt hơn cách làm cũ.
3. **Cân bằng quyền và nghĩa vụ:** VD người chịu trách nhiệm được toàn quyền quyết, nhưng có nghĩa vụ tham vấn, cộng tác, và báo lên khi bị chặn. Tránh hiểu lầm "toàn quyền = độc đoán".
4. **Minh họa bằng ví dụ thật:** một ví dụ cụ thể làm khái niệm trừu tượng trở nên nắm được.
5. **Kết bằng hành động làm được ngay:** VD "khi được giao việc, hãy xác nhận rõ mình có phải người chịu trách nhiệm không, và được quyết những gì".

### Công thức chung cho MỌI trang tốt
- **Mở bằng lý do** (mục đích/tinh thần), không mở bằng luật.
- **Vai trò rõ ràng** trước khi liệt kê bước.
- **Cụ thể, đo được** ở mọi con số và quy tắc.
- **Link, đừng copy** khi chạm nội dung ở trang khác.
- **Kèm ví dụ thật** cho những gì trừu tượng.
- **Kết bằng hành động** người đọc làm được ngay.
- **Quy tắc cứng tách riêng + luôn kèm lý do.**

---

## Phần 5 — Từ vựng chung của CyberK

Bộ khái niệm cốt lõi để cả công ty nói cùng một ngôn ngữ.

| Khái niệm | Nghĩa | Vì sao quan trọng |
|---|---|---|
| **Người chịu trách nhiệm chính** | Một cá nhân chịu trách nhiệm trực tiếp cho một việc/trang | Mỗi việc có đúng 1 người → không đùn đẩy, không mơ hồ ai quyết |
| **Nguồn thông tin duy nhất** | Mỗi thông tin chỉ sống ở một nơi | Xóa nhầm lẫn "bản nào mới nhất" |
| **Viết-trước** | Viết xuống trước, thông báo sau | Tài liệu không bao giờ bị bỏ quên |
| **Cải tiến liên tục** | Sửa từng bước nhỏ, thường xuyên | Handbook ra mắt sớm và lớn dần, không chết yểu |
| **Đề xuất sửa** | Ai cũng đề xuất được, người phụ trách duyệt | Đóng góp mở nhưng vẫn có kiểm soát |

---

## Phần 6 — Cách giữ handbook SỐNG (phần dễ bị bỏ quên nhất)

Handbook chết là vì không ai duy trì. Thiết lập những thứ sau ngay từ đầu:

**6.1. Chọn công cụ.**
- *Nếu team quen Git và muốn handbook có lịch sử thay đổi như code:* dùng Git + Markdown (review qua Pull Request, giống review code).
- *Nếu muốn nhẹ nhàng, ai cũng sửa được ngay:* Notion hoặc Confluence. Đánh đổi: kiểm soát phiên bản yếu hơn Git.
- **Khuyến nghị:** công ty phần mềm như CyberK nên nghiêng về Git/Markdown để tận dụng văn hóa review sẵn có; nhưng nếu ưu tiên tốc độ áp dụng cho cả người không code, Notion là khởi đầu hợp lý.

**6.2. Chỉ định một người biên tập handbook.** Một người giữ vai trò biên tập tổng, đảm bảo nhất quán style và cấu trúc. Với công ty nhỏ, đây có thể là kiêm nhiệm, không cần cả một team.

**6.3. Gán người chịu trách nhiệm cho từng phần.** Mỗi mục lớn có một người chịu trách nhiệm cập nhật và duyệt đề xuất.

**6.4. Biến "viết-trước" thành thói quen công ty.** Quy ước: bất kỳ câu trả lời/giải pháp nào chưa được ghi lại thì cần được ghi lại. "Nó có trong handbook chưa?" trở thành câu hỏi phản xạ.

**6.5. Chốt quyết định từ chat vào handbook.** Thảo luận nhanh trong Slack là bình thường, nhưng quyết định quan trọng phải được chốt lại vào handbook trong vòng 48h — nếu không, kiến thức sẽ tan biến trong luồng chat và mọi người lại hỏi đi hỏi lại.

**6.6. Nhịp review.** Mỗi trang có ngày cập nhật; định kỳ (VD mỗi quý) người phụ trách rà lại phần của mình. Trang lỗi thời đánh dấu rõ.

---

## Phần 7 — Lộ trình triển khai (Bắt đầu nhỏ, lớn dần)

**Cấu trúc mục lục khởi đầu:**

```
CyberK Handbook
├── 1. Công ty (Nền tảng)
│   ├── Câu chuyện & sứ mệnh, tầm nhìn, giá trị cốt lõi
│   ├── Chúng ta phục vụ ai (khách hàng)
│   ├── Điều gì làm CyberK khác biệt
│   └── Cách chúng ta giao tiếp & công cụ dùng
├── 2. Con người
│   ├── Onboarding / Offboarding
│   ├── Chính sách nghỉ phép, làm việc
│   └── Cách tuyển dụng
├── 3. Delivery (Design → Code → Ship)   ← lõi của CyberK
│   ├── Quy tắc handoff Design → Dev → QA → Ship
│   ├── Definition of Ready / Definition of Done
│   ├── Code Review Guidelines
│   └── Design Doc template
├── 4. Khách hàng
│   ├── Quy trình báo giá / hợp đồng
│   ├── Kickoff dự án
│   └── Bàn giao & nghiệm thu
└── 5. Về Handbook
    ├── Cách đóng góp / sửa handbook
    ├── Style guide
    └── Danh sách người chịu trách nhiệm theo từng phần
```

**Thứ tự viết đề xuất (5 trang đầu tiên, làm ngay tuần này):**
1. Trang "Cách đóng góp handbook" (mục 5) — vì nó khiến mọi trang sau nhân rộng được
2. Giá trị cốt lõi + cách giao tiếp (mục 1) — la bàn văn hóa
3. Onboarding (mục 2) — dùng ngay cho người mới, giá trị cao nhất
4. Quy tắc handoff Design→Code→Ship (mục 3) — đau nhất với công ty outsourcing
5. Quy trình kickoff dự án (mục 4) — điểm chạm khách hàng đầu tiên

**Sau đó:** mỗi tuần thêm 2–3 trang, ưu tiên theo "cái gì đang hay bị hỏi lại nhiều nhất".

---
*Playbook v2.0 — dành riêng cho CyberK. Đây là tài liệu sống: chính playbook này cũng nên được cải tiến khi CyberK bắt đầu viết handbook thật và rút ra bài học.*