# ⛓ Solana Contract

> **Đối tượng:** Lead, Dev, Reviewer làm program Solana (người hoặc AI session)
> **Mục đích:** Quy trình làm một program on-chain từ thiết kế đến launch, sao cho bug được bắt trước khi có tiền thật

**Phạm vi:** chỉ program on-chain. Frontend, indexer, RPC không thuộc bộ tài liệu này; off-chain chỉ xuất hiện ở đầu ra bàn giao (IDL, client sinh tự động, runbook).

---

## Tài liệu

| File | Nội dung | Đọc khi |
|------|----------|---------|
| [dev-solana-contract-process.md](./dev-solana-contract-process.md) | 5 bước Thiết kế → Spike → Build → Audit → Launch: việc làm, ai làm, đầu ra, bằng chứng, tiêu chí "xong khi", 7 quy tắc cứng | Đang làm dự án, cần biết bước tiếp theo |
| [dev-solana-contract-handbook.md](./dev-solana-contract-handbook.md) | Vì sao của từng bước, ví dụ tốt/tồi, gotcha, chuyện thật từ dự án Flux | Muốn hiểu lý do, hoặc gặp lỗi lạ |
| [solana-runtime-limits-reference.md](./solana-runtime-limits-reference.md) | Bảng giới hạn runtime (kích thước tx, số account, CPI depth, CU, rent, stack) kèm ngày kiểm và cách kiểm lại | Cần tra một con số khi thiết kế hoặc spike |

## Bản gửi khách hàng

| File | Nội dung | Đối tượng |
|------|----------|-----------|
| [cyberk-solana-contract-process-en.html](./client-documents/cyberk-solana-contract-process-en.html) | Quy trình 5 bước (EN, 9 trang A4, có minh hoạ): mỗi bước gồm việc Cyberk làm, khách nhận gì, khách cần cung cấp gì, cổng duyệt; kèm trang 7 quy tắc | Khách hàng |

Bản tiếng Việt chưa có. Bản HTML không ghi timeline vì timeline chưa chốt. Xuất PDF: mở file trong trình duyệt, Ctrl/Cmd + P, chọn "Save as PDF", khổ A4.

## Đọc theo thứ tự

1. **Lần đầu** → đọc process để nắm 5 bước và 7 quy tắc cứng
2. **Trước mỗi bước** → đọc mục tương ứng trong handbook
3. **Khi thiết kế và spike** → mở reference bên cạnh, và kiểm lại số nào mình sắp dựa vào

## Tra nhanh

| Cần gì | Xem mục |
|--------|---------|
| Tiêu chí qua từng bước | "Xong khi" trong [process](./dev-solana-contract-process.md#các-bước) |
| Việc gì tuyệt đối không làm | [Quy tắc cứng](./dev-solana-contract-process.md#quy-tắc-cứng-không-được-vi-phạm--lý-do) |
| Fuzz xanh có đáng tin không | [Planted control](./dev-solana-contract-handbook.md#planted-control) |
| Build xong mà program chạy sai | [Gotcha thực tế](./dev-solana-contract-handbook.md#gotcha-thực-tế) |
| Những điều owner chưa quyết | [Chưa chốt](./dev-solana-contract-process.md#chưa-chốt-cần-owner-quyết) |

## Độ tin cậy

Bốn bước đầu dựa trên dự án Flux (11/2026). Bước Launch trên mainnet **chưa có dự án thật kiểm chứng**. Chi tiết ở mục [Nguồn và độ tin cậy](./dev-solana-contract-handbook.md#nguồn-và-độ-tin-cậy) của handbook.
