# 📧 BÀI TẬP LỚN: PHÂN TÍCH & THIẾT KẾ TEST CASE TỰ ĐỘNG GMAIL (GROUP 07)

## 📌 GIỚI THIỆU DỰ ÁN
* **Môn học:** Kiểm thử Phần mềm (Software Testing)
* **Đối tượng kiểm thử:** Hệ thống Google Gmail (`https://mail.google.com/`)
* **Phạm vi:** Phân tích, thiết kế Test Case và Lập kế hoạch Automation Test cho 12 chức năng cơ bản của Gmail.

---

## 👥 PHÂN CÔNG NHIỆM VỤ THÀNH VIÊN

### 👤 Thành viên 1: Cá nhân hóa Giao diện & Cấu hình Hệ thống (Settings)
*(Chuyên sâu vào phần Cài đặt của Gmail — hoàn toàn không đụng chạm tới đăng nhập/đăng xuất)*
* **Chức năng 1:** Tùy chỉnh Bố cục Hộp thư & Khung đọc thư (Inbox Layout, Density & Reading Pane)
* **Chức năng 2:** Quản lý Chữ ký email & Cài đặt chung (Signatures & General Settings)
* **Chức năng 3:** Thiết lập Trả lời tự động & Mẫu thư có sẵn (Vacation Responder & Templates)

---

### 👤 Thành viên 2: Soạn thảo, Đính kèm cục bộ & Quản lý Thư nháp
*(Kiểm soát toàn bộ vòng đời tạo mới một email)*
* **Chức năng 4:** Soạn và Gửi thư đa luồng (Compose & Send Email)
* **Chức năng 5:** Đính kèm tệp từ máy tính & Định dạng văn bản (Local Attachments & Formatting)
* **Chức năng 6:** Quản lý Thư nháp tự động (Drafts Lifecycle)

---

### 👤 Thành viên 3: Phản hồi thư, Tìm kiếm & Quản lý Nhãn (Labels)
*(Tập trung vào luồng xử lý, truy xuất và phân loại thư)*
* **Chức năng 7:** Trả lời, Trả lời tất cả & Chuyển tiếp (Reply, Reply All & Forward)
* **Chức năng 8:** Tìm kiếm cơ bản & Bộ lọc Tìm kiếm nâng cao (Basic & Advanced Search)
* **Chức năng 9:** Quản lý Nhãn cá nhân & Phân loại thư (Labels Management)

---

### 👤 Thành viên 4: Tổ chức Hộp thư, Bộ lọc tự động & Thùng rác
*(Tập trung vào các thao tác hàng loạt và tự động hóa quy tắc hộp thư)*
* **Chức năng 10:** Đánh dấu ưu tiên, Tạm ẩn & Thao tác hàng loạt (Star, Snooze & Bulk Actions)
* **Chức năng 11:** Quản lý Bộ lọc thư tự động (Filters & Rules)
* **Chức năng 12:** Xử lý Thư rác, Thùng rác & Khôi phục dữ liệu (Spam, Trash & Recovery)

---

## 📂 CẤU TRÚC REPOSITORY
```text
Group07_SoftwareTesting_Gmail/
├── README.md                          # Tài liệu giới thiệu & Phân công dự án
├── Group07_GmailProject.xlsx          # Tài liệu Test Case tổng hợp của cả nhóm
└── individual_docs/                   # Bài nộp cá nhân theo tuần
    ├── Group07_MaSV1_HoTen1.xlsx
    ├── Group07_MaSV2_HoTen2.xlsx      # (Chức năng 4, 5, 6)
    ├── Group07_MaSV3_HoTen3.xlsx
    └── Group07_MaSV4_HoTen4.xlsx
