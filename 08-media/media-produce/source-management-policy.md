---
type: handbook
tags: [media, sop, nas, storage, vj, editor, process]
created-date: 2026-09-03
updated-date: 2026-11-26
author: Media Manager
status: Đang dùng
---

# CyberK Media Team: Quy trình Quản lý Nguồn Media & Chính sách Lưu trữ NAS
*(Media Source Management & NAS Storage Policy)*

> **Người chịu trách nhiệm:** Media Manager (Editor Lead)  
> **Cập nhật lần cuối:** 04-09-2026  
> **Trạng thái:** Đang dùng  

---

## 1. Tại sao có trang này

Trang này quy định cách đóng gói, đặt tên và lưu trữ source media trên NAS công ty. Tuân thủ đúng chuẩn để:

1. **AI tìm được:** tên file và đường dẫn nhất quán (`YYYY-MM-DD`, phân cách `_`, không khoảng trắng, không dấu) thì AI quét và trả lời được ngay câu hỏi kiểu *"tìm tất cả source dự án remo do VJ Dennis quay tháng 9/2026"*.
2. **Người tìm được:** Editor mới vào team tự tra cứu và tái sử dụng b-roll, audio, popup graphics mà không phải hỏi người cũ. Không còn file rác hay mất source.
3. **VJ và Editor không phải hỏi nhau:** dựng thô cho Editor thấy nhịp cắt; kịch bản có note popup text, motion graphics giúp Editor dựng đúng ý ngay lần đầu.

---

## 2. Phạm vi & Đối tượng áp dụng (Scope & Applicability)

Chính sách này áp dụng bắt buộc cho:
* **VJ**: quay, dựng thô (rough cut), đóng gói source.
* **Editor**: lưu gói source lên NAS, dựng hoàn thiện, export clip final vào `social/`.

---

## 3. Quy chuẩn Đóng gói Source từ VJ (VJ Source Packaging Standards)

Trước khi bàn giao dữ liệu cho Team Media đẩy lên NAS, **VJ có trách nhiệm đóng gói dữ liệu** theo đúng cấu trúc tiêu chuẩn bên dưới.

### 3.1. Cấu trúc Thư mục Đóng gói của VJ

```text
YYYY-MM-DD/ (Folder cha theo ngày)
└── ten-du-an_ten-vj_ten-clip/ (Folder con dự án)
    ├── source/ (Folder chứa tất cả cảnh quay VJ đã thực hiện)
    ├── [clip_dung_tho.mp4/.mov] (Clip VJ đã dựng thô: định dạng .mp4 hoặc .mov)
    └── [kich_ban.docx/.md/.pdf] (File kịch bản note chi tiết popup text, motion graphics)
```

### 3.2. Quy tắc Chi tiết & Lý do

1. **Folder cha (`YYYY-MM-DD`)**:
   * *Quy tắc:* Đặt tên theo ngày bàn giao/tạo gói theo định dạng `YYYY-MM-DD` (Ví dụ: `2026-09-03`).
   * *Lý do:* Định dạng chuẩn ISO 8601 giúp hệ điều hành và AI tự động sắp xếp thư mục theo đúng trình tự thời gian tăng dần.

2. **Folder con (`ten-du-an_ten-vj_ten-clip`)**:
   * *Quy tắc:* Đặt tên theo cú pháp `ten-du-an_ten-vj_ten-clip` (dùng chữ thường không dấu, phân cách nhóm bằng `_`, phân cách từ bằng `-`).
   * *Ví dụ:* `remo_dennis_claude-design-patterns`
   * *Lý do:* Ký tự `_` đóng vai trò là "token delimiter" giúp máy tính và AI phân tách 3 thực thể thông tin riêng biệt: **[Tên dự án]**, **[Tên VJ]**, **[Tên clip]**.

3. **Thành phần bắt buộc bên trong folder con**:
   * **Thư mục `source/`**: Thư mục chứa toàn bộ video footage thô, b-roll, audio mà VJ đã quay.
   * **File Clip Dựng Thô**: Bản dựng sơ bộ (**bắt buộc định dạng `.mp4` hoặc `.mov`**) để Editor nắm được nhịp và ý đồ cắt dựng.
   * **File Kịch Bản**: Văn bản mô tả chi tiết, trong đó **bắt buộc có note** rõ các mốc thời gian/vị trí muốn chèn **Popup Text** hoặc **Motion Graphics**.

---

### 3.3. Ví dụ Tốt (✅) vs Ví dụ Tồi (❌) về Đóng gói VJ

#### ✅ Mẫu Đóng Gói TỐT
**Cấu trúc thư mục:**
```text
2026-09-03/
└── remo_dennis_claude-design-patterns/
    ├── source/
    │   ├── CAM_A_001.MOV
    │   ├── CAM_B_002.MOV
    │   └── mic_voice.wav
    ├── rough-cut.mp4
    └── script-and-notes.md
```
**Nội dung file `script-and-notes.md`:**
> - `00:15 - 00:20`: Chèn Popup Text ở góc dưới bên trái: *"Prompt Engineering Tips"*.  
> - `01:05`: Hiệu ứng Motion Graphic hình tia sét khi VJ nhấn mạnh từ "Speed".  

*Tại sao tốt:* Tên folder không chứa khoảng trắng hay tiếng Việt có dấu. Thư mục gọn gàng, file kịch bản có timestamp chính xác giúp Editor thao tác dựng ngay lập tức mà không cần hỏi lại.

---

#### ❌ Mẫu Đóng Gói TỒI
**Cấu trúc thư mục:**
```text
Clip Ngay 3 Thang 9/
└── Gói Video Mới Của Dennis/
    ├── Video Quay Thô 1.MP4
    ├── Video Quay Thô 2.MP4
    ├── File nhac hay.mp3
    ├── Ban dung.avi
    └── Kich ban nhap.docx
```
**Nội dung file `Kich ban nhap.docx`:**
> "Nhờ Editor chèn mấy cái chữ hoạt họa đẹp đẹp đoạn giữa video giúp em nhé."

*Tại sao tồi:*
- Folder dùng dấu cách và tiếng Việt có dấu (`Clip Ngay 3 Thang 9`), tên không có chuẩn `YYYY-MM-DD` làm AI parser bị lỗi đường dẫn (broken path).
- Dùng định dạng `.avi` vi phạm quy tắc định dạng video chuẩn (`.mp4`/`.mov`).
- Ghép chung footage thô với file nhạc ra ngoài root thay vì gom vào `source/`.
- File kịch bản ghi chung chung ("chèn mấy cái chữ đẹp đẹp") làm Editor phải nhắn hỏi lại trên Telegram, gây mất thời gian của cả 2 bên.

---

## 4. Cấu trúc Thư mục NAS & Quy trình Team Media (NAS Directory Architecture)

Team Media (Editor) phụ trách tiếp nhận gói dữ liệu từ VJ và đẩy lên hệ thống NAS theo 2 khu vực chính: `sources/` và `social/`.

```text
Cyberk Media NAS Root/
├── sources/
│   └── YYYY-MM-DD/ (Thư mục chung cho các clip/dự án cùng ngày)
│       ├── ten-du-an-1_ten-vj_ten-clip-1/
│       │   ├── source/
│       │   ├── clip-dung-tho.mp4 (hoặc .mov)
│       │   └── kich-ban.md
│       └── ten-du-an-2_ten-vj_ten-clip-2/
│           ├── source/
│           ├── clip-dung-tho.mp4 (hoặc .mov)
│           └── kich-ban.md
└── social/
    └── YYYY-MM-DD_ten-du-an_ten-vj_ten-clip.mp4 (hoặc .mov)
```

### 4.1. Thư mục Nguồn NAS (`sources/`)
* **Phụ trách**: Editor / Team Media.
* **Cách sắp xếp**: Editor đẩy tất cả các folder dự án mà VJ gửi lên mục `sources/`.
* **Quy tắc gộp ngày**: Những dự án/clip có **ngày giống nhau** (`YYYY-MM-DD`) sẽ được gom chung vào cùng **1 thư mục cha `YYYY-MM-DD`** trên NAS.
* *Lý do:* Tránh làm phình to cấp thư mục root của `sources/`, giữ cho thư mục NAS sạch sẽ và dễ quét dữ liệu.

### 4.2. Thư mục Sản phẩm Hoàn thiện (`social/`)
* **Phụ trách**: Editor / Team Media.
* **Nội dung**: Chứa các video clip final đã được dựng hoàn chỉnh (đã xử lý màu, âm thanh, popup text, motion graphics) sẵn sàng đăng tải lên các nền tảng mạng xã hội.
* **Định dạng đặt tên file final**: `YYYY-MM-DD_ten-du-an_ten-vj_ten-clip.mp4` (hoặc `.mov`)
  * *Ví dụ:* `2026-09-03_vj-outfit_hung_outfit-cong-so.mp4`
* *Quy định chuẩn:* **Tất cả các video clip (cả clip dựng thô & clip final) bắt buộc chỉ sử dụng định dạng `.mp4` hoặc `.mov`**.
* *Lý do:* Đảm bảo tính tương thích tuyệt đối khi upload lên Facebook, TikTok, YouTube Shorts và giúp AI xem trước (preview/encode) mượt mà mà không bị lỗi codec.

---

### 4.3. Ví dụ Tốt (✅) vs Ví dụ Tồi (❌) về Lưu trữ NAS & Export Final

#### ✅ Mẫu Đặt Tên File Final TỐT
`social/2026-09-03_vj-outfit_hung_outfit-cong-so.mp4`

*Tại sao tốt:* Tên file ngắn gọn, chứa đầy đủ metadata (Ngày xuất bản, Dự án, VJ, Tên clip), phân tách bằng dấu `_`, hoàn toàn không có dấu cách hay ký tự đặc biệt. AI chỉ cần regex là tách được ngay thông tin.

---

#### ❌ Mẫu Đặt Tên File Final TỒI
`social/Bản Dựng Final Đã Sửa Lần 2 (Update 03-09) - Outfit Công Sở.mp4`

*Tại sao tồi:*
- Chứa tiếng Việt có dấu và khoảng trắng.
- Tên mơ hồ ("Bản Dựng Final Đã Sửa Lần 2"), thiếu tên dự án (`vj-outfit`) và tên VJ (`hung`).
- Khi AI hoặc công cụ tìm kiếm tự động lọc file sẽ không thể trích xuất được VJ nào làm clip này nếu không mở trực tiếp file video lên xem.

---

## 5. Quy tắc Cứng (Bắt buộc) & Lý do

1. **Tuyệt đối KHÔNG dùng ký tự đặc biệt, khoảng trắng, tiếng Việt có dấu trong tên folder và file.**
   - *Lý do:* Đảm bảo không bị lỗi mã hóa đường dẫn (URL encoding error) trên hệ thống NAS Linux và tương thích hoàn toàn với script/AI tự động quét dữ liệu.
2. **Mọi video (dựng thô & final) chỉ chấp nhận định dạng `.mp4` hoặc `.mov`.**
   - *Lý do:* Đây là 2 chuẩn container phổ biến nhất, hỗ trợ tốt nhất trên các thiết bị Mac/Windows và các nền tảng Social Media.
3. **Mọi dự án từ VJ bàn giao BẮT BUỘC phải có đủ 3 thành phần: Thư mục `source/`, File dựng thô, File kịch bản.**
   - *Lý do:* Thiếu thư mục `source/` dẫn tới không lưu lại được footage gốc để tái sử dụng; thiếu dựng thô và kịch bản note làm gián đoạn và giảm chất lượng khâu hậu kỳ của Editor.
4. **Tên file final trong thư mục `social/` phải bắt đầu bằng `YYYY-MM-DD_`.**
   - *Lý do:* Giúp quản lý danh sách file theo mốc thời gian xuất bản, tránh việc đè file trùng tên.

---

## Liên kết

- [Quy trình Quay & Dựng](./produce-process.md): các bước SHOOT → PACK → EDIT và checklist
