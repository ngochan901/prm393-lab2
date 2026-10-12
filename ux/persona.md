# UX Analysis: Persona & Problem Statement

## 1. Primary Persona (Giảng viên / Người quản lý lớp)

- **Name:** Thầy Nguyễn Văn Nam (Email: `namnv@fpt.edu.vn`)
- **Age Range:** 32 - 38 tuổi
- **Role:** Giảng viên bộ môn Lập trình di động (PRM393 - Lớp SE1917, PRN232 - Lớp SE1918) tại FPT University TP. Hồ Chí Minh
- **Daily Context:** Giảng dạy nhiều ca/slot trong ngày tại các phòng học 101, 203 cơ sở TP. Hồ Chí Minh. Cần bắt đầu buổi học đúng giờ, mở điểm danh nhanh trong 5-10 phút đầu ca, theo dõi sĩ số thực tế (35 sinh viên) và xuất kết quả sang Google Sheets của bộ môn.
- **Goals:**
  - Mở phiên điểm danh QR trực tiếp trên màn hình/máy chiếu chỉ với 1-click.
  - Mã QR tự động làm mới mỗi 45 giây để chống sinh viên chụp ảnh gửi cho bạn điểm danh hộ.
  - Đồng bộ danh sách sinh viên tự động 2 chiều với Google Sheets.
  - Xem thống kê chuyên cần tích lũy, phát hiện sinh viên vắng nhiều (như sinh viên Nguyễn Văn An vắng 3/5 tiết - 60%) để kịp thời nhắc nhở trước khi bị cấm thi.
- **Pain Points:**
  - Điểm danh giấy hoặc gọi tên tốn 15-20 phút của ca học 135 phút.
  - Sinh viên gian lận điểm danh hộ nếu mã QR là mã tĩnh không đổi.
  - Nhập liệu kết quả điểm danh vào bảng tính Google Sheets thủ công sau giờ dạy tốn nhiều thời gian và dễ nhầm lẫn.
- **Device Habits:** Sử dụng smartphone Android / Tablet và Laptop giảng đường, thao tác nhanh, cần giao diện trực quan và phản hồi tức thì.
- **Accessibility Needs:** Màu sắc độ tương phản cao, thẻ thông tin rõ ràng, số liệu sĩ số lớn (35 sĩ số, 28 có mặt, 7 vắng) dễ quan sát từ khoảng cách bàn giảng viên.

---

## 2. Secondary Persona (Sinh viên tham gia điểm danh)

- **Name:** Nguyễn Văn An (Mã sinh viên: SE190001)
- **Role:** Sinh viên năm 3 lớp SE1917 môn PRM393
- **Goals:** Đăng nhập 1-Touch bằng tài khoản Google trường (`@fpt.edu.vn`), quét QR điểm danh nhanh trong 10 giây đầu buổi học, kiểm tra số buổi vắng tích lũy để không vượt quá 20%.

---

## 3. Problem Statement

> "Giảng viên và sinh viên FPT cần một ứng dụng quản lý giảng dạy và điểm danh bằng mã QR động tích hợp Google Authentication và Google Sheets để tự động hóa quy trình điểm danh trong 10 giây, chống gian lận điểm danh hộ và đồng bộ dữ liệu chuyên cần tức thì mà không cần thao tác thủ công."

---

## 4. Measurable Success Criterion

- **Chỉ số đo lường (Metric):** Giảng viên có thể mở phiên điểm danh QR động và tiếp nhận điểm danh của 35 sinh viên, đồng thời xuất kết quả sang Google Sheets trong thời gian **dưới 30 giây**.
