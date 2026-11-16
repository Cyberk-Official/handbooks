---
type: hr
tags: [onboarding, newbie, setup, handbook]
created: 2026-11-09
updated: 2026-11-09
author: anderson
status: Nháp
---

# Nhận & Cài Đặt Máy — Cẩm nang cho Newbie

**Người chịu trách nhiệm:** [HR / Line Manager]
**Cập nhật lần cuối:** 2026-11-09
**Trạng thái:** Nháp

Chiếc máy tính là "vũ khí" gắn bó với bạn mỗi ngày tại Cyberk. Trang này hướng dẫn bạn từng bước từ lúc nhận bàn giao thiết bị từ HR/Admin, kiểm tra phần cứng, **reset máy sạch sẽ**, thiết lập bảo mật bắt buộc, đến khi cài xong bộ công cụ chuẩn để sẵn sàng làm việc ngay trong buổi sáng ngày đầu tiên.

---

## 1. Vừa nhận máy từ HR/Admin — Kiểm tra gì trước tiên?

Đừng vội mở máy cài app ngay. Hãy dành **5–10 phút đầu tiên** kiểm tra tình trạng vật lý và phụ kiện đi kèm trước khi ký biên bản bàn giao. Việc này bảo vệ quyền lợi của chính bạn và giúp HR/Admin ghi nhận chính xác hiện trạng thiết bị.

### Các hạng mục cần kiểm tra

| Hạng mục | Kiểm tra cụ thể |
|----------|-----------------|
| **Ngoại quan** | Vỏ máy, các góc cạnh, bản lề có vết móp, trầy xước lớn hoặc nứt vỡ không? |
| **Màn hình & Camera** | Mở nền sáng/tối kiểm tra điểm chết, sọc màn hình; bật thử webcam xem có rõ nét không. |
| **Bàn phím, Trackpad & Cổng kết nối** | Gõ thử các phím, bấm/vuốt trackpad, cắm thử các cổng USB-C/HDMI. |
| **Phụ kiện đi kèm** | Đủ củ sạc, dây sạc (và chuột, hub chuyển đổi, màn hình rời nếu được cấp kèm). |
| **Cấu hình & Pin** | Kiểm tra thông tin máy (Chip/CPU, RAM, dung lượng ổ cứng) và tình trạng pin có khớp với biên bản bàn giao không. |

**✅ Cách tốt:**

```
Kiểm tra máy ngay tại bàn cùng HR/Admin.
Phát hiện cạnh máy có vết xước nhỏ từ trước → chụp ảnh lại, báo HR ghi chú vào biên bản bàn giao rồi mới ký xác nhận.
```

Tại sao tốt: Minh bạch ngay từ đầu. Khi bạn đổi máy hoặc bàn giao lại sau này, cả hai bên đều có căn cứ rõ ràng, không ai phải khó xử.

**❌ Cách tồi:**

```
Nhận máy, ký biên bản luôn không kiểm tra.
2 tuần sau mới phát hiện cổng sạc bên trái bị lỏng hoặc vỏ máy móp góc → báo lại thì không rõ lỗi có từ trước hay phát sinh trong quá trình dùng.
```

Tại sao tồi: Thiếu bước xác nhận ban đầu khiến việc bảo hành, sửa chữa hoặc quy trách nhiệm về sau rất mất thời gian.

---

## 2. Reset máy về trạng thái sạch — Không dùng tiếp môi trường của người cũ

Sau khi kiểm tra phần cứng xong, nếu bạn bật máy lên mà thấy **đã có sẵn user cũ, phần mềm hoặc dữ liệu từ người sử dụng trước** (thay vì màn hình chào mừng *Welcome / Setup Assistant* như máy mới), bạn **bắt buộc phải Reset toàn bộ máy** trước khi bắt đầu cài đặt.

### Tại sao bắt buộc phải Reset máy?

- **Tránh xung đột cấu hình ngầm:** File cấu hình cũ (Git config, SSH keys, biến môi trường, Docker volumes, cache) của người trước để lại rất dễ gây lỗi khó hiểu khi bạn làm việc hoặc khiến bạn commit nhầm tên người cũ.
- **Giải phóng dung lượng & tốc độ:** Xóa sạch các file rác, ứng dụng dư thừa hoặc tiến trình chạy ngầm không cần thiết.
- **Đảm bảo an toàn bảo mật:** Không giữ lại dữ liệu, lịch sử trình duyệt, hoặc phần mềm không rõ nguồn gốc từ người dùng trước.

### Cách thực hiện Reset nhanh

- **Trên macOS:**
  1. Vào **System Settings (Cài đặt hệ thống)** → **General (Cài đặt chung)** → **Transfer or Reset (Chuyển hoặc đặt lại)**.
  2. Chọn **Erase All Content and Settings... (Xóa tất cả nội dung và cài đặt)** và làm theo hướng dẫn trên màn hình để đưa máy về màn hình *Hello / Xin chào* ban đầu.
  3. *Lưu ý:* Nếu máy yêu cầu mật khẩu Apple ID / Find My của người cũ, hãy báo ngay cho **HR/Admin** để gỡ khóa trước khi tiếp tục.
- **Trên Windows:**
  1. Vào **Settings** → **System** → **Recovery** → **Reset this PC**.
  2. Chọn **Remove everything (Xóa mọi thứ)** → **Local reinstall** để cài lại bản Windows sạch.

**✅ Cách tốt:**

```
Mở máy thấy vẫn còn tài khoản và thư mục Download/Projects của nhân sự cũ.
→ Chạy ngay "Erase All Content and Settings" (mất khoảng 10–15 phút) để máy sạch hoàn toàn, rồi mới tạo user của riêng mình.
```

Tại sao tốt: Tốn 15 phút đầu giờ nhưng bạn có một chiếc máy sạch 100%, chính chủ từ tên user đến cấu hình hệ thống, không bao giờ gặp lỗi vặt do tàn dư của người trước.

**❌ Cách tồi:**

```
Thấy máy đang vào sẵn màn hình Desktop của người cũ → cứ thế dùng luôn cho tiện, chỉ đổi tên hoặc xóa vài thư mục ngoài màn hình.
```

Tại sao tồi: Hàng loạt cấu hình ẩn trong hệ thống vẫn mang thông tin của người cũ, ổ cứng bị chiếm dụng ngầm và tiềm ẩn rủi ro bảo mật.

---

## 3. Thiết lập tài khoản hệ thống & Bảo mật — Bắt buộc làm gì?

Tại Cyberk, chúng ta làm việc với nhiều dự án công nghệ và khách hàng quốc tế. **Bảo mật thiết bị là nguyên tắc sống còn** — một chiếc máy không khóa màn hình hoặc dính mã độc từ phần mềm lậu có thể làm lộ tài liệu, mã nguồn và tài sản của khách hàng.

### 4 thiết lập bảo mật bắt buộc ngay khi mở máy

1. **Đổi mật khẩu máy & Bật sinh trắc học (Touch ID / Windows Hello):**
   - Đổi ngay mật khẩu mặc định (nếu HR/IT bàn giao mật khẩu khởi tạo) sang mật khẩu mạnh của riêng bạn.
   - Thiết lập vân tay (Touch ID trên Mac / Windows Hello) để mở khóa nhanh và tiện lợi.

2. **Cấu hình tự động khóa màn hình (Auto-Lock) tối đa 5 phút:**
   - Cài đặt máy tự động khóa màn hình và yêu cầu mật khẩu ngay khi tắt màn hình hoặc sau tối đa **5 phút** không thao tác.
   - Tập thói quen bấm tổ hợp phím khóa máy mỗi khi rời khỏi chỗ ngồi (dù chỉ đi lấy nước hay đi vệ sinh):
     - **macOS:** `Ctrl + Cmd + Q`
     - **Windows:** `Win + L`

3. **Tài khoản Apple ID / Microsoft Account theo quy định công ty:**
   - **Không dùng Apple ID / iCloud cá nhân** để bật *Find My Mac* (Activation Lock) hoặc đồng bộ ảnh/dữ liệu cá nhân lên máy công ty.
   - Nếu cần đăng nhập App Store / Microsoft Store để tải phần mềm làm việc, hãy sử dụng tài khoản gắn với **email công ty** hoặc làm theo hướng dẫn của HR/Admin.
   - *Lý do:* Tránh trộn lẫn dữ liệu riêng tư vào máy công ty và tránh tình trạng máy bị dính khóa iCloud cá nhân khi thu hồi/đổi máy.

4. **Tuyệt đối KHÔNG cài phần mềm lậu / crack:**
   - Nghiêm cấm tải và cài đặt các phần mềm bẻ khóa (crack, patch, keygen) hoặc ứng dụng không rõ nguồn gốc trên máy làm việc.
   - Nếu công việc cần phần mềm trả phí, hãy trao đổi trực tiếp với **Line Manager** để công ty cấp bản quyền hoặc tìm giải pháp thay thế an toàn.

**✅ Cách tốt:**

```
Vừa nhận máy → đổi mật khẩu + cài Touch ID → chỉnh Auto-Lock 5 phút.
Cần dùng phần mềm thiết kế/chuyên dụng → nhắn hỏi Buddy/Manager xem công ty đang dùng bản nào hoặc xin cấp license.
```

Tại sao tốt: Máy an toàn ngay từ phút đầu, tuân thủ chuẩn bảo mật của công ty và khách hàng.

**❌ Cách tồi:**

```
Lên mạng tải bản "full thuốc/crack" về cài cho nhanh để làm việc.
Hoặc đăng nhập iCloud cá nhân, đồng bộ toàn bộ ảnh gia đình và mật khẩu riêng vào máy công ty.
```

Tại sao tồi: Phần mềm crack là con đường ngắn nhất để dính malware đánh cắp session trình duyệt, tài khoản Telegram, GitHub và dữ liệu dự án.

---

## 4. Cài đặt bộ công cụ chuẩn — Làm sao để "online" cùng team?

Sau khi xong bước bảo mật, bạn chỉ cần hoàn tất **4 mục dưới đây** trong buổi sáng ngày đầu để kết nối với toàn bộ công ty:

### Bước 4.1. Kết nối WiFi văn phòng
- Liên hệ **Buddy** hoặc **Line Manager** để nhận tên mạng WiFi văn phòng và mật khẩu.

### Bước 4.2. Cài đặt Google Chrome & Tạo Chrome Profile công việc
- Tải và cài đặt **Google Chrome** (nếu máy chưa có).
- Tạo một **Chrome Profile riêng** dành cho công việc và đăng nhập bằng **Email công ty** (do Manager/HR cấp).
- Mở **Gmail** và **Google Calendar**, bật thông báo trên trình duyệt (Desktop Notifications) để không bỏ lỡ lịch họp và email quan trọng.

**✅ Cách tốt:**

```
Tạo Chrome Profile riêng tên "Cyberk - [Tên bạn]" đăng nhập email công ty.
Mọi tài liệu, bookmark dự án, Google Meet của công ty chỉ mở trên profile này.
```

Tại sao tốt: Tách biệt hoàn toàn với tài khoản cá nhân. Khi bạn share màn hình trong cuộc họp với khách hàng hoặc đồng nghiệp, không bao giờ lo lộ tab cá nhân, thông báo riêng tư hay nhầm tài khoản Google khi mở tài liệu.

**❌ Cách tồi:**

```
Đăng nhập chung email công ty vào Chrome cá nhân đang có sẵn 4–5 tài khoản Gmail khác.
```

Tại sao tồi: Rất dễ gặp lỗi *"You need access"* khi mở link Google Meet/Docs của công ty do trình duyệt tự nhảy sang Gmail cá nhân, hoặc vô tình lộ thông tin cá nhân khi share màn hình.

### Bước 4.3. Cài đặt Telegram Desktop
- **Telegram** là kênh giao tiếp chính thức tại Cyberk (cả nội bộ lẫn với khách hàng).
- Tải và cài đặt **Telegram Desktop** lên máy tính, đăng nhập tài khoản của bạn.
- Nhờ **Buddy** hoặc **Line Manager** thêm vào các group chat của công ty và dự án.
- Kiểm tra cài đặt thông báo để đảm bảo bạn nhận được tin nhắn khi có người tag (`@username`).

### Bước 4.4. Kiểm tra bộ gõ tiếng Việt & Thiết bị họp (Mic / Loa / Camera)
- Cài đặt hoặc bật bộ gõ tiếng Việt phù hợp (bộ gõ mặc định trên macOS hoặc EVKey/OpenKey).
- Mở thử một phòng **Google Meet** trống để cấp quyền (Permission) cho Chrome sử dụng **Microphone**, **Camera** và **Screen Recording (Chia sẻ màn hình)** — tránh cảnh đến giờ họp với team/khách hàng mới loay hoay cấp quyền và phải khởi động lại trình duyệt.

---

## 5. Bước tiếp theo theo vai trò của bạn

Khi đã hoàn thành các bước trên, máy của bạn đã sẵn sàng cho công việc chung! Tùy theo vị trí, hãy tiếp tục như sau:

- **Dành cho mọi thành viên:** Quay lại [Cẩm nang Bắt đầu tại Cyberk](getting-started-handbook.md) để nắm lịch trình ngày đầu tiên, ăn trưa cùng team và đọc các quy định cốt lõi.
- **Dành riêng cho Developer:** Việc cài đặt môi trường lập trình (Git, IDE, Docker, biến môi trường `.env` và chạy thử dự án trên `localhost`) sẽ được thực hiện cùng Product Owner theo [Quy trình Onboarding Dự Án](../../04-developer/dev-project-onboarding/dev-project-onboarding-process.md).

---

## Checklist tự kiểm khi nhận máy

- [ ] Kiểm tra ngoại quan máy (màn hình, bàn phím, vỏ, cổng kết nối) và phụ kiện đi kèm (sạc, cáp...)
- [ ] Ký xác nhận biên bản bàn giao thiết bị với HR/Admin (ghi chú/chụp ảnh nếu có vết xước sẵn)
- [ ] **Reset máy về trạng thái sạch** (*Erase All Content and Settings* / *Reset this PC*) nếu máy còn dữ liệu hoặc user từ người sử dụng trước
- [ ] Tạo user mới của riêng bạn, đặt mật khẩu mạnh + thiết lập vân tay (Touch ID / Windows Hello)
- [ ] Cài đặt tự động khóa màn hình (Auto-Lock ≤ 5 phút) và nhớ phím tắt khóa máy (`Ctrl + Cmd + Q` / `Win + L`)
- [ ] Không đăng nhập iCloud/Find My cá nhân; dùng Apple ID / Microsoft Account theo quy định công ty
- [ ] Kết nối WiFi văn phòng
- [ ] Tạo Chrome Profile riêng cho công việc + đăng nhập email công ty + bật thông báo Gmail/Calendar
- [ ] Cài đặt Telegram Desktop + join các nhóm công ty/dự án cùng Buddy
- [ ] Kiểm tra bộ gõ tiếng Việt và cấp sẵn quyền Mic / Camera / Share màn hình trên Google Meet

---

## Tóm lại

| Giai đoạn | Việc cần làm | Nguyên tắc cốt lõi |
|-----------|-------------|-------------------|
| **1. Nhận bàn giao** | Kiểm tra máy, sạc, cấu hình + ký biên bản với HR/Admin | Kiểm tra kỹ ngay lúc nhận để minh bạch trách nhiệm |
| **2. Reset máy sạch** | Chạy *Erase All Content and Settings* (Mac) / *Reset PC* (Win) nếu còn dữ liệu cũ | Tuyệt đối không dùng tiếp user/môi trường dư thừa từ người trước |
| **3. Bảo mật máy** | Mật khẩu + Touch ID, Auto-Lock ≤ 5 phút, đúng quy định Apple ID/MS Account | Không khóa màn hình = rủi ro bảo mật; tuyệt đối không cài app crack |
| **4. Công cụ chuẩn** | WiFi, Chrome Profile công việc (Email công ty), Telegram, test Google Meet | Tách bạch profile công việc và cá nhân; online Telegram ngay sáng Ngày 1 |

---

## Liên kết

- [Quy trình Getting Started](getting-started-process.md) — Luồng tổng thể và checklist ngày đầu tiên
- [Bắt đầu tại Cyberk — Cẩm nang cho Newbie](getting-started-handbook.md) — Cách hoà nhập nhanh trong tuần đầu
- [Onboarding Dự Án (dành cho Developer)](../../04-developer/dev-project-onboarding/dev-project-onboarding-process.md) — Cài đặt môi trường code và chạy local trong 24h
