---
type: qa
tags: [bugs, github, logging, handbook]
created: 2026-09-11
author: kate
status: Nháp
---

# Tạo Bug trên GitHub — Cẩm nang cho QA

Một bug report chuẩn giúp Developer tái hiện và sửa lỗi ngay trong 15 phút. Một bug report sơ sài khiến cả team tốn nửa ngày tranh luận và hỏi lại thông tin.

Cuốn cẩm nang này hướng dẫn bạn cách viết bug report chuẩn chỉnh trên GitHub — từ cách đặt tiêu đề, mô tả các bước tái hiện, đính kèm bằng chứng cho đến gắn nhãn (labels) chính xác.

---

## Đặt tiêu đề bug — Viết sao để nhìn là hiểu ngay?

Tiêu đề là thứ đầu tiên xuất hiện trên GitHub Board. Tiêu đề tốt phải trả lời được các câu hỏi: **Cái gì? Như thế nào? Ở đâu? Khi nào? **

Cú pháp chuẩn: `[Tính năng][Môi trường] Tóm tắt ngắn gọn lỗi kèm điều kiện xảy ra (nếu có)`

**✅ Cách tốt:**

```text
[SignIn][Staging] SignIn button bị disabled nếu access token bị expired
[Riz][Gallery] User vẫn mua thành công credit dù số dư tài khoản thanh toán = 0
```

Tại sao tốt: Có feature rõ ràng, mô tả đúng hiện tượng và ngữ cảnh kích hoạt lỗi. Nhìn tiêu đề là dev phân loại và tìm được file code liên quan ngay.

**❌ Cách tồi:**

```text
Lỗi ví
App bị crash
Không rút tiền được, dev check gấp
Bug nghiêm trọng trên mobile
```

Tại sao tồi: Không biết tính năng nào, không rõ lỗi gì, không biết điều kiện xảy ra. Dev và PO bắt buộc phải mở issue ra đọc mới biết chuyện gì đang xảy ra.

---

## Các bước tái hiện (Steps to Reproduce) — Viết sao để Dev không hỏi lại?

Đừng viết dạng văn xuôi. Hãy đánh số thứ tự từ bước đầu tiên đến bước phát sinh lỗi, đi kèm dữ liệu kiểm thử (test data) cụ thể.

**✅ Cách tốt:**

```markdown
### Steps to Reproduce
1. Đăng nhập tài khoản test: `qa_user_01@cyberk.io` (Role: Member).
2. Điều hướng vào menu **Wallet** > Chọn **Withdraw**.
3. Nhập số lượng: `50 USDT` (Số dư khả dụng hiện tại: `100 USDT`).
4. Nhấn nút **Confirm Withdraw**.
```

Tại sao tốt: Rõ ràng từng thao tác, có tài khoản test và dữ liệu đầu vào cụ thể. Bất kỳ ai làm theo 4 bước trên đều sẽ tái hiện được lỗi.

**❌ Cách tồi:**

```text
Vào ví rồi bấm rút tiền là bị lỗi, bấm mấy lần không được.
```

Tại sao tồi: Không nói dùng tài khoản nào, rút bao nhiêu, ở màn hình nào, thao tác cụ thể ra sao. Dev làm thử với tài khoản admin thì thấy bình thường và đóng bug với lý do "Cannot Reproduce".

---

## Kết quả kỳ vọng vs Thực tế (Expected vs Actual) — Làm rõ điểm sai

Hãy chỉ rõ sự khác biệt giữa **thiết kế/yêu cầu** và **thực tế đang diễn ra**.

**✅ Cách tốt:**

```markdown
### Expected Result
- Hệ thống hiển thị popup xác nhận mã 2FA.
- Sau khi nhập đúng 2FA, hiển thị thông báo "Withdrawal submitted successfully" và trừ số dư khả dụng.

### Actual Result
- Nút "Confirm Withdraw" bị xoay vòng (loading spinner) liên tục.
- Console báo lỗi: `POST /api/v1/wallet/withdraw 500 (Internal Server Error)`.
- Số dư ví không thay đổi nhưng không có thông báo lỗi trên UI.
```

Tại sao tốt: Tách biệt rõ ràng giữa kỳ vọng và thực tế, chỉ ra cả hiện tượng trên giao diện (UI) lẫn mã lỗi kỹ thuật (API/Console).

**❌ Cách tồi:**

```markdown
Expected: Hoạt động bình thường.
Actual: Không chạy được.
```

Tại sao tồi: "Bình thường" là như thế nào? "Không chạy được" là crash, đứng hình hay hiện alert lỗi? Hoàn toàn vô giá trị cho việc debug.

---

## Bằng chứng (Evidence & Logs) — Cần đính kèm những gì?

Một hình ảnh bằng chứng đáng giá bằng mười dòng mô tả. Tuy nhiên, bằng chứng phải có giá trị kỹ thuật.

1. **Screenshot:** Khoanh vùng đỏ vị trí lỗi, hiển thị cả thanh địa chỉ URL và thời gian nếu có. Với các lỗi khác so với thiết kế, nên chụp ảnh bản thiết kế kèm theo và khoanh đỏ vùng lỗi ở trên sản phẩm để thấy rõ được sự khác biệt giữa kỳ vọng và thực tế.
2. **Video / GIF:** Bắt buộc đối với các lỗi liên quan đến animation, thao tác phức tạp, hoặc lỗi chập chờn (intermittent).
3. **Console Log & Network Payload:** Chụp tab Console (báo đỏ) và tab Network (Request URL, Request Payload, Response JSON, Status Code).

