# Screen Specifications & Design Intent

## 1. Bảng Tổng Hợp Ánh Xạ Màn Hình (Screen Mapping & Assets Table)

Hệ thống **FPT Attendance System (CAMPUS / STUDIO)** gồm đúng 10 màn hình chuẩn hóa từ S01 đến S10, kết nối trực tiếp với 10 file thiết kế Figma Final UI và 10 bản vẽ Stitch UI ban đầu:

| Mã MH | Tên Màn Hình Chuẩn Hóa | Figma Final UI (Page 03) | Stitch UI Ban Đầu (Page 01) | Mục Đích & Nghiệp Vụ Chính | Gán Vào User Flow |
| :---: | :--- | :--- | :--- | :--- | :---: |
| **S01** | **Đăng nhập (Google SSO)** | [`assets/figma/S01 — Đăng nhập.png`](<../assets/figma/S01 — Đăng nhập.png>) | [`assets/stitch/scr01_google_signin.png`](../assets/stitch/scr01_google_signin.png) | Xác thực 1-Touch bằng tài khoản FPT Education (`@fpt.edu.vn`) | Flow 1 |
| **S02** | **Tổng quan giảng dạy** | [`assets/figma/S02 — Tổng quan giảng dạy.png`](<../assets/figma/S02 — Tổng quan giảng dạy.png>) | [`assets/stitch/scr02_home_dashboard.png`](../assets/stitch/scr02_home_dashboard.png) | Dashboard trung tâm: Ca học hôm nay, thẻ Tiết đang điểm danh, nút Tạo lớp & Xếp lịch | Flow 1, 2, 3 |
| **S03** | **Lớp học của tôi** | [`assets/figma/S03 — Lớp học của tôi.png`](<../assets/figma/S03 — Lớp học của tôi.png>) | [`assets/stitch/scr05_class_list.png`](../assets/stitch/scr05_class_list.png) | Quản lý danh sách lớp giảng dạy: PRM393 (SE1917), PRN232, SWP391 | Flow 2 |
| **S04** | **Chi tiết lớp học** | [`assets/figma/S04 — Chi tiết lớp học.png`](<../assets/figma/S04 — Chi tiết lớp học.png>) | [`assets/stitch/scr06_history_stats.png`](../assets/stitch/scr06_history_stats.png) | Thống kê tích lũy học kỳ (Tỷ lệ vắng 4.0%), danh sách sinh viên vắng nhiều cảnh báo cấm thi | Flow 2 |
| **S05** | **Nhập sinh viên từ Sheet** | [`assets/figma/S05 — Nhập sinh viên từ Google Sheet.png`](<../assets/figma/S05 — Nhập sinh viên từ Google Sheet.png>) | [`assets/stitch/scr07_google_sheet_link.png`](../assets/stitch/scr07_google_sheet_link.png) | Wizard 3 bước nhập URL Google Sheet, chọn tab lớp học và đồng bộ 35 sinh viên | Flow 2 |
| **S06** | **Lịch dạy theo tuần** | [`assets/figma/S06 — Lịch dạy (Lịch tuần di động).png`](<../assets/figma/S06 — Lịch dạy (Lịch tuần di động).png>) | [`assets/stitch/scr05_schedule_calendar.png`](../assets/stitch/scr05_schedule_calendar.png) | Thời khóa biểu tuần di động, bộ chọn ngày thứ T2–CN, chấm báo hiệu ca dạy | Flow 3 |
| **S07** | **Xếp lịch tiết học** | [`assets/figma/S07 — Xếp lịch tiết học.png`](<../assets/figma/S07 — Xếp lịch tiết học.png>) | [`assets/stitch/scr03_create_schedule.png`](../assets/stitch/scr03_create_schedule.png) | Form tạo ca học mới cho lớp, chọn Slot 1, Phòng 101 và xử lý xung đột phòng | Flow 3 |
| **S08** | **Chi tiết tiết học** | [`assets/figma/S08 — Chi tiết tiết học.png`](<../assets/figma/S08 — Chi tiết tiết học.png>) | [`assets/stitch/scr03_session_detail.png`](../assets/stitch/scr03_session_detail.png) | Xem chi tiết ca học PRM393 Slot 1 (07:00–09:15) Phòng 101, cảnh báo giờ & Nút Mở điểm danh | Flow 1 |
| **S09** | **Điểm danh trực tiếp** | [`assets/figma/S09 — Điểm danh trực tiếp.png`](<../assets/figma/S09 — Điểm danh trực tiếp.png>) | [`assets/stitch/scr03_live_qr_attendance.png`](../assets/stitch/scr03_live_qr_attendance.png) | Dynamic QR đếm ngược 45s chống điểm danh hộ, sĩ số realtime 28/35, nút Phóng to QR | Flow 1 |
| **S10** | **Báo cáo điểm danh** | [`assets/figma/S10 — Báo cáo điểm danh.png`](<../assets/figma/S10 — Báo cáo điểm danh.png>) | [`assets/stitch/scr04_attendance_report.png`](../assets/stitch/scr04_attendance_report.png) | Tổng kết ca học (26 có mặt, 2 muộn, 7 vắng), Nút xuất sang Cột F Google Sheet | Flow 1 |

