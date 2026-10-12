# Design Decisions & Accessibility Checklist

## 1. Core Design Decisions ($\le 10$)

| # | Quyết định Thiết kế | Các lựa chọn cân nhắc | Lựa chọn cuối cùng & Lập luận | Tác động UI / UX |
| :--- | :--- | :--- | :--- | :--- |
| **1** | **Mã QR Động tự làm mới 45 giây** | Mã QR tĩnh cố định vs Mã QR động đếm ngược 45s | **QR Động đếm ngược 45s:** Ngăn chặn triệt để tình trạng sinh viên chụp ảnh mã gửi qua Zalo/Messenger cho bạn ở nhà điểm danh hộ. | Tăng tính trung thực và độ tin cậy tuyệt đối cho dữ liệu điểm danh. |
| **2** | **Đồng bộ trực tiếp với Google Sheets** | Lưu database nội bộ riêng vs Tích hợp trực tiếp Google Sheets | **Tích hợp Google Sheets (Cột F):** Giảng viên FPT quản lý điểm danh bằng file Sheet của trường; cho phép ghi kết quả vào cột F của tab môn học. | Loại bỏ 100% công đoạn copy-paste thủ công sau buổi dạy. |
| **3** | **4 Thẻ thống kê Realtime trên màn hình QR** | Chỉ hiện mã QR vs Hiện kèm 4 thẻ sĩ số trực tiếp | **4 Thẻ trực tiếp (35 Sĩ số, 28 Đã quét, 7 Chưa quét, 80% Tỷ lệ):** Giúp giảng viên nhìn thấy ngay tiến độ lớp học mà không cần đếm tay. | Tăng khả năng hiển thị trạng thái hệ thống (Nielsen Heuristic #1). |
| **4** | **Nút Phóng to QR & Làm mới QR** | Khung QR cố định vs Có nút phóng to toàn màn hình | **Có nút "Phóng to QR":** Hỗ trợ chiếu lên máy chiếu phòng học lớn (Phòng 101 cơ sở TP. Hồ Chí Minh) để sinh viên ngồi cuối lớp quét được từ xa. | Thân thiện với bối cảnh phòng học lớn và thiết bị máy chiếu. |
| **5** | **Wizard 3 bước cho Form Google Sheet** | Form 1 trang dài vs Wizard 3 bước (File $\rightarrow$ Tab $\rightarrow$ Kết quả) | **Wizard 3 bước:** Chia nhỏ thao tác kiểm tra quyền truy cập Viewer và chọn tab môn học `12_PRM393_SE1917`. | Giảm thiểu lỗi sai ID Sheet và nhầm lẫn tab lớp học. |
| **6** | **Trực quan hóa Sinh viên vắng nhiều (Cảnh báo cấm thi)** | Bảng điểm danh thuần vs Danh sách Top sinh viên vắng nhiều | **Mục Top vắng nhiều kèm % cảnh báo:** Nêu rõ Nguyễn Văn An (60% vắng - 3/5 tiết) với badge đỏ nổi bật. | Giúp giảng viên cảnh báo sinh viên trước khi vượt quá ngưỡng 20% cấm thi. |
| **7** | **Lịch tuần dạng Strip Bar có chấm trạng thái** | Lịch tháng đầy đủ vs Thanh ngang tuần 7 ngày | **Thanh ngang tuần (T2 đến CN):** Có chấm xanh báo hiệu ngày có ca dạy (T7 ngày 03), nút "Hôm nay" tiện dụng. | Tiết kiệm không gian màn hình di động, thao tác 1 chạm chuyển ngày. |
| **8** | **Màu sắc Campus Pine `#1E3A2F` & Mustard Gold `#D99B26`** | Màu mặc định cơ bản vs Bảng màu nhận diện học đường | **Tone màu Pine & Gold kết hợp nền ngà `#F0F4F2`:** Tạo cảm giác trang nhã, tập trung, dễ phân biệt nút chính và thông tin. | Nâng tầm thẩm mỹ giao diện vượt bậc so với các app thông thường. |
| **9** | **Realtime Attendance Feed với Avatar viết tắt** | Danh sách text thuần vs Danh sách item có Avatar 2 chữ cái + Giờ quét | **Avatar 2 chữ cái (NA, TB, LC) + Giờ quét:** Sinh viên quét xong tên nhảy lên đầu danh sách theo chu kỳ 5 giây. | Phản hồi tức thì cho sinh viên biết mình đã được ghi nhận. |
| **10** | **Form Xếp lịch tiết học có kiểm tra xung đột phòng** | Không kiểm tra vs Báo lỗi Conflict khi trùng phòng 101 | **Cơ chế phát hiện xung đột phòng/slot:** Cho phép giảng viên đổi phòng hoặc đổi slot ngay trên form. | Ngăn ngừa lỗi trùng lịch phòng học trong nhà trường. |

---

## 2. Accessibility & Responsive Checklist

| Tiêu chí Kiểm tra | Tiêu chuẩn Đặt ra | Kết quả Đạt được | Bằng chứng & Chi tiết thực hiện |
| :--- | :--- | :--- | :--- |
| **Độ tương phản chữ (Contrast Ratio)** | $\ge 4.5:1$ cho chữ thường; $\ge 3:1$ cho chữ lớn và controls | **PASSED** | Chữ chính `#1C2A24` trên nền trắng `#FFFFFF` đạt ratio **14.5:1**. Chữ trắng trên nền `#1E3A2F` đạt **11.2:1**. Vượt xa chuẩn WCAG 2.1 AA. |
| **Vùng chạm tối thiểu (Touch Target)** | Tối thiểu $48 \times 48\text{ dp}$ cho mọi nút bấm | **PASSED** | Nút "+ Tạo lớp học", "Xếp lịch", "Xuất sang Google Sheets" đều có chiều cao $\ge 48\text{ dp}$, nút QR có vùng chạm rộng $100\%$. |
| **Kích thước chữ nội dung** | Tối thiểu 14sp; Không truyền đạt thông tin chỉ bằng màu | **PASSED** | Font chữ nội dung nhỏ nhất là 14sp. Mọi trạng thái luôn đi kèm **Icon + Chữ + Màu** ("Có mặt", "Đi muộn", "Vắng", "Chưa mở"). |
| **Độ co giãn Responsive** | Kiểm tra trên màn hình 360dp và 412dp | **PASSED** | Thiết kế với Figma Auto Layout (`Fill Container`), các thẻ card và cột thống kê tự động căn chỉnh hoàn hảo trên cả 360dp và 412dp. Bằng chứng kiểm tra thực tế: Bản 360dp tại [`assets/stitch/scr02_home_dashboard.png`](../assets/stitch/scr02_home_dashboard.png) và Bản 412dp tại [`assets/stitch/scr02_home_dashboard_412dp.png`](../assets/stitch/scr02_home_dashboard_412dp.png). |
| **Hành vi trên màn hình rộng ($\ge 600\text{ dp}$)** | Được mô tả chi tiết trong file Handoff | **PASSED** | Giao diện trên Tablet/Web tự động giới hạn độ rộng nội dung 600dp ở giữa, thanh điều hướng chuyển sang Sidebar bên trái. |
