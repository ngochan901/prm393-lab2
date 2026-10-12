# AI Design Log & Iteration History

> **Nguyên tắc cốt lõi của môn học:** *"AI tạo ra; bạn quyết định."*  
> Tài liệu này lưu trữ nguyên văn toàn bộ prompt từ Google Stitch, quá trình phản biện bằng trợ lý AI (VisionCode AI Studio & Google Gemini) và 3 vòng lặp tinh chỉnh có ý nghĩa theo đúng chuẩn 5 yêu cầu bắt buộc của đề bài.

---

## 1. UI Ban Đầu (Google Stitch) — Nguyên Văn Từng Chữ Toàn Bộ Prompt

Dưới đây là nguyên văn toàn bộ các prompt được nhập vào Google Stitch để sinh ra bộ giao diện di động (Mobile Viewport 360 × 800 dp, tương thích 412 dp) cho ứng dụng FPT Attendance (CAMPUS / STUDIO), cơ sở TP. Hồ Chí Minh. Các phòng học được chuẩn hóa theo định dạng số thuần (Phòng 101, Phòng 203).

### 1.1. Prompt Màn hình S01 — Đăng nhập (Google SSO)
```text
Chuyển giao diện đăng nhập desktop của Lab 1 trong ảnh tham chiếu thành giao diện mobile cho cùng ứng dụng.
Đây là chuyển đổi bố cục sang mobile, không thiết kế lại thương hiệu.
Giữ hình ảnh, màu sắc, nội dung và phong cách của bản desktop.
Chỉ tạo một trang: S01 — Đăng nhập.
Kích thước 360 × 800, tương thích chiều rộng 412.
THÀNH PHẦN GIỮ TỪ LAB 1
- Dùng đúng ảnh trường đã đính kèm làm nền toàn màn hình.
- Phủ lớp xanh đen lên ảnh để nội dung dễ đọc: chuyển sắc từ #0A1A18 với độ trong suốt 60% tới #05100E với độ trong suốt 80%.
- Dùng logo FPT University đính kèm, giữ tỷ lệ và màu gốc.
- Thẻ đăng nhập màu trắng, bo góc 24, bóng nhẹ.
- Tiêu đề “Đăng nhập”, màu #1E293B.
- Nội dung phụ màu #64748B.
- Nút Google màu #4285F4, chữ trắng, bo góc 12.
- Màu nhận diện bổ sung: xanh đậm #173D35, xanh nhạt #DCEAA5 và trắng kem #F8F6EE.
CHUYỂN BỐ CỤC DESKTOP SANG MOBILE
- Sắp xếp một cột, không giữ hai cột desktop.
- Safe area trên và dưới.
- Padding ngoài 20; thẻ rộng 320 ở frame 360.
- Padding bên trong thẻ 24.
- Phía trên thẻ có cụm nhận diện nhỏ: “CAMPUS / STUDIO” và khẩu hiệu “Có mặt. Kết nối. Tiến xa.”
- Khẩu hiệu màu trắng kem, không dùng cỡ chữ lớn như desktop.
- Ẩn các vòng tròn trang trí lớn để tránh chật màn hình.
- Phần đăng nhập là trọng tâm và nút Google nhìn thấy ngay ở kích thước chữ mặc định.
- Cho phép cuộn dọc nếu màn hình thấp hoặc người dùng tăng cỡ chữ.
NỘI DUNG TRONG THẺ, THEO THỨ TỰ
1. Logo FPT University, căn giữa.
2. Khoảng cách 24.
3. Tiêu đề “Đăng nhập”, 26, đậm.
4. Khoảng cách 12.
5. Mô tả căn giữa, 14–16: “Để tiếp tục sử dụng ứng dụng điểm danh FPT University”
6. Khoảng cách 28.
7. Nút cao 56, rộng hết phần nội dung: biểu tượng Google và “Đăng nhập bằng Google”.
8. Khoảng cách 24.
9. Đường phân cách hai bên chữ “FPT UNIVERSITY”.
10. Chú thích có icon khiên: “Kết nối bằng tài khoản Google của bạn”.
TYPOGRAPHY: Segoe UI / Roboto hỗ trợ tiếng Việt. Chữ nội dung tối thiểu 14.
KHÔNG THÊM: Form email/mật khẩu, đăng ký, quên mật khẩu, chọn vai trò, bottom navigation.
```

