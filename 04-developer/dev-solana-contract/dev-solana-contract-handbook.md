---
type: handbook
tags: [solana, smart-contract, handbook, developer]
created-date: 2026-11-19
updated-date: 2026-11-19
author: anderson
status: Nháp
---

# Solana contract — Cẩm nang cho Lead, Dev, Reviewer

**Người chịu trách nhiệm:** Anderson (mặc định theo [owners-reference](../../02-about-handbook/owners-reference.md), chưa gán owner riêng)
**Cập nhật lần cuối:** 2026-11-19
**Trạng thái:** Nháp

Bạn đang làm theo [quy trình Solana contract](./dev-solana-contract-process.md) và muốn biết vì sao mỗi bước tồn tại, làm thế nào cho đúng, và những chỗ người đi trước đã vấp. Trang này trả lời từng câu đó, phần lớn bằng chuyện thật của dự án Flux (một program Solana đi từ thiết kế đến devnet trong 11/2026).

**Nhãn nguồn** dùng trong trang:
`Flux` đã làm và đo trên dự án Flux · `Skill` skill `solana-dev` v2.8.0 của Solana Foundation · `Audit research` nghiên cứu phương pháp audit nội bộ của Cyberk · `Ngoài` tài liệu công khai · `Chưa kiểm` chưa đọc được nguồn gốc.

---

## "Đo trước khi tin" trông như thế nào?

Mỗi claim kỹ thuật trong doc thiết kế, báo cáo spike, báo cáo audit đều mang một nhãn: `[V]` đã kiểm, `[ER]` suy luận, `[U]` chưa biết. `[V]` phải đi kèm thứ người khác chạy lại được.

Lý do không phải hình thức. Ở Flux, một worker đọc docs và SIMD rồi kết luận "swap vẫn dùng v0 + ALT, tx v1 chỉ hợp tx nhỏ" (nhãn `[ER]`). Một worker khác gửi tx thật trên fork mainnet: tx swap dạng Flux vượt 1.232 B ở route 3-split và 2-hop, còn với v1 thì mọi route đều vừa. Thiết kế chốt dùng v1. Nếu claim đầu không mang nhãn `[ER]`, không ai biết nó cần được đo. `Flux`

**✅ Cách tốt:**

```
Tx swap lớn nhất đo được: 2.275 B (Titan, Raydium CLMM 3-split), vừa 4.096 B của tx v1.
[V] gửi thật trên fork mainnet 10/11/2026, số đo thô trong raw/, lệnh chạy lại ở §7.
```

Tại sao tốt: có con số, có điều kiện đo, có ngày, có chỗ để chạy lại.

**❌ Cách tồi:**

```
Dùng ALT thì số account không bị giới hạn nữa.
```

Tại sao tồi: không nhãn, không nguồn, và sai. Doc thiết kế đầu tiên của Flux có đúng câu này; thực tế mỗi tx khóa tối đa 64 account, tính cả account nạp qua ALT. `Flux`

---

## Thiết kế: vì sao account trước, code sau?

Trên EVM, state nằm trong contract. Trên Solana, program không giữ state: mọi dữ liệu nằm trong account được truyền vào từng instruction, và kẻ tấn công chọn được account nào sẽ truyền vào. Vì vậy danh sách account của từng instruction **chính là** bề mặt tấn công. Viết nó ra trước khi code thì review được bằng mắt; để nó lẫn trong code thì chỉ thấy khi đã muộn.

Doc thiết kế cần trả lời đủ bốn nhóm câu hỏi: `Skill`

| Nhóm | Phải trả lời |
|------|--------------|
| **State** | Chia dữ liệu thành những account nào? Seed PDA là gì, bump canonical lưu ở đâu? Kích thước, có realloc không, state machine ra sao? |
| **Rent và vòng đời** | Ai trả rent khi tạo? Ai được đóng, lamports về đâu? |
| **Từng instruction** | Account nào signer, account nào writable? CPI sang program nào, PDA nào ký? Phát event gì? |
| **Token và song song** | SPL Token hay Token-2022, xử lý extension nào? Có account global nào bị ghi ở mọi tx không (khóa ghi làm mất tính song song)? |

