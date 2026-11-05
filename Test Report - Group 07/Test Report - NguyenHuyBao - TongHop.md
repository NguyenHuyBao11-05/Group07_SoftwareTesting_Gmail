# Test Report – Nguyễn Huy Bảo (23130022) – CN10, CN11, CN12

Website: Google Gmail (`https://mail.google.com/`) · Công cụ: Katalon Recorder trên Chrome 156 (Windows 10)

## Tổng hợp

| Test Suite | Ngày chạy | Thời gian chạy | Tổng TC | Pass | Fail | Skipped | Report |
|---|---|:-:|:-:|:-:|:-:|:-:|---|
| CN10 – Star, Important, Snooze & Bulk | 05/11/2026 00:23 | 3,4 phút | 25 | 23 | 2 | 0 | `Test Report - NguyenHuyBao - CN10 - (5-11-2026).html` |
| CN11 – Filters & Rules | 05/11/2026 20:52 | 19,9 phút | 25 | 22 | 3 | 0 | `Test Report - NguyenHuyBao - CN11 - (5-11-2026).html` |
| CN12 – Spam, Trash & Recovery | 06/11/2026 00:47 | 15,4 phút | 26* | 24 | 2 | 0 | `Test Report - NguyenHuyBao - CN12 - (6-11-2026).html` |
| **Tổng** | | **38,7 phút** | **76** | **69** | **7** | **0** | |

\* Gồm 1 TC `TC_GMAIL_12_SETUP` tạo dữ liệu (25 TC kiểm thử + 1 SETUP).

## Danh sách Test Case thất bại

| TC | Nội dung | Nguyên nhân | Minh chứng |
|---|---|---|---|
| TC_GMAIL_10_NAV_03 | Mất mạng khi Bulk Action | Gmail vẫn xóa được thư trên giao diện, không hiện thông báo mất kết nối | `TC_GMAIL_10_NAV_03_1..2.png` |
| TC_GMAIL_10_NAV_04 | Chọn tất cả hội thoại khớp tìm kiếm | Không có banner/link "Chọn tất cả N cuộc hội thoại" sau khi tích checkbox tổng | `TC_GMAIL_10_NAV_04_1..2.png` |
| TC_GMAIL_11_VAL_01 | Tạo bộ lọc khi bỏ trống điều kiện | Nút "Tạo bộ lọc" mờ nhưng vẫn nhận click, chuyển sang bước chọn hành động | `TC_GMAIL_11_VAL_01_1..2.png` |
| TC_GMAIL_11_VAL_03 | Size là ký tự chữ | Ô Kích thước nhận "abc", không báo lỗi; điều kiện bị bỏ âm thầm | `TC_GMAIL_11_VAL_03_1..5.png` |
| TC_GMAIL_11_VAL_04 | Size = 0 và số âm | Ô Kích thước nhận -1, không báo lỗi; vẫn tạo bộ lọc | `TC_GMAIL_11_VAL_04_1..6.png` |
| TC_GMAIL_12_VIS_02 | Giao diện Thùng rác | Thanh công cụ không có nút "Chuyển tới Hộp thư đến" | `TC_GMAIL_12_VIS_02_1..2.png` |
| TC_GMAIL_12_FUN_06 | Khôi phục từ Trash về Inbox (Move to Inbox) | Cùng nguyên nhân VIS_02; khôi phục vẫn làm được qua "Chuyển tới" (FUN_07 Pass) | `TC_GMAIL_12_FUN_06_1..3.png` |

Ảnh minh chứng: `Envidence - Group 07/HuyBao/` (kèm `CN10/11/12_TestSuite_KetQua.png` – ảnh kết quả cả suite trên Katalon Recorder).

## Độ ổn định (Flaky Test)
Các TC sau từng Fail ở lần chạy đầu và Pass sau khi sửa script – nguyên nhân do script/thời gian chờ, không phải lỗi Gmail:
- CN11 – các TC soạn thư (FUN_01, FUN_05, FUN_08, FUN_09): cửa sổ soạn thư mở chậm/bị thu nhỏ → đổi sang URL soạn thư toàn màn hình.
- CN11 – FUN_05: bộ lọc chưa kịp lưu khi chuyển trang → thêm `pause 4000`.
- CN12 – FUN_02: tìm `in:spam` cập nhật chậm → kiểm tra trong thư mục `#spam`.
- CN12 – các TC thao tác toolbar: toolbar chưa sẵn sàng → bấm mở/đóng nút 3 chấm trước, thêm `waitForElementPresent`.

Các TC Fail ở bảng trên đã chạy lại và đối chiếu thủ công trên Gmail: kết quả lặp lại → không phải flaky.

## Ghi chú
- Bước làm tay: CN10 NAV_03 (ngắt/bật mạng), CN11 FUN_08 (đính kèm tệp), CN12 FUN_10/FUN_09 (bấm OK hộp xác nhận xóa vĩnh viễn).
- Kết quả chi tiết từng TC (Actual Result, Pass/Fail, Ngày test, Ghi chú): `individual_docs/Group07_23130022_NguyenHuyBao.xlsx`.
