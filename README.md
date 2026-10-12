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
| **Figma Setup Step-by-Step Guide** | [`presentation/FIGMA_SETUP_GUIDE.md`](presentation/FIGMA_SETUP_GUIDE.md) |
| **Slide Presentation Content (12 Slides)** | [`presentation/SLIDES.md`](presentation/SLIDES.md) |
| **Live Demo Script & Q&A Checklist** | [`presentation/DEMO_GUIDE.md`](presentation/DEMO_GUIDE.md) |

---

## Final Submission Checklist (8/8 Hoàn Thành)

- [x] **1. README:** Đầy đủ chủ đề, persona một dòng, link Figma Design & Prototype, link Google Stitch, công cụ AI và bản đồ tài liệu chi tiết.
- [x] **2. UX Analysis:** Persona Thầy Nguyễn Văn Nam có pain points & tiêu chí đo được (<30s); 3 User Flows có happy path, alternative path, error & recovery path cùng bảng ánh xạ màn hình S01–S10.
- [x] **3. Final Screens:** Đầy đủ 10 màn hình UI cuối cùng khác nhau (vượt chuẩn tối thiểu 8 màn hình) được xuất tại `assets/figma/` và đối ứng `assets/stitch/`.
- [x] **4. AI Design Log:** Lưu nguyên văn 10 prompt Stitch, 5 phát hiện phản biện UX của VisionCode AI Studio gắn với từng màn hình, 3 vòng lặp có ảnh Trước/Sau (`iter01` $\rightarrow$ `iter03`) và quyết định Accept/Modify.
- [x] **5. Figma Architecture:** Cấu trúc đúng 6 trang theo thứ tự (`01 User Flow`, `02 Wireframe`, `03 Final UI`, `04 Design System`, `05 Components`, `06 Prototype`), chuẩn hóa design tokens và 9 nhóm component bắt buộc.
- [x] **6. Interactive Prototype:** Đủ 3 flows hoàn chỉnh có thể bấm từ đầu đến cuối, dialog overlay (Overlay phóng to QR `S09-QR-OVERLAY`, Dialog xác nhận xuất Sheet `S10-CONFIRM-EXPORT`) và chuyển cảnh loading $\rightarrow$ kết quả.
- [x] **7. Flutter Handoff:** Đầy đủ 6 mục chi tiết cho từng màn hình S01–S10 và 2 bảng mapping toàn cục (Tokens $\to$ ColorScheme/TextTheme, Components $\to$ Flutter Widgets).
- [x] **8. Verification & Links:** Tất cả liên kết tài liệu Markdown, ảnh minh chứng trong `assets/figma/` và `assets/stitch/`, và link Figma/Stitch đều hoạt động chính xác.


