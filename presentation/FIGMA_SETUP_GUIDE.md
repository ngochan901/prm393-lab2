# Hướng dẫn thiết lập Figma chuẩn 10 Màn hình - FPT Attendance System

> **Áp dụng cho:** [PRM393 Lab 2 – FPT Attendance – MSSV](https://www.figma.com/design/WSs5fDFhGkez9FHZ00unad/PRM323-Lab-2-%25E2%2580%2593-FPT-Attendance-%25E2%2580%2593-MSSV?node-id=5-2&p=f&t=64UpgIKBLIRKm5Gh-0)  
> **Kích thước chuẩn Frame Android:** $360 \times 800 \text{ dp}$

---

## 1. Cấu trúc 6 Pages chuẩn trong Figma:
1. `01 User Flow` (Sơ đồ luồng 3 flows liên kết các màn hình)
2. `02 Wireframe` (Bố cục Low-fi khung xám)
3. `03 Final UI` (10 màn hình hoàn chỉnh từ SCR-01 đến SCR-10)
4. `04 Design System` (Variables Tokens)
5. `05 Components` (Thư viện tái sử dụng với Auto Layout & Variants)
6. `06 Prototype` (Luồng bấm tương tác có điểm xuất phát rõ ràng)

---

## 2. Tokens (Variables) cần định nghĩa tại Page `04`:
- **Color Variables:**
  - `color/primary-dark`: `#1E3A2F` (Campus Pine)
  - `color/accent-gold`: `#D99B26` (Mustard Gold)
  - `color/google-blue`: `#3B82F6` (Google Sign-In)
  - `color/background`: `#F0F4F2` (Màu nền Campus)
  - `color/surface`: `#FFFFFF`
  - `color/status-green`: Background `#D1F2E2`, Text `#0E7A4A`
  - `color/status-amber`: Background `#FFF3D6`, Text `#B27B00`
  - `color/status-red`: Background `#FDE8E8`, Text `#D32F2F`

---

## 3. Danh sách 10 Màn hình hoàn chỉnh tại Page `03 Final UI`:
- `SCR-01 Google Sign-In`: Đăng nhập bằng Google SSO
- `SCR-02 Home Dashboard`: Tổng quan giảng dạy & Tiết học hôm nay
- `SCR-03 Chi tiết tiết học`: Thông tin phòng 101, Slot 1 & Nút Mở điểm danh
- `SCR-04 Live QR Điểm danh`: Mã QR động đếm ngược 45s, 4 thẻ sĩ số 28/35, Danh sách realtime
- `SCR-05 Báo cáo điểm danh`: Tổng kết ca học & Nút Xuất sang Google Sheets
- `SCR-06 Lớp học của tôi`: Danh sách lớp PRM393, PRN232, SWP391
- `SCR-07 Thống kê tích lũy lớp`: Tỷ lệ vắng 4.0% & Top sinh viên vắng nhiều (Nguyễn Văn An 60%)
- `SCR-08 Kết nối Google Sheet`: Wizard 3 bước nhập link Sheet nạp sinh viên
- `SCR-09 Lịch dạy theo tuần`: Lịch dạy dạng tuần Strip bar, T7 ngày 03
- `SCR-10 Xếp lịch tiết học mới`: Form tạo lịch và kiểm tra xung đột phòng