---

## 2. Đặc Tả Chi Tiết Từng Màn Hình (Detailed Intent & Constraints per Screen)

### S01 — Đăng nhập (Google SSO Screen)
- **Mục đích:** Xác thực danh tính Giảng viên & Sinh viên nhanh chóng qua tài khoản Google trường FPT.
- **Bố cục & Nội dung:**
  - Background ảnh campus trường FPT phủ màu gradient xanh đen (`#0A1A18` 60% $\rightarrow$ `#05100E` 80%).
  - Cụm nhận diện thương hiệu: "CAMPUS / STUDIO", khẩu hiệu "Có mặt. Kết nối. Tiến xa."
  - Card trắng nổi bo góc 24dp, Logo FPT Education căn giữa.
  - Tiêu đề "Đăng nhập" (26sp bold `#1E293B`), mô tả "Để tiếp tục sử dụng ứng dụng điểm danh FPT University".
  - Nút Google Blue `#4285F4` toàn chiều rộng (cao 56dp, icon Google + "Đăng nhập bằng Google").
  - Phân cách "FPT UNIVERSITY", ghi chú bảo mật có icon khiên: "Kết nối bằng tài khoản Google của bạn".
- **Trạng thái:** Default, Loading (vòng xoay trắng), Error (SnackBar nếu không phải email `@fpt.edu.vn`).
- **Liên kết file:** Figma: [`assets/figma/S01 — Đăng nhập.png`](<../assets/figma/S01 — Đăng nhập.png>) | Stitch: [`assets/stitch/scr01_google_signin.png`](../assets/stitch/scr01_google_signin.png).

---

### S02 — Tổng quan giảng dạy (Home Dashboard)
- **Mục đích:** Cung cấp bức tranh toàn cảnh về lịch giảng dạy trong ngày, đưa hành động điểm danh lên vị trí ưu tiên cao nhất.
- **Bố cục & Nội dung:**
  - Header thanh thoát nền kem `#F5F4EC`: Dòng nhỏ "FPT Attendance", Tiêu đề "Tổng quan", Avatar "N" (`36x36 dp`).
  - Dòng ngày "Thứ Bảy, 03/10/2026", 2 card tóm tắt nhanh: "2 tiết hôm nay" và "1 đang điểm danh".
  - **Khối ưu tiên cao nhất:** Card Tiết đang điểm danh (PRM393 · SE1917, Slot 2, Phòng 101) kèm nút chính "Xem điểm danh" màu xanh đậm `#173D35` hiển thị ngay trong màn hình đầu (Above the fold).
  - Khối Tiết tiếp theo: Card PRN232 (Slot 3, Phòng 203, badge "Chưa đến giờ").
  - Cụm nút hành động: "+ Tạo lớp học" (vàng đất `#D69E2E`) và "Xếp lịch".
  - Thanh Bottom Navigation 4 mục cố định: Tổng quan, Lớp học, Lịch dạy, Báo cáo.
- **Trạng thái:** Populated (đủ ca học), Empty ("Hôm nay không có tiết dạy"), Loading (Skeleton placeholder).
- **Liên kết file:** Figma: [`assets/figma/S02 — Tổng quan giảng dạy.png`](<../assets/figma/S02 — Tổng quan giảng dạy.png>) | Stitch: [`assets/stitch/scr02_home_dashboard.png`](../assets/stitch/scr02_home_dashboard.png).

---

### S03 — Lớp học của tôi (Class List)
- **Mục đích:** Quản lý toàn bộ danh sách lớp giảng dạy trong học kỳ hiện tại.
- **Bố cục & Nội dung:**
  - Thanh tìm kiếm mã lớp/môn học (debounce 300ms) và dropdown lọc học kỳ "FA2026".
  - Nút "+ Tạo lớp học" và nút toàn chiều rộng "Nhập tất cả lớp từ Sheet".
  - Danh sách card các lớp: PRM393 (SE1917, 35 SV, 8 buổi), PRN232 (SE1918, 32 SV), SWP391.
  - Badge trạng thái liên kết Google Sheet (chấm xanh báo hiệu đã kết nối bảng tính).
- **Trạng thái:** Populated (danh sách 3 lớp), Search Empty ("Không tìm thấy lớp học phù hợp").
- **Liên kết file:** Figma: [`assets/figma/S03 — Lớp học của tôi.png`](<../assets/figma/S03 — Lớp học của tôi.png>) | Stitch: [`assets/stitch/scr05_class_list.png`](../assets/stitch/scr05_class_list.png).

