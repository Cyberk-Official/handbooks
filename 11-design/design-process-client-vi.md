# Cyberk – Quy trình Thiết kế (dành cho khách hàng)

> Từ ý tưởng đến sản phẩm sẵn sàng phát triển.

Bản gốc: [cyberk-quy-trinh-thiet-ke-vi.html](./cyberk-quy-trinh-thiet-ke-vi.html) (8 trang A4, có hình minh hoạ). Bản thiết kế chỉnh sửa được: https://claude.ai/artifact/31H3RN4cYZXBfgqqexgDUB

---

## 4 bước từ ý tưởng đến sản phẩm

Mỗi bước khép lại bằng một mốc để bạn xem, góp ý và duyệt trước khi sang bước tiếp theo.

01. **Khám phá & Prototype**: Nghiên cứu thị trường và người dùng, rồi biến thành bản thiết kế khung có thể bấm thử
02. **Định hướng thị giác & Màn hình mẫu**: Xem sản phẩm của bạn mang diện mạo thương hiệu trên vài màn hình chính, rồi chọn hướng đi
03. **Hệ thống thiết kế**: Một bộ quy chuẩn cho diện mạo sản phẩm, giúp mọi màn hình đồng bộ và AI xây dựng nhanh hơn
04. **Thiết kế chi tiết & Kiểm thử**: Hoàn thiện mọi màn hình, kể cả những lúc hay bị bỏ quên: mất mạng, chưa có dữ liệu, gặp lỗi

---

## Ba nguyên tắc

1. **Khung trước, màu sau.** Chốt luồng và cấu trúc bằng bản đen trắng trước khi đầu tư vào màu sắc và hình ảnh.
2. **Kiểm chứng thật sớm.** Thử với người dùng thật và rà soát kỹ thuật khi mọi thay đổi còn ít tốn kém.
3. **Bạn duyệt ở mỗi mốc.** Mỗi bước khép lại bằng một mốc duyệt rõ ràng, không bất ngờ ở cuối dự án.

---

## Bước 01 · Khám phá & Prototype
*Đúng vấn đề, đúng luồng*

_Hình minh hoạ: thẻ nghiên cứu → màn hình wireframe → màn hình danh sách wireframe_

**Chúng tôi làm gì**
- Xem lại mục tiêu kinh doanh, yêu cầu và thương hiệu của bạn
- Nghiên cứu thị trường, đối thủ và các ứng dụng người dùng của bạn đã quen
- Trò chuyện với người dùng mục tiêu, hoặc phân tích phản hồi bạn đã có
- Vẽ luồng sử dụng và khung từng màn hình (wireframe)
- Nối thành prototype bấm thử được và cho người dùng thử

**Bạn nhận được**
- Nghiên cứu thị trường & đối thủ
- Chân dung người dùng
- Luồng sử dụng & wireframe
- Prototype bấm thử được
- Kết quả thử nghiệm

**Chúng tôi cần từ bạn:** Tài liệu nghiệp vụ, brand guideline, kết nối với người dùng thật nếu có, và góp ý về các luồng.

**Mốc duyệt:** Thống nhất mục tiêu, luồng & danh sách màn hình

---

## Bước 02 · Định hướng thị giác & Màn hình mẫu
*Thử phong cách trên vài màn hình*

_Hình minh hoạ: moodboard + hai màn hình mẫu đã lên màu_

**Chúng tôi làm gì**
- Xây dựng moodboard: màu sắc, kiểu chữ, phong cách hình ảnh
- Thiết kế hoàn chỉnh 2–4 màn hình cốt lõi
- Kiểm tra độ tương phản, thứ bậc thị giác và xem thử trên điện thoại thật

**Bạn nhận được**
- Moodboard định hướng
- 2–4 màn hình mẫu hoàn chỉnh

**Chúng tôi cần từ bạn:** Cảm nhận của bạn và lựa chọn phương án phù hợp nhất với thương hiệu.

**Mốc duyệt:** Chốt phong cách thị giác

---

## Bước 03 · Hệ thống thiết kế
*Một bộ quy chuẩn, xây dựng nhanh hơn*

_Hình minh hoạ: bảng hệ thống thiết kế: màu sắc, kiểu chữ, thành phần_

**Chúng tôi làm gì**
- Đặt quy chuẩn cho màu sắc, kiểu chữ và khoảng cách
- Tạo sẵn bộ nút bấm, ô nhập và thẻ thông tin dùng lại cho mọi màn hình
- Sắp xếp mọi thứ để công cụ AI có thể đọc và chuyển thành code
- Đảm bảo chữ dễ đọc và nút dễ bấm

**Bạn nhận được**
- Thư viện phong cách hoàn chỉnh trên Figma
- File sẵn sàng cho đội lập trình và công cụ AI
- Hướng dẫn sử dụng ngắn gọn

**Chúng tôi cần từ bạn:** Không bắt buộc. Bạn có thể xem và góp ý.

**Mốc duyệt:** Xác nhận bộ quy chuẩn

---

## Bước 04 · Thiết kế chi tiết & Kiểm thử
*Không bỏ sót màn hình nào*

_Hình minh hoạ: ba màn hình tình huống hiếm: mất mạng, trống, báo lỗi_

**Chúng tôi làm gì**
- Hoàn thiện toàn bộ màn hình còn lại của sản phẩm
- Thiết kế những tình huống hay bị bỏ quên: mất mạng, chưa có dữ liệu, báo lỗi
- Chuốt lại từng chi tiết để cả ứng dụng trông hoàn chỉnh
- Kiểm tra lần cuối với nội dung thật trên điện thoại thật

**Bạn nhận được**
- Toàn bộ màn hình của ứng dụng, đã hoàn thiện
- Giao diện chỉn chu, đồng bộ
- File sẵn sàng bàn giao cho đội lập trình

**Chúng tôi cần từ bạn:** Duyệt từng màn hình và gửi nội dung chữ chính thức.

**Mốc duyệt:** Chốt thiết kế để phát triển

---

## Bước tiếp theo

**Bắt đầu với ý tưởng của bạn.** Một buổi trao đổi ngắn là đủ để chúng tôi hiểu bài toán và đề xuất phạm vi phù hợp.

_Thông tin liên hệ trong bản thiết kế đang để trống ([Email liên hệ], [Số điện thoại]), cần điền trước khi gửi khách._
