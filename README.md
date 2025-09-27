# simple_auth

# Cookie Authentication API

## 1. Giới thiệu
Dự án minh họa cơ chế **xác thực bằng Cookie** trong Node.js + Express.  
Bao gồm 3 API chính:
- `POST /login` → Đăng nhập & tạo cookie
- `GET /profile` → Truy cập trang bảo vệ (yêu cầu cookie)
- `POST /logout` → Đăng xuất & xóa cookie

---

## 2. Cách chạy dự án

```bash
# Cài đặt thư viện
npm install

# Khởi động server
node cookie_auth.js

## 3. Kiểm thử với Postman

Tất cả ảnh chụp kết quả test được lưu tại thư mục:

public/results

## 3.1. Đăng nhập (POST /login)

URL: http://localhost:3001/login
Method: POST
Body: (JSON)

{
  "username": "admin",
  "password": "12345"
}


📸 Kết quả thành công:


📸 Kết quả sai tài khoản:


🔐 3.2. Truy cập trang bảo vệ (GET /profile)

Khi đã đăng nhập (cookie hợp lệ):


Khi chưa đăng nhập (không có cookie):


🚪 3.3. Đăng xuất (POST /logout)

URL: http://localhost:3001/logout
Method: POST

📸 Kết quả:


📝 4. Ghi chú

Cookie có thời gian sống 5 phút (maxAge = 5 phút).

Sau khi cookie hết hạn, cần đăng nhập lại để truy cập /profile.

Nếu thay đổi cổng server, nhớ chỉnh lại URL trong Postman.

## 5. Thông tin sinh viên

Họ tên: Nguyễn Hồng Ngọc Hân

MSSV: 22660931

Môn: Lập trình Hướng Dịch vụ

Tuần: 06
