# Flutter Handoff Specification

> **Tiêu chuẩn kiểm thử Handoff:** *"Một lập trình viên Flutter cùng lớp có thể cài đặt hoàn chỉnh ứng dụng từ file handoff này chỉ bằng cách mở Figma xem giao diện, không cần phải hỏi lại bất kỳ chi tiết nào."*

---

## 1. Global Mapping Tables

### Table A: Design Tokens to Flutter Code

| Design Token Category | Figma Token Name | Value | Flutter Target (`ColorScheme` / `TextTheme` / Constant) | Implementation Note |
| :--- | :--- | :--- | :--- | :--- |
| **Color Primary Dark** | `color/primary-dark` | `#173D35` / `#1E3A2F` | `Theme.of(context).colorScheme.primary` | Header Dashboard, thẻ tổng quan, nút chính "Xem điểm danh" |
| **Color Primary Accent** | `color/accent-gold` | `#D69E2E` / `#D99B26` | `Theme.of(context).colorScheme.tertiary` | Nút hành động nổi bật: "+ Tạo lớp", "Xếp lịch", "Xuất Sheets" |
| **Color Google Blue** | `color/google-blue` | `#4285F4` / `#3B82F6` | `AppColors.googleBlue` (`Color(0xFF4285F4)`) | Nút "Đăng nhập bằng Google" (S01) |
| **Color Background** | `color/background` | `#E8F0ED` / `#F5F7F4` | `Theme.of(context).colorScheme.surfaceContainerLowest` | Nền toàn ứng dụng, dịu mắt học đường |
| **Color Surface** | `color/surface` | `#FFFFFF` | `Theme.of(context).colorScheme.surface` | Nền thẻ Card trắng, Container form, Dialog |
| **Color Text Primary** | `color/text-primary` | `#1C2A24` / `#243D36` | `Theme.of(context).colorScheme.onSurface` | Độ tương phản cao 14.5:1 với nền trắng |
| **Color Text Secondary** | `color/text-secondary`| `#52645E` / `#62756E` | `Theme.of(context).colorScheme.onSurfaceVariant`| Chữ phụ: Slot ca học, phòng học, mã sinh viên |
| **Color Accent Mint** | `color/accent-mint` | `#DCEAA5` | `AppColors.accentMint` (`Color(0xFFDCEAA5)`) | Điểm nhấn tab active, dải viền ca đang điểm danh |
| **Status Green (Present)**| `color/status-green` | Text `#0E7A4A`, Nền `#D1F2E2`| `AppColors.statusPresentText` / `AppColors.statusPresentBg` | Badge "Có mặt", "Đang điểm danh" |
| **Status Amber (Late)** | `color/status-amber` | Text `#B27B00`, Nền `#FFF3D6`| `AppColors.statusLateText` / `AppColors.statusLateBg` | Badge "Đi muộn" |
| **Status Red (Absent)** | `color/status-red` | Text `#D32F2F`, Nền `#FDE8E8`| `Theme.of(context).colorScheme.error` / `errorContainer` | Badge "Vắng", nút "Kết thúc điểm danh" |
| **Status Neutral** | `color/status-neutral` | Text `#5A6B7C`, Nền `#E8ECF0`| `AppColors.statusNeutralText` / `AppColors.statusNeutralBg` | Badge "Chưa mở", "Chưa đến giờ" |
| **Typography Display** | `type/display-large` | 24sp / Bold | `Theme.of(context).textTheme.headlineMedium` | Tiêu đề trang: "Tổng quan", "Đăng nhập" |
| **Typography Header** | `type/header-medium` | 18sp / SemiBold | `Theme.of(context).textTheme.titleLarge` | Tên môn PRM393, tiêu đề khối |
| **Typography Stat Number**| `type/stat-large` | 28sp / Bold | `Theme.of(context).textTheme.displaySmall` | Số liệu lớn: 35, 28, 7, 80% |
| **Typography Body** | `type/body-regular` | 14sp / Regular | `Theme.of(context).textTheme.bodyMedium` | Nội dung mô tả, chi tiết ca học |
| **Typography Caption** | `type/caption` | 12sp / Medium | `Theme.of(context).textTheme.labelSmall` | Chip tags, giờ quét (07:06:14) |
| **Spacing Small** | `spacing/sm` | 8.0 dp | `AppSpacing.sm` | Khoảng cách icon và text |
| **Spacing Medium** | `spacing/md` | 16.0 dp | `AppSpacing.md` | Padding lề chuẩn màn hình, khoảng cách các card |
| **Spacing Large** | `spacing/lg` | 24.0 dp | `AppSpacing.lg` | Padding bên trong card đăng nhập, khoảng cách các khối lớn |
| **Radius Card** | `radius/card` | 16.0 - 20.0 dp | `BorderRadius.circular(16.0)` | Bo góc các card nội dung |
| **Radius Button / Input**| `radius/control` | 12.0 dp | `BorderRadius.circular(12.0)` | Bo góc nút bấm và textfield |
| **Radius Chip** | `radius/chip` | 999.0 dp | `BorderRadius.circular(999.0)` | Bo tròn hoàn toàn các badge trạng thái |

