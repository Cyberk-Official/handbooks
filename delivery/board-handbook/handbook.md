
# Handbook Hướng dẫn quản lý dự án: 

Dành cho mọi thành viên của Cyberk. 
Đọc sách để nắm được phương pháp quản trị hiệu quả minh bạch của Cyberk. 

## Quản lý dự án là gì? 

Tại Cyberk quản lý dự án bao gồm 4 thành phần: 

Scope: Đề bài, tổng khối lượng công việc. 
Deadline: Deadline cho mỗi phần công việc đó. 
Resource: Nguồn lực, effort, số lượng nhân sự dành cho dự án đó. 
Responsibility: Trách nhiệm công việc, tinh thần hoàn thành công việc của từng cá nhân 

## Quản lý dự án tốt là: 

- Scope rõ ràng, được cập nhật liên tục, và không bị out-dated 
- Deadline là cố định, và hiếm khi bị trễ, Luôn bàn giao đúng hạn 
- Resource hợp lý, Anh em hiếm khi phải overtime. 
- Team đoàn kết, Anh em luôn sẵn sàng hỗ trợ nhau để hoàn thành dự án 

## Quản lý dự án thì cần quản lý: 

- Epic: Là đề bài, là các tính năng / đầu việc cụ thể cần phải hoàn thành. Luôn đảm bảo Epic đúng hạn.
- Milestone: Là mốc bàn giao công việc (thường là Weekly hoặc các mốc đặc biệt như Alpha, Beta, YYYY-MM-DD).
- Tasks: Là đầu việc mà một người có thể hoàn thành trong dưới 4 giờ. Luôn làm tasks trong 1 ngày.
- Bugs: Là các issue của dự án. Cần được phát hiện càng sớm càng tốt. 
- Board: Là bảng tổng hợp của Tasks và Bugs, nơi thể hiện tổng quan của dự án, Luôn đảm bảo gọn gàng, rõ ràng. 

### Làm thế nào để quản lý dự án tốt ?

### Tasks: 
- Luôn cập nhật task mới nhất lên board.
- Bỏ các tasks đã outdate.
- Task/Bugs mới được tạo luôn đầy đủ các thông tin: Title, Description, deadline, assignees, labels, Epics, Milestones.

### Bugs: 
- Mô tả đầy đủ, rõ ràng sao cho người đọc không cần hỏi lại cũng hiểu được vấn đề.
- Deadline luôn nằm trong Epics/Milestones, và Fix càng sớm càng tốt. 
- Người chịu trách nhiệm cho Epic, thì sẽ chịu trách nhiệm cho bugs thuộc về Epic đó. 

### Epic: 
- Epic là một tính năng cụ thể hoặc một tập hợp công việc lớn của hệ thống.
- Đủ nhỏ sao cho như là một tính năng, hoặc một cập nhật chỉnh sửa, đủ lớn để 1 người hoặc 1 team < 5 người làm việc dưới 1 tuần. 
- Luôn có 1 và chỉ 1 người chịu trách nhiệm cho 1 Epic tại 1 thời điểm. 
- Có thêm Epic có nghĩa là cần mở rộng effort, thay đổi scope. Khi cần có thêm Epic hãy báo cáo ngay cho quản lý. 
- Khi khách hàng có thêm Epic có nghĩa là có cơ hội mở rộng hợp đồng, cần giúp khách hàng làm rõ, tư vấn, và báo cáo cho quản lý để đàm phán hợp đồng.

### Milestone (Mốc bàn giao):
- Milestone là một mốc bàn giao công việc, thường là Weekly (hàng tuần) nếu như không có gì đặc biệt. Có thể đặt tên theo Tuần đó (Ví dụ: `2026-08-15`, `W33`) hoặc theo tên phiên bản bàn giao (Ví dụ: `Alpha`, `Beta`).

### Board: 

- Cả team nhìn vào và biết phải làm gì trong tuần. 
- Mỗi người phải có một dashboard cá nhân, ví dụ như: "Tất cả các task/bugs của Đức (Đức's all Tasks/bugs)", "Sprint 33 - Công việc của team tuần thứ 33".
- 3 loại board cơ bản: 
    - Sprint board: là các tasks, bugs cần được team hoàn thành trong tuần hiện tại. 
    - Bugs board: là danh sách bugs đang tồn đọng của dự án.
    - Personal board: là dashboard của từng cá nhân, cho phép cá nhân tự nhìn thấy được effort của mình, và biết mình cần phải làm gì.

- 3 Loại board nâng cao: 
    - Sprint Future board: là các tasks, bugs cần được team hoàn thành trong tuần tiếp theo. 
    - Gantt chart: là biểu đồ thể hiện tiến độ trực quan của dự án.
    - Filter Boards: là các board được filter theo từng Epic, từng Milestone, hoặc từng project để dễ dàng quản lý. 

- Board tốt là cả team nhìn vào và biết phải làm gì trong tuần. Dự án có đang trễ hạn hay không. 

---

## Tạo Board & Tạo Task chuẩn (GitHub Projects)

### 1. Hướng dẫn Tạo Project Board Chuẩn

Mọi dự án tại Cyberk đều bắt buộc sử dụng **GitHub Projects** (Project V2) làm nguồn sự thật duy nhất.

#### 📌 Phụ phụ: Quy tắc đặt tên Board (Board Naming Convention)
- **Các dự án phần mềm / sản phẩm**: Đặt theo định dạng `[project-name]-management`
  - *Ví dụ*: `koto-management`, `atlantis-management`, `relmo-management`.
