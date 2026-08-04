---
title: "Worklog Tuần 3"
date: 2026-05-06
weight: 1
chapter: false
pre: " <b> 1.3. </b> "
---

### Mục tiêu tuần 3:

* Xây dựng kiến thức nền tảng về Amazon EC2 và tìm hiểu các thành phần quan trọng của dịch vụ máy chủ ảo trên AWS.
* Nghiên cứu quy trình triển khai, khởi tạo và quản lý EC2 Instance thông qua Amazon Machine Image (AMI).
* Khám phá các giải pháp lưu trữ dành cho EC2, bao gồm Amazon Elastic Block Store (EBS) và Instance Store, đồng thời hiểu rõ đặc điểm và trường hợp sử dụng của từng loại.
* Tìm hiểu các cơ chế sao lưu dữ liệu, phương thức xác thực truy cập an toàn và các dịch vụ hỗ trợ tự động mở rộng tài nguyên nhằm nâng cao tính sẵn sàng và khả năng mở rộng của hệ thống AWS.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc                                                                                                                                                                                                                                                                                                           | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                                                     |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ------------------------------------------------------------------ |
| 2   | - Tìm hiểu Amazon Elastic Compute Cloud (EC2) và các khái niệm cơ bản: <br>  + EC2 Instance <br>  + Elasticity <br>  + Instance Type <br>  + CPU / GPU <br>  + Memory <br>  + Network <br>  + Storage                                                                                                               | 01/06/2026   | 01/06/2026      | https://cloudjourney.awsstudygroup.com/ <br> https://byvn.net/PcQc |
| 3   | - Tìm hiểu kiến trúc EC2: <br>  + Hardware Node <br>  + Hypervisor <br>  + Nitro System <br>  + HVM <br>  + Paravirtualization (PV) <br> - Tìm hiểu Amazon Machine Image (AMI): <br>  + Root Volume <br>  + Permission <br>  + Block Device Mapping                                                                 | 02/06/2026   | 02/06/2026      | https://cloudjourney.awsstudygroup.com/ <br> https://byvn.net/PcQc |
| 4   | - Tìm hiểu Snapshot và cơ chế Backup EC2 <br> - Tìm hiểu Key Pair và cơ chế xác thực EC2 <br>  + Public Key <br>  + Private Key <br>  + SSH <br>  + Remote Desktop <br> - **Thực hành:** <br>  + Tạo EC2 Instance <br>  + Tạo Key Pair                                                                              | 03/06/2026   | 03/06/2026      | https://cloudjourney.awsstudygroup.com/ <br> https://byvn.net/PcQc |
| 5   | - Tìm hiểu Elastic Block Store (EBS): <br>  + SSD Volume <br>  + HDD Volume <br>  + EBS Snapshot <br>  + EBS Multi-Attach <br>  + Backup dữ liệu lên Amazon S3 <br> - Tìm hiểu Instance Store: <br>  + NVMe Storage <br>  + Temporary Storage <br> - So sánh EBS và Instance Store                                  | 04/06/2026   | 04/06/2026      | https://cloudjourney.awsstudygroup.com/ <br> https://byvn.net/PcQc |
| 6   | - Tìm hiểu User Data và Metadata <br>  + User Data Script <br>  + EC2 Metadata <br> - Tìm hiểu EC2 Auto Scaling <br>  + Scale Out <br>  + Scale In <br>  + Tích hợp Elastic Load Balancer <br> - Tìm hiểu các dịch vụ AWS liên quan: <br>  + Amazon Lightsail <br>  + Amazon EFS <br>  + Amazon FSx <br>  + AWS MGN | 05/06/2026   | 05/06/2026      | https://cloudjourney.awsstudygroup.com/ <br> https://byvn.net/PcQc |


### Kết quả đạt được tuần 3:

* Xây dựng nền tảng kiến thức về Amazon EC2 và hiểu vai trò của dịch vụ này trong việc triển khai, vận hành và quản lý ứng dụng trên nền tảng AWS. 

* Tìm hiểu các thành phần cấu hình quan trọng của một EC2 Instance, bao gồm:
  * CPU / GPU
  * Bộ nhớ (Memory)
  * Mạng (Network)
  * Lưu trữ (Storage)

* Nắm được kiến trúc hoạt động của Amazon EC2, bao gồm:

  * Hardware Node
  * Hypervisor
  * AWS Nitro System
  * Hardware Virtual Machine (HVM)
  * Paravirtualization (PV)

* Khám phá chức năng của Amazon Machine Image (AMI) và cách sử dụng AMI để triển khai, quản lý EC2 Instance, bao gồm:
  
  * Root Volume
  * Image Permissions
  * Block Device Mapping

* Hiểu quy trình tạo nhiều EC2 Instance từ cùng một AMI nhằm đảm bảo tính đồng nhất trong quá trình triển khai.

* Tìm hiểu cơ chế Snapshot và các phương pháp sao lưu dữ liệu để hỗ trợ khôi phục hệ thống khi xảy ra sự cố.

* Nắm được các phương thức xác thực và bảo mật khi truy cập EC2 thông qua:
  
  * Public Key
  * Private Key
  * Key Pair

* Tìm hiểu các tính năng của Amazon Elastic Block Store (EBS), bao gồm:
  
  * SSD Volume
  * HDD Volume
  * Snapshot
  * EBS Multi-Attach

* So sánh sự khác biệt giữa Amazon EBS và Instance Store, đồng thời đánh giá ưu điểm, hạn chế và trường hợp sử dụng phù hợp của từng giải pháp lưu trữ.

* Tìm hiểu cách sử dụng User Data để tự động hóa quá trình cài đặt và cấu hình EC2 Instance ngay khi khởi tạo.

* Hiểu vai trò của EC2 Instance Metadata trong việc cung cấp thông tin cấu hình và trạng thái của máy chủ.

* Nắm được nguyên lý hoạt động của EC2 Auto Scaling, bao gồm:
  
  * Tự động mở rộng số lượng EC2 Instance khi nhu cầu sử dụng tăng.
  * Tự động thu hẹp số lượng EC2 Instance khi lưu lượng giảm để tối ưu chi phí.
  * Kết hợp với Elastic Load Balancer (ELB) nhằm phân phối lưu lượng và nâng cao tính sẵn sàng của hệ thống.

* Mở rộng kiến thức về một số dịch vụ AWS liên quan, bao gồm:
  
  * Amazon Lightsail
  * Amazon Elastic File System (EFS)
  * Amazon FSx
  * AWS Application Migration Service (AWS MGN)

* Hoàn thành các bài thực hành về triển khai EC2 Instance, quản lý Key Pair và cấu hình các giải pháp lưu trữ trên AWS.

* Phát triển khả năng lựa chọn cấu hình EC2, giải pháp lưu trữ và chiến lược mở rộng phù hợp với từng yêu cầu triển khai và vận hành ứng dụng trên nền tảng AWS.