Ba bài học thiết kế của Flux: `Flux`

- **"Ai được đóng account" là câu hỏi bảo mật.** Trên EVM, dấu "grant đã revoke" nằm trong storage mãi mãi. Trên Solana account đóng được, và đóng account làm mất luôn dấu revoke, nên grant có thể bị đăng ký lại. Flux phải thêm một bất biến riêng: grant đã revoke mà chưa hết hạn thì không được đóng.
- **Mô hình tin cậy phải do owner chốt, kèm đánh đổi.** Owner Flux chọn cả hai program upgradeable, upgrade authority ở một multisig Squads có time_lock. Bảng quyết định ghi thẳng hệ quả: người giữ multisig đó thay được code, nên user phải tin multisig. Không ai phải đoán lại chuyện này về sau.
- **Chừa chỗ cho tương lai ngay từ đầu.** Flux thêm vùng reserved vào các account sống lâu (Vault, Grant, Config) để upgrade sau thêm field mà không phá layout.

**✅ Cách tốt** (ví dụ minh hoạ một dòng của bảng instruction × account):

```
withdraw(amount)
  vault       PDA ["vault", vault_id]                  writable
  owner       signer, phải khớp vault.owner
  vault_ata   token account, authority = vault         writable
  recipient   phải là địa chỉ đã đăng ký và đang active  writable
  CPI         Token transfer_checked, ký bằng vault PDA
  Event       Withdrawn
```

Tại sao tốt: nhìn là biết ai ký, cái gì bị ghi, kiểm gì, tiền đi đâu. Reviewer hỏi được "nếu `recipient` là account khác thì sao" mà không cần đọc code.

**❌ Cách tồi:**

```
withdraw: owner rút tiền từ vault về ví.
```

Tại sao tồi: không có account nào, không có điều kiện nào. Mọi lỗ hổng kinh điển của Solana (thiếu owner check, thiếu signer check, account trùng) đều trốn được trong câu này.

---

## Spike: khác gì với viết thử program?

Spike là code nháp, viết ra chỉ để trả lời "có chạy được không, tốn bao nhiêu". **Đầu ra của spike là thay đổi trong doc thiết kế, không phải code.** Code spike không đem đi deploy.

Cách làm: `Flux`

1. Đặt câu hỏi cụ thể, đo được, lấy từ các giả định `[ER]` / `[U]` của thiết kế.
2. Dựng harness trên fork mainnet, gửi tx thật, lưu số đo thô ra file kèm lệnh chạy lại.
3. Ghi luôn gotcha của toolchain gặp trên đường.
4. Mỗi phát hiện kèm một dòng "sửa ở đâu trong doc thiết kế".

Flux chạy ba spike song song (CPI swap trên fork, fact-check giới hạn runtime và dependency, thử hai fuzzer). Một phần kết quả: `Flux`

| Câu hỏi | Đo được | Thiết kế đổi thế nào |
|---------|---------|----------------------|
| Tx swap có vừa không? | Vượt 1.232 B ở route 3-split và 2-hop; mọi route vừa 4.096 B | Swap dùng tx v1, bỏ ALT |
| Trần thật nằm ở đâu? | 64 account mỗi tx, không phải số byte. Wrapper thêm khoảng 14 account; tham số `maxAccounts` của Jupiter chỉ gần đúng (đặt 24 ra 30) | Giới hạn số account của route; client đếm trước khi gửi |
| CPI sâu mấy tầng? | Mình → Titan → Jupiter → DEX → Token vừa đúng trần | Bỏ program router trung gian |
| Program bên ngoài có trên devnet không? | Jupiter và Titan không có; địa chỉ đó trên devnet là account rỗng | e2e swap chạy trên fork mainnet |
| Oracle cập nhật nhanh cỡ nào? | Pyth push feed heartbeat 60 giây; doc đặt `max_age = 10` nên gần như luôn revert | Đổi tham số |
| Fuzzer nào chạy được binary sẽ deploy? | Trident rc.4 không nạp được sBPF v3; Crucible nạp được | Chọn Crucible |