---

### Table B: Figma Components to Flutter Widgets

| Figma Component | Variant Name | Flutter Widget Mapping | Implementation Notes |
| :--- | :--- | :--- | :--- |
| **Button Accent** | `Type=Gold, State=Default/Pressed/Disabled` | `FilledButton` | Background `#D69E2E`, Text tối màu `#243D36`, height 52dp |
| **Button Dark** | `Type=Pine, State=Default/Pressed` | `FilledButton` | Background `#173D35`, Text trắng, height 52dp |
| **Button Google** | `Type=GoogleSSO, State=Default` | `FilledButton.icon` | Background `#4285F4`, icon Google SVG, height 56dp |
| **QR Code Container** | `Type=LiveQR, State=Active` | `QrImageView` (`qr_flutter`) | Box $224\times 224\text{ dp}$, timer đếm lùi 45s tự sinh chuỗi token |
| **Stat Summary Card** | `Type=MetricBox` | `Container` bo góc 16dp | Grid 2x2: Icon tròn + Số liệu lớn 28sp Bold + Nhãn chữ |
| **Class Session Card** | `Type=SessionItem, Status=Live/Pending` | `Card` với `InkWell` | Viền xanh `#DCEAA5` khi đang mở, badge trạng thái, nút hành động |
| **Student Feed Tile** | `Type=AttendanceTile, Status=Present/Late` | `ListTile` | Avatar 2 chữ cái tròn + Họ tên bold + MSSV + Giờ quét + Badge |
| **Bottom Navigation Bar**| `Type=Standard, Items=4` | `NavigationBar` | 4 tab: Tổng quan, Lớp học, Lịch dạy, Báo cáo (cao 68dp) |
| **Stepper Indicator** | `Type=3Steps, Step=1/2/3` | `Row` các `CircleAvatar` nối nhau | 1. Chọn file $\rightarrow$ 2. Chọn tab $\rightarrow$ 3. Kết quả |
| **Conflict Alert Box** | `Type=ErrorWarning` | `Container` viền đỏ `#D32F2F` | Icon cảnh báo + Mô tả xung đột + Gợi ý đổi slot/phòng |

---

## 2. Detailed Screen Specifications (Đặc tả chi tiết từng màn hình)

---

### Screen S01: Đăng nhập (Google SSO)
1. **Layout:**
   - Cố định toàn màn hình: `Scaffold` $\rightarrow$ `Stack` $\rightarrow$ Background Image FPT Campus (làm mờ nhẹ) $\rightarrow$ Gradient Overlay (`#0A1A18` 60% đến `#05100E` 80%).
   - Vùng cuộn an toàn (`SingleChildScrollView` + `SafeArea`): Căn giữa màn hình bằng `Center`. Cụm nhận diện thương hiệu phía trên ("CAMPUS / STUDIO", khẩu hiệu "Có mặt. Kết nối. Tiến xa." màu `#F8F6EE`) $\rightarrow$ Card trắng nổi (`width: 320dp`, bo góc 24dp, `padding: 24dp`).
2. **Components:**
   - `Logo` FPT Education (`height: 38dp`, căn giữa).
   - `Headline` ("Đăng nhập", 26sp bold, `#1E293B`).
   - `BodyText` ("Để tiếp tục sử dụng ứng dụng điểm danh FPT University", 14sp, `#64748B`).
   - `Button Google` (`height: 56dp`, rộng 100%, `#4285F4`, chữ trắng, bo góc 12dp).
   - `Divider` hai bên chữ "FPT UNIVERSITY" $\rightarrow$ Footer có icon khiên bảo mật: "Kết nối bằng tài khoản Google của bạn".