### 1.2. Prompt Màn hình S02 — Tổng quan giảng dạy (Dashboard)
```text
Thiết kế tiếp S02 — Tổng quan giảng dạy cho ứng dụng mobile FPT Attendance, sau màn hình đăng nhập đã tạo.
Chỉ tạo trang S02. Giữ nguyên trang S01.
Đây là chuyển giao diện desktop Lab 1 sang mobile: giữ nhận diện, tên chức năng và nghiệp vụ hiện có, sắp xếp lại bố cục để dùng thuận tiện trên điện thoại.
KÍCH THƯỚC: Frame 360 × 800, thích ứng chiều rộng 412. Safe area trên và dưới. Nội dung cuộn dọc. Padding ngang 16, khoảng cách khối 16–24.
PHONG CÁCH: Nền chính xanh nhạt #E8F0ED, thanh đầu trang trắng kem #F5F4EC, chữ chính xanh xám đậm #3A504E. Banner gradient nhẹ từ #435A58 đến #2C3E3D. Card trắng bo góc 16–20. Nút “Tạo lớp học” vàng đất #D69E2E. Điểm nhấn xanh nhạt #DCEAA5. Vùng chạm tối thiểu 48 × 48.
BỐ CỤC:
1. APP BAR: Icon menu bên trái, nhãn “CAMPUS / TỔNG QUAN”, avatar tròn chữ N bên phải.
2. BANNER: Tiêu đề trắng “Tổng quan giảng dạy”, mô tả “Quản lý lớp, lịch dạy và điểm danh.”, mốc “Cập nhật lúc 09:40”.
3. THAO TÁC NHANH: Hàng 1 gồm nút “Tạo lớp học” (vàng đất) và “Xếp lịch”. Hàng 2 gồm nút phụ “Đọc lịch từ ảnh”.
4. BỘ LỌC VÀ ĐỒNG BỘ: Dropdown “Tất cả học kỳ”, nút icon “Đồng bộ”, switch “Tự đồng bộ 30 giây”.
5. THỐNG KÊ HÔM NAY: 2 card nhỏ cạnh nhau: “Tiết hôm nay”: 2 và “Đang điểm danh”: 1.
6. DANH SÁCH “TIẾT HÔM NAY”: Card 1: Môn PRM393, Lớp SE1917, Phòng 101, Slot 2 · 09:30–11:45, badge “Đang điểm danh”, nút “Xem điểm danh”. Card 2: Môn PRN232, Lớp SE1918, Phòng 203, Slot 3 · 12:30–14:45, badge “Chưa đến giờ”, hành động “Xem chi tiết”.
7. CÁC TIẾT SẮP TỚI: Card minh họa ngày mai PRM393 · SE1917 · Phòng 101 · Slot 1 · 07:00–09:15.
```

### 1.3. Prompt Màn hình S05 — Nhập sinh viên từ Google Sheet
```text
Thiết kế tiếp S05 — Nhập sinh viên từ Google Sheet cho ứng dụng mobile FPT Attendance.
Chỉ tạo S05 và các trạng thái của S05. Giữ nguyên S01–S04.
Kế thừa quy trình Lab 1: Nhập đường dẫn hoặc ID Google Sheet -> lấy danh sách tab -> chọn một tab -> nhập sinh viên -> hiển thị kết quả.
Frame 360 × 800, thích ứng 412. Nền #E8F0ED, App bar #F5F4EC, Card trắng bo góc 20, nút vàng đất #D69E2E.
1. APP BAR: Nút Back, tiêu đề “Nhập sinh viên”.
2. THÔNG TIN LỚP ĐÍCH: Card nhỏ hiển thị “PRM393 · SE1917”, badge “FA2026”, dòng “Nhập danh sách vào lớp này”.
3. CHỈ BÁO TIẾN TRÌNH: 3 bước gọn “1. Chọn file” -> “2. Chọn tab” -> “3. Kết quả”.
CÁC FRAME TRẠNG THÁI:
- S05-A (Nhập đường dẫn): Ô nhập URL/ID file, ghi chú quyền đọc file, nút “Lấy danh sách tab”.
- S05-B (Chọn tab): Radio danh sách tab (12_PRM393_SE1917, 11_PRN232_SE1918, 10_SWP391_SE1908), nút “Nhập sinh viên”.
- S05-C (Đang nhập): Spinner đang xử lý danh sách.
- S05-D (Kết quả thành công): Nhập mới: 0, Bỏ qua: 35 (đã có trong lớp), Sĩ số: 35 sinh viên, nút “Về chi tiết lớp”.
- S05-E (Không đọc được file): Icon lỗi, thông báo kiểm tra quyền đọc file, nút “Thử lại”.
```

