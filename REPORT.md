\# Báo cáo Bài 1: Kiểm tra cài đặt Docker Engine và chạy container Hello-World

\#\# 1\. Mục tiêu  
Kiểm tra Docker đã được cài đặt đúng và hoạt động ổn định trên máy cá nhân, đồng thời khởi chạy container đầu tiên để xác nhận toàn bộ luồng hoạt động từ Docker CLI đến Docker Daemon.

\#\# 2\. Môi trường thực hiện  
\- Hệ điều hành: Windows (kiến trúc amd64)  
\- Công cụ: Docker Desktop 4.89.0  
\- Context đang dùng: desktop-linux  
\- Terminal: \[PowerShell / Git Bash / WSL\]

\#\# 3\. Kết quả kiểm tra

\#\#\# 3.1. Phiên bản Docker  
\- Docker Client (CLI) phiên bản 29.7.2, API version 1.55, được build bằng Go 1.26.5.  
\- Docker Server (Engine) phiên bản 29.7.2, chạy trên nền Linux/amd64 bên trong Docker Desktop.  
\- Các thành phần bên dưới Engine gồm containerd v2.3.3, runc 1.4.3 và docker-init 0.19.0.  
\- Việc cả hai phần Client và Server cùng hiển thị chứng tỏ CLI đã kết nối thành công tới Docker Daemon.

\#\#\# 3.2. Thông tin hệ thống Docker  
\- Số container hiện có: \[điền số\]; số image hiện có: \[điền số\].  
\- Storage driver: \[điền, ví dụ overlayfs\].  
\- Cgroup driver: \[điền\]; Cgroup version: \[điền\].  
\- Hệ điều hành của Engine: \[điền\]; số CPU: \[điền\]; dung lượng RAM: \[điền\].  
\- Thông tin này cho thấy Docker Engine đã sẵn sàng tạo và quản lý container trên máy.

\#\#\# 3.3. Chạy container Hello-World  
\- Docker kiểm tra image hello-world trong máy cục bộ. Nếu chưa có, Docker tự tải từ Docker Hub về.  
\- Docker tạo container từ image, chạy chương trình bên trong, in ra thông điệp "Hello from Docker\! This message shows that your installation appears to be working correctly." rồi tự thoát.  
\- Kết quả: container chạy thành công, đúng với kết quả mong đợi của đề bài.

\#\# 4\. Nhận xét  
\- Ban đầu Docker Daemon chưa chạy nên CLI báo không kết nối được tới Docker API. Nguyên nhân là chưa mở Docker Desktop. Sau khi khởi động Docker Desktop và chờ Engine ở trạng thái đang chạy, lỗi được khắc phục.  
\- Trên Windows với Docker Desktop, không cần dùng sudo hay thêm user vào group docker như trên Linux. Nếu gặp lỗi quyền thì cần kiểm tra tài khoản có thuộc nhóm docker-users hay không.  
\- Luồng hoạt động của container đầu tiên: Docker CLI gửi yêu cầu tới Docker Daemon, Daemon tải image từ Docker Hub (nếu chưa có), tạo container từ image, chạy container và trả kết quả về Terminal.

\#\# 5\. Kết luận  
Docker Engine đã được cài đặt và hoạt động đúng. Môi trường đủ điều kiện để thực hiện các bài thực hành tiếp theo về image, container, volume và network.  
