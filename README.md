# 📧 AUTOMATION TESTING PROJECT — GOOGLE GMAIL (GROUP 07)

Dự án tích hợp \& thực thi kịch bản kiểm thử tự động (Automation Test Suite) cho giao diện web **Google Gmail** (`https://mail.google.com/`), thuộc môn học **Kiểm thử Phần mềm (Software Testing)**.

\---

## 👥 PHÂN CÔNG NHIỆM VỤ THÀNH VIÊN

|STT|Thành viên|MSSV|Vai trò \& Nhóm Chức năng Phụ trách|Công cụ \& Script|
|:-:|-|:-:|-|:-:|
|1|Nguyễn Huy Bảo|23130022|**Cấu hình \& Giao diện:** Tùy chỉnh Hộp thư, Chữ ký email, Trả lời tự động (CN 1, 2, 3)|Katalon Recorder (`.side`)|
|2|Nguyễn Khoa Đăng|23130041|**Soạn thảo \& Thư nháp:** Soạn/Gửi thư, Đính kèm \& Định dạng, Thư nháp (CN 4, 5, 6)|Katalon Recorder (`.side`)|
|3|Trương Trọng Nhân|23130217|**Phản hồi \& Tìm kiếm:** Reply/Forward, Tìm kiếm nâng cao, Quản lý Nhãn (CN 7, 8, 9)|Selenium Java (`.java`) / Katalon|
|4|Trương Phúc Nền|23130203|**Tổ chức Hộp thư \& Thùng rác:** Star/Snooze, Bộ lọc tự động, Spam \& Thùng rác (CN 10, 11, 12)|Katalon Recorder (`.side`)|

\---

## 📁 CẤU TRÚC REPOSITORY TÍCH HỢP

Repository được cấu trúc để chứa đồng thời các kịch bản kiểm thử dạng `.side` (Katalon Recorder / Selenium IDE) và các mã nguồn `.java` (Selenium WebDriver), bảo đảm các thành viên có thể phát triển độc lập và tích hợp vào một dự án chung.

```text
Group07\\\_SoftwareTesting\\\_Gmail/
├── README.md                           # Tài liệu hướng dẫn cài đặt \\\& chạy project
├── Group07\\\_GmailProject.xlsx           # File Excel tổng hợp toàn bộ Test Case của nhóm
├── pom.xml                             # Cấu hình Maven (dành cho Selenium Java)
│
├── Automation Testing Project - Group 07/                            # Thư mục chứa toàn bộ Automation Scripts
│   ├── katalon\\\_side/           # Chứa các file kịch bản .side / .json
│   │   ├── MemberX\\\_Feature.side	# Thành viên trong nhóm\\\_Chức năng test
│   │   ├── MemberX\\\_Feature.side
│   │   └── MemberX\\\_Feature.side
│   │
│   └── java\\\_selenium/          # Chứa mã nguồn Selenium Java (.java)
│       └── MemberX\\\_Feature.java   
│
├── Test Report - Group 07/                            # Thư mục lưu báo cáo kết quả kiểm thử
│   ├── test-report.html     # Báo cáo kết quả tổng hợp Test Suite
│   └── test-execution-log.txt          # File Log thực thi
│
└── Envidence - Group 07/                        # Ảnh chụp màn hình minh chứng thực thi
    ├── execution\\\_katalon.png
    └── execution\\\_java.png
```

\---

## 🛠️ YÊU CẦU MÔI TRƯỜNG \& PHẦN MỀM

1. **Trình duyệt Web:** Google Chrome (phiên bản mới nhất).
2. **Katalon Recorder Extension:** Cài đặt trên Chrome Web Store (dùng cho các file `.side`).
3. **Môi trường Java (cho Selenium Java):**

   * JDK 17 trở lên.
   * Apache Maven 3.x.
   * IDE: VS Code / Eclipse / IntelliJ IDEA.

\---

## 🚀 HƯỚNG DẪN CHẠY TEST SUITE

### Cách 1: Chạy kịch bản `.side` bằng Katalon Recorder (Khuyên dùng)

1. Mở trình duyệt Google Chrome và khởi động tiện ích **Katalon Recorder**.
2. Đăng nhập sẵn tài khoản Gmail kiểm thử trên trình duyệt.
3. Trong giao diện Katalon Recorder, chọn **Open Test Suite / Open Project** $\\rightarrow$ Trỏ tới thư mục `./scripts/katalon\\\_side\\\_scripts/` và chọn file `.side` cần chạy.
4. Chọn Test Suite tổng và nhấn **Play Test Suite**.

### Cách 2: Chạy kịch bản Selenium Java (`.java`)

1. Mở dự án trong IDE (VS Code / IntelliJ).
2. Tải các thư viện phụ thuộc bằng Maven:

```bash
   mvn clean install
   ```

3. Mở file test (ví dụ: `Member2\\\_ComposeDraft.java`) trong thư mục `./scripts/java\\\_selenium\\\_scripts/` và chọn **Run Test** (hoặc dùng JUnit / TestNG Runner).

\---

## 📊 BÁO CÁO KẾT QUẢ KIỂM THỬ (TEST REPORT)

Sau khi hoàn tất thực thi toàn bộ Test Suite, báo cáo kết quả tổng hợp sẽ được xuất và lưu trữ tại thư mục `reports/` theo quy chuẩn đặt tên:

* **Tên file báo cáo chung:** `Test Report - Group 07.html`
* **Cách xuất báo cáo từ Katalon Recorder:**

  1. Sau khi chạy xong Test Suite, chuyển sang tab **Log / Test Execution Summary**.
  2. Chọn **Export Logs** $\\rightarrow$ **Export HTML Report**.
  3. Đổi tên file thành `Test Report - Group 07.html` và lưu vào thư mục `reports/`.

\---

## 📝 QUY ĐỊNH COMMIT \& TÍCH HỢP CODE (GIT WORKFLOW)

1. Mỗi thành viên làm việc trên branch cá nhân (`feature/member-name`).
2. Đưa file script cá nhân vào đúng thư mục (`katalon\\\_side\\\_scripts/` hoặc `java\\\_selenium\\\_scripts/`).
3. Tạo Pull Request (PR) về branch `dev` và thông báo cho trưởng nhóm review trước khi Merge.

