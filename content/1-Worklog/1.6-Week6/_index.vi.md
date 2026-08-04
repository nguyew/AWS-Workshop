---
title: "Week 6 Worklog"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.6. </b> "
---

### Mục tiêu tuần 6:

* Nắm vững các khái niệm nền tảng về cơ sở dữ liệu và hệ quản trị cơ sở dữ liệu.
* Hiểu sự khác biệt giữa cơ sở dữ liệu quan hệ (RDBMS) và cơ sở dữ liệu NoSQL.
* Tìm hiểu mô hình xử lý giao dịch (OLTP) và xử lý phân tích (OLAP).
* Khám phá các dịch vụ cơ sở dữ liệu trên AWS và trường hợp sử dụng của từng dịch vụ.
* Thực hành triển khai, kết nối, sao lưu và khôi phục cơ sở dữ liệu bằng Amazon RDS.
* Tìm hiểu quy trình di chuyển cơ sở dữ liệu từ Oracle sang Amazon Aurora PostgreSQL.

### Công việc thực hiện trong tuần:

| Ngày | Công việc | Ngày bắt đầu | Ngày hoàn thành | Tài liệu |
| --- | --------- | ------------ | --------------- | -------- |
| Thứ 2 | Tìm hiểu các khái niệm cơ bản về cơ sở dữ liệu như Session, Index, Partition, Transaction Log, Buffer và Execution Plan. Đồng thời nghiên cứu kỹ thuật tối ưu truy vấn và so sánh cơ sở dữ liệu quan hệ với NoSQL. | 22/06/2026 | 22/06/2026 | https://cloudjourney.awsstudygroup.com/ <br> https://byvn.net/PcQc |
| Thứ 3 | Nghiên cứu các mô hình NoSQL gồm Document, Key-Value, Wide-Column và Graph Database. Tìm hiểu sự khác biệt giữa OLTP và OLAP cũng như vai trò của Data Warehouse trong phân tích dữ liệu. | 23/06/2026 | 23/06/2026 | https://cloudjourney.awsstudygroup.com/ <br> https://byvn.net/PcQc |
| Thứ 4 | Tìm hiểu kiến trúc Amazon RDS, các loại cơ sở dữ liệu được hỗ trợ cùng những tính năng như Read Replica, Multi-AZ, Automatic Failover, Storage Auto Scaling và mã hóa dữ liệu. Thực hành tạo một Amazon RDS Database Instance. | 24/06/2026 | 24/06/2026 | https://cloudjourney.awsstudygroup.com/ <br> https://byvn.net/PcQc |
| Thứ 5 | Nghiên cứu kiến trúc Amazon Aurora và các tính năng nâng cao như Backtrack, Clone, Global Database và Multi-Master. Thực hành kết nối ứng dụng với cơ sở dữ liệu, đồng thời thực hiện sao lưu và khôi phục dữ liệu. | 25/06/2026 | 25/06/2026 | https://cloudjourney.awsstudygroup.com/ <br> https://byvn.net/PcQc |
| Thứ 6 | Tìm hiểu Amazon ElastiCache và Amazon Redshift. Thực hành quy trình di chuyển cơ sở dữ liệu từ Oracle sang Amazon Aurora PostgreSQL, bao gồm chuyển đổi schema và di chuyển dữ liệu. | 26/06/2026 | 26/06/2026 | https://cloudjourney.awsstudygroup.com/ <br> https://byvn.net/PcQc |

### Kết quả đạt được trong tuần 6:

* **Tổng quan:**
  * Trong tuần này, tôi đã củng cố kiến thức về cơ sở dữ liệu và các dịch vụ cơ sở dữ liệu trên AWS thông qua việc học lý thuyết kết hợp với thực hành. Tôi hiểu rõ hơn về cách triển khai, quản lý, bảo vệ và di chuyển cơ sở dữ liệu trên nền tảng AWS, đồng thời biết cách lựa chọn dịch vụ phù hợp với từng nhu cầu sử dụng.

* **Kiến thức đã học:**
  * Nắm được các khái niệm quan trọng trong cơ sở dữ liệu như Session, Index, Partition, Transaction Log, Buffer và Execution Plan.
  * Hiểu sự khác biệt giữa cơ sở dữ liệu quan hệ (RDBMS) và NoSQL, đồng thời tìm hiểu các mô hình NoSQL phổ biến như Document, Key-Value, Wide-Column và Graph Database.
  * Hiểu được đặc điểm của hai mô hình xử lý OLTP và OLAP cũng như vai trò của Data Warehouse trong các hệ thống phân tích dữ liệu.
  * Nắm được kiến trúc Amazon RDS và các tính năng quan trọng như Read Replica, Multi-AZ, Automatic Failover, Storage Auto Scaling và mã hóa dữ liệu.
  * Tìm hiểu kiến trúc Amazon Aurora cùng các tính năng nâng cao như Backtrack, Clone, Global Database và Multi-Master.
  * Hiểu vai trò của Amazon ElastiCache trong việc tăng tốc truy cập dữ liệu và Amazon Redshift trong xử lý dữ liệu phân tích quy mô lớn.
  * Nắm được quy trình di chuyển cơ sở dữ liệu từ Oracle sang Amazon Aurora PostgreSQL bằng các công cụ hỗ trợ của AWS.

* **Thực hành:**
  * Tạo và cấu hình cơ sở dữ liệu trên Amazon RDS.
  * Kết nối ứng dụng với Amazon RDS và Amazon Aurora.
  * Thực hiện sao lưu, khôi phục và kiểm tra khả năng phục hồi của cơ sở dữ liệu.
  * Thực hành chuyển đổi schema từ Oracle sang Aurora PostgreSQL.
  * Thực hiện di chuyển dữ liệu lên AWS và xác minh kết quả sau khi hoàn tất.
  * Rèn luyện khả năng lựa chọn dịch vụ cơ sở dữ liệu AWS phù hợp với từng loại ứng dụng và yêu cầu triển khai.