# Katalon Recorder – Nguyễn Huy Bảo (23130022) – CN10, CN11, CN12

| File (Test Suite) | Chức năng | Số TC | Kết quả |
|---|---|:-:|:-:|
| `23130022_NguyenHuyBao_ChucNang10_KatalonRecorder.html` | CN10 – Star, Important, Snooze & Bulk Actions | 25 | 23 Pass / 2 Fail |
| `23130022_NguyenHuyBao_ChucNang11_KatalonRecorder.html` | CN11 – Filters & Rules | 25 | 22 Pass / 3 Fail |
| `23130022_NguyenHuyBao_ChucNang12_KatalonRecorder.html` | CN12 – Spam, Trash & Recovery (+1 TC SETUP tạo dữ liệu) | 26 | 24 Pass / 2 Fail |

Định dạng: Katalon Recorder Test Suite (Selenese HTML). Mỗi suite chạy độc lập được.
Test Case chi tiết: `individual_docs/Group07_23130022_NguyenHuyBao.xlsx`.
Log/Report: `Test Report - Group 07/Test Report - NguyenHuyBao - CNxx - (ngày).html`.
Ảnh minh chứng: `Envidence - Group 07/HuyBao/`.

## Chuẩn bị trước khi chạy
1. Chrome + extension **Katalon Recorder**; đăng nhập sẵn Gmail (giao diện tiếng Việt hoặc tiếng Anh).
2. Tạo sẵn nhãn **Work** (CN10 – FUN_12) và **Ưu tiên** (CN11 – FUN_03, FUN_04, FUN_08).
3. Sửa lệnh `store … MY_EMAIL` thành địa chỉ Gmail đang đăng nhập (các TC FUN của CN11 và `TC_GMAIL_12_SETUP`).
   CN11 – FUN_08 cần `ATTACH_FILE` = đường dẫn 1 file `.txt` nhỏ.
4. CN10: 2 email đầu Inbox chưa đọc, email đầu chưa Quan trọng, Inbox > 50 thư.
5. CN12 – NAV_01: menu trái đang thu gọn (thấy mục "Hiện thêm").

## Chạy
Katalon Recorder → **Open test suite** → chọn file `.html` → **Play suite**.
Sau mỗi lần sửa file, phải mở lại suite trong Katalon Recorder.

- **CN11:** mỗi TC tự xóa bộ lọc vừa tạo.
- **CN12:** chạy đúng thứ tự (SETUP gửi 11 email `KR12-*` cho chính mình, các TC sau dùng lại).
  4 TC cuối (FUN_10, VAL_03, FUN_09, VAL_02) **xóa vĩnh viễn toàn bộ Thư rác và Thùng rác** – chỉ chạy trên tài khoản test.

### Các bước làm tay (script tạm dừng và in hướng dẫn bằng `echo`)
| TC | Bước làm tay | Lý do |
|---|---|---|
| CN10 – NAV_03 | Ngắt mạng / bật lại mạng | Katalon Recorder không điều khiển được mạng |
| CN11 – FUN_08 | Đính kèm tệp | Katalon Recorder không tải tệp lên được |
| CN12 – FUN_10, FUN_09 | Bấm **OK** trong hộp xác nhận xóa vĩnh viễn (có 10 giây) | Gmail bỏ qua click/Enter giả lập ở hộp thoại này |

## Kỹ thuật dùng trong script
- **Tải lại trang bằng URL có tham số riêng** (`?kr=1`, `?kr=2`…) thay cho lệnh `refresh` (Katalon Recorder bản đang dùng không mở được suite có `refresh`, `if/else`, `storeElementPresent`).
- **Lọc phần tử đang hiển thị:** Gmail giữ DOM ẩn của màn hình cũ, nên locator thêm
  `[not(ancestor::*[contains(@style,'display: none')])]`.
- **Gmail tách dấu tiếng Việt** (ví dụ "Báo cáo spam" có `a` + dấu riêng) → locator so phần chữ không dấu
  (`starts-with(@aria-label,'X')`, `contains(.,'ng r')`…), chạy được cả giao diện Anh/Việt.
- **Soạn thư toàn màn hình** qua URL `?view=cm&fs=1&to=${MY_EMAIL}` – ổn định hơn bấm nút Soạn thư.
- **Mẹo nút 3 chấm:** bấm mở/đóng nút "Tùy chọn khác" trước thao tác toolbar để toolbar sẵn sàng.
- **Chọn mục trong menu:** gõ chữ vào ô lọc của menu rồi `${KEY_ENTER}` (Gmail bỏ qua click chuột vào mục menu).
- Kiểm tra Spam/Trash bằng thư mục `#spam`, `#trash` thay cho tìm kiếm `in:spam` (kết quả tìm kiếm cập nhật chậm).
- Không dùng id dạng `:2r`, `:nc` (Gmail tự sinh, thay đổi giữa các lần tải).