Các con số giới hạn nằm ở [bảng giới hạn runtime](./solana-runtime-limits-reference.md).

**Review thiết kế trước khi code.** Sau khi doc đã sửa theo số đo, một reviewer phản biện doc cùng báo cáo spike. Lead phân loại từng ý: sửa, không sửa kèm lý do, hoặc hỏi owner. Ở Flux lượt này ra 0 Critical, 4 High, 7 Medium, 1 Low, tất cả trước khi program có dòng code nào. Một finding ví dụ: giá qua nhiều hop phải tính trong miền giá, không cộng tick hay bin của các pool có bin step khác nhau. `Flux`

**✅ Cách tốt:**

```
Tx swap qua aggregator, route 2 hop, kèm 6 account của mình và tip, có vừa 1.232 B không?
Nếu không: cần ALT nào, hay chuyển sang tx v1?
```

Tại sao tốt: trả lời được bằng một lần đo, và câu trả lời dẫn thẳng đến một quyết định thiết kế.

**❌ Cách tồi:**

```
Tìm hiểu giới hạn transaction của Solana.
```

Tại sao tồi: không biết khi nào xong, và kết quả sẽ là một bài tổng hợp từ docs, đúng thứ mà spike sinh ra để thay thế.

---

## Build: pin những gì, và ba tầng test bắt được gì?

### Pin toolchain

Pin đủ: Rust toolchain, Anchor, Solana CLI, platform-tools, **kiến trúc sBPF**, và version của từng crate test, fuzz. Mục tiêu là một câu: *binary đã test trùng binary sẽ deploy.*

Stack Flux đã chạy được (11/2026, sẽ cũ dần): Anchor 1.2.2 build sBPF v3 · Solana CLI 4.1.2 · LiteSVM 0.15 và Mollusk `=0.14.0` cho unit test · Surfpool 1.7.0 cho fork mainnet · Crucible `0.3.0-alpha.1` cho fuzz · Codama + `@solana/kit` sinh client · `solana-verify` 0.5.2 · Squads v4. `Flux`

Vì sao phải pin từng thứ: template Anchor kéo về Mollusk 0.10, bản này báo `invalid file header` với ELF sBPF v3. Image Docker của `solana-verify` mang platform-tools v1.54 trong khi Anchor dùng v1.57, phải truyền thêm tham số. Không phát hiện sớm thì CI xanh trên một binary khác với bản deploy. `Flux`

### Thứ tự code

Phần lõi trước (state, phân quyền), phần tích hợp sau (CPI, oracle, Token-2022). Trong lúc code, mỗi instruction phải trả lời được: `Skill`

| Lỗ hổng | Câu hỏi |
|---------|---------|
| Thiếu owner check | Account này có đúng do program mong đợi sở hữu không? |
| Thiếu signer check | Người có quyền đã ký chưa? |
| Arbitrary CPI | Program được gọi có đúng program ID mong đợi không? |
| Reinitialization | Có khởi tạo lại được account đã tồn tại không? |
| PDA sharing, bump | Seed có đủ riêng cho từng user không? Bump có canonical không? |
| Type cosplay | Có kiểm discriminator để không nhận nhầm loại account không? |
| Duplicate mutable | Hai tham số writable có thể là cùng một account không? |
| Revival | Account đã đóng có bị "hồi sinh" trong cùng tx không? |
| Data matching | Quan hệ giữa các account có được kiểm không? |

### Ba tầng test

| Tầng | Công cụ | Bắt được | Không bắt được |
|------|---------|----------|----------------|
| **Unit** | LiteSVM, Mollusk | Từng instruction, đường lỗi (sai signer, sai owner, account trùng, 0 và max), CU | Hành vi của program bên ngoài; giới hạn kích thước tx (LiteSVM không chặn) |
| **Fork** | Surfpool fork mainnet | CPI sang program thật, giới hạn byte và account của tx | Chuỗi thao tác hiếm |
| **Fuzz** | Crucible | Vi phạm bất biến sau nhiều bước, tổ hợp mà người viết test không nghĩ tới | Thứ không được viết thành bất biến |

Một ví dụ vì sao cần cả fuzz: Flux có một lỗi `UnbalancedInstruction` ở lệnh đổi owner, chỉ xảy ra khi người trả phí và người nhận lại rent là cùng một account. Unit test luôn dùng hai account khác nhau nên không thấy; fuzzer dùng chung một relayer nên bắt được. `Flux`

### Planted control

Planted control là một bản build cố tình cài bug (bật bằng cargo feature), dùng để chứng minh fuzzer **có khả năng** bắt loại bug đó. Fuzz xanh mà không có control thì không phân biệt được "program đúng" với "fuzzer mù".

Cách Flux làm: `Flux`
- Mỗi bất biến quan trọng có ít nhất một control. Gate bắt đầu ở 19/19, sau các lượt review tăng lên 30/30.
- Mỗi control phải bị bắt trong thời gian có trần (Flux đặt dưới 60 giây). Control nào bắt chậm thì sửa harness cho dễ tới, không tăng timeout.
- Finding của audit trở thành control mới, để lần sau không lọt lại.
- Kiểm kết quả bằng nội dung log (`FUZZ_FINDING`), không bằng exit code.

**✅ Cách tốt:**

```
Bản build có feature bug-owner (withdraw bỏ kiểm owner): fuzzer bắt ở lần chạy thứ 8, sau 1,1 giây.
Bản build đúng: 60 giây, 0 vi phạm.
```

Tại sao tốt: có cả phép thử dương (bắt được bug) lẫn phép thử âm (không báo oan).

**❌ Cách tồi:**

```
Fuzz chạy 1 giờ, exit code 0, không có crash.
```

Tại sao tồi: Crucible `0.3.0-alpha.1` thoát với exit code 0 cả khi tìm ra crash. Và kể cả khi không có crash thật, chưa có gì chứng minh fuzzer tới được chỗ có bug. `Flux`

---

## Audit: làm sao để lượt review không thành thủ tục?

### Đóng băng và brief

Chọn một commit pin, đóng băng code program. Reviewer ghi finding theo `file:dòng` tại pin đó; sửa code giữa chừng làm lệch dòng. Trong lúc đóng băng, Flux chỉ cho sửa harness fuzz. `Flux`

Brief gửi reviewer gồm: scope kèm commit pin, spec cần đọc, và danh sách **claim có giới hạn** (nói rõ điều gì được khẳng định và điều gì không). Viết bằng ngôn từ trung tính, đứng từ phía người giữ tài sản.

**✅ Cách tốt:**

```
Bao nhiêu giá trị có thể rời vault ngoài phạm vi grant, và kiểm tra X có chặn được không?
```

**❌ Cách tồi:**

```
Code đã test kỹ, nhờ mọi người xác nhận là an toàn.
```

Tại sao tồi: câu này mời reviewer đồng ý. Reviewer nhận sẵn kết luận thường trả lại đúng kết luận đó.

### Vì sao cần nhiều reviewer độc lập

Mỗi reviewer làm trên bản sao riêng tại pin, không đọc báo cáo của nhau; hash của từng báo cáo được chốt trước khi gộp. Ở lượt 1 của Flux (3 reviewer), trong 19 mục finding có 7 mục chỉ một reviewer tìm ra, gồm cả finding Medium duy nhất. Một lượt đọc không phải là độ phủ. `Flux`

### Vì sao fix xong phải verify lại

Lượt 1 của Flux không có Critical hay High. Sau khi fix, cả 3 reviewer verify độc lập: 11 finding được xác nhận đã đóng, nhưng **cả 3 cùng tìm ra một lỗ hổng mới nằm trong chính bản fix** của guard oracle (lỗi logic trong chuỗi clamp). Cả 3 cũng tìm thêm một lỗi chưa có trong báo cáo lượt 1: reader oracle cấp phát bộ nhớ theo dữ liệu mà ai cũng nới được, làm swap hết heap. Bản fix là code mới, chưa ai review; nó cần được review như mọi code khác. `Flux`

Sau khi sạch, Flux chạy thêm một lượt simplify (một người tìm chỗ thừa, một người khác phân xử): program bớt 194 dòng, CU của swap giảm 2,7–5,7%, lượt verify cuối không còn gì trên mức Info. Lượt này là tùy chọn. `Flux`

### Gợi ý phương pháp cho reviewer

Thay vì đọc cả repo một lượt, dựng bảng mô hình rồi quét từng hàng. Đơn vị công việc là một đối tượng cụ thể (một instruction, một biến, một chỗ CPI), không phải một chủ đề trên cả repo. `Audit research`

| Bảng mô hình | Mỗi hàng là |
|--------------|-------------|
| M1 Entry point | Mỗi instruction đổi state: ai gọi được, điều kiện, giới hạn input, tiền đi đâu |
| M2 State | Mỗi biến: ý nghĩa, mọi chỗ ghi, biến nào phải nhất quán với nó |
| M3 Dòng tiền | Mỗi chỗ chuyển tiền: tài sản, từ đâu, đến đâu, số lượng |
| M4 Đơn vị | Decimals, scale (bps…), hướng làm tròn |
| M5 External call | Mỗi CPI: target lấy từ đâu, giả định gì về kết quả |
| M6 Role | Mỗi quyền và tham số: ai giữ, giới hạn on-chain, thiệt hại nếu mất key |

| Lượt quét | Tỷ lệ finding Critical/High | Câu hỏi cho từng hàng |
|-----------|------|------------------------|
| Guards | 30% | Ai gọi được, ở trạng thái nào, cái gì chặn trường hợp xấu? Hàm anh em có kiểm giống nhau không? |
| Math và đơn vị | 24% | Đơn vị hai vế có khớp? Làm tròn có lợi cho ai? Chuyện gì xảy ra ở 0, 1, max? |
| Cập nhật state | 19% | Biến có được cập nhật ở mọi nhánh trước khi bị đọc không? |
| External boundary | 12% | Giả định gì về program được gọi, và nó thật sự làm gì? |
| Giá và kinh tế | 10% | Người gọi có xê dịch được con số này trong một tx và lời không? |
| Liveness | 10% | Cái gì làm đường rút tiền revert mãi, và ai điều khiển nó? |
| Config và trust | 5% | Nếu giá trị này sai hoặc key bị lộ thì mất tối đa bao nhiêu? |
| Chữ ký và message | 3% | Hash ràng buộc những gì, replay được ở đâu? |

Lưu ý khi dùng:
- Tỷ lệ trên là số chung mọi ngôn ngữ, dùng để xếp thứ tự công việc. Riêng Rust trên Solana: 1.603 finding trong cơ sở dữ liệu, 11% là Critical/High; nhóm lỗi lớn nhất là business logic 28%, input validation 15%, accounting 15%, access control 12,5%. Pattern gặp nhiều nhất: thiếu kiểm state, thiếu kiểm input, truyền sai tham số, thiếu phân quyền, account bị khởi tạo lại.
- Finding do người (hoặc agent) khác cố bác bỏ trước, rồi mới chứng minh. Không có PoC chạy được thì tối đa Medium.
- Phương pháp bảng và lượt quét là thiết kế từ nghiên cứu, **chưa được đo hiệu quả** trên benchmark. Reviewer của Flux được tự chọn phương pháp.

---

## Launch: deploy đúng cái đã audit nghĩa là gì?

> ⚠️ Flux chưa deploy mainnet. Trong mục này, phần nhãn `Flux` đã kiểm trên devnet hoặc trên máy; phần nhãn `Ngoài` lấy từ tài liệu công khai; các lệnh CLI đã đối chiếu với `--help` của Solana CLI 4.1.2 và `solana-verify` 0.5.2.

Là giữ được một chuỗi không đứt: **commit đã audit → build trong Docker → hash của file `.so` → deploy → hash on-chain.** Đứt một mắt thì báo cáo audit không còn nói về code đang chạy.

### Build artifact

- Build bằng `solana-verify build` trong Docker, cùng kiến trúc sBPF và platform-tools với lúc test. Lấy hash bằng `solana-verify get-executable-hash`. `Flux`
- **Build trên macOS không bao giờ khớp hash với Docker.** Flux so từng byte: thư viện std dựng sẵn của platform-tools nhúng đường dẫn khác nhau giữa macOS và Linux. `Flux`
- **Build trên một checkout sạch, tách riêng.** Lệnh build mount thư mục đang làm việc suốt thời gian chạy (khoảng 16 phút ở Flux); sửa file trong lúc đó thì thay đổi lọt vào `.so` trong khi hash vẫn ghi tên commit cũ. `Flux`
- Đừng chạy build thường đè lên artifact sau đó.

### Deploy

- Deploy đi qua một buffer account, không atomic. Đứt giữa chừng: tìm buffer bằng `solana program show --buffers`, deploy tiếp với `--buffer`, đóng buffer thừa bằng `solana program close --buffers` để lấy lại SOL. `Ngoài`
- Keypair của program và của deployer nằm ngoài repo. `Flux`

### Upgrade authority

- Chuyển sang multisig bằng `solana program set-upgrade-authority`. Vault của multisig là PDA, không ký được, nên phải dùng cờ `--skip-new-upgrade-authority-signer-check`; nhập sai địa chỉ là mất quyền upgrade `[ER]`. Đây là lý do phải diễn tập trên devnet trước.
- Muốn program bất biến thì dùng `--final`. Không đảo ngược được.
- Kiểm lại bằng `solana program show <PROGRAM_ID>`.

Những điều Flux đã kiểm trong source của Squads v4: `Flux`
- time_lock đếm từ lúc đủ ngưỡng approve, không phải từ lúc tạo proposal.
- Không có đường tắt qua time_lock trong cùng một multisig. Hệ quả: quyền pause khẩn cấp phải nằm ở một key nóng hoặc một multisig riêng có time_lock 0.
- Upgrade về sau: ghi buffer, chuyển buffer authority cho vault của multisig, tạo proposal, **so hash của buffer với hash artifact trước khi approve** (`solana-verify get-buffer-hash`), chờ time_lock, execute.

Flux tách ba vai: một multisig có time_lock giữ quyền upgrade và admin, một multisig time_lock 0 giữ quyền unpause, và key nóng chỉ được pause và thu hẹp quyền. Owner chốt time_lock mainnet 3.600 giây, thấp hơn mức mà chuẩn bên dưới đặt cho protocol lớn; đánh đổi này được ghi trong bảng quyết định. `Flux`

Diễn tập devnet của Flux bắt được một lỗi vận hành: vault của multisig unpause chưa có SOL nên lệnh unpause fail cho đến khi nạp tiền. Lỗi kiểu này chỉ lộ khi chạy thật đủ các bước multisig. `Flux`

### Chuẩn tham khảo cho multisig

Solana Operational Security Standard (SOS, do Accretion viết và duy trì) chia bốn cấp theo Funds at Risk, tức số tiền tối đa mất được nếu protocol bị chiếm hoàn toàn, không phải TVL. `Ngoài`

