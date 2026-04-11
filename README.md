# 🏥 Hệ Thống Đặt Lịch Khám Bệnh & Quản Lý Bệnh Viện (Web & Mobile)

![Hospital Management System](https://img.shields.io/badge/Platform-Web_%7C_Mobile-blue.svg)
![Backend](https://img.shields.io/badge/Backend-.NET_Core_MVC-512BD4.svg)
![Frontend](https://img.shields.io/badge/Mobile-Flutter-02569B.svg)
![Database](https://img.shields.io/badge/Database-SQL_Server-CC2927.svg)

# 📁 Lịch sử phát triển dự án
Dự án được phát triển từ demo PHP của nhóm FourRock: Trần Quang Hiển, Lê Trần Kim Hưng, Nguyễn Hoàng Anh.
Link tham khảo dự án PHP của nhóm FourRock: https://github.com/hienquangtranht1/DoAnCoSo-DAT-LICH-KHAM-BENH-DEMO.

Một giải pháp toàn diện hỗ trợ đặt lịch khám bệnh trực tuyến, quản lý phòng khám và tương tác giữa Bệnh nhân - Bác sĩ - Nhân viên chăm sóc khách hàng. Hệ thống bao gồm **Web Admin Portal** (dành cho quản lý, bác sĩ, CSKH) và **Mobile Application** (dành cho bệnh nhân).

---

## 🚀 Tính năng nổi bật

### 📱 Dành cho Bệnh nhân (Mobile App / Web)
* **Đặt lịch thông minh:** Chọn chuyên khoa, bác sĩ, ngày giờ khám linh hoạt.
* **Thanh toán trực tuyến:** Tích hợp cổng thanh toán **VNPay** và **Ví MoMo**.
* **Tư vấn trực tuyến:** Chat trực tiếp (Real-time) với CSKH hoặc Bác sĩ.
* **Hồ sơ bệnh án số:** Tra cứu lịch sử khám bệnh, đơn thuốc, và kết quả chẩn đoán.
* **Nhắc nhở lịch khám:** Nhận thông báo tự động (Push Notifications) khi sắp đến giờ khám.
* **Chatbot AI:** Hỗ trợ giải đáp các câu hỏi thường gặp về y tế.

### 👨‍⚕️ Dành cho Bác sĩ (Web Portal)
* **Quản lý lịch làm việc:** Xem danh sách bệnh nhân và lịch hẹn trong ngày/tuần.
* **Cập nhật hồ sơ:** Ghi nhận triệu chứng, chẩn đoán và cập nhật bệnh án trực tiếp.
* **Tương tác bệnh nhân:** Chat trực tuyến với bệnh nhân để theo dõi tình hình sau khám.

### 💼 Dành cho Admin / Nhân viên CSKH (Web Portal)
* **Dashboard Thống kê:** Theo dõi doanh thu, số lượng lịch hẹn, đánh giá chất lượng.
* **Quản lý Hệ thống:** Quản lý danh sách Bác sĩ, Chuyên khoa, Bệnh nhân, và Lịch làm việc.
* **Quản lý Nội dung (CMS):** Đăng tải và quản lý các bài viết tin tức, cẩm nang y tế (Blog).
* **Chăm sóc khách hàng:** Tiếp nhận và xử lý yêu cầu, chat hỗ trợ trực tiếp.

---

## 🛠 Công nghệ sử dụng

### Backend & Web Portal (`/BookinhMVC`)
* **Framework:** ASP.NET Core MVC (.NET 8)
* **ORM:** Entity Framework Core
* **Cơ sở dữ liệu:** Microsoft SQL Server
* **Real-time:** SignalR (Xử lý Chat, Booking, Thông báo)
* **Thanh toán:** Tích hợp API VNPay & MoMo
* **Bảo mật:** Authentication & Authorization (Phân quyền Admin, Doctor, User, CSKH)

### Mobile Application (`/mobile/Booking`)
* **Framework:** Flutter (Dart)
* **Kết nối API:** Giao tiếp với Backend qua RESTful API
* **Real-time:** Tích hợp thư viện SignalR client cho Flutter để nhận tin nhắn/thông báo.
* **State Management:** (Tùy thuộc kiến trúc dự án: Provider / GetX / Bloc...)

---

### ⚙️ Hướng dẫn cài đặt & Chạy dự án
1. Cài đặt Backend (Web Portal)
Yêu cầu: Đã cài đặt .NET SDK (phiên bản phù hợp), SQL Server và Visual Studio / VS Code.
- Clone dự án về máy:
git clone <url-repo-của-bạn>
cd WEB_MOBILE_QLBV-main/BookinhMVC
- Mở file appsettings.json, cập nhật chuỗi kết nối cơ sở dữ liệu (DefaultConnection) cho phù hợp với SQL Server của bạn.
- Chạy Migration để tạo Database: dotnet ef database update.
-  Khởi chạy ứng dụng: dotnet run. "Web sẽ chạy tại http://localhost:<port> hoặc https://localhost:<port>".
2. Cài đặt Mobile App (Flutter)
Yêu cầu: Đã cài đặt Flutter SDK và Android Studio / Xcode.
- Di chuyển vào thư mục Mobile: cd mobile/Booking.
- Tải các dependencies: flutter pub get.
- Cấu hình đường dẫn API: 
Mở file lib/services/api_service.dart (hoặc nơi chứa cấu hình API) và thay đổi Base URL trỏ về địa chỉ IP của Backend đang chạy.
(Lưu ý: Nếu dùng máy ảo Android, sử dụng 10.0.2.2 thay cho localhost)
- Chạy ứng dụng trên thiết bị ảo hoặc điện thoại: flutter run.
🔑 Môi trường & API Keys (Lưu ý)
Các cấu hình liên quan đến cổng thanh toán (VNPay, MoMo) hiện đang đặt trong appsettings.json. Vui lòng thay thế bằng thông tin (Merchant ID, Secret Key) từ tài khoản Sandbox/Production của bạn để có thể thực hiện giao dịch thử nghiệm.
✍️ Tác giả / Đóng góp
Dự án được phát triển bởi [Nhóm Four Rocks- Trần Quang Hiển(Dev Full Stack Mobile, Leader); Lê Trần Kim Hưng(Backend Web); Nguyễn Hoàng Anh(Frontend Web)].
Nếu bạn có bất kỳ thắc mắc nào hoặc muốn đóng góp cho dự án, vui lòng tạo Issues hoặc gửi Pull Request.

---
## 📁 Cấu trúc dự án

```text
WEB_MOBILE_QLBV/
├── BookinhMVC/             # Mã nguồn Backend & Web Portal (ASP.NET Core MVC)
│   ├── Controllers/        # Xử lý logic API và Web (Admin, Chat, Payment...)
│   ├── Models/             # Chứa các Entity Models (Bệnh nhân, Bác sĩ, Lịch hẹn...)
│   ├── Views/              # Giao diện cho Admin, Bác sĩ, CSKH
│   ├── Hubs/               # Cấu hình SignalR (ChatHub, BookingHub)
│   ├── Services/           # Logic tích hợp (VNPay, MoMo, Reminder...)
│   └── appsettings.json    # Cấu hình chuỗi kết nối DB và API Keys
└── mobile/Booking/         # Mã nguồn Mobile App (Flutter)
    ├── lib/                
    │   ├── models/         # Data models mapping với Backend API
    │   ├── screens/        # Giao diện ứng dụng (Home, Booking, Chat, Profile...)
    │   ├── services/       # Xử lý API calls và SignalR
    │   └── widgets/        # Component UI dùng chung
    └── pubspec.yaml        # Quản lý dependencies

