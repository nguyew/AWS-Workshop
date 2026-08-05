---
title : "Deploy Source Code và Cấu hình Web Server"
date : 2026-08-02 
weight : 3
chapter : false
pre : " <b> 5.3. </b> "
---

+ Vào EC2

![ec2](/AWS-Workshop/images/5-Workshop/5.3-Deploy-Config/12.png)

+ Vào Instance và bấm connect

![ec2](/AWS-Workshop/images/5-Workshop/5.3-Deploy-Config/13.png)

+ Check status 3/3 và chọn SSM Session Manager

![ec2](/AWS-Workshop/images/5-Workshop/5.3-Deploy-Config/14.png)

+ Bấm connect

![ec2](/AWS-Workshop/images/5-Workshop/5.3-Deploy-Config/15.png)

+ Sau khi bấm connect sẽ tự động chuyển sang system manager

![ec2](/AWS-Workshop/images/5-Workshop/5.3-Deploy-Config/16.png)

## Triển khai ứng dụng Splitly trên EC2

Sau khi truy cập vào máy chủ EC2 theo đường dẫn:

**EC2 → Connect → Session Manager → Connect**

Chạy lệnh sau để chuyển sang tài khoản `ec2-user`:

```bash
sudo su - ec2-user
```

---

### 1. Tạo thư mục triển khai

Tạo thư mục dùng để triển khai dự án Splitly:

```bash
sudo mkdir -p /opt/splitly
sudo chown -R ec2-user:ec2-user /opt/splitly
cd /opt/splitly
```

Trong đó:

* `mkdir -p /opt/splitly`: Tạo thư mục `/opt/splitly`.
* `chown`: Cấp quyền sở hữu thư mục cho tài khoản `ec2-user`.
* `cd /opt/splitly`: Di chuyển vào thư mục triển khai.

---

### 2. Clone mã nguồn từ GitHub

Clone mã nguồn của dự án vào thư mục triển khai:

```bash
git clone <URL_GITHUB_REPOSITORY> .
```

Ví dụ:

```bash
git clone https://github.com/username/splitly.git .
```

Dấu chấm `.` ở cuối lệnh có nghĩa là mã nguồn sẽ được clone trực tiếp vào thư mục hiện tại.

Sau khi clone thành công, cần kiểm tra và đảm bảo dự án có các thư mục sau:

```text
app
backend
```

Cấu trúc thư mục dự kiến:

```text
/opt/splitly
├── app
└── backend
```

Trong đó:

* `app`: Chứa mã nguồn frontend.
* `backend`: Chứa mã nguồn backend.

---

### 3. Triển khai Backend

Di chuyển vào thư mục backend:

```bash
cd /opt/splitly/backend
```

#### Tạo file cấu hình môi trường cho Backend

Tạo file `.env`:

```bash
nano .env
```

Sao chép nội dung từ file `.env` trong mã nguồn và cập nhật các giá trị phù hợp với môi trường triển khai.

Mẫu cấu hình:

```env
PORT=5000

MONGODB_URI=<CHUOI_KET_NOI_MONGODB_ATLAS>
MONGODB_DB=Splitly

JWT_SECRET=<CHUOI_BI_MAT_JWT>

EMAIL_PROVIDER=gmail
GMAIL_SMTP_USER=<DIA_CHI_EMAIL_GMAIL>
GMAIL_APP_PASSWORD=<MAT_KHAU_UNG_DUNG_GMAIL>
EMAIL_FROM=Splitly <<DIA_CHI_EMAIL_GMAIL>>

AWS_REGION=ap-southeast-1
S3_RECEIPTS_BUCKET=<TEN_BUCKET_S3>
S3_RECEIPTS_PREFIX=receipts/
S3_PRESIGN_EXPIRES_SECONDS=3000

FRONTEND_URL=http://<PUBLIC_IP_EC2>

VNPAY_TMN_CODE=
VNPAY_HASH_SECRET=
VNPAY_URL=https://sandbox.vnpayment.vn/paymentv2/vpcpay.html
```

Sau khi nhập xong, lưu và đóng file bằng các phím:

```text
Ctrl + O
Enter
Ctrl + X
```

> Không được commit file `.env` lên GitHub hoặc công khai các thông tin bảo mật như chuỗi kết nối MongoDB, JWT Secret, Gmail App Password và thông tin VNPay.

#### Cài đặt thư viện và build Backend

Chạy các lệnh sau:

```bash
npm install
npm run build
```

Trong đó:

* `npm install`: Cài đặt các thư viện cần thiết của backend.
* `npm run build`: Biên dịch mã nguồn backend sang thư mục `dist`.

#### Khởi chạy Backend bằng PM2

Chạy backend bằng PM2:

```bash
pm2 start dist/server.js --name splitly-api
```

Lưu danh sách tiến trình PM2:

```bash
pm2 save
```

Kiểm tra trạng thái backend:

```bash
pm2 status
```

Tiến trình `splitly-api` cần có trạng thái:

```text
online
```

---

### 4. Triển khai Frontend

Di chuyển vào thư mục frontend:

```bash
cd /opt/splitly/app
```

#### Tạo file cấu hình môi trường cho Frontend

Tạo file `.env.production`:

```bash
nano .env.production
```

Sao chép nội dung từ file môi trường của frontend trong mã nguồn và cập nhật các giá trị cần thiết.

Mẫu cấu hình:

```env
VITE_API_URL=http://<PUBLIC_IP_EC2>
VITE_RECEIPTS_PUBLIC_BASE_URL=
VITE_GOOGLE_CLIENT_ID=<GOOGLE_CLIENT_ID>
```

Sau khi nhập xong, lưu và đóng file bằng các phím:

```text
Ctrl + O
Enter
Ctrl + X
```

#### Cài đặt thư viện và build Frontend

Chạy các lệnh sau:

```bash
npm install
npm run build
```

Sau khi build thành công, thư mục `dist` sẽ được tạo bên trong thư mục frontend.

#### Kiểm tra kết quả build Frontend

Chạy lệnh:

```bash
test -f dist/index.html && echo "Frontend build: OK"
```

Kết quả mong đợi:

```text
Frontend build: OK
```

Kết quả này xác nhận file `dist/index.html` đã được tạo thành công.

---

### 5. Cấu hình và khởi chạy Nginx

Tạo file cấu hình Nginx cho ứng dụng Splitly:

```bash
sudo nano /etc/nginx/conf.d/splitly.conf
```

Thêm nội dung sau vào file:

```nginx
server {
    listen 80;
    server_name _;

    root /opt/splitly/app/dist;
    index index.html;

    location / {
        try_files $uri $uri/ /index.html;
    }

    location /api/ {
        proxy_pass http://127.0.0.1:5000;
        proxy_http_version 1.1;

        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Forwarded-Proto $scheme;
    }
}
```

Trong cấu hình trên:

* Nginx lắng nghe các yêu cầu trên cổng `80`.
* Frontend được phục vụ từ thư mục `/opt/splitly/app/dist`.
* Các yêu cầu bắt đầu bằng `/api/` được chuyển tiếp đến backend đang chạy trên cổng `5000`.
* `try_files` hỗ trợ định tuyến cho ứng dụng React Single Page Application.

Sau khi nhập xong, lưu và đóng file:

```text
Ctrl + O
Enter
Ctrl + X
```

#### Kiểm tra cấu hình Nginx

Chạy lệnh:

```bash
sudo nginx -t
```

Nếu cấu hình hợp lệ, kết quả sẽ tương tự:

```text
syntax is ok
test is successful
```

#### Khởi động lại Nginx

Chạy lệnh:

```bash
sudo systemctl restart nginx
```

Kiểm tra trạng thái Nginx:

```bash
sudo systemctl is-active nginx
```

Kết quả mong đợi:

```text
active
```

---

### 6. Kiểm tra toàn bộ quá trình triển khai

#### Kiểm tra tiến trình Backend

```bash
pm2 status
```

Tiến trình `splitly-api` cần có trạng thái `online`.

#### Kiểm tra Backend có đang lắng nghe trên cổng 5000

```bash
sudo ss -lntp | grep 5000
```

Nếu backend đang hoạt động, kết quả sẽ hiển thị tiến trình đang lắng nghe trên cổng `5000`.

#### Kiểm tra Frontend đã được build

```bash
test -f /opt/splitly/app/dist/index.html && echo "Frontend build: OK"
```

Kết quả mong đợi:

```text
Frontend build: OK
```

#### Kiểm tra lại cấu hình Nginx

```bash
sudo nginx -t
```

#### Kiểm tra trạng thái dịch vụ Nginx

```bash
sudo systemctl is-active nginx
```

Kết quả mong đợi:

```text
active
```

#### Kiểm tra website ngay trên máy chủ EC2

```bash
curl -I http://127.0.0.1
```

Nếu ứng dụng hoạt động bình thường, kết quả sẽ chứa mã trạng thái HTTP như sau:

```text
HTTP/1.1 200 OK
```

---

### 7. Truy cập ứng dụng Splitly

Mở trình duyệt và truy cập ứng dụng bằng địa chỉ Public IP của EC2:

```text
http://<PUBLIC_IP_EC2>
```

Ví dụ:

```text
http://13.xxx.xxx.xxx
```

Nếu quá trình triển khai thành công:

* Giao diện frontend của Splitly sẽ được hiển thị.
* Các yêu cầu API bắt đầu bằng `/api/` sẽ được Nginx chuyển tiếp đến backend.
* Backend sẽ xử lý các yêu cầu trên cổng `5000`.
* Người dùng chỉ cần truy cập ứng dụng thông qua cổng HTTP mặc định là cổng `80`.