3. **States:**
   - *Default:* Sẵn sàng đăng nhập.
   - *Loading:* Nút Google hiển thị `CircularProgressIndicator(strokeWidth: 2, color: Colors.white)` và vô hiệu hóa tap.
   - *Error:* Hiển thị `SnackBar` đỏ nếu tài khoản không thuộc tên miền `@fpt.edu.vn`.
4. **User Interactions:**
   - Tap "Đăng nhập bằng Google" $\rightarrow$ Kích hoạt `google_sign_in` SDK $\rightarrow$ Chọn tài khoản trường FPT $\rightarrow$ Đăng nhập thành công chuyển sang S02.
5. **Navigation:**
   - Khởi chạy ứng dụng $\rightarrow$ S01.
   - Đăng nhập thành công $\rightarrow$ Chuyển thẳng tới S02 (Home Dashboard).
   - Nút Back: Thoát ứng dụng (System Exit).
6. **Important UI Constraints:**
   - Không chứa form email/password, không có bottom navigation.
   - Chiều cao nút Google đạt chuẩn 56dp (vượt xa mức tối thiểu 48dp). Chiều rộng card cố định 320dp trên frame 360dp, tự động căn giữa cân đối trên màn hình 412dp.

---

### Screen S02: Tổng quan giảng dạy (Home Dashboard)
1. **Layout:**
   - Cố định trên cùng: Top Bar gọn (`height: 56dp`, nền `#F5F4EC`) gồm dòng nhỏ "FPT Attendance", tiêu đề "Tổng quan" và Avatar tròn "N" (`36x36 dp`) bên phải.
   - Cố định dưới đáy: `NavigationBar` 4 mục (Tổng quan, Lớp học, Lịch dạy, Báo cáo) cao 68dp.
   - Vùng cuộn ở giữa (`SingleChildScrollView`, `padding: 16dp`):
     - Dòng ngày "Thứ Bảy, 03/10/2026" + Nút mở Sheet "Bộ lọc & Đồng bộ".
     - 2 Thẻ thống kê nhanh: "2 tiết hôm nay" & "1 đang điểm danh".
     - **Khối ưu tiên cao nhất:** Card Tiết đang điểm danh (PRM393 · SE1917, Slot 2, Phòng 101, nút chính "Xem điểm danh" cao 52dp).
     - Khối Tiết tiếp theo: Card PRN232 (Slot 3, Phòng 203, badge "Chưa đến giờ", nút "Xem chi tiết").
     - Thao tác quản trị: Nút vàng đất "+ Tạo lớp học" và nút phụ "Xếp lịch".
2. **Components:**
   - `Class Session Card` (`Status=Live` viền xanh `#DCEAA5`; `Status=Pending` viền xám).
   - `Button Dark` (Nút "Xem điểm danh" màu `#173D35`).
   - `Button Accent` (Nút "+ Tạo lớp học" màu `#D69E2E`).
   - `Bottom Navigation Bar` (Tab "Tổng quan" active nền `#DCEAA5`).
3. **States:**
   - *Default / Populated:* Hiển thị đủ 2 ca học và số liệu thống kê.
   - *Empty:* Nếu ngày không có ca dạy, hiển thị Card minh họa thân thiện "Hôm nay không có tiết dạy".
   - *Loading:* Skeleton placeholder xám nhạt trong 500ms đầu đồng bộ dữ liệu.
4. **User Interactions:**
   - Tap "Xem điểm danh" trên card PRM393 $\rightarrow$ Mở ngay màn hình Live QR S09.
   - Tap "Xem chi tiết" trên card PRN232 $\rightarrow$ Mở chi tiết tiết học S08.
   - Tap "+ Tạo lớp học" $\rightarrow$ Mở S03; Tap "Xếp lịch" $\rightarrow$ Mở S07.
   - Tap nút "Bộ lọc & Đồng bộ" $\rightarrow$ Mở Bottom Sheet chọn học kỳ và công tắc "Tự đồng bộ 30s".
5. **Navigation:**
   - Đến từ: S01 sau khi đăng nhập.
   - Dẫn tới: S03 (Lớp học), S06 (Lịch dạy), S08 (Chi tiết tiết), S09 (Điểm danh), S10 (Báo cáo).
   - Nút Back: Nhấn 2 lần trong 2 giây để thoát ứng dụng (Double-tap to exit).
6. **Important UI Constraints:**
   - Card tiết đang điểm danh nằm ngay trong khung nhìn đầu tiên (Above the fold), không bắt buộc phải cuộn mới thấy nút.
   - Vùng chạm mọi nút $\ge 48\times 48\text{ dp}$. Xử lý text overflow `TextOverflow.ellipsis` cho tên môn và phòng.

