# PRM393 - Lab 2: AI-Assisted UI/UX Design

## Project Overview
- **Topic:** FPT Attendance System (CAMPUS / STUDIO) — Hệ thống Quản lý Giảng dạy & Điểm danh Sinh viên bằng mã QR động tích hợp Google Authentication & Google Sheets.
- **One-line Persona:** Giảng viên & Cán bộ bộ môn (quản lý lịch dạy, mở phiên QR điểm danh động 45s, đồng bộ Google Sheets) cùng Sinh viên Nguyễn Văn An (điểm danh nhanh qua Google SSO và theo dõi tỷ lệ chuyên cần tránh cấm thi).

## AI Tools & Links Used
- **GitHub Repository:** [https://github.com/ngochan901/prm393-lab2](https://github.com/ngochan901/prm393-lab2)
- **Figma Design File:** [PRM393 Lab 2 – FPT Attendance – MSSV](https://www.figma.com/design/WSs5fDFhGkez9FHZ00unad/PRM323-Lab-2-%25E2%2580%2593-FPT-Attendance-%25E2%2580%2593-MSSV?node-id=5-2&p=f&t=64UpgIKBLIRKm5Gh-0)
- **Figma Prototype Link:** [Figma Interactive Prototype](https://www.figma.com/make/C1mMATOxXbnsmcGP7qAedV/Link-buttons-to-functions?p=f&t=ZtMtdaCP6rMN5hoh-0&preview-route=%2F%23dashboard)
- **Google Stitch Project:** [Stitch Project #4183462632766005206](https://stitch.withgoogle.com/projects/4183462632766005206)
- **AI Assistant for Critique & Generation:** [VisionCode AI Studio](https://visioncode-1.ai.studio/) (Phản biện UX theo 10 Usability Heuristics của Nielsen và tiêu chuẩn WCAG 2.1)

## Deliverables Map
| Deliverable | File Path / Location |
| :--- | :--- |
| **Persona & Problem Statement** | [`ux/persona.md`](ux/persona.md) |
| **Information Architecture & User Flows** | [`ux/user-flow.md`](ux/user-flow.md) |
| **Design Brief (Stitch Prompt Baseline)** | [`design/DESIGN.md`](design/DESIGN.md) |
| **Screen Specifications** | [`design/screen-spec.md`](design/screen-spec.md) |
| **Design Decisions & Accessibility Checklist** | [`design/design-decisions.md`](design/design-decisions.md) |
| **AI Design Log & Iteration History** | [`ai/ai-design-log.md`](ai/ai-design-log.md) |
| **Stitch Screenshots** | [`assets/stitch/`](assets/stitch/) |
| **Figma Final Screen Exports** | [`assets/figma/`](assets/figma/) |
| **Flutter Handoff Specification** | [`handoff/flutter-handoff.md`](handoff/flutter-handoff.md) |

---

## Chi Tiết Triển Khai & Báo Cáo Sản Phẩm

1. **Thông Tin & Điều Hướng (README)**
   - Xác định rõ chủ đề ứng dụng FPT Attendance System (CAMPUS / STUDIO).
   - Persona trọng tâm: Giảng viên Thầy Nguyễn Văn Nam (`namnv@fpt.edu.vn`) & Sinh viên Nguyễn Văn An (`SE190001`).
   - Cung cấp đầy đủ đường dẫn truy cập Figma Design, Figma Prototype, Google Stitch và công cụ AI phản biện.

2. **Tài Liệu Phân Tích UX (`ux/`)**
   - [`ux/persona.md`](ux/persona.md): Chi tiết bối cảnh, mục tiêu, pain points và tiêu chí đo lường định lượng (<30s).
   - [`ux/user-flow.md`](ux/user-flow.md): Sơ đồ cây Information Architecture, 3 sơ đồ User Flow chuẩn Mermaid (Happy Path, Alternative Path, Error & Recovery) và bảng ánh xạ toàn bộ màn hình S01–S10.

3. **Giao Diện Hoàn Chỉnh (`assets/figma/` & `assets/stitch/`)**
   - Đầy đủ 10 màn hình Final UI xuất từ Figma Page 03 tại [`assets/figma/`](assets/figma/).
   - Đầy đủ 11 ảnh Stitch gốc tại [`assets/stitch/`](assets/stitch/) bao gồm ảnh kiểm thử độ co giãn responsive 412dp và 3 cặp ảnh vòng lặp Trước/Sau.

4. **Nhật Ký Thiết Kế AI (`ai/`)**
   - [`ai/ai-design-log.md`](ai/ai-design-log.md): Lưu trữ nguyên văn 10 prompt nhập vào Google Stitch.
   - 5 phát hiện phản biện UX chuyên sâu từ VisionCode AI Studio dựa trên 10 Nielsen Heuristics và WCAG 2.1 AA.
   - 3 vòng lặp có ý nghĩa (S02 - Điều hướng, S09 - Dynamic QR, S07 - Xung đột lịch) kèm quyết định Accept/Modify của sinh viên.

5. **Cấu Trúc Figma 6 Trang Chuẩn Hóa**
   - Xây dựng đúng thứ tự 6 trang: `01 User Flow`, `02 Wireframe`, `03 Final UI`, `04 Design System`, `05 Components`, `06 Prototype`.
   - Hệ thống Design Tokens (Figma Variables) và 9 nhóm component có đầy đủ variants trạng thái.

6. **Interactive Prototype**
   - 3 user flows có thể tương tác xuyên suốt từ điểm bắt đầu đến điểm kết thúc.
   - Tích hợp Modal / Dialog overlay (Overlay phóng to QR S09, Dialog xác nhận xuất Sheet S10) và hiệu ứng chuyển cảnh loading sang kết quả.

7. **Bàn Giao Kỹ Thuật Flutter (`handoff/`)**
   - [`handoff/flutter-handoff.md`](handoff/flutter-handoff.md): Bảng quy đổi Design Token sang Flutter (`ColorScheme`/`TextTheme`), Bảng Component sang Flutter Widgets.
   - Đặc tả chi tiết 6 mục chuẩn hóa (Layout, Components, States, Interactions, Navigation, Constraints) cho từng màn hình S01–S10.
