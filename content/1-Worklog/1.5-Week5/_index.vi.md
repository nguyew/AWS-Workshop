---
title: "Worklog Tuần 5"
date: 2026-06-19
weight: 1
chapter: false
pre: " <b> 1.5. </b> "
---

### Mục tiêu tuần 5:

* Tìm hiểu mô hình trách nhiệm chia sẻ trong AWS Security.
* Tìm hiểu dịch vụ AWS Identity and Access Management (IAM).
* Thực hành quản lý người dùng, nhóm và phân quyền trong AWS.
* Tìm hiểu các cơ chế xác thực, phân quyền và quản lý khóa mã hóa trên AWS.
* Tìm hiểu các dịch vụ hỗ trợ quản trị tập trung và bảo mật trên AWS.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc                                                                                                                                                                                                                                                                                 | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                                                     |
| --- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ------------------------------------------------------------------ |
| 2   | - Tìm hiểu Shared Responsibility Model trên AWS <br> - Tìm hiểu AWS IAM: <br>  + Root Account <br>  + IAM User <br>  + IAM Group <br>  + IAM Policy <br>  + IAM Role <br> - **Thực hành:** <br>  + Tạo IAM Group và IAM User <br>  + Tạo IAM Role <br>  + Assume Role                     | 15/06/2026   | 15/06/2026      | https://cloudjourney.awsstudygroup.com/ <br> https://byvn.net/PcQc |
| 3   | - Tìm hiểu cơ chế phân quyền trong IAM <br> - Tìm hiểu IAM Condition: <br>  + Giới hạn theo IP Address <br>  + Giới hạn theo thời gian truy cập <br> - **Thực hành:** <br>  + Tạo User quản trị EC2 <br>  + Tạo User quản trị RDS <br>  + Tạo Group quản trị <br>  + Cấu hình Switch Role | 16/06/2026   | 16/06/2026      | https://cloudjourney.awsstudygroup.com/ <br> https://byvn.net/PcQc |
| 4   | - Tìm hiểu Permission Boundary <br> - Tìm hiểu nguyên tắc Least Privilege <br> - **Thực hành:** <br>  + Tạo Policy giới hạn quyền <br>  + Tạo IAM User bị giới hạn quyền <br>  + Kiểm tra User bị giới hạn quyền                                                                          | 17/06/2026   | 17/06/2026      | https://cloudjourney.awsstudygroup.com/ <br> https://byvn.net/PcQc |
| 5   | - Tìm hiểu Access Key và AWS CLI Authentication <br> - Tìm hiểu IAM Role trên Amazon EC2 <br> - Tìm hiểu Amazon Cognito: <br>  + User Pool <br>  + Identity Pool <br> - **Thực hành:** <br>  + Sử dụng Access Key <br>  + Gán IAM Role cho EC2                                            | 18/06/2026   | 18/06/2026      | https://cloudjourney.awsstudygroup.com/ <br> https://byvn.net/PcQc |
| 6   | - Tìm hiểu AWS Organizations <br> - Tìm hiểu Service Control Policy (SCP) <br> - Tìm hiểu AWS Identity Center (SSO) <br> - Tìm hiểu AWS KMS và Customer Managed Key (CMK) <br> - Tìm hiểu AWS Security Hub và các tiêu chuẩn bảo mật AWS                                                  | 19/06/2026   | 19/06/2026      | https://cloudjourney.awsstudygroup.com/ <br> https://byvn.net/PcQc |


### Kết quả đạt được tuần 5:

* Xây dựng hiểu biết về AWS Shared Responsibility Model và nắm rõ phạm vi trách nhiệm bảo mật giữa AWS và khách hàng khi sử dụng dịch vụ đám mây.

* Tìm hiểu kiến trúc và cơ chế quản lý danh tính, quyền truy cập thông qua AWS Identity and Access Management (IAM).

* Nắm vững các thành phần cốt lõi của AWS IAM, bao gồm:

  * Root Account
  * IAM User
  * IAM Group
  * IAM Policy
  * IAM Role

* Hiểu nguyên tắc Principle of Least Privilege (PoLP) và cách áp dụng để cấp quyền tối thiểu nhưng vẫn đáp ứng yêu cầu công việc.

* Tìm hiểu quy trình đánh giá quyền của IAM Policy, đặc biệt là cách Explicit Deny được ưu tiên hơn các quyền Allow.

* Khám phá cách sử dụng IAM Conditions để kiểm soát quyền truy cập dựa trên:

  * Địa chỉ IP
  * Thời gian truy cập

* Hiểu cơ chế Assume Role và Switch Role, đồng thời biết cách áp dụng trong môi trường AWS nhiều tài khoản.

* Tìm hiểu vai trò của Permission Boundaries trong việc giới hạn phạm vi quyền tối đa có thể được cấp cho IAM User hoặc IAM Role.

* Hiểu cách Access Keys hỗ trợ truy cập AWS thông qua lập trình và nắm được các nguyên tắc bảo mật khi sử dụng.

* Nhận biết lợi ích của việc sử dụng IAM Role cho Amazon EC2 thay vì lưu trữ trực tiếp Access Key trên máy chủ.

* Tìm hiểu các thành phần chính của Amazon Cognito, bao gồm:

  * User Pool
  * Identity Pool

* Hiểu cách AWS Organizations hỗ trợ quản lý tập trung nhiều tài khoản AWS trong cùng một tổ chức.

* Tìm hiểu vai trò của Service Control Policies (SCPs) trong việc kiểm soát quyền truy cập và thiết lập chính sách quản trị ở cấp tổ chức.

* Tìm hiểu cách triển khai Single Sign-On (SSO) bằng AWS Identity Center để đơn giản hóa việc quản lý người dùng và xác thực.

* Nắm được cách AWS Key Management Service (KMS) quản lý khóa mã hóa và cách sử dụng Customer Managed Keys (CMKs) để bảo vệ dữ liệu.

* Hiểu vai trò của AWS Security Hub trong việc tổng hợp, giám sát và đánh giá trạng thái bảo mật theo các tiêu chuẩn và khuyến nghị của AWS.

* Hoàn thành các bài thực hành như:

  * Tạo IAM User và IAM Group
  * Tạo và sử dụng IAM Role
  * Thiết lập người dùng quản trị cho EC2 và RDS
  * Cấu hình IAM Conditions
  * Thiết lập Switch Role
  * Tạo Permission Boundaries
  * Sử dụng Access Keys
  * Gán IAM Role cho EC2 Instance

* Phát triển khả năng thiết kế và triển khai các giải pháp quản lý danh tính và quyền truy cập (IAM) theo các nguyên tắc và thông lệ bảo mật tốt nhất của AWS.