| | L1 Baseline | L2 Managed | L3 Hardened | L4 Critical |
|---|---|---|---|---|
| Dành cho | Team chưa launch | Đa số protocol đang giữ tiền user | Lending, liquid staking, perps, từ 25 triệu USD | Stablecoin, bridge, oracle, từ 100 triệu USD |
| Multisig giữ upgrade authority, tối thiểu | 2-of-3 | 3-of-5 | 4-of-7 | 5-of-9 |
| Time lock cho program upgrade | Tùy chọn | Tùy chọn | Bắt buộc, ≥ 48 giờ | Bắt buộc, ≥ 72 giờ |
| Tách multisig upgrade và treasury | Nên | Bắt buộc | Bắt buộc | Bắt buộc |
| Guardian multisig cho việc khẩn cấp | Tùy chọn | Nên | Bắt buộc | Bắt buộc |
| Thiết bị ký riêng, không dùng máy hằng ngày | Nên | Bắt buộc | Bắt buộc | Bắt buộc |

Bảng này đọc từ [trang gốc](https://publish.obsidian.md/sos/standard/wiki/multisigs) ngày 19/11/2026 qua công cụ đọc web tự động. Chuẩn đang ghi "Work in Progress", nên đọc lại trang gốc trước khi chốt con số cho một dự án.

### Verify

- So `solana-verify get-program-hash <PROGRAM_ID>` với hash artifact.
- Đăng ký verified build khi authority là multisig: `solana-verify export-pda-tx` với uploader là vault của multisig → execute qua multisig → `solana-verify remote submit-job`. Cờ `--remote` cũ đã bị bỏ và báo lỗi. `Flux`
- "Verified" chỉ chứng minh bytecode build từ commit nào. Nó không chứng minh code an toàn. `Ngoài`

**✅ Cách tốt:**

```
Artifact: commit <sha đã audit>, solana-verify build trong Docker trên checkout sạch.
Hash artifact = <h1>. Hash on-chain (get-program-hash) = <h1>. Authority = <vault multisig>.
```

**❌ Cách tồi:**

```
anchor build trên máy Dev rồi solana program deploy.
```

Tại sao tồi: hash không tái lập được, không ai nối được bản on-chain với commit đã audit, và authority đang nằm ở ví của người deploy.

---

## Nhiều Dev hoặc nhiều AI session cùng làm thì chia thế nào?

Flux chạy một lead và ba worker song song. Những quy ước đã giúp tránh giẫm chân nhau: `Flux`

- Mỗi worker một git worktree và một branch riêng; chỉ lead merge. Chi tiết branch và commit theo [quy chuẩn Git](../dev-source-code-git/).
- Chia ranh giới theo crate, thư mục, module ngay từ kế hoạch, để hai người không sửa cùng file.
- Hai worktree không dùng chung thư mục build: một bản dependency cũ từ cây bên kia đã lọt vào và sinh lỗi biên dịch giả.
- Mỗi worker một cổng Surfpool cố định; script dừng nếu cổng đang bận, để không ghi nhầm vào fork của người khác.
- Gom lệnh đọc RPC vào batch, không gọi trong vòng lặp. Không in nội dung `.env` hay URL RPC ra output: Flux đã phải xoay một API key vì nó lọt vào output của công cụ.

---

## Gotcha thực tế

Đều đã tái hiện ở Flux trên Anchor 1.2.2 và Solana CLI 4.1.2 (11/2026). Version khác có thể khác. `Flux`

| Hiện tượng | Nguyên nhân | Cách tránh |
|------------|-------------|------------|
| Program chạy sai ngẫu nhiên dù build thành công | Stack frame vượt 4.096 B chỉ in một dòng lỗi, build vẫn ra file | Cho build fail khi log có `overflows the maximum`; box struct lớn, tách hàm `#[inline(never)]` |
| Test phân quyền nhận sai mã lỗi | Anchor chạy `init` (tạo account) trước các `constraint` của field đứng trước | Test quyền bằng một account chưa tồn tại |
| `UnbalancedInstruction` | Cộng lamports trực tiếp vào một account rồi CPI có truyền account đó mà không truyền account bị trừ | Làm hết CPI trước khi đóng account bằng tay |
| Hash build không khớp on-chain | Build trên macOS | Chỉ lấy artifact từ Docker hoặc CI Linux |
| Program "thành công" trong 2 CU mà không làm gì | Trên Surfpool, set program account trước programdata | Nạp programdata trước |
| Program thứ hai trong fuzz chạy nhầm binary | `--program-so` của Crucible thay byte của mọi program được nạp | Nạp program phụ bằng đường khác |
| Tx có ed25519 fail trong unit test | LiteSVM chỉ chạy precompile khi bật feature `precompiles` | Bật feature |
| Một phép tính tốn 65k CU | Thư viện U256 tốn khoảng 1,1k CU mỗi phép nhân | Viết lại phép nhân 128×128; Flux giảm còn 12k CU |
| Planted control lúc bắt lúc không | Đổi harness làm xáo trộn tìm kiếm với seed cố định, khi bug nằm sâu nhiều bước | Sửa trạng thái khởi đầu cho dễ tới, không tăng timeout |
| Fuzz treo hàng giờ, giữ khóa CI | Crucible bản alpha đôi khi không tự dừng | Bọc mọi lần chạy bằng một trần thời gian cứng |
| Owner không thấy mình đang ký gì | Ký ed25519 qua precompile thường chỉ ký hash | Thiết kế message đọc được cho thao tác quan trọng |

---

## Tóm lại

| Bước | Câu tự hỏi trước khi qua bước sau |
|------|-----------------------------------|
| Thiết kế | Tôi có chỉ ra được, cho từng instruction, account nào ký và account nào bị ghi không? |
| Spike | Còn con số nào tôi đang tin mà chưa đo không? |
| Build | Nếu tôi cài một bug vào đây, test có bắt được không? Tôi đã thử chưa? |
| Audit | Bản fix cuối cùng đã có người khác đọc chưa? |
| Launch | Tôi có chứng minh được code on-chain là code đã audit không? |

---

## Nguồn và độ tin cậy

| Phần | Nguồn | Độ tin cậy |
|------|-------|------------|
| Thiết kế, Spike, Build, Audit | Kế hoạch, báo cáo spike, nhật ký và báo cáo review của Flux (10–16/11/2026) | Đã làm thật trên một dự án |
| Checklist lỗ hổng, câu hỏi thiết kế | Skill `solana-dev` v2.8.0 | Tài liệu của Solana Foundation, chưa đối chiếu lại từng mục |
| Bảng mô hình, lượt quét, số liệu finding | Nghiên cứu audit nội bộ Cyberk (11/2026) | Số liệu từ cơ sở dữ liệu finding; phương pháp chưa đo hiệu quả |
| Launch trên mainnet | Tài liệu công khai, `--help` của CLI | **Chưa có dự án thật kiểm chứng** |
| Bảng SOS | Trang gốc, đọc 19/11/2026 | Đọc qua công cụ tự động; chuẩn còn đang soạn |
| Trang Production Readiness của solana.com | — | `Chưa kiểm`: không tải được trang (HTTP 429), nên không dùng nội dung nào từ đó |

---

## Liên kết

- [Quy trình làm dự án Solana contract](./dev-solana-contract-process.md)
- [Bảng giới hạn runtime Solana](./solana-runtime-limits-reference.md)
- [Quy chuẩn Source Code & Git](../dev-source-code-git/)
- [Solana Operational Security Standard](https://publish.obsidian.md/sos/standard/README)
- [Production Readiness — solana.com](https://solana.com/docs/tools/production-readiness) (chưa kiểm)