### 1.4. Prompt Màn hình S07 — Xếp lịch tiết học & Xử lý xung đột
```text
Thiết kế tiếp S07 — Xếp lịch tiết học cho ứng dụng mobile FPT Attendance, kế thừa nghiệp vụ Lab 1.
Chỉ tạo S07 và các trạng thái liên quan. Frame 360 × 800, thích ứng 412.
1. APP BAR: Nút Back, tiêu đề “Xếp lịch tiết học”.
2. GIỚI THIỆU: “Tạo lịch cho lớp”, mô tả “Chọn lớp, ngày, slot và phòng học.”
3. FORM: Lớp học (PRM393 · SE1917), Ngày học (05/10/2026), Slot học (Slot 1 · 07:00–09:15), Phòng học (Phòng 101).
4. TÓM TẮT TRƯỚC KHI LƯU: Khối tóm tắt thông tin lớp, ngày, slot, phòng kèm chú thích tiết ở trạng thái Chưa mở. Nút “Lưu lịch học” cao 52px.
CÁC FRAME:
- S07-DEFAULT: Form điền mới đề xuất.
- S07-CONFLICT: Hiển thị lỗi trùng lịch “Bạn đã có lịch dạy trong khung giờ này. Chọn slot hoặc ngày khác.” Cho phép chọn lại Slot 2 hoặc đổi sang Phòng 203.
- S07-SUCCESS: Xác nhận “Đã xếp lịch tiết học”, badge “Chưa mở”, nút quay về.
```

### 1.5. Prompt Màn hình S09 — Điểm danh trực tiếp (Live Dynamic QR)
```text
Thiết kế tiếp S09 — Điểm danh trực tiếp cho ứng dụng mobile FPT Attendance, kế thừa giao diện desktop Lab 1.
Tiết minh họa: PRM393 · SE1917 · FA2026 · 05/10/2026 · Slot 1 · 07:00–09:15 · Phòng 101 · 35 sinh viên.
Frame 360 × 800, thích ứng 412.
1. APP BAR: Nút Back, tiêu đề “Điểm danh”.
2. THÔNG TIN PHIÊN: Badge “Đang điểm danh”, dòng “Cập nhật mỗi 5 giây”.
3. THỐNG KÊ 2x2: Sĩ số: 35, Đã điểm danh: 28, Chưa điểm danh: 7, Tỷ lệ tham gia: 80%.
4. CARD MÃ QR: Khung QR đen trên nền trắng 224x224, thời hạn đếm ngược “Mã QR còn hiệu lực: 00:45”, nút “Làm mới QR” và nút “Phóng to QR”.
5. DANH SÁCH ĐIỂM DANH: Realtime feed hiển thị họ tên, MSSV, giờ quét (07:06:14), badge Có mặt/Đi muộn.
6. HÀNH ĐỘNG: Nút cảnh báo “Kết thúc điểm danh” mở dialog xác nhận (7 sinh viên chưa điểm danh sẽ bị ghi vắng).
CÁC FRAME: S09-LIVE, S09-QR-OVERLAY (phóng to toàn màn hình), S09-CONFIRM-CLOSE, S09-CONNECTION-ERROR, S09-CLOSED.
```

### 1.6. Prompt Màn hình S10 — Báo cáo điểm danh & Xuất Google Sheets
```text
Thiết kế tiếp S10 — Báo cáo điểm danh cho ứng dụng mobile FPT Attendance.
Mục đích: Giảng viên xem kết quả điểm danh của một tiết và xuất kết quả sang Google Sheets đã liên kết.
1. BỘ CHỌN: Lớp PRM393 · SE1917, Tiết 05/10/2026 · Slot 1 · 07:00–09:15 · Phòng 101.
2. KẾT QUẢ: Badge “Đã kết thúc”, Sĩ số: 35. Lưới 2x2: Có mặt: 26, Đi muộn: 2, Vắng: 7, Có phép: 0. Tỷ lệ tham gia: 80%.
3. DANH SÁCH: Chi tiết từng sinh viên kèm giờ quét (người vắng hiển thị gạch ngang).
4. CARD XUẤT GOOGLE SHEETS: Tab “12_PRM393_SE1917”, thông báo rõ: “Kết quả sẽ được ghi vào cột F của tab này, thay thế kết quả đã xuất trước đó.” Nút “Xuất sang Google Sheets”.
CÁC FRAME: S10-RESULT, S10-CONFIRM-EXPORT (hộp thoại xác nhận ghi đè cột F), S10-EXPORTING, S10-EXPORT-SUCCESS, S10-EXPORT-ERROR.
```

- **Minh chứng xuất file:** Các ảnh chụp màn hình UI ban đầu được lưu trữ đầy đủ tại thư mục [`assets/stitch/`](../assets/stitch/) và liên kết trực tiếp trên file Figma.

---

## 2. Phản Biện Bằng Trợ Lý AI (VisionCode AI Studio / Gemini 1.5 Pro)

### 2.1. Prompt phản biện nguyên văn (Verbatim Critique Prompt)
```text
You are a Lead Usability Auditor evaluating the generated mobile UI screens for the FPT University Attendance App.
Evaluate the screens against:
1. Jakob Nielsen's 10 Usability Heuristics.
2. WCAG 2.1 AA Accessibility Standards (Contrast >= 4.5:1, Touch Targets >= 48x48 dp).
3. Primary Persona: Instructor Thầy Nguyễn Văn Nam (needs to launch dynamic attendance and sync records in < 30 seconds from lecture podium in Room 101, FPT University HCMC Campus).
Identify at least 5 concrete usability findings tied directly to specific screen IDs. State the exact heuristic violated, severity level, affected screen ID, and concrete UX remedy.
```

### 2.2. Toàn bộ câu trả lời phản biện (5 Phát hiện gắn với màn hình cụ thể)

1. **Phát hiện 1 (Màn hình S02 — Tổng quan giảng dạy):**  
   - *Vi phạm:* **Nielsen Heuristic #7 (Flexibility and efficiency of use)** & **Heuristic #1 (Visibility of system status)**.  
   - *Vấn đề:* Phần đầu trang chứa Banner giới thiệu quá lớn (`#435A58` $\rightarrow$ `#2C3E3D`) cùng cụm thao tác nhanh và bộ lọc học kỳ chiếm tới hơn 55% chiều cao màn hình ($>450\text{ dp}$). Giảng viên khi mở app không thể nhìn thấy ngay tiết học đang mở điểm danh ("Above the fold") mà bắt buộc phải cuộn xuống, làm chậm thời gian thao tác trong 5 phút đầu buổi học.
   - *Khuyến nghị:* Cắt giảm hoàn toàn banner cồng kềnh, đưa card Tiết đang điểm danh (PRM393, Slot 2, Phòng 101) lên vị trí ưu tiên cao nhất ngay trong màn hình đầu, chuyển các bộ lọc phụ vào Bottom Sheet.

2. **Phát hiện 2 (Màn hình S09 — Điểm danh trực tiếp):**  
   - *Vi phạm:* **Nielsen Heuristic #1 (Visibility of system status)** & **Persona Thầy Nam (Chống gian lận)**.  
   - *Vấn đề:* Mã QR ban đầu là ảnh tĩnh không có đồng hồ đếm ngược. Sinh viên có thể chụp lại mã gửi qua Zalo/Messenger cho bạn vắng mặt điểm danh hộ. Ngoài ra, sinh viên ngồi ở cuối giảng đường Phòng 101 khó quét được mã kích thước nhỏ trên điện thoại giảng viên.
   - *Khuyến nghị:* Bắt buộc tích hợp bộ đếm thời hạn bảo mật đếm ngược 45 giây (`00:45`) tự động làm mới mã, bổ sung nút "Làm mới QR" và nút "Phóng to QR" mở overlay toàn màn hình.

3. **Phát hiện 3 (Màn hình S07 — Xếp lịch tiết học):**  
   - *Vi phạm:* **Nielsen Heuristic #5 (Error prevention)** & **Heuristic #9 (Help users recognize, diagnose, and recover from errors)**.  
   - *Vấn đề:* Form cho phép giảng viên chọn phòng và slot nhưng thiếu cơ chế phát hiện trùng lịch giảng dạy của chính giảng viên hoặc trùng phòng học. Nếu xảy ra xung đột, hệ thống không báo trước, dẫn đến việc hai lớp cùng vào Phòng 101 tại Slot 1.
   - *Khuyến nghị:* Thiết lập trạng thái `S07-CONFLICT` hiển thị cảnh báo lỗi cụ thể: "Bạn đã có lịch dạy trong khung giờ này. Chọn slot hoặc ngày khác" kèm cơ chế phục hồi cho phép chọn lại Slot 2 hoặc chuyển sang Phòng 203 ngay trên form mà không bắt nhập lại lớp.

4. **Phát hiện 4 (Màn hình S08 — Chi tiết tiết học):**  
   - *Vi phạm:* **Nielsen Heuristic #5 (Error prevention)**.  
   - *Vấn đề:* Khi tiết học chưa đến giờ (ví dụ 06:50 đối với ca học 07:00), nút "Mở điểm danh" nếu vẫn cho bấm sẽ gây lỗi hệ thống hoặc nếu chỉ khóa nút xám mà không giải thích sẽ khiến giảng viên tưởng ứng dụng bị đơ.
   - *Khuyến nghị:* Chia rõ 2 biến thể: `S08-A` (Chưa đến giờ — khóa nút kèm thông báo giải thích rõ "Bạn có thể mở từ 07:00 đến trước 09:15") và `S08-B` (Đủ điều kiện — nút vàng đất kích hoạt sẵn sàng).

5. **Phát hiện 5 (Màn hình S10 — Báo cáo điểm danh):**  
   - *Vi phạm:* **Nielsen Heuristic #5 (Error prevention)** & **Heuristic #3 (User control and freedom)**.  
   - *Vấn đề:* Thao tác "Xuất sang Google Sheets" nếu bấm trực tiếp sẽ ghi đè ngay vào Cột F của bảng tính khoa. Nếu giảng viên bấm nhầm khi chưa kiểm tra đủ dữ liệu, kết quả cũ sẽ bị xóa mất mà không có cách hoàn tác.
   - *Khuyến nghị:* Thiết kế Dialog xác nhận trung gian `S10-CONFIRM-EXPORT` cảnh báo rõ "Cột F của tab 12_PRM393_SE1917 sẽ được cập nhật. Kết quả cũ sẽ bị thay thế" kèm nút "Hủy" và "Xác nhận xuất".

---

## 3. Ba Vòng Lặp Có Ý Nghĩa & Ghi Nhận Quyết Định (3 Meaningful Iterations & Student Decisions)

### 🔄 Vòng lặp 1: Tối ưu hóa "Above the fold" & Chuyển đổi Điều hướng (Màn hình S02 — Tổng quan)
- **Tên vấn đề cụ thể:** *Header cồng kềnh che khuất hành động chính & Điều hướng Drawer khó thao tác 1 tay (Nielsen Heuristic #7: Flexibility & Efficiency of Use, Heuristic #1: Visibility of System Status)*.
- **Nguyên văn Prompt tinh chỉnh:**
  ```text
  Tinh chỉnh giao diện mobile FPT Attendance đã có. Giữ nghiệp vụ, dữ liệu và nhận diện Lab 1, nhưng nâng chất lượng thiết kế cho trải nghiệm mobile. Bước này CHỈ chỉnh S02 — Tổng quan. Giữ bản cũ để so sánh trước/sau.
  MỤC TIÊU CẢI TIẾN: Giảm phần điều khiển chiếm diện tích đầu trang, để giảng viên nhìn thấy tiết đang điểm danh sớm hơn. Tăng tính nhất quán của màu nút và khoảng cách.
  BỐ CỤC S02 MỚI:
  1. HEADER GỌN: Dòng nhỏ “FPT Attendance”, Tiêu đề “Tổng quan”, Avatar bên phải. Bỏ banner giới thiệu lớn.
  2. NGÀY VÀ THỐNG KÊ: “Thứ Bảy, 03/10/2026”, 2 ô thống kê gọn: “2 tiết hôm nay” và “1 đang điểm danh”.
  3. TIẾT ĐANG ĐIỂM DANH — ƯU TIÊN CAO NHẤT: Card nổi bật viền xanh PRM393 · SE1917 · Slot 2 · 09:30–11:45 · Phòng 101, badge “Đang điểm danh”, nút chính xanh đậm “Xem điểm danh” hiển thị ngay trong viewport đầu.
  4. THAO TÁC QUẢN LÝ: Đặt sau các tiết quan trọng; đưa Bộ lọc học kỳ và switch tự đồng bộ vào Bottom Sheet “Bộ lọc & đồng bộ”.
  5. BOTTOM NAVIGATION: 4 mục: Tổng quan, Lớp học, Lịch dạy, Báo cáo (thay thế navigation drawer).
  RESPONSIVE: Tạo 2 frame S02-360 và S02-412 cùng một thiết kế.
  ```
- **Kết quả AI sinh ra:** Giao diện S02 mới loại bỏ banner 450dp, đưa card PRM393 lên ngay vị trí đầu tiên, tích hợp Bottom Navigation 4 tab.
- **Phản biện UX:** Thầy Nam khi đứng trên bục giảng Phòng 101 chỉ cần mở app là chạm được ngay nút "Xem điểm danh" trong dưới 3 giây mà không cần cuộn trang.
- **Quyết định của sinh viên:** **CHẤP NHẬN (ACCEPTED)**.
- **Lý do căn cứ:** Loại bỏ thao tác cuộn vô ích, hỗ trợ dùng 1 tay (One-thumb navigation) bằng Bottom Bar thay vì Drawer khó với tới góc trên bên trái.
- **Minh chứng Trước / Sau (Evidence Files):**
  - *Ảnh Trước (Before - Banner cồng kềnh, Drawer):* [`assets/stitch/scr02_home_dashboard.png`](../assets/stitch/scr02_home_dashboard.png)
  - *Ảnh Sau (After - Header gọn, Card ưu tiên đầu, Bottom Nav):* [`assets/figma/S02 — Tổng quan giảng dạy.png`](<../assets/figma/S02 — Tổng quan giảng dạy.png>)

---

### 🔄 Vòng lặp 2: Chống gian lận bằng Dynamic QR 45s & Overlay Phóng to (Màn hình S09 — Điểm danh)
- **Tên vấn đề cụ thể:** *Mã QR tĩnh dễ gian lận điểm danh hộ & Sinh viên xa khó quét (Nielsen Heuristic #1: Visibility of System Status, Persona Giảng viên: Chống gian lận)*.
- **Nguyên văn Prompt tinh chỉnh:**
  ```text
  Nâng cấp màn hình điểm danh trực tiếp cho ứng dụng FPT Attendance.
  VẤN ĐỀ: Mã QR tĩnh dễ bị sinh viên chụp ảnh gửi ra ngoài cho bạn vắng mặt điểm danh hộ; sinh viên cuối giảng đường Phòng 101 khó quét.
  YÊU CẦU CẢI TIẾN:
  1. Tích hợp bộ đếm ngược bảo mật 45 giây (00:45) tự động đổi mã hash QR định kỳ.
  2. Bổ sung nút 'Làm mới QR' thủ công và nút 'Phóng to QR' mở Overlay toàn màn hình.
  3. Cập nhật realtime danh sách sinh viên vừa quét điểm danh kèm dấu mốc thời gian chính xác từng giây.
  4. Nút cảnh báo màu đỏ 'Kết thúc điểm danh' mở Dialog xác nhận trước khi chốt vắng.
  ```
- **Kết quả AI sinh ra:** Khung QR động tích hợp đồng hồ đếm lùi `00:45`, 2 nút điều khiển làm mới/phóng to, feed sinh viên quét realtime.
- **Phản biện UX:** Đảm bảo chỉ sinh viên đang có mặt thực tế tại phòng mới kịp quét trước khi mã xoay vòng, giảm thiểu tối đa gian lận điểm danh hộ.
- **Quyết định của sinh viên:** **CHẤP NHẬN (ACCEPTED)**.
- **Lý do căn cứ:** Phục vụ trực tiếp Persona Thầy Nam, loại bỏ hoàn toàn lỗ hổng điểm danh hộ mà không cần sinh viên phải xếp hàng lên bục giảng.
- **Minh chứng Trước / Sau (Evidence Files):**
  - *Ảnh Trước (Before - QR tĩnh, không đếm ngược):* [`assets/stitch/scr03_session_detail.png`](../assets/stitch/scr03_session_detail.png)
  - *Ảnh Sau (After - Dynamic QR 45s, đếm ngược, nút phóng to):* [`assets/figma/S09 — Điểm danh trực tiếp.png`](<../assets/figma/S09 — Điểm danh trực tiếp.png>)

---

### 🔄 Vòng lặp 3: Kiểm soát Xung đột Phòng học & Cơ chế Phục hồi (Màn hình S07 — Xếp lịch & Flow 3)
- **Tên vấn đề cụ thể:** *Thiếu ngăn chặn lỗi trùng lịch phòng học & Ngõ cụt thao tác (Nielsen Heuristic #5: Error Prevention, Heuristic #9: Help users recognize, diagnose, and recover from errors)*.
- **Nguyên văn Prompt tinh chỉnh:**
  ```text
  Thiết kế cơ chế phát hiện và phục hồi xung đột lịch học cho màn hình S07 — Xếp lịch tiết học.
  NGHIỆP VỤ: Khi giảng viên chọn lớp PRM393, ngày 05/10/2026, Slot 1 tại Phòng 101 nhưng phòng này đã có lớp khác đăng ký:
  1. Hiển thị trạng thái cảnh báo S07-CONFLICT với thông báo lỗi cụ thể: 'Bạn đã có lịch dạy trong khung giờ này. Chọn slot hoặc ngày khác.'
  2. Không được xóa trắng form khiến người dùng phải nhập lại từ đầu.
  3. Cung cấp gợi ý phòng học số thay thế (Phòng 203) hoặc chọn Slot 2 để phục hồi ngay lập tức.
  ```
- **Kết quả AI sinh ra:** AI ban đầu đề xuất tự động đổi sang slot kế tiếp và tự động lưu mà không hỏi giảng viên.
- **Phản biện UX:** Vi phạm nghiêm trọng **Nielsen Heuristic #3 (User Control and Freedom)** vì tước đoạt quyền quyết định thời gian dạy của giảng viên.
- **Quyết định của sinh viên:** **CHỈNH SỬA & CHẤP NHẬN (MODIFIED)**.
- **Lý do căn cứ:** Bác bỏ việc AI tự ý lưu lịch; thay vào đó hiển thị banner cảnh báo đỏ rõ ràng, giữ nguyên toàn bộ thông tin môn học và đưa ra lựa chọn Phòng 203 / Slot khác để giảng viên tự tay chọn và bấm lưu.
- **Minh chứng Trước / Sau (Evidence Files):**
  - *Ảnh Trước (Before - Lịch dạy đơn thuần, không có form kiểm tra lỗi):* [`assets/stitch/scr05_schedule_calendar.png`](../assets/stitch/scr05_schedule_calendar.png)
  - *Ảnh Sau (After - Form xếp lịch có nhánh xung đột S07-CONFLICT & gợi ý phục hồi):* [`assets/figma/S07 — Xếp lịch tiết học.png`](<../assets/figma/S07 — Xếp lịch tiết học.png>)

---

## 4. Khai Báo Sử Dụng Công Cụ AI (AI Tools Disclosure Table)

| Tên công cụ | Nhà cung cấp / Phiên bản | Mục đích sử dụng | Mức độ can thiệp của sinh viên (Human-in-the-loop) |
| :--- | :--- | :--- | :--- |
| **Google Stitch** | Google Labs (Project #4183462632766005206) | Sinh bộ UI Mobile ban đầu (S01 đến S10) từ prompt tiếng Việt và hệ thống design tokens | Viết prompt chi tiết từ Lab 1 Desktop, điều chỉnh bố cục 1 cột và xuất ảnh mẫu |
| **VisionCode AI Studio** | VisionCode (`visioncode-1.ai.studio`) | Phản biện UX theo 10 Usability Heuristics của Nielsen & WCAG 2.1 AA | Đưa ra tiêu chí persona giảng viên FPT, phản biện các đề xuất và quyết định giải pháp |
| **Google Gemini 1.5 Pro** | Google DeepMind | Hỗ trợ phân tích Information Architecture, xây dựng kịch bản User Flow và tổng hợp tài liệu Handoff | Rà soát cấu trúc nghiệp vụ, kiểm tra đối chiếu dữ liệu trường FPT và quy tắc phòng học |
| **Figma Auto Layout Assistant** | Figma Inc. | Tối ưu hóa các thông số Auto Layout padding, gap và cấu trúc component variants | Tự thiết lập toàn bộ tokens, đặt tên component và nối dây tương tác prototype |
