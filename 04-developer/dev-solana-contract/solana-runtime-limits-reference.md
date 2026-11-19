---
type: handbook
tags: [solana, smart-contract, reference, developer]
created-date: 2026-11-19
updated-date: 2026-11-19
author: anderson
status: Nháp
---

# Giới hạn runtime Solana — Sổ tay cho Lead và Dev

**Người chịu trách nhiệm:** Anderson (mặc định theo [owners-reference](../../02-about-handbook/owners-reference.md), chưa gán owner riêng)
**Cập nhật lần cuối:** 2026-11-19
**Trạng thái:** Nháp

Bảng này để tra nhanh các giới hạn của runtime khi làm bước Thiết kế và Spike trong [quy trình Solana contract](./dev-solana-contract-process.md).

> ⚠️ **Các số này đúng trên mainnet tại ngày kiểm ghi ở từng dòng, không phải hằng số vĩnh viễn.** Trước khi dựa vào một con số để chốt thiết kế, kiểm lại theo mục [Cách kiểm lại](#cách-kiểm-lại). Số đo của dự án luôn thắng bảng này.

**Nhãn:** `[V]` đã kiểm (kèm ngày) · `[ER]` suy luận hoặc lấy từ tài liệu, chưa đối chiếu source · `[U]` chưa biết.

**Hai lần kiểm:**
- **10/11/2026** — dự án Flux đọc source Agave (nhánh `master` tại ngày đó), nội dung SIMD và feature account trên mainnet.
- **19/11/2026** — đọc lại on-chain bằng một batch RPC tại slot 471.184.938 (mainnet chạy `solana-core 4.4.0`): sysvar Rent và 4 feature account.

---

## Bảng giới hạn

### Transaction

| Giới hạn | Giá trị | Hệ quả khi thiết kế | Nguồn | Nhãn |
|----------|---------|---------------------|-------|------|
| Kích thước tx legacy / v0 | 1.232 B | Route nhiều hop hoặc nhiều account dễ vượt | Agave `runtime-transaction/src/transaction_limits.rs:18-19` | `[V]` 10/11 |
| Kích thước tx v1 (SIMD-0385) | 4.096 B; không dùng được ALT; tối đa 12 chữ ký, 64 instruction | Vừa 64 địa chỉ viết thẳng, không cần ALT. CU limit và loaded-data limit nằm trong message config, bỏ trống là 0 | Feature `txv1aq4p…`, bật ở slot 447.120.000 (15/09/2026); nội dung SIMD-0385 | Feature `[V]` 19/11 · chi tiết `[V]` 10/11 |
| Account bị khóa mỗi tx | 64, cho cả legacy, v0, v1. v0 tính cả account nạp qua ALT | ALT chỉ tiết kiệm byte, không thêm được account. Đây thường là giới hạn chạm trước, không phải số byte | Agave `accounts-db/src/account_locks.rs:14` | `[V]` 10/11 |
| Account mỗi instruction | 255 | — | SIMD-0406 | `[V]` 10/11 |
| Độ sâu CPI | 4 tầng CPI (stack height 5, instruction top-level tính là 1) | Mình → Titan → Jupiter → DEX → Token là 5, chạm trần. Chuỗi 4 program (mình → aggregator → DEX → Token) còn dư 1 tầng. Đã ở trần thì thêm một program trung gian hoặc mint có TransferHook là vượt | Agave `program-runtime/src/execution_budget.rs:8-18` | `[V]` 10/11 |
| Instruction trace mỗi tx | 64, gồm instruction top-level và mọi CPI | Mỗi `emit_cpi!` là một self-CPI, tính 1. Tính event vào ngân sách | Agave `transaction-context/src/lib.rs:26` | `[V]` 10/11 |
| Compute unit mỗi tx | Tối đa 1.400.000; mặc định 200.000 mỗi instruction | CU là ngân sách chung của cả tx. Đặt CU limit theo simulate | Agave `program-runtime/src/execution_budget.rs:26` | `[V]` 10/11 |
| Compute unit mỗi block | 100.000.000 (SIMD-0286) | Mỗi account writable tối đa 40% block = 40.000.000 `[ER]` | Feature `P1BCUMpA…`, bật ở slot 435.888.000 | Feature `[V]` 19/11 |
| Loaded accounts data | Mặc định 64 MB và có tính phí | Đặt `loadedAccountsDataSizeLimit` theo simulate. Flux đo được 5–19 MB mỗi route | Báo cáo spike Flux | Mặc định `[ER]` · số đo `[V]` 10/11 |
| Chữ ký precompile ed25519 | Tối đa 8 mỗi tx | Ảnh hưởng thiết kế ký message off-chain | SIMD-0152 | `[V]` 10/11 |

### Account và rent

| Giới hạn | Giá trị | Hệ quả khi thiết kế | Nguồn | Nhãn |
|----------|---------|---------------------|-------|------|
| Rent | 5.080 lamports/byte. Số dư tối thiểu = (128 + kích thước data) × 5.080 | Token account 165 B cần 293 × 5.080 = 1.488.440 lamports | Sysvar Rent trên mainnet | `[V]` 19/11 |
| Tăng kích thước account | +10.240 B mỗi instruction; tối đa 10 MiB (10.485.760 B) | Account lớn phải realloc qua nhiều instruction | `solana-sdk` `account-info`, `system-interface` | `[V]` 10/11 |
| Seed của PDA | Tối đa 16 seed, mỗi seed ≤ 32 byte | — | Skill `solana-dev` v2.8.0 | `[ER]` |

### Program

| Giới hạn | Giá trị | Hệ quả khi thiết kế | Nguồn | Nhãn |
|----------|---------|---------------------|-------|------|
| Stack frame | 4.096 B mỗi frame | **Vượt thì build vẫn thành công**, chỉ in một dòng `overflows the maximum allowed frame space`, program chạy với hành vi không xác định. Box struct lớn, tách hàm `#[inline(never)]` | Flux tái hiện trên Anchor 1.2.2 | `[V]` 12/11 |
| Heap | 32 KB mặc định | Không cấp phát theo kích thước dữ liệu mà người ngoài nới được | Skill `solana-dev` v2.8.0 | `[ER]` |
| Kiến trúc sBPF | v3 chạy được trên mainnet. Anchor 1.2.2 build v3 mặc định; `cargo build-sbf` gọi trực tiếp mặc định v0. v0–v2 vẫn deploy được | Mọi công cụ test phải chạy được đúng kiến trúc sẽ deploy | Feature `5cC3foj7…`, bật ở slot 428.976.000 (26/06/2026) | Feature `[V]` 19/11 · mặc định của tool `[V]` 10/11 |

---

## Sắp đổi

| Thay đổi | Từ → đến | Trạng thái | Nhãn |
|----------|----------|------------|------|
| SIMD-0268: độ sâu CPI | 4 → 8 | Feature `6TkHkRmP…` chưa có trên mainnet | `[V]` 19/11 |
| SIMD-0437: rent giảm theo bước | 5.080 → 2.575 → 1.322 → 696 lamports/byte | Đang ở bước 2/5. Các bước sau chưa có ngày | Giá trị hiện tại `[V]` 19/11 · lộ trình `[V]` 10/11 |
| SIMD-0596: account mỗi tx v1 | 64 → 96 | Draft, chưa bật | `[V]` 10/11 |
| SIMD-0500: chặn deploy sBPF v0–v2 | — | Mới là ý tưởng, chưa có feature account | `[V]` 10/11 |

---

## Quy tắc đặc biệt

| Quy tắc | Lý do |
|---------|-------|
| Không hard-code rent; program đọc `Rent::get()` | Rent đã giảm hai lần trong 09/2026 và còn giảm tiếp. Doc cũ của Flux từng dùng 6.960 lamports/byte lấy từ một fork, lệch với mainnet |
| Test giới hạn byte và account của tx trên Surfpool, không trên LiteSVM | LiteSVM (npm 1.6.2) cho một tx v0 2.034 B chạy qua; nó không chặn kích thước packet `[V]` 10/11 |
| Đo CU trên đúng kiến trúc sBPF sẽ deploy | Chưa kiểm số đo trên sBPF v0–v2 có dùng lại được cho bản v3 không `[U]`. Số CU của Flux trước spike đến từ build v0, nên phải đo lại |
| Trường `status` trong repo SIMD chậm hơn thực tế | SIMD-0437 ghi "Idea" trong khi bước của nó đã chạy trên mainnet. Muốn biết đã bật chưa thì đọc feature account |

---

## Cách kiểm lại

Feature account do `Feature111…` sở hữu. Account không tồn tại thì chắc chắn chưa bật. Có account thì phải đọc dữ liệu, vì feature đang chờ kích hoạt cũng có account: byte đầu bằng 1 và 8 byte sau là slot kích hoạt (u64 little-endian) mới là đã bật. Gom mọi địa chỉ vào **một** request, đừng gọi từng cái:

```bash
curl -s https://api.mainnet-beta.solana.com -X POST -H 'Content-Type: application/json' -d '{
  "jsonrpc":"2.0","id":1,"method":"getMultipleAccounts",
  "params":[[
    "SysvarRent111111111111111111111111111111111",
    "6TkHkRmP7JZy1fdM6fg5uXn76wChQBWGokHBJzrLB3mj",
    "txv1aq4pp281K9um3tnPgkfX8UqtFT6wcVW3hNezGLL",
    "5cC3foj77CWun58pC51ebHFUWavHWKarWyR5UUik7dnC"
  ],{"encoding":"jsonParsed"}]}'
```

Thứ tự kết quả: sysvar Rent (`lamportsPerByte`), SIMD-0268 (CPI depth 8), tx v1, sBPF v3. Kết quả `null` là chưa bật. Feature account trả dữ liệu dạng base64, ví dụ `AYCCphoAAAAA` là byte đầu 1 và slot 447.120.000.

Với hằng số trong source: mở file Agave ghi ở cột Nguồn tại tag mà mainnet đang chạy. Kiểm xong thì sửa bảng và ghi ngày mới.

---

## Liên kết

- [Quy trình làm dự án Solana contract](./dev-solana-contract-process.md)
- [Cẩm nang Solana contract](./dev-solana-contract-handbook.md)
- [SIMD — Solana Improvement Documents](https://github.com/solana-foundation/solana-improvement-documents)
- [Agave (validator client)](https://github.com/anza-xyz/agave)
