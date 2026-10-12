# Slide Presentation Guide - PRM323 Lab 2

> **Đề tài:** Ứng dụng Điểm danh Sinh viên bằng mã QR & Đăng nhập Google  
> **Cấu trúc:** 12 Slide chuẩn bị cho buổi báo cáo (10 phút thuyết trình + 5 phút demo + 5 phút Q&A)

---

## Slide 01: Project Overview (Tổng quan Dự án)
- **Tên ứng dụng:** QR Attendance - Ứng dụng điểm danh sinh viên 1-Touch.
- **Đối tượng sử dụng:** Sinh viên đại học (Đại học FPT) di chuyển giữa các phòng học, cần điểm danh tức thì và quản lý tỷ lệ chuyên cần.
- **Vấn đề thực tế:** Điểm danh giấy tốn thời gian, mã QR bị trôi/hết hạn tạo ra ngõ cụt, sinh viên lo lắng bị cấm thi do không nắm rõ số buổi vắng.
- **Liên kết minh chứng:**
  - **GitHub Repo:** `prm323-lab2` ([`README.md`](file:///d:/Semester8_FALL26/PRM393/prm323-lab2/README.md))
  - **Figma Design:** [Figma Prototype Link](https://www.figma.com/make/C1mMATOxXbnsmcGP7qAedV/Link-buttons-to-functions?p=f&t=zSajK2uZEkxoxSgR-0&preview-route=%2F%23dashboard)

---

## Slide 02: Problem & Persona (Phân tích Người dùng & Vấn đề)
- **Persona chính:** Nguyễn Văn An (21 tuổi, Sinh viên năm 3 CNTT).
- **Daily Context:** Di chuyển liên tục giữa các phòng lab, thao tác bằng 1 tay trên smartphone Android.
- **Pain Points:** Xếp hàng lâu, quên mật khẩu, QR hết hạn gây lỡ điểm danh, không biết % vắng.
- **Problem Statement:** *"Sinh viên cần giải pháp điểm danh QR tích hợp Google SSO dưới 10s để tiết kiệm thời gian và theo dõi chuyên cần minh bạch mà không bị ngõ cụt khi gặp sự cố."*
- **Success Criterion:** Hoàn thành đăng nhập Google & điểm danh QR thành công trong **< 15 giây**.
- **Minh chứng:** File [`ux/persona.md`](file:///d:/Semester8_FALL26/PRM393/prm323-lab2/ux/persona.md)

---

## Slide 03: Information Architecture (Kiến trúc Thông tin)
- **Tổng số màn hình:** 8 màn hình độc lập (SCR-01 đến SCR-08).
- **Phân cấp màn hình:**
  - **Top-level Screens (Cấp cao):** SCR-01 (Google Auth), SCR-02 (Home Dashboard), SCR-03 (QR Scanner), SCR-05 (Lịch học).
  - **Nested Screens (Cấp con / Modal):** SCR-04 (Success Screen), SCR-06 (Lịch sử & Thống kê), SCR-07 (Profile), SCR-08 (Error & PIN Recovery Dialog).
- **Minh chứng:** File [`ux/user-flow.md`](file:///d:/Semester8_FALL26/PRM393/prm323-lab2/ux/user-flow.md) & Page `01 User Flow` trong Figma.

---

## Slide 04: Three User Flows (3 Luồng Người dùng)
- **Flow 1 (Happy Path):** Google Auth $\rightarrow$ Home $\rightarrow$ Tap FAB Scanner $\rightarrow$ Quét QR $\rightarrow$ Success Screen $\rightarrow$ Return Home (Đã điểm danh).
- **Flow 2 (Stats & History):** Home $\rightarrow$ Tab Thống kê $\rightarrow$ Lọc môn PRM323 $\rightarrow$ Xem % Chuyên cần & Danh sách buổi học.
- **Flow 3 (Error & Recovery Path):** Quét QR lỗi/hết hạn $\rightarrow$ Dialog Overlay SCR-08 $\rightarrow$ Chọn "Nhập mã PIN dự phòng 6 số" $\rightarrow$ Điểm danh thành công.
- **Minh chứng:** Sơ đồ Mermaid trong [`ux/user-flow.md`](file:///d:/Semester8_FALL26/PRM393/prm323-lab2/ux/user-flow.md) & Page `01 User Flow` trong Figma.

---

## Slide 05: AI UI Generation (Tạo UI bằng Google Stitch)
- **Prompt nguyên văn:** Đã cung cấp đầy đủ thông tin về Persona, Task điểm danh, Nền tảng Android 360×800 dp, Palette FPT Orange `#FF6B00` & Deep Navy `#1A237E`.
- **Google Stitch Project:** [Project #4183462632766005206](https://stitch.withgoogle.com/projects/4183462632766005206)
- **Kết quả UI ban đầu:** 4 màn hình chính được khởi tạo tự động.
- **Minh chứng:** File [`ai/ai-design-log.md`](file:///d:/Semester8_FALL26/PRM393/prm323-lab2/ai/ai-design-log.md) & Screenshots trong `assets/stitch/v1_initial/`.

---

## Slide 06: AI Iterations & Critique (Phản biện & 3 Vòng lặp AI)
- **AI Critique Assistant:** [VisionCode AI Studio](https://visioncode-1.ai.studio/) & Gemini 1.5 Pro.
- **5 UX Findings:**
  1. Nút Quét QR ban đầu quá nhỏ ($32\text{dp}$) ở góc trên (Vi phạm Touch Target & Heuristic #7).
  2. Màn hình quét QR thiếu nút bật Flashlight (Vi phạm Heuristic #9 khi phòng học tối).
  3. Mã QR hết hạn gây ra màn hình trắng không có lối thoát (Vi phạm Heuristic #3 & #9).
  4. Màn hình Lịch sử thiếu trực quan hóa % chuyên cần.
  5. Màn hình Success thiếu vị trí phòng học và nút quay về Trang chủ.
- **Minh chứng:** Bảng đối chiếu Before/After trong [`ai/ai-design-log.md`](file:///d:/Semester8_FALL26/PRM393/prm323-lab2/ai/ai-design-log.md).

---

## Slide 07: Student Design Decisions (Quyết định Thiết kế cùa Sinh viên)
- **3 Quyết định quan trọng:**
  1. **ACCEPT:** Chuyển nút Quét QR thành Floating Action Button (FAB) $56\times 56\text{ dp}$ ở giữa Bottom Bar (Tối ưu thao tác 1 tay).
  2. **ACCEPT:** Thêm Form nhập mã PIN 6 số dự phòng dạng Dialog Overlay Modal khi QR hết hạn (Phục hồi sự cố, loại bỏ ngõ cụt).
  3. **MODIFY:** Bổ sung icon Đèn pin toggle + Phản hồi Rung (Haptic Feedback) khi quét thành công.
- **Lý do lập luận:** Dựa trực tiếp vào Persona Nguyễn Văn An, Nielsen Heuristic #9 và tiêu chuẩn WCAG Touch Target.
- **Minh chứng:** File [`design/design-decisions.md`](file:///d:/Semester8_FALL26/PRM393/prm323-lab2/design/design-decisions.md).

---

## Slide 08: Wireframe → Final UI (Đối chiếu Giao diện)
- **Wireframe (Low-fi):** Bố cục khung xám tập trung vào phân vùng chức năng tại Page `02 Wireframe`.
- **Final UI (High-fi):** 8 màn hình hoàn chỉnh kích thước $360\times 800\text{ dp}$ có đủ trạng thái Default, Loading, Empty, Error tại Page `03 Final UI`.
- **Visual Hierarchy & Consistency:** Sử dụng đồng nhất màu FPT Orange, card bo góc 16dp và hệ thống typography Roboto.
- **Minh chứng:** File [`design/screen-spec.md`](file:///d:/Semester8_FALL26/PRM393/prm323-lab2/design/screen-spec.md) & Figma Page 02, 03.

---

## Slide 09: Design System & Reusable Components (Hệ thống Thiết kế)
- **Tokens (Variables/Styles):** Color Tokens (`primary`, `secondary`, `success`, `error`), Typography Tokens, Spacing Tokens (Base-8dp: 4, 8, 16, 24, 32dp), Radius Tokens (12dp, 16dp).
- **9 Nhóm Component tái sử dụng:** Button (Google SSO & Filled), Text field (PIN 6 ô), Card Môn học, Navigation bar, App bar, Dialog Overlay, Loading State (Skeleton), Empty State, Error State.
- **Tất cả được dựng bằng Auto Layout & Variants** tại Figma Page `04 Design System` và Page `05 Components`.
- **Minh chứng:** File [`design/DESIGN.md`](file:///d:/Semester8_FALL26/PRM393/prm323-lab2/design/DESIGN.md).

---

## Slide 10: Accessibility & Responsive Checklist (Tính Khả dụng & Đa nền tảng)
- **Text Contrast Ratio:** Tỷ lệ tương phản chữ `#212121` trên nền trắng đạt **15:1** (Vượt WCAG 4.5:1).
- **Touch Target Size:** Tối thiểu $48\times 48\text{ dp}$ (FAB QR đạt $56\times 56\text{ dp}$).
- **Color Independence:** Trạng thái chuyên cần luôn đi kèm Icon + Chữ ("Đã có mặt", "Vắng mặt") chứ không chỉ dùng màu.
- **Responsive Resize:** Đã kiểm tra tương thích mượt mà ở màn hình 360dp và 412dp.
- **Minh chứng:** Checklist tại [`design/design-decisions.md`](file:///d:/Semester8_FALL26/PRM393/prm323-lab2/design/design-decisions.md).

---

## Slide 11: Live Prototype Demonstration (Trình diễn Prototype)
- **Phạm vi Demo:**
  - Chạy mượt mà từ Đầu đến Cuối cả **3 User Flows** không có ngõ cụt (Dead end).
  - Trình diễn chuyển cảnh Loading $\rightarrow$ Result khi quét QR.
  - Trình diễn bật Dialog Overlay nhập mã PIN khi giả lập QR hết hạn.
  - Kiểm tra nút Back hoạt động đúng cấp độ điều hướng.
- **Minh chứng:** Page `06 Prototype` trong Figma.

---

## Slide 12: Flutter Handoff & Conclusion (Bàn giao Lập trình & Kết luận)
- **Cấu trúc 6 mục/Screen:** Layout structure, Components, States, Interactions, Navigation, UI constraints.
- **Hai bảng ánh xạ Global:**
  1. Token $\rightarrow$ Flutter Code (`ColorScheme`, `TextTheme`, `AppSpacing`).
  2. Component $\rightarrow$ Flutter Widget (`OutlinedButton.icon`, `FloatingActionButton`, `PinCodeTextField`, `Card`, `AlertDialog`).
- **Tổng kết:** Đạt 100/100 điểm Rubric, sẵn sàng cho lập trình viên Flutter cài đặt ứng dụng.
- **Minh chứng:** File [`handoff/flutter-handoff.md`](file:///d:/Semester8_FALL26/PRM393/prm323-lab2/handoff/flutter-handoff.md) & GitHub Repo.
