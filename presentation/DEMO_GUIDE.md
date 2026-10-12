# Live Demo Guide & Q&A Response Checklist - PRM323 Lab 2

> **Tài liệu hướng dẫn thao tác Demo trực tiếp (5 phút) và Bộ câu trả lời 7 câu hỏi vấn đáp với Giảng viên.**

---

## I. Kịch bản Demo Trực tiếp (7 Bước Chuẩn)

### Bước 1: Mở File Figma & Kiểm tra 6 Pages Đúng Thứ Tự
- **Thao tác:** Mở Figma qua [Figma Link](https://www.figma.com/make/C1mMATOxXbnsmcGP7qAedV/Link-buttons-to-functions?p=f&t=zSajK2uZEkxoxSgR-0&preview-route=%2F%23dashboard) trong trình duyệt private/incognito.
- **Thuyết minh:** *"Dạ thưa thầy/cô, file Figma của nhóm em gồm đúng 6 page theo thứ tự quy định:*
  1. `01 User Flow` (Sơ đồ luồng)
  2. `02 Wireframe` (Bố cục Low-fi)
  3. `03 Final UI` (8 màn hình hoàn chỉnh)
  4. `04 Design System` (Tokens)
  5. `05 Components` (Thư viện tái sử dụng)
  6. `06 Prototype` (Luồng tương tác trực tiếp)."*

### Bước 2: Chỉ ra 8 Màn hình Độc lập trên Page `03 Final UI`
- **Thao tác:** Zoom tổng quan Page `03 Final UI`.
- **Thuyết minh:** *"Nhóm em đã thiết kế 8 màn hình độc lập bao gồm:*
  - SCR-01: Google Sign-In
  - SCR-02: Home Dashboard
  - SCR-03: QR Camera Scanner
  - SCR-04: Attendance Success
  - SCR-05: Class Schedule
  - SCR-06: History & Statistics
  - SCR-07: Student Profile
  - SCR-08: Error & PIN Recovery Dialog Overlay."*

### Bước 3: Đổi sang Page `06 Prototype` & Chạy 3 User Flows
- **Thao tác:** Bấm nút **Play / Present** trên Figma.
- **Demo Flow 1 (Happy Path):** Click "Đăng nhập với Google" $\rightarrow$ Click FAB Quét QR $\rightarrow$ Quét thành công $\rightarrow$ Hiện màn hình Success $\rightarrow$ Click "Về Trang Chủ" (Cập nhật trạng thái "Đã có mặt").
- **Demo Flow 2 (Thống kê & Lịch sử):** Click tab "Thống kê" $\rightarrow$ Chọn môn PRM323 $\rightarrow$ Kiểm tra % chuyên cần và danh sách buổi học.
- **Demo Flow 3 (Phục hồi sự cố):** Tại màn hình Scanner, click giả lập QR hết hạn $\rightarrow$ Hiện Dialog Overlay SCR-08 $\rightarrow$ Nhập mã PIN 6 số dự phòng $\rightarrow$ Chuyển sang màn hình Success.

### Bước 4: Trình diễn Dialog Overlay & Chuyển cảnh Loading $\rightarrow$ Result
- **Thao tác:** Cho giảng viên xem hiệu ứng Dialog Overlay hiển thị làm mờ nền phía sau, và vòng xoay Loading chuyển sang dấu tích xanh Success.

### Bước 5: Kiểm tra Reusable Components & Tokens (Page `04` & `05`)
- **Thao tác:** Mở Page `05 Components`, click chọn Nút bấm hoặc Card môn học để cho thấy các Variants (Default, Focused, Error, Loading) được dựng bằng Auto Layout. Mở panel Variables/Styles để chứng minh không gán cứng màu/kích thước.

### Bước 6: Minh chứng Nhật ký AI (AI Log & Stitch Output)
- **Thao tác:** Mở file [`ai/ai-design-log.md`](file:///d:/Semester8_FALL26/PRM393/prm323-lab2/ai/ai-design-log.md) trên GitHub hoặc Slide 06.
- **Thuyết minh:** *"Nhóm em đã sử dụng Google Stitch (Project #4183462632766005206) để tạo UI ban đầu, sau đó dùng VisionCode AI Studio để phản biện 5 lỗi UX và thực hiện 3 vòng lặp tinh chỉnh."*

### Bước 7: Mở GitHub Repo & Kiểm tra Flutter Handoff
- **Thao tác:** Mở file [`handoff/flutter-handoff.md`](file:///d:/Semester8_FALL26/PRM393/prm323-lab2/handoff/flutter-handoff.md).
- **Thuyết minh:** *"File handoff đã quy định đủ 6 mục cho 8 màn hình và 2 bảng ánh xạ Token $\rightarrow$ Flutter Code và Component $\rightarrow$ Widget."*

---

## II. Bộ Câu Hỏi & Câu Trả Lời Mẫu với Giảng Viên (7 Câu Hỏi Vấn Đáp)

### Câu 1: Persona có nhu cầu gì khiến nhóm chọn cấu trúc điều hướng này?
> **Trả lời mẫu:**  
> *"Dạ thưa thầy/cô, Persona Nguyễn Văn An là sinh viên thường xuyên di chuyển giữa các phòng học và phải điểm danh cực nhanh ngay khi bước vào lớp. Do đó, nhóm em chọn cấu trúc Bottom Navigation Bar kết hợp với Nút Quét QR nổi (FAB) kích thước lớn $56\times 56\text{ dp}$ ở chính giữa. Cấu trúc này giúp An có thể mở ứng dụng và chạm điểm danh ngay bằng 1 tay trong thời gian dưới 10 giây mà không cần đi qua nhiều cấp menu phức tạp."*

---

### Câu 2: Flow nào dễ thất bại nhất? Khi xảy ra lỗi người dùng có thể phục hồi ra sao?
> **Trả lời mẫu:**  
> *"Dạ, flow dễ thất bại nhất là Flow điểm danh bằng mã QR do máy chiếu phòng học có thể bị mờ, QR hết hạn quá nhanh (dưới 15s) hoặc máy bị mất mạng/sai GPS. Để xử lý, nhóm em thiết kế Flow 3 với cơ chế phục hồi không có ngõ cụt (No Dead End): Khi quét QR lỗi, một Dialog Overlay (SCR-08) sẽ hiện ra giải thích rõ nguyên nhân bằng tiếng Việt và cung cấp Form nhập mã PIN 6 số dự phòng do giảng viên đọc trực tiếp. Nhờ đó sinh viên vẫn hoàn thành điểm danh thành công."*

---

### Câu 3: Một đề xuất AI nào đã bị nhóm từ chối hoặc chỉnh sửa? Vì sao?
> **Trả lời mẫu:**  
> *"Dạ, ở Vòng lặp 2, AI đề xuất khi mã QR hết hạn thì chuyển sang một màn hình lỗi riêng biệt (Full-screen Error Page). Nhóm em đã **TỪ CHỐI / CHỈNH SỬA** đề xuất này vì việc mở màn hình riêng sẽ làm mất hoàn toàn ngữ cảnh camera quét của sinh viên. Nhóm em đã thay bằng Dialog Overlay Modal giữ nguyên 50% độ mờ camera phía sau, vừa giúp sinh viên giữ ngữ cảnh vừa có thể nhấn 'Quét lại' ngay lập tức."*

---

### Câu 4: Ba vòng lặp chỉnh sửa đã giải quyết ba vấn đề UX khác nhau như thế nào?
> **Trả lời mẫu:**  
> *"Dạ thưa thầy/cô, 3 vòng lặp giải quyết 3 vấn đề UX hoàn toàn khác nhau:*
> 1. **Vòng 1 (Visual & Efficiency):** Tăng kích thước nút Quét QR từ $32\text{dp}$ góc trên thành FAB $56\text{dp}$ chính giữa để thao tác 1 tay đạt tiêu chuẩn Touch Target $\ge 48\text{dp}$.
> 2. **Vòng 2 (Error Recovery & Freedom):** Loại bỏ ngõ cụt khi QR hết hạn bằng Form nhập mã PIN 6 số dự phòng trên Dialog Overlay.
> 3. **Vòng 3 (Accessibility & Feedback):** Bổ sung nút Đèn pin Flashlight cho phòng học tối + hiệu ứng Rung (Haptic Feedback) và thanh Progress Bar trực quan hóa tỷ lệ vắng mặt."*

---

### Câu 5: Nếu đổi primary color hoặc spacing token, các màn hình nào tự cập nhật?
> **Trả lời mẫu:**  
> *"Dạ, tất cả **cả 8 màn hình** và toàn bộ các components trong file Figma sẽ tự động cập nhật ngay lập tức. Lý do là vì nhóm em đã định nghĩa màu FPT Orange `#FF6B00` thành Figma Variable `color/primary` và khoảng cách thành Variable `spacing/md` (16dp). Các nút bấm, header và card đều liên kết trực tiếp với Variable này chứ không dùng giá trị gán cứng (hard-coded values)."*

---

### Câu 6: Làm thế nào chứng minh màn hình rộng 412 dp không vỡ layout?
> **Trả lời mẫu:**  
> *"Dạ, toàn bộ khung màn hình và component trong Figma đều được thiết kế bằng tính năng **Auto Layout** với thiết lập Constraint `Fill Container` theo chiều ngang và `Fixed/Hug` theo chiều dọc. Khi em thay đổi kích thước Frame từ 360dp lên 412dp, các Card môn học, Form nhập liệu và Nút bấm tự động co giãn theo chiều rộng màn hình mà không bị vỡ bố cục hay tràn viền."*

---

### Câu 7: Một lập trình viên Flutter chưa biết dự án sẽ dựa vào đâu để hiện thực màn hình và states?
> **Trả lời mẫu:**  
> *"Dạ, lập trình viên Flutter chỉ cần dựa vào file [`handoff/flutter-handoff.md`](file:///d:/Semester8_FALL26/PRM393/prm323-lab2/handoff/flutter-handoff.md) trong repository. File này cung cấp:*
> 1. **Bảng ánh xạ Tokens $\rightarrow$ Code Flutter:** Quy định chính xác mã màu nào thuộc `ColorScheme.primary`, font chữ nào thuộc `TextTheme.titleLarge`.
> 2. **Bảng ánh xạ Component $\rightarrow$ Widget:** Chỉ rõ Button nào dùng `FilledButton`, Form PIN dùng `PinCodeTextField`, Dialog dùng `AlertDialog`.
> 3. **Đặc tả 6 mục cho từng màn hình:** Mô tả cấu trúc Layout từ trên xuống dưới (`Scaffold` $\rightarrow$ `AppBar` $\rightarrow$ `Column`), danh sách component, trạng thái (Default, Loading, Empty, Error), quy tắc tương tác và ràng buộc UI."*