---

### Screen S03: Lớp học của tôi
1. **Layout:**
   - Cố định trên: `AppBar` ("CAMPUS / LỚP HỌC", Avatar "N").
   - Cố định dưới: `NavigationBar` (Tab "Lớp học" active).
   - Vùng cuộn ở giữa (`ListView`, `padding: 16dp`):
     - Tiêu đề trang "Lớp học của tôi" + Mô tả.
     - Cụm nút thao tác: Nút vàng đất "+ Tạo lớp học" và nút toàn chiều rộng "Nhập tất cả lớp từ Sheet".
     - Thanh tìm kiếm `TextField` (icon kính lúp, placeholder "Tìm mã lớp, mã môn, học kỳ...") + Dropdown "Tất cả học kỳ".
     - Danh sách 1 cột các Card lớp học (PRM393, PRN232, SWP391).
2. **Components:**
   - `Class Info Card`: Header thẻ màu `#F4F7FA` (icon sách, badge học kỳ FA2026, mã môn 26sp bold, mã lớp 14sp). Phần thân: icon nhóm (35 sinh viên), số buổi học, badge liên kết Google Sheet, nút "Mở lớp $\nearrow$".
   - `Search TextFormField` (bo góc 12dp, nền `#F4F7FA`).
3. **States:**
   - *Populated:* Hiển thị danh sách 3 lớp học.
   - *Search Empty:* Nếu từ khóa không khớp, hiển thị "Không tìm thấy lớp học phù hợp".
4. **User Interactions:**
   - Nhập từ khóa $\rightarrow$ Lọc danh sách tức thì theo thời gian thực (realtime debounce 300ms).
   - Tap "Mở lớp $\nearrow$" trên PRM393 $\rightarrow$ Chuyển sang S04 (Chi tiết lớp).
   - Tap "Nhập tất cả lớp từ Sheet" $\rightarrow$ Mở wizard nhập dữ liệu.
5. **Navigation:**
   - Đến từ: Bottom Navigation Tab "Lớp học" hoặc nút "+ Tạo lớp" ở S02.
   - Dẫn tới: S04 (Chi tiết lớp PRM393).
   - Nút Back: Quay về tab Tổng quan S02.
6. **Important UI Constraints:**
   - Danh sách lớp cuộn dọc 1 cột, không cuộn ngang. Chiều cao vùng bấm "Mở lớp" $\ge 48\text{ dp}$.

---

### Screen S04: Chi tiết lớp học (PRM393 · SE1917)
1. **Layout:**
   - Cố định trên: `AppBar` (Nút Back bên trái, Tiêu đề "Chi tiết lớp", Menu 3 chấm góc phải chứa tùy chọn "Xóa lớp học" kèm dialog xác nhận).
   - Vùng cuộn ở giữa (`SingleChildScrollView`, `padding: 16dp`):
     - Thẻ nhận diện lớp PRM393 · SE1917 (Sĩ số 35, 8 buổi, link sheet tab `12_PRM393_SE1917`).
     - Hàng nút hành động: Nút vàng đất "Xếp lịch tiết học" và nút viền "Nhập từ Google Sheet".
     - Nhóm danh sách tiết học: Tiết đang mở (03/10 Slot 2 Phòng 101, viền xanh nhạt), 2 tiết sắp tới (04/10, 06/10), accordion thu gọn 5 tiết đã kết thúc.
     - Thẻ "Tổng quan khóa học": Tỷ lệ vắng 4.0% và danh sách Top sinh viên vắng nhiều (Nguyễn Văn An 60%, Trần Minh Bình 40%...).
2. **Components:**
   - `Class Header Card`, `Accordion ExpansionTile`, `Absent Student ListTile` (kèm badge % vắng đỏ/cam).
3. **States:**
   - *Populated:* Dữ liệu đầy đủ 8 ca học và thống kê chuyên cần.
4. **User Interactions:**
   - Tap "Xếp lịch tiết học" $\rightarrow$ Mở S07 (điền sẵn lớp PRM393).
   - Tap "Nhập từ Google Sheet" $\rightarrow$ Mở S05 (Nhập sinh viên vào đúng lớp PRM393).
   - Tap vào tiết đang mở $\rightarrow$ Mở S09; Tap vào tiết chưa mở $\rightarrow$ Mở S08.
5. **Navigation:**
   - Đến từ: S03 ("Mở lớp").
   - Dẫn tới: S05, S07, S08, S09.
   - Nút Back: Quay về S03 (giữ nguyên bộ lọc học kỳ).
6. **Important UI Constraints:**
   - Danh sách sinh viên vắng nhiều hiển thị tối đa 4 người có % vắng cao nhất để tránh tràn màn hình. Tên tab Google Sheet dài tự động wrap text.

---

### Screen S05: Nhập sinh viên từ Google Sheet (Stepper 3 bước)
1. **Layout:**
   - Cố định trên: `AppBar` (Nút Back, Tiêu đề "Nhập sinh viên").
   - Cố định dưới: Nút CTA chính đặt ở đáy thẻ nội dung.
   - Vùng cuộn (`SingleChildScrollView`, `padding: 16dp`):
     - Thẻ lớp đích cố định: "PRM393 · SE1917" (Badge FA2026, dòng "Nhập danh sách vào lớp này").
     - Stepper 3 bước trực quan: 1. Chọn file $\rightarrow$ 2. Chọn tab $\rightarrow$ 3. Kết quả.
     - Vùng nội dung động tương ứng với từng bước (`S05-A` đến `S05-E`).
2. **Components:**
   - `Stepper Indicator`, `URL TextFormField` (placeholder "Dán đường dẫn hoặc ID file"), `RadioListTile` (danh sách tab), `Button Accent`.
3. **States (5 Frames nghiệp vụ):**
   - *S05-A (Nhập đường dẫn):* Nút "Lấy danh sách tab" bị disabled khi ô nhập trống; hiển thị thông báo quyền đọc file.
   - *S05-B (Chọn tab):* Tóm tắt file, danh sách radio các tab (`12_PRM393_SE1917`, `11_PRN232_SE1918`...), nút "Nhập sinh viên" (disabled nếu chưa chọn tab).
   - *S05-C (Đang nhập):* Spinner loading với thông báo "Đang nhập sinh viên... Vui lòng chờ hệ thống xử lý", nút bị khóa.
   - *S05-D (Kết quả thành công):* Icon check xanh, tóm tắt: Nhập mới 0, Bỏ qua 35 (đã có trong lớp), Sĩ số 35, nút "Về chi tiết lớp".
   - *S05-E (Lỗi file):* Icon lỗi, giải thích không thể đọc file, nút "Thử lại" và giữ nguyên URL để sửa.
4. **User Interactions:**
   - Nhập URL $\rightarrow$ Bấm "Lấy danh sách tab" $\rightarrow$ Chọn radio tab `12_PRM393_SE1917` $\rightarrow$ Xác nhận nhập $\rightarrow$ Thành công.
5. **Navigation:**
   - Đến từ: S04 ("Nhập từ Google Sheet").
   - Dẫn tới: S04 sau khi hoàn tất bước 3.
   - Nút Back: Quay về S04 mà không lưu thay đổi.
6. **Important UI Constraints:**
   - Bàn phím mở: `resizeToAvoidBottomInset: true`, trường URL và nút bấm tự động cuộn vào vùng nhìn thấy.

---

### Screen S06: Lịch dạy theo tuần (Calendar View)
1. **Layout:**
   - Cố định trên: `AppBar` ("CAMPUS / LỊCH DẠY", Avatar "N").
   - Cố định dưới: `NavigationBar` (Tab "Lịch dạy" active).
   - Vùng cuộn ở giữa (`SingleChildScrollView`, `padding: 16dp`):
     - Banner tiêu đề "Lịch dạy" gọn gàng + mốc "Cập nhật lúc 09:40".
     - Thao tác nhanh: Nút "Xếp lịch tiết học" (vàng đất) và nút "Đọc lịch từ ảnh".
     - Hàng điều hướng tuần: Nút tuần trước, ngày trung tâm `28/09 – 04/10/2026`, nút tuần sau, nút "Hôm nay".
     - **Thanh 7 ngày (Weekly Strip):** T2 28 $\rightarrow$ CN 04. Ngày đang chọn T7 03 có nền xanh đậm `#173D35` và chấm tròn xanh bên dưới.
     - Tiêu đề danh sách: "Thứ Bảy, 03/10 — 2 tiết học".
     - Danh sách các ca dạy trong ngày: Card PRM393 (Slot 2, Phòng 101, "Xem điểm danh $\rightarrow$") và Card PRN232 (Slot 3, Phòng 203, "Xem chi tiết").
2. **Components:**
   - `Weekly Date Picker Item` (kích thước tối thiểu $48\times 56\text{ dp}$ cho mỗi ngày).
   - `Class Session Card`, `Button Accent`.
3. **States:**
   - *Populated (T7 03/10):* Có 2 tiết học.
   - *S06-Empty (CN 04/10):* Ngày không có lịch dạy, hiển thị Card trống thân thiện: "Ngày này chưa có lịch dạy. Bạn có thể chọn ngày khác hoặc xếp lịch mới" kèm nút CTA "Xếp lịch tiết học".
4. **User Interactions:**
   - Tap vào các ô ngày trên thanh Strip Bar $\rightarrow$ Đổi ngày được chọn tức thì và tải danh sách tiết tương ứng.
   - Tap "Xem điểm danh $\rightarrow$" $\rightarrow$ Mở S09.
5. **Navigation:**
   - Đến từ: Bottom Navigation Tab "Lịch dạy".
   - Dẫn tới: S07 (Xếp lịch mới), S08 (Chi tiết tiết), S09 (Điểm danh).
   - Nút Back: Quay về tab Tổng quan S02.
6. **Important UI Constraints:**
   - Thanh 7 ngày dàn đều vừa khít chiều rộng màn hình 360dp mà không bị tràn ngang, mỗi ô ngày đảm bảo vùng chạm $\ge 48\times 48\text{ dp}$.

---

### Screen S07: Xếp lịch tiết học mới (Conflict Detection & Recovery)
1. **Layout:**
   - Cố định trên: `AppBar` (Nút Back, Tiêu đề "Xếp lịch tiết học").
   - Vùng cuộn (`SingleChildScrollView`, `padding: 16dp`):
     - Card form trắng (bo góc 20dp):
       - Trường Lớp học: Dropdown chọn lớp (mặc định PRM393 · SE1917, FA2026).
       - Trường Ngày học: `DatePicker` (giá trị 05/10/2026, khóa ngày trong quá khứ).
       - Trường Slot học: Bottom Sheet chọn 6 slot chuẩn FPT (Slot 1: 07:00–09:15 đến Slot 6: 20:00–22:15).
       - Trường Phòng học: `TextFormField` có icon vị trí (nhập số thuần: ví dụ 101, 203).
     - Khối Tóm tắt trước khi lưu: Hiển thị thông tin tổng hợp + Ghi chú: "Sau khi lưu, tiết học ở trạng thái Chưa mở. Bạn sẽ mở điểm danh khi đến giờ học."
     - Nút chính: "Lưu lịch học" (vàng đất, cao 52dp, rộng 100%).
2. **Components:**
   - `DropdownButtonFormField`, `TextFormField`, `Conflict Alert Box`, `Button Accent`.
3. **States (3 Frames nghiệp vụ):**
   - *S07-DEFAULT:* Form điền bình thường lịch mới đề xuất ngày 05/10 Slot 1 Phòng 101.
   - *S07-CONFLICT (Nhánh lỗi):* Hiển thị viền đỏ và hộp thoại cảnh báo: "Bạn đã có lịch dạy trong khung giờ này. Chọn slot hoặc ngày khác". Cho phép chọn lại Slot 2 hoặc đổi sang Phòng 203 ngay trên form mà không bắt nhập lại lớp.
   - *S07-SUCCESS (Nhánh thành công):* Overlay xác nhận "Đã xếp lịch tiết học", badge "Chưa mở" kèm nút "Về lịch dạy (S06)" hoặc "Về chi tiết lớp (S04)".
4. **User Interactions:**
   - Nhập thông tin form $\rightarrow$ Nhấn "Lưu lịch học" $\rightarrow$ Nếu trùng giờ hiển thị banner lỗi $\rightarrow$ Chọn lại slot/phòng $\rightarrow$ Lưu thành công.
5. **Navigation:**
   - Đến từ: S04 hoặc S06.
   - Dẫn tới: S06 (Lịch dạy) sau khi lưu thành công.
   - Nút Back: Quay về trang nguồn, giữ nguyên dữ liệu chưa lưu nếu xác nhận hủy.
6. **Important UI Constraints:**
   - Validation: Bắt buộc chọn đủ 4 trường; tự động viết hoa và lọc số cho mã phòng; không cho phép chọn ngày quá khứ.

---

### Screen S08: Chi tiết tiết học & Điều kiện mở điểm danh
1. **Layout:**
   - Cố định trên: `AppBar` (Nút Back, Tiêu đề "Chi tiết tiết học").
   - Cố định dưới: Nút hành động chính cao 52dp đặt ở cuối màn hình.
   - Vùng cuộn ở giữa (`SingleChildScrollView`, `padding: 16dp`):
     - Card nhận diện lớp: PRM393 · SE1917, FA2026, Sĩ số 35.
     - Card thông tin tiết học: Ngày 05/10/2026, Slot 1, Giờ 07:00–09:15, Phòng 101.
     - Khối Trạng thái & Hướng dẫn: Badge trạng thái + Thông báo giải thích chi tiết.
2. **Components:**
   - `Class Header Card`, `Status Info Card`, `Button Accent`.
3. **States (Các biến thể thời gian thực):**
   - *S08-A (Chưa đến giờ — lúc 06:50):* Badge "Chưa mở", thông báo: "Chưa đến giờ mở điểm danh. Bạn có thể mở từ 07:00 đến trước 09:15". Nút "Mở điểm danh" bị khóa (disabled). Không hiện mã QR.
   - *S08-B (Đủ điều kiện mở — lúc 07:05):* Badge "Chưa mở", thông báo: "Đã đến giờ. Bạn có thể mở điểm danh cho tiết này". Nút vàng đất "Mở điểm danh" kích hoạt khả dụng.
   - *S08-C (Đang mở phiên):* Nút chuyển sang trạng thái disabled kèm spinner "Đang mở điểm danh...".
   - *S08-D (Phiên đã mở):* Badge nhấp nháy xanh "Đang điểm danh", nút chuyển thành "Xem điểm danh $\rightarrow$" (dẫn tới S09).
   - *S08-E (Mở thất bại):* Banner lỗi kết nối kèm nút "Thử lại".
4. **User Interactions:**
   - Khi đủ điều kiện (S08-B) $\rightarrow$ Tap "Mở điểm danh" $\rightarrow$ Hiển thị loading S08-C $\rightarrow$ Chuyển sang phiên trực tiếp S09.
5. **Navigation:**
   - Đến từ: S04 hoặc S06.
   - Dẫn tới: S09 khi mở phiên hoặc xem phiên.
   - Nút Back: Quay về đúng trang nguồn.
6. **Important UI Constraints:**
   - Khóa nút mở điểm danh trước giờ bắt đầu, có giải thích rõ ràng bằng chữ (không chỉ làm mờ nút).

---

### Screen S09: Điểm danh trực tiếp (Live Dynamic QR Session)
1. **Layout:**
   - Cố định trên: `AppBar` (Nút Back, Tiêu đề "Điểm danh").
   - Cố định dưới: Nút cảnh báo màu đỏ "Kết thúc điểm danh" (cao 52dp).
   - Vùng cuộn ở giữa (`SingleChildScrollView`, `padding: 16dp`):
     - Khối thông tin phiên: PRM393 · SE1917, Slot 1, Phòng 101, Badge "Đang điểm danh" kèm dòng "Cập nhật mỗi 5 giây".
     - Lưới thống kê 2x2: Sĩ số 35, Đã điểm danh 28, Chưa điểm danh 7, Tỷ lệ 80%.
     - **Card Mã QR Trung tâm:** Khung QR $224\times 224\text{ dp}$, dòng đồng hồ đếm ngược bảo mật: "Mã QR còn hiệu lực: 00:45". Hàng 2 nút phụ: "Làm mới QR" và "Phóng to QR".
     - **Danh sách điểm danh thời gian thực (Realtime Feed):** Ô tìm kiếm, dropdown lọc trạng thái, danh sách các sinh viên vừa quét (Nguyễn Văn An 07:06 Có mặt, Lê Ngọc Chi 07:22 Đi muộn...).
2. **Components:**
   - `QR Code Box`, `Metric Grid Container`, `Student Feed ListTile`, `Button Danger` (Màu đỏ `#D32F2F`).
3. **States (5 Frames nghiệp vụ):**
   - *S09-LIVE:* Phiên đang chạy, QR đếm ngược 45s, sĩ số nhảy 28/35 realtime.
   - *S09-QR-OVERLAY:* Dialog phóng to mã QR toàn màn hình cho sinh viên cuối Phòng 101 quét từ xa, có nút "Đóng" quay về S09 mà không tắt phiên.
   - *S09-CONFIRM-CLOSE:* Dialog xác nhận: "Còn 7 sinh viên chưa điểm danh. Khi kết thúc, những sinh viên này sẽ được ghi vắng. Phiên đã kết thúc không thể mở lại" (2 nút: "Tiếp tục" và "Kết thúc").
   - *S09-CONNECTION-ERROR:* Banner mất mạng, giữ nguyên số liệu đã nạp gần nhất, nút "Thử lại".
   - *S09-CLOSED:* Phiên đã kết thúc, thay thế vùng QR bằng thông báo hoàn tất, số liệu Vắng: 7, nút CTA chính "Xem báo cáo (S10)".
4. **User Interactions:**
   - Tap "Làm mới QR" $\rightarrow$ Sinh mã mới và reset đếm ngược về 00:45.
   - Tap "Phóng to QR" $\rightarrow$ Mở overlay full-screen.
   - Tap "Kết thúc điểm danh" $\rightarrow$ Mở dialog xác nhận $\rightarrow$ Chuyển sang S10.
5. **Navigation:**
   - Đến từ: S08 ("Mở điểm danh" hoặc "Xem điểm danh").
   - Dẫn tới: S10 sau khi kết thúc phiên.
   - Nút Back: Hiển thị cảnh báo "Rời màn hình không làm tắt phiên điểm danh ngầm".
6. **Important UI Constraints:**
   - Vùng lề an toàn (quiet zone) quanh mã QR tối thiểu 16dp, không chèn logo đè lên mã. Đảm bảo timer đếm lùi chính xác theo `Timer.periodic`.

---

### Screen S10: Báo cáo điểm danh & Xuất Google Sheets
1. **Layout:**
   - Cố định trên: `AppBar` (Nút Back quay về S09, Tiêu đề "Báo cáo điểm danh").
   - Vùng cuộn ở giữa (`SingleChildScrollView`, `padding: 16dp`):
     - Bộ chọn lớp và tiết: PRM393 · SE1917, 05/10/2026 Slot 1 Phòng 101.
     - Khối thông tin kết quả: Badge "Đã kết thúc", Sĩ số 35, Lưới 2x2 kết quả (Có mặt: 26, Đi muộn: 2, Vắng: 7, Có phép: 0), Thẻ tỷ lệ 80% ("28/35 sinh viên có mặt hoặc đi muộn").
     - Danh sách kết quả chi tiết: Bộ lọc tab (Tất cả, Có mặt, Đi muộn, Vắng), chi tiết từng sinh viên kèm giờ quét (sinh viên vắng hiển thị gạch ngang `—`, không ghi 00:00).
     - **Card Xuất Google Sheets:** Icon bảng tính xanh lá, Tab đã liên kết `12_PRM393_SE1917`, cảnh báo: "Kết quả sẽ được ghi vào cột F của tab này, thay thế kết quả đã xuất trước đó".
     - Nút hành động chính: "Xuất sang Google Sheets" (vàng đất, cao 52dp, rộng 100%).
2. **Components:**
   - `Report Metric Grid`, `Filter Segmented Control`, `Google Sheet Sync Card`, `Button Accent`.
3. **States (5 Frames luồng xuất Sheets):**
   - *S10-RESULT:* Xem báo cáo mặc định của tiết đã đóng.
   - *S10-CONFIRM-EXPORT:* Modal xác nhận ghi đè Cột F (2 nút: "Hủy" và "Xác nhận xuất").
   - *S10-EXPORTING:* Spinner loading "Đang xuất kết quả...", khóa thao tác bấm lặp.
   - *S10-EXPORT-SUCCESS:* Modal thông báo thành công kèm nút "Mở Google Sheet" và nút "Đóng".
   - *S10-EXPORT-ERROR:* Banner báo lỗi nếu mất mạng hoặc thiếu quyền truy cập Sheet, nút "Thử lại" và giữ nguyên kết quả trên app.
4. **User Interactions:**
   - Chuyển tab lọc danh sách sinh viên Có mặt/Vắng.
   - Tap "Xuất sang Google Sheets" $\rightarrow$ Mở dialog xác nhận $\rightarrow$ Tap "Xác nhận xuất" $\rightarrow$ Đồng bộ dữ liệu vào Cột F $\rightarrow$ Hiện modal thành công.
5. **Navigation:**
   - Đến từ: S09 sau khi kết thúc phiên điểm danh.
   - Dẫn tới: Mở URL Google Sheet qua trình duyệt hoặc quay về S02.
   - Nút Back: Quay về S09 của đúng tiết đang xem.
6. **Important UI Constraints:**
   - Tuyệt đối không xuất dữ liệu khi chưa qua bước xác nhận ghi đè Cột F. Giữ nguyên dữ liệu trên ứng dụng kể cả khi việc đồng bộ Sheets gặp sự cố kết nối.
