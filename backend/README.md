# StudyHub – bản đã kết nối Backend và SQLite

## 1. Công nghệ
- Frontend: HTML, CSS, JavaScript.
- Backend: Node.js 22, Express.
- Database: SQLite (`backend/data/studyhub.sqlite`).
- Xác thực: JWT trong HttpOnly cookie, mật khẩu bcrypt.
- Biểu đồ: Chart.js 4.

## 2. Cài đặt và chạy
1. Cài Node.js 22.
2. Mở Terminal tại thư mục `backend`.
3. Chạy `npm install`.
4. Sao chép `.env.example` thành `.env`, đổi `JWT_SECRET` thành chuỗi bí mật ngẫu nhiên.
5. Chạy `npm start`. API chạy tại `http://localhost:3000`.
6. Mở thư mục dự án bằng VS Code, chạy Live Server trên cổng 5500. Truy cập `html/login.html`.
   - Có thể dùng `localhost:5500` hoặc `127.0.0.1:5500`; `auth.js` tự dùng hostname hiện tại để gọi API.

## 3. Tài khoản thử nghiệm

Thông tin đăng nhập thử nghiệm được quản lý riêng trong quá trình demo. Không lưu mật khẩu, ngày sinh hoặc danh sách thông tin đăng nhập của sinh viên trong README/repository công khai.

## 4. Dữ liệu và API
- `backend/data/studyhub.sqlite` là CSDL đang được Backend sử dụng.
- `backend/data/studyhub.sql` là bản SQL có thể import để dựng lại cùng cấu trúc và dữ liệu.
- `GET /api/health`: kiểm tra Backend.
- `POST /api/auth/login`, `GET /api/auth/me`, `POST /api/auth/logout`: đăng nhập/phiên.
- `GET /api/student/dashboard`: dữ liệu tổng quan riêng của sinh viên đang đăng nhập, gồm môn học, điểm, bài tập, tiến độ, lịch lớp và phân bố điểm.
- `GET /api/student/courses`, `/assignments`, `/schedule`: dữ liệu các trang theo sinh viên và lớp.

## 5. Dữ liệu mẫu cần lưu ý
Danh sách sinh viên, ngày sinh, email, lớp, ngành, năm học và 33 môn học/giảng viên/phòng học/tín chỉ được nhập theo dữ liệu bạn cung cấp. Bảng điểm, tiến độ và trạng thái bài tập hiện là **dữ liệu mẫu riêng từng tài khoản** để kiểm thử dashboard và biểu đồ Chart.js vì bạn chưa cung cấp bảng điểm/bài tập thực tế. Lịch lớp mẫu dùng chung cho DA24TTA; cần thay bằng lịch chính thức của lớp khi có dữ liệu.

## 6. Sao lưu
Trước khi thay đổi dữ liệu, sao lưu `backend/data/studyhub.sqlite`. Các bản database cũ được chuyển vào `backend/backups/` để tránh nhầm với database đang chạy.
