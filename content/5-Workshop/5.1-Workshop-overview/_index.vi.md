---
title : "Giới thiệu"
date : 2026-08-01 
weight : 1
chapter : false
pre : " <b> 5.1. </b> "
---

#### Giới thiệu về Splitly

* **Splitly** là nền tảng quản lý và chia sẻ chi phí nhóm, giúp người dùng theo dõi các khoản chi tiêu chung, tính toán số tiền cần thanh toán giữa các thành viên và quản lý lịch sử giao dịch một cách minh bạch.

* Hệ thống được xây dựng theo kiến trúc web hiện đại, bao gồm frontend **React + Vite**, backend **Node.js/Express** và cơ sở dữ liệu **MongoDB Atlas**. Ứng dụng được triển khai trên AWS nhằm tận dụng khả năng mở rộng, bảo mật và giám sát của nền tảng điện toán đám mây.

* **Amazon EC2** được sử dụng để triển khai backend API và frontend, **Amazon S3** dùng để lưu trữ các tệp hóa đơn và biên lai (Receipt), **Amazon CloudWatch** hỗ trợ theo dõi log và trạng thái hệ thống, trong khi **Amazon VPC** và **Security Group** đảm bảo kết nối mạng an toàn giữa các thành phần.

#### Tổng quan về hệ thống

Trong hệ thống Splitly, các thành phần chính bao gồm:

* **Frontend Application**

  * Được xây dựng bằng React + Vite.
  * Cung cấp giao diện để người dùng quản lý nhóm, khoản chi và trạng thái thanh toán.

* **Backend Application**

  * Sử dụng Node.js/Express để cung cấp các REST API.
  * Xử lý các nghiệp vụ như tạo nhóm, quản lý expense, tính toán settlement và xác thực người dùng.

* **Database**

  * Sử dụng MongoDB Atlas để lưu trữ dữ liệu người dùng, nhóm, giao dịch và lịch sử thanh toán.

* **Cloud Storage**

  * Amazon S3 được sử dụng để lưu trữ hình ảnh, hóa đơn điện tử và biên lai được người dùng tải lên.

* **Monitoring & Security**

  * Amazon CloudWatch được sử dụng để thu thập log và giám sát trạng thái hoạt động của hệ thống.
  * Amazon VPC, Security Group và AWS IAM giúp kiểm soát kết nối mạng và quyền truy cập vào các tài nguyên AWS.

Kiến trúc nâng cấp giúp Splitly cải thiện **hiệu suất**, **bảo mật** và **khả năng mở rộng** thông qua việc tách riêng frontend và backend.

+ Frontend được lưu trữ trên **Amazon S3** và phân phối qua **Amazon CloudFront**.
+ **Amazon Route 53** hỗ trợ quản lý tên miền.
+ **AWS Certificate Manager** cung cấp chứng chỉ SSL/TLS cho kết nối HTTPS.
+ **AWS WAF** hỗ trợ bảo vệ ứng dụng khỏi các yêu cầu truy cập bất thường.
+ Backend tiếp tục được triển khai trên **Amazon EC2** và kết nối với **MongoDB Atlas**.

Kiến trúc này tạo nền tảng để mở rộng backend và tích hợp thêm các dịch vụ AWS trong tương lai mà không cần thay đổi lớn đối với toàn bộ hệ thống.