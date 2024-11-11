# Hướng dẫn cài vps Ovh
> sudo su -
> passwd
> nano /etc/ssh/sshd_config
Edit PermitRootLogin yes & PasswordAuthentication yes (Lưu ctr+x y)
> systemctl restart ssh

# Để cài đặt Node.js phiên bản 18.18.0 trên Ubuntu 24.04, bạn có thể sử dụng Node Version Manager (NVM), một công cụ hữu ích cho phép quản lý nhiều phiên bản Node.js trên cùng một hệ thống. Dưới đây là hướng dẫn chi tiết:

## Bước 1: Cài đặt NVM
Mở terminal và chạy lệnh sau để tải và cài đặt NVM:

> curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash

Sau khi cài đặt, tải lại cấu hình shell để NVM có hiệu lực:

> source ~/.bashrc

## Bước 2: Cài đặt Node.js phiên bản 18.18.0
Sử dụng NVM để cài đặt Node.js phiên bản 18.18.0:

> nvm install 18.18.0

## Bước 3: Kiểm tra phiên bản Node.js
Xác nhận rằng Node.js đã được cài đặt thành công bằng cách kiểm tra phiên bản:

> node -v

Kết quả hiển thị sẽ là: v18.18.0

## Bước 4: Thiết lập phiên bản Node.js mặc định (tùy chọn)
Nếu bạn muốn thiết lập Node.js phiên bản 18.18.0 làm phiên bản mặc định, chạy lệnh:

> nvm alias default 18.18.0

Lưu ý:
NVM cho phép bạn cài đặt và quản lý nhiều phiên bản Node.js trên cùng một hệ thống, giúp dễ dàng chuyển đổi giữa các phiên bản khi cần thiết.
Nếu bạn chưa cài đặt NVM, hãy làm theo hướng dẫn tại trang chính thức của NVM:
Với các bước trên, bạn đã cài đặt thành công Node.js phiên bản 18.18.0 trên Ubuntu 24.04.


# 1. Cài đặt PHP 8.1
Trước tiên, bạn cần cài đặt PHP 8.1 và các module PHP cần thiết.
## Bước 1: Cập nhật hệ thống
Thêm kho lưu trữ PHP PPA
Trước tiên, bạn cần thêm kho lưu trữ của Ondřej Surý:

> sudo add-apt-repository ppa:ondrej/php
> sudo apt update

## Bước 2. Cài đặt PHP 8.1 và các module cần thiết
Sau khi thêm kho lưu trữ, bạn có thể cài đặt PHP 8.1 và các module cần thiết.

> sudo apt install -y php8.1 php8.1-fpm php8.1-cli php8.1-mysql php8.1-redis php8.1-curl php8.1-xml php8.1-mbstring php8.1-zip

## Bước 3. Kiểm tra phiên bản PHP
Kiểm tra xem PHP 8.1 đã được cài đặt thành công chưa:

> php -v

## Bước 4. Kiểm tra PHP-FPM
Nếu bạn sử dụng PHP-FPM với Nginx, bạn có thể kiểm tra dịch vụ PHP-FPM:

> sudo systemctl status php8.1-fpm

Sau khi thực hiện các bước trên, bạn sẽ có PHP 8.1 và các module cần thiết trên Ubuntu 24.04 của mình.


# 2. Cài đặt MariaDB
MariaDB là một hệ quản trị cơ sở dữ liệu tương thích với MySQL.
## Bước 1: Cài đặt MariaDB

> sudo apt install -y mariadb-server

## Bước 2: Khởi động và bảo mật MariaDB
Khởi động MariaDB:

> sudo systemctl start mariadb

Thiết lập bảo mật cho MariaDB:

> sudo mysql_secure_installation

# 3. Cài đặt Redis
Redis là một hệ thống lưu trữ dữ liệu theo kiểu key-value, thường được sử dụng như một bộ nhớ đệm.
## Bước 1: Cài đặt Redis

> sudo apt install -y redis-server

## Bước 2: Khởi động và kiểm tra Redis
Khởi động Redis:

> sudo systemctl start redis

Kiểm tra Redis đang chạy:

> sudo systemctl status redis

# 4. Cài đặt Nginx
Nginx là một web server và reverse proxy phổ biến.
## Bước 1: Cài đặt Nginx

> sudo apt install -y nginx

## Bước 2: Khởi động và kiểm tra Nginx
Khởi động Nginx:

> sudo systemctl start nginx

Kiểm tra Nginx:

> sudo systemctl status nginx

nginx -t
systemctl restart nginx
