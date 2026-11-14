# Hướng dẫn cài đặt và chạy StudyHub Dashboard

## 1. Môi trường cần có

- Node.js phiên bản 22.
- Visual Studio Code.
- Trình duyệt Google Chrome hoặc Microsoft Edge.
- Extension Live Server (nếu muốn chạy frontend bằng Live Server).

## 2. Tải mã nguồn

1. Truy cập repository StudyHub Dashboard trên GitHub.
2. Chọn **Code → Download ZIP** hoặc clone repository.
3. Giải nén dự án (nếu tải ZIP).
4. Mở thư mục dự án bằng Visual Studio Code.

## 3. Cài đặt và chạy Backend

Mở Terminal tại thư mục gốc dự án, sau đó chạy:

```bash
cd backend
npm install
```

Tạo file `.env` từ file mẫu `.env.example` và thay `JWT_SECRET` bằng một chuỗi bí mật ngẫu nhiên đủ dài. Không chia sẻ hoặc commit file `.env` lên GitHub.

Khởi động Backend:

```bash
npm start
```

Backend mặc định chạy tại `http://localhost:3000`. Có thể kiểm tra trạng thái bằng địa chỉ:

```text
http://localhost:3000/api/health
```

Giữ Terminal Backend hoạt động trong khi sử dụng các chức năng cần API.

## 4. Chạy Frontend

Mở Terminal thứ hai tại thư mục gốc dự án và chạy:

```bash
npx http-server . -p 5500
```

Sau đó truy cập:

```text
http://127.0.0.1:5500/html/login.html
```

Có thể dùng Live Server nếu cấu hình cổng và địa chỉ frontend phù hợp với `FRONTEND_ORIGINS` trong file `.env`.

## 5. Database

- Hệ quản trị cơ sở dữ liệu: SQLite.
- Thư viện kết nối: `better-sqlite3`.
- Database được tạo tại `backend/data/studyhub.sqlite` theo cấu hình mặc định.
- Khi chưa có database, Backend sử dụng `backend/data/studyhub.sql` để khởi tạo dữ liệu ban đầu.

Không xóa database đang sử dụng hoặc chạy các script seed/fix dữ liệu nếu chưa sao lưu và chưa hiểu rõ tác động của script.

## 6. Tài khoản thử nghiệm

Thông tin đăng nhập thử nghiệm được quản lý riêng trong quá trình demo. Không ghi mật khẩu, ngày sinh, số điện thoại hoặc thông tin đăng nhập của sinh viên vào README hay repository công khai.

## 7. Xử lý lỗi cơ bản

- Nếu API không hoạt động, kiểm tra Backend đã chạy và Terminal có báo lỗi hay không.
- Nếu trình duyệt không kết nối được Backend, kiểm tra `FRONTEND_ORIGINS` và địa chỉ API trong cấu hình frontend.
- Nếu thiếu thư viện, chạy lại `npm install` trong thư mục `backend`.
- Trước khi gửi yêu cầu hỗ trợ, lưu lại thông báo lỗi trong Terminal để kiểm tra.
