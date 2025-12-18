# 💬 LAN Chat Application - Nhóm 19

> **Môn học:** Lập trình mạng (Network Programming)  
> **Giảng viên hướng dẫn:** Bùi Dương Thế  

---

## 👥 Thành viên nhóm 19

| STT | Họ và Tên |
|:---:|:---:|
| 1 | **Phạm Gia Thịnh** |
| 2 | **Trần Trung Chiến** |
| 3 | **Nguyễn Hoàng Linh Tú** |

---

## 📖 Giới thiệu đề tài

### 1. Tên đề tài
**Xây dựng ứng dụng trò chuyện trực tuyến (Chat App) qua mạng LAN sử dụng kiến trúc Client-Server.**

### 2. Lý do chọn đề tài
Trong kỷ nguyên số, nhu cầu giao tiếp thời gian thực (Real-time communication) là cốt lõi của mọi hệ thống mạng. Chúng tôi chọn đề tài này vì:
* **Tính nền tảng:** Ứng dụng Chat là bài toán kinh điển giúp hiểu sâu sắc nhất về mô hình TCP/IP, cách thức hoạt động của Socket và luồng dữ liệu.
* **Thách thức kỹ thuật:** Đề tài yêu cầu xử lý đồng thời (Concurrency) để nhiều người dùng có thể giao tiếp cùng lúc, giúp nhóm rèn luyện kỹ năng xử lý Đa luồng (Multi-threading).
* **Tính thực tiễn:** Có khả năng mở rộng để ứng dụng trong các hệ thống mạng nội bộ doanh nghiệp, trường học.

---

## 🛠 Công nghệ sử dụng

Dự án được phát triển hoàn toàn bằng **Python 3.x** với các thư viện tiêu chuẩn, đảm bảo tính ổn định và dễ dàng triển khai.

### Backend (Server)
* **Ngôn ngữ:** Python.
* **Thư viện Socket:** Sử dụng `socket` (họ giao thức `AF_INET`, kiểu `SOCK_STREAM` cho TCP) để đảm bảo độ tin cậy của tin nhắn.
* **Xử lý đa luồng:** Thư viện `threading` để quản lý các kết nối Client độc lập, tránh hiện tượng nghẽn mạng (blocking).

### Frontend (Client)
* **Giao diện người dùng (GUI):** Thư viện `Tkinter` để xây dựng giao diện thân thiện, trực quan.
* **Cơ chế hoạt động:** Client duy trì 2 luồng song song:
    1.  Luồng chính để vẽ giao diện và gửi tin.
    2.  Luồng phụ để liên tục lắng nghe tin nhắn đến từ Server.

---

## 🚀 Tính năng hệ thống

### Phía Server (Máy chủ)
- [x] Khởi tạo Socket, bind IP và Port.
- [x] Chấp nhận kết nối từ nhiều Client cùng lúc.
- [x] Quản lý danh sách người dùng đang online.
- [x] **Broadcast:** Nhận tin từ một người và gửi lại cho tất cả người khác.
- [x] Ghi nhận log hoạt động (Người dùng kết nối/ngắt kết nối).

### Phía Client (Máy khách)
- [x] Màn hình đăng nhập (Nhập IP Server và Nickname).
- [x] Gửi tin nhắn văn bản (Text).
- [x] Hiển thị lịch sử chat thời gian thực.
- [x] Thông báo khi có người mới tham gia hoặc rời phòng chat.

---

## 📂 Cấu trúc thư mục

ChatApp/
├── Client/
│   ├── client_main.py      # File chạy chính của Client
│   ├── client_ui.py        # Xử lý giao diện đồ họa
│   └── client_logic.py     # Xử lý kết nối Socket phía Client
├── Server/
│   ├── server_main.py      # File chạy chính của Server
│   └── connection_handler.py # Xử lý các luồng kết nối
├── README.md               # Hướng dẫn sử dụng
└── requirements.txt        # Các thư viện cần cài đặt

---

## ⚙️ Hướng dẫn cài đặt và chạy

### 1. Yêu cầu hệ thống

* Cài đặt Python 3.8 trở lên.
* Hệ điều hành: Windows/macOS/Linux.

### 2. Các bước thực hiện

**Bước 1: Clone dự án**

```bash
git clone https://github.com/gthinh29/Laptrinhmang-Nhom19-ChatApp.git
cd ChatApp

```

**Bước 2: Cài đặt thư viện**
Mở terminal và chạy lệnh:

```bash
pip install -r requirements.txt

```

**Bước 3: Khởi chạy Server**
Mở terminal và chạy lệnh:

```bash
python Server/server_main.py

```

**Bước 4: Khởi chạy Client**
Mở một terminal mới khác và chạy:

```bash
python Client/client_main.py

```

---

## 📝 Cam kết và Đóng góp

Dự án được thực hiện bởi sự đóng góp công bằng của cả 3 thành viên Nhóm 19. Lịch sử commit code được lưu trữ đầy đủ trên Git Repository này.