---

### S04 — Chi tiết lớp học (Class Detail & Thống kê tích lũy)
- **Mục đích:** Cung cấp góc nhìn toàn cảnh về mức độ chuyên cần của cả lớp trong học kỳ để phát hiện sinh viên vắng nhiều nguy cơ cấm thi.
- **Bố cục & Nội dung:**
  - Thông tin lớp: PRM393 · SE1917, Học kỳ FA2026, Sĩ số 35 sinh viên.
  - Chỉ số tổng quan: Tỷ lệ vắng tích lũy 4.0% (7/175 lượt vắng).
  - Lịch sử các ca học đã qua và ca học sắp tới kèm trạng thái.
  - Bảng cảnh báo: "Sinh viên vắng nhiều nhất" hiển thị số tiết và phần trăm: Nguyễn Văn An (3/5 tiết - 60% vắng - cảnh báo đỏ), Trần Minh Bình (40%), Lê Ngọc Chi (20%).
- **Trạng thái:** Normal, Warning Alert (đánh dấu đỏ sinh viên vượt ngưỡng 20% vắng).
- **Liên kết file:** Figma: [`assets/figma/S04 — Chi tiết lớp học.png`](<../assets/figma/S04 — Chi tiết lớp học.png>) | Stitch: [`assets/stitch/scr06_history_stats.png`](../assets/stitch/scr06_history_stats.png).

---

### S05 — Nhập sinh viên từ Google Sheet (3-Step Wizard)
- **Mục đích:** Hướng dẫn giảng viên liên kết và nạp danh sách 35 sinh viên từ Google Sheets vào lớp học.
- **Bố cục & Nội dung:**
  - Thông tin lớp đích: PRM393 · SE1917 · FA2026.
  - Thanh chỉ báo 3 bước: "1. Chọn file" $\rightarrow$ "2. Chọn tab" $\rightarrow$ "3. Kết quả".
  - Ô nhập "Đường dẫn hoặc ID Google Sheet", hộp hướng dẫn cấp quyền Viewer cho email hệ thống.
  - Nút vàng đất "Lấy danh sách tab $\rightarrow$", danh sách chọn tab (`12_PRM393_SE1917`).
- **Trạng thái:** Step 1 (Input URL), Step 2 (Select Tab), Step 3 (Success: nạp 35 sinh viên), Error (Không đọc được file / Sai quyền).
- **Liên kết file:** Figma: [`assets/figma/S05 — Nhập sinh viên từ Google Sheet.png`](<../assets/figma/S05 — Nhập sinh viên từ Google Sheet.png>) | Stitch: [`assets/stitch/scr07_google_sheet_link.png`](../assets/stitch/scr07_google_sheet_link.png).

---

### S06 — Lịch dạy theo tuần (Schedule Calendar)
- **Mục đích:** Xem thời khóa biểu các ca giảng dạy theo tuần dạng lịch di động trực quan.
- **Bố cục & Nội dung:**
  - Thanh điều hướng tuần (28/09 – 04/10/2026).
  - Bộ chọn ngày thứ trong tuần (T2 đến CN) với chấm màu báo hiệu ca dạy (Thứ Bảy 03/10 có chấm xanh).
  - Danh sách ca dạy trong ngày: PRM393 (Slot 2, Phòng 101) và PRN232 (Slot 3, Phòng 203) kèm nút "Xem điểm danh".
- **Trạng thái:** Date Selected (hiển thị ca học), Empty Date ("Không có ca dạy trong ngày được chọn").
- **Liên kết file:** Figma: [`assets/figma/S06 — Lịch dạy (Lịch tuần di động).png`](<../assets/figma/S06 — Lịch dạy (Lịch tuần di động).png>) | Stitch: [`assets/stitch/scr05_schedule_calendar.png`](../assets/stitch/scr05_schedule_calendar.png).

---

### S07 — Xếp lịch tiết học (Schedule Creation & Conflict Detection)
- **Mục đích:** Cho phép giảng viên tạo lịch học mới cho lớp và kiểm tra xung đột phòng học.
- **Bố cục & Nội dung:**
  - Form chọn: Lớp học (PRM393 · SE1917), Ngày học (05/10/2026), Slot học (Slot 1 · 07:00–09:15), Phòng học (Phòng 101).
  - Khối tóm tắt thông tin ca học trước khi lưu.
  - Nút "Lưu lịch học" (cao 52dp) và "Hủy bỏ".
- **Trạng thái:**
  - *Default:* Form nhập liệu sẵn sàng.
  - *Conflict Error (`S07-CONFLICT`):* Cảnh báo đỏ "Bạn đã có lịch dạy trong khung giờ này. Chọn slot hoặc ngày khác." Cho phép đổi sang Phòng 203 hoặc chọn Slot 2 mà không mất dữ liệu đã nhập.
  - *Success (`S07-SUCCESS`):* Thông báo lưu lịch thành công và chuyển sang Lịch tuần S06.
- **Liên kết file:** Figma: [`assets/figma/S07 — Xếp lịch tiết học.png`](<../assets/figma/S07 — Xếp lịch tiết học.png>) | Stitch: [`assets/stitch/scr03_create_schedule.png`](../assets/stitch/scr03_create_schedule.png).

---

### S08 — Chi tiết tiết học (Session Detail)
- **Mục đích:** Cung cấp thông tin chi tiết của một ca học trước khi bấm mở phiên điểm danh.
- **Bố cục & Nội dung:**
  - Thẻ môn học PRM393 (Lớp SE1917, Sĩ số 35 sinh viên, Học kỳ FA2026).
  - Thông tin thời gian: Ngày 05/10/2026, Slot 1 (07:00–09:15), Phòng học 101.
  - Hộp thông báo trạng thái: "Chưa đến giờ mở điểm danh" (vàng cam) hoặc "Sẵn sàng mở điểm danh" (xanh).
  - Nút hành động chính: "Mở điểm danh" màu vàng đất `#D69E2E`.
- **Trạng thái:** Pending (chưa đến giờ - khóa nút kèm ghi chú giải thích), Ready (nút kích hoạt).
- **Liên kết file:** Figma: [`assets/figma/S08 — Chi tiết tiết học.png`](<../assets/figma/S08 — Chi tiết tiết học.png>) | Stitch: [`assets/stitch/scr03_session_detail.png`](../assets/stitch/scr03_session_detail.png).

---

### S09 — Điểm danh trực tiếp (Live Dynamic QR Session)
- **Mục đích:** Cốt lõi của hệ thống điểm danh chống gian lận, phát mã QR động và theo dõi sĩ số theo thời gian thực.
- **Bố cục & Nội dung:**
  - Header cảnh báo: "Đang điểm danh trực tiếp - Cập nhật mỗi 5 giây".
  - Thống kê 2x2: Sĩ số 35, Đã điểm danh 28, Chưa điểm danh 7, Tỷ lệ tham gia 80%.
  - Thẻ mã QR động: Kích thước $224\times 224\text{ dp}$, đồng hồ đếm ngược bảo mật `00:45` ("Mã QR còn hiệu lực: 00:45").
  - 2 nút điều khiển: "Làm mới QR" và "Phóng to QR" (`S09-QR-OVERLAY` mở toàn màn hình cho sinh viên cuối giảng đường Phòng 101 quét).
  - Danh sách sinh viên quét thành công thời gian thực (Nguyễn Văn An 07:06:14, Trần Minh Bình 07:06:28...).
  - Nút đỏ cảnh báo "Kết thúc điểm danh" (kèm dialog xác nhận 7 sinh viên chưa quét sẽ bị đánh vắng).
- **Trạng thái:** Live Active, Enlarged Overlay, Confirm Finish Dialog, Connection Error.
- **Liên kết file:** Figma: [`assets/figma/S09 — Điểm danh trực tiếp.png`](<../assets/figma/S09 — Điểm danh trực tiếp.png>) | Stitch: [`assets/stitch/scr03_live_qr_attendance.png`](../assets/stitch/scr03_live_qr_attendance.png).

---

### S10 — Báo cáo điểm danh (Attendance Report & Sheets Export)
- **Mục đích:** Tổng kết kết quả sau khi kết thúc ca học và xuất dữ liệu sang Google Sheets với 1 chạm.
- **Bố cục & Nội dung:**
  - Badge trạng thái "Đã kết thúc - Sĩ số: 35 sinh viên".
  - Thống kê 4 ô màu sắc: Có mặt 26 (xanh), Đi muộn 2 (vàng cam), Vắng 7 (đỏ), Có phép 0. Tỷ lệ tham gia 80% Đạt chỉ tiêu.
  - Danh sách chi tiết sinh viên phân loại theo tab Có mặt / Đi muộn / Vắng.
  - Card đồng bộ Google Sheet: "Tab đã liên kết: 12_PRM393_SE1917 - Kết quả sẽ được ghi vào cột F của tab này".
  - Nút lớn vàng đất "Xuất sang Google Sheets" (kèm dialog xác nhận ghi đè cột F).
- **Trạng thái:** Summary View, Confirm Export Dialog, Exporting Spinner, Export Success SnackBar.
- **Liên kết file:** Figma: [`assets/figma/S10 — Báo cáo điểm danh.png`](<../assets/figma/S10 — Báo cáo điểm danh.png>) | Stitch: [`assets/stitch/scr04_attendance_report.png`](../assets/stitch/scr04_attendance_report.png).