**✅ Cách tốt:**

```markdown
### Evidence & Logs
- **Screenshot/Video:** ![Withdrawal Bug Demo](https://github.com/user-attachments/assets/...)
- **Request URL:** `POST https://api-staging.koto.io/api/v1/wallet/withdraw`
- **Request Payload:**
  ```json
  {
    "amount": 50,
    "currency": "USDT",
    "network": "BSC"
  }
  ```
- **Response Error:**
  ```json
  {
    "code": "ERR_WALLET_LOCK_TIMEOUT",
    "message": "Database transaction lock timeout after 3000ms"
  }
  ```
```

Tại sao tốt: Dev backend đọc được payload và mã lỗi database là có thể nhảy ngay vào đúng hàm code bị deadlock để fix mà không cần bật app lên test lại.

**❌ Cách tồi:**

```markdown
Evidence: Đã chụp màn hình gửi qua Telegram cho anh Hùng.
```

Tại sao tồi: Bug trên GitHub là tài liệu lưu trữ lâu dài. Gửi qua chat riêng sẽ bị trôi, người khác vào xem issue không thấy dữ liệu gì.

---

## Mẫu Bug Report chuẩn trên GitHub

Dưới đây là template markdown chuẩn cần dùng khi tạo bất kỳ Bug Issue nào trên GitHub:

```markdown
## 🐛 Bug Report

**Severity:** P[0/1/2/3]
**Project / Module:** [Koto / Riz / America Fun / Skin Agent] — [Module Name]
**Environment:** [Production / Staging / Dev]
**Device / Browser:** [e.g. Chrome v128 / macOS 14.5 | Safari iOS 17.4 | iPhone 15 Pro]
**Test Account:** `qa_test_user@cyberk.io`

---

### Description
[1-2 câu tóm tắt ngắn gọn lỗi và mức độ ảnh hưởng đến người dùng]

### Steps to Reproduce
1. Truy cập vào [...]
2. Thực hiện hành động [...]
3. Nhập dữ liệu [...]
4. Nhấn nút [...]

### Expected Result
- [Hành vi đúng theo đặc tả yêu cầu / thiết kế]

### Actual Result
- [Hành vi sai thực tế đang diễn ra, thông báo lỗi nếu có]

### Evidence & Technical Logs
- **Media:** [Đính kèm link ảnh hoặc kéo thả video/ảnh vào đây]
- **Console Logs / Network Payloads:**
```json
{
  "status": 500,
  "error": "Error message here"
}
```

### Workaround (Nếu có)
- [Mô tả cách tạm thời để tránh lỗi nếu có, ví dụ: Reload lại trang, chuyển sang mạng 4G...]
```

---

## Gắn Labels & Assignee — Làm sao để bug không bị trôi?

Sau khi viết xong nội dung, bắt buộc phải thiết lập các trường metadata trên GitHub Issue:

| Trường | Quy định thiết lập |
|---|---|
| **Labels cơ bản** | `bug` + `severity:p[0/1/2/3]` |
| **Labels nguồn gốc** | `client-reported` (nếu từ khách) hoặc `qa-internal` (nếu QA tự tìm thấy) |
| **Labels module** | `module:wallet`, `module:auth`, `module:chat`, v.v. |
| **Labels trạng thái** | `needs-fix` (mặc định sau khi tạo), `verified` (sau khi test xong) |
| **Assignee** | Gán trực tiếp cho Developer phụ trách module hoặc Tech Lead dự án |
| **Milestone / Sprint** | Gán đúng Sprint hoặc Release Milestone hiện tại |
| **Project Board** | Đưa vào Project Board của dự án tương ứng ở cột **Todo / Backlog** |

> 📌 **Lưu ý SLA:** Nếu là bug **P0** hoặc **P1**, sau khi tạo issue trên GitHub, **phải ping ngay link issue vào nhóm Telegram của dự án** kèm tag Developer và PO để xử lý khẩn cấp.

---

## Tóm lại

Một bug report đạt chuẩn cần vượt qua checklist 5 điểm sau trước khi nhấn **Submit new issue**:

| # | Tiêu chí | Câu hỏi tự kiểm tra |
|---|---|---|
| 1 | **Tiêu đề** | Có đúng format `[Module][Môi trường] Tóm tắt lỗi` không? |
| 2 | **Tái hiện** | Người khác đọc các bước có tự làm theo và thấy lỗi được không? |
| 3 | **Bằng chứng** | Đã có ảnh khoanh vùng / video / console log chưa? |
| 4 | **Phân loại** | Đã chọn đúng mức Severity (P0/P1/P2/P3) theo SLA chưa? |
| 5 | **Metadata** | Đã gắn label, assignee và project board chưa? |

Nguyên tắc cốt lõi: **Đầy đủ — Rõ ràng — Dễ tái hiện — Có bằng chứng.**

---

## Liên kết

- [Quy trình tạo bug](qa-bugs-logs-process.md)
- [Xử lý Bugs](../qa-bugs-handling/bug-handling-handbook.md)
- [Phân loại Severity & SLA](../qa-bugs-handling/bug-severity-sla-handbook.md)
- [Mẫu tin nhắn tiếp nhận](../qa-bugs-handling/acknowledgment-messages-example.md)