- **Board dành cho bộ phận / phòng ban cụ thể**: Đặt tên theo đúng tên bộ phận
  - *Ví dụ*: `leader`, `media`, `design`, `dev`, `qa`.

#### Các bước khởi tạo Board:
1. Truy cập vào GitHub Organization `Cyberk-Official` → Chọn tab **Projects** → Nhấn **New project**.
2. Đặt tên Board theo chuẩn Quy tắc đặt tên ở trên (Ví dụ: `atlantis-management` hoặc `media`).
3. **Cấu hình các Field bắt buộc (Project Fields):**
   - **`Status`**: `Backlog` *(mặc định)*, `Todo`, `In Progress`, `Done`.
   - **`Assignees`**: Chọn chính xác GitHub ID của nhân sự (`anna-cyberk`, `anderson-cyberk`, `hungdn-cyberk`, `truonglx-cyberk`).
   - **`Labels`**: Nhãn phân loại (`operations`, `dev`, `design`, `qa`, `bug`).
   - **`Epic`**: Gắn đúng tên tính năng / Epic của dự án.
   - **`Milestone`**: BẮT BUỘC gắn mốc bàn giao (`YYYY-MM-DD`, `Alpha`, `Beta`...).
   - **`Week`**: Số tuần thực hiện trong năm (Ví dụ: `33`, `34`, `35`).
   - **`Start date` & `Target date`**: Ngày bắt đầu và hạn chót hoàn thành.
   - **`Estimate`**: Ước tính giờ công (tính theo giờ).

#### Thiết lập 3 View chuẩn cho Board:
- 📌 **View 1: Sprint Board** (Filter theo `Week = [Tuần hiện tại]` & Group theo `Status`).
- 🐞 **View 2: Bugs Board** (Filter theo `Labels = bug`).
- 👤 **View 3: Personal Board** (Mỗi member bắt buộc phải có một dashboard riêng cho cá nhân mình, ví dụ filter: `Assignees = anderson-cyberk` hoặc `Assignees = anna-cyberk`).

---

### 2. Hướng dẫn Tạo Task Chuẩn (Standard Task)

Một task chuẩn giúp cả team không cần phải trao đổi lại vẫn hiểu và thực thi chính xác.

#### Quy tắc tạo Task:
- **Độ dài task**: Đủ nhỏ để 1 người hoàn thành trong **dưới 4 giờ** (không tạo task quá to).
- **Trạng thái khởi tạo**: Tất cả task mới tạo luôn để ở trạng thái **`Backlog`**.
- **Tiêu đề task (Title)**: Ngắn gọn, bắt đầu bằng hành động, ví dụ: `[IP-037] Gửi thông báo Telegram W33-W36`.

#### 6 Trường bắt buộc phải điền khi tạo Task:
1. ✅ **`Assignees`**: BẮT BUỘC gán **GitHub ID chính xác** (Ví dụ: `@anna-cyberk`).
2. ✅ **`Target date` (Deadline)**: BẮT BUỘC có hạn chót cụ thể (`YYYY-MM-DD`).
3. ✅ **`Labels`**: BẮT BUỘC chọn đúng loại việc (Ví dụ: `operations`, `dev`).
4. ✅ **`Epic`**: Ghi rõ tính năng / Epic liên quan.
5. ✅ **`Milestone`**: BẮT BUỘC có Milestone. Milestone là một mốc bàn giao, thường là Weekly nếu như không có gì đặc biệt, có thể đặt tên theo ngày (Ví dụ: `2026-08-15`) hoặc tên phiên bản bàn giao (Ví dụ: `Alpha`, `Beta`).
6. ✅ **`Week`**: BẮT BUỘC ghi số tuần thực hiện (Ví dụ: `33`).

#### Format nội dung Task (Body Markdown):
```markdown
## Mục tiêu
[Mô tả ngắn gọn kết quả cần đạt được trong 1-2 câu]

## Checklist công việc
- [ ] Đầu việc 1
- [ ] Đầu việc 2
- [ ] Đầu việc 3

## Tài liệu / Lưu ý
> [Ghi chú đặc biệt hoặc link tài liệu tham khảo nếu có]
```

---

## Những dấu hiệu khi quản lý dự án không tốt. 

- Bạn không rõ, mơ hồ, hoặc không biết mục tiêu cuối cùng của dự án là gì (Scope) ? Tháng này phải bàn giao tính năng nào cho khách hàng, tại sao ? 
- Không rõ việc cần làm và chờ người quản lý giao việc cho bạn ? hoặc bạn không biết mình cần phải làm gì. 
- Bạn không biết đâu là task quan trọng nhất cần phải làm ngay trong hôm nay ? 
- Bạn không rõ rủi ro, tính năng nào có rủi ro gì cần lưu ý. Chỗ nào là điểm nóng cần phải giải quyết ngay ? 
- Bạn là "Tôn Ngộ Không" gánh team, trong khi những người còn lại là Trư Bát Giới, Sa Tăng.
- Bạn không có task nào, hoặc task của bạn chỉ có đủ đến hết tuần, và bạn không rõ mình cần làm gì về mặt dài hạn.
- Bạn được assign task-by-task thay vì theo một Epic cụ thể.
- Task tạo ra không có deadline, Epic, Milestones.
- Task của bạn treo từ tuần này qua tuần khác.
- Todo bị Abandoned, không có ai làm, hoặc có quá nhiều / quá ít Todo.

