---
title: "Workshop"
date: 2026-08-03
weight: 5
chapter: false
pre: " <b> 5. </b> "
---
# Triển khai ứng dụng Splitly trên AWS bằng CloudFormation và EC2

#### Tổng quan

Trong workshop này, chúng ta sẽ triển khai ứng dụng **Splitly** lên AWS bằng cách sử dụng **AWS CloudFormation** để tự động tạo các tài nguyên cần thiết.

Sau khi hạ tầng được khởi tạo, chúng ta sẽ kết nối đến máy chủ **Amazon EC2** thông qua **AWS Systems Manager Session Manager**, sau đó triển khai Backend và Frontend của ứng dụng.

Các công việc chính trong workshop bao gồm:

+ Sử dụng **AWS CloudFormation** để triển khai hạ tầng.
+ Kết nối đến EC2 bằng **Session Manager**.
+ Clone mã nguồn Splitly từ GitHub.
+ Cài đặt và build Backend.
+ Chạy Backend bằng **PM2**.
+ Build Frontend.
+ Cấu hình **Nginx** để phục vụ Frontend và chuyển tiếp các yêu cầu API đến Backend.
+ Kiểm tra trạng thái hoạt động của toàn bộ hệ thống.
+ Xóa CloudFormation stack sau khi hoàn thành để tránh phát sinh chi phí.

#### Nội dung

1. [Tổng quan về Workshop](5.1-Workshop-overview/)
2. [Chuẩn bị](5.2-Prerequiste/)
3. [Triển khai mã nguồn và Web Server](5.3-DeployCode-WebServer/)
4. [Kiểm tra hệ thống](5.4-Test/)
5. [Dọn dẹp tài nguyên](5.5-Cleanup/)