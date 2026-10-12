# Design Brief (Stitch Prompt Foundation)

## 1. Visual & Brand Identity (CAMPUS / STUDIO Style)

Ứng dụng sử dụng phong cách thiết kế **Modern Academic / Campus Dashboard** chuyên nghiệp, màu sắc lấy cảm hứng từ nhận diện giáo dục đại học FPT:

### Color Palette (Bảng màu hệ thống)
- **Primary Brand Dark (Forest Pine):** `#1E3A2F` (Thanh tiêu đề, Card tổng quan dark, Nút hành động chính "Xem điểm danh", "Phóng to QR")
- **Primary Accent Gold (Mustard Yellow):** `#D99B26` (Nút hành động nổi bật: "+ Tạo lớp học", "Xếp lịch tiết học", "Lấy danh sách tab", "Xuất sang Google Sheets")
- **Google Blue:** `#3B82F6` (Nút Đăng nhập bằng Google SSO trên SCR-01)
- **Background Color:** `#F0F4F2` (Màu nền ngà nhạt Campus, tạo cảm giác dịu mắt khi theo dõi màn hình lâu)
- **Surface / Card Color:** `#FFFFFF` (Nền thẻ trắng, bo góc 16dp, viền mảnh hoặc đổ bóng nhẹ)
- **Text On Surface:** `#1C2A24` (Màu chữ đen xám độ tương phản cao, contrast ratio 14.5:1)
- **Text Secondary / Muted:** `#62756E` (Ghi chú slot học, phòng học, email)

### Status Semantic Colors (Màu trạng thái chuyên dụng)
- **Status Green (Có mặt / Đang điểm danh):** Background `#D1F2E2`, Text `#0E7A4A`
- **Status Amber (Đi học muộn):** Background `#FFF3D6`, Text `#B27B00`
- **Status Red (Vắng mặt / Kết thúc điểm danh):** Background `#FDE8E8`, Text `#D32F2F`
- **Status Neutral (Chưa mở / Chưa đến giờ):** Background `#E8ECF0`, Text `#5A6B7C`

### Typography Scale (Font: Plus Jakarta Sans / Roboto)
- **Display Large / Dashboard Header:** Bold 22sp - 24sp (Ví dụ: "Tổng quan giảng dạy", "Đăng nhập")
- **Section Title / Class Name:** Bold 18sp - 20sp (Ví dụ: "PRM393", "Lịch dạy", "Báo cáo điểm danh")
- **Stat Numbers:** Bold 26sp - 32sp (Các chỉ số lớn: 35, 28, 7, 80%, 4.0%)
- **Body Large / Button Text:** SemiBold 15sp - 16sp (Nút bấm, nhãn input)
- **Body Regular:** Regular 14sp (Chi tiết phòng học, thời gian slot)
- **Caption / Tag Text:** Medium 12sp - 13sp (Các nhãn FA2026, SE1917, Slot 1)

### Spacing & Grid System
- **Base Grid Unit:** 8dp (Tokens: 4dp, 8dp, 12dp, 16dp, 24dp, 32dp)
- **Screen Margin:** 16dp (Chuẩn màn hình di động 360×800 dp)
- **Card Padding:** 16dp - 20dp
- **Minimum Touch Target:** $48 \times 48\text{ dp}$ trên mọi nút bấm và icon tương tác.

### Elevation & Corner Radius
- **Corner Radius:** 16dp cho Card nội dung; 12dp cho Buttons; 24dp cho Modal Card; 999dp cho Tag Chips.
- **Elevation:** Soft Shadow `0px 4px 16px rgba(30, 58, 47, 0.06)` tạo cảm giác lớp nổi nhẹ nhàng.

---

## 2. Component Rules

- **Nút Hành Động Kép (Action Pair):** Nút chính dùng màu Gold `#D99B26` ("Tạo lớp học"), nút phụ dùng Outlined trắng viền xám ("Xếp lịch").
- **Card Tiết Học (Session Card):** Chia 3 phần: Tiêu đề môn + Slot/Phòng học + Nút hành động tương ứng trạng thái ("Xem điểm danh $\rightarrow$" hoặc "Xem chi tiết").
- **Mã QR Động Container:** Khung QR trung tâm kích thước lớn có đếm ngược thời gian (00:45) và 2 nút hỗ trợ: "Làm mới QR" và "Phóng to QR".
- **Realtime Attendance List Item:** Avatar viết tắt 2 chữ cái (NA, TB, LC) trong hình tròn màu nhạt, Tên sinh viên, MSSV, Giờ quét chính xác (07:06:14) và Chip trạng thái (Có mặt / Đi muộn).
- **Step Wizard (Form Google Sheet):** Tiến trình 3 bước (1. Chọn file $\rightarrow$ 2. Chọn tab $\rightarrow$ 3. Kết quả) với thanh nối rõ ràng.
