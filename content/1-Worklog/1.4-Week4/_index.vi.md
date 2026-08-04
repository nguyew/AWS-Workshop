---
title: "Worklog Tuần 4"
date: 2026-06-12
weight: 1
chapter: false
pre: " <b> 1.4. </b> "
---

### Mục tiêu tuần 4:

* Xây dựng nền tảng kiến thức về Amazon S3 và tìm hiểu các thành phần chính của dịch vụ lưu trữ đối tượng trên AWS.
* Khám phá các giải pháp lưu trữ, sao lưu và khôi phục dữ liệu nhằm đảm bảo tính sẵn sàng và an toàn cho hệ thống trên AWS.
* Tìm hiểu các phương pháp tối ưu hóa chi phí lưu trữ cũng như các chiến lược Disaster Recovery (DR) để nâng cao khả năng phục hồi khi xảy ra sự cố.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc                                                                                                                                                                                                                                                                                                                                                                                                 | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                                                     |
| --- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ------------------------------------------------------------------ |
| 2   | - Tìm hiểu Amazon Simple Storage Service (S3): <br>  + Bucket <br>  + Object <br>  + Object Key <br>  + Multipart Upload <br>  + Event Notification <br>  + Access Point <br> - **Thực hành:** <br>  + Tạo S3 Bucket <br>  + Upload dữ liệu lên Amazon S3                                                                                                                                                 | 08/06/2026   | 08/06/2026      | https://cloudjourney.awsstudygroup.com/ <br> https://byvn.net/PcQc |
| 3   | - Tìm hiểu các lớp lưu trữ của Amazon S3: <br>  + S3 Standard <br>  + S3 Standard-IA <br>  + S3 Intelligent-Tiering <br>  + S3 One Zone-IA <br>  + Glacier <br>  + Deep Archive <br> - Tìm hiểu Lifecycle Policy và cơ chế quản lý vòng đời dữ liệu                                                                                                                                                       | 09/06/2026   | 09/06/2026      | https://cloudjourney.awsstudygroup.com/ <br> https://byvn.net/PcQc |
| 4   | - Tìm hiểu Static Website Hosting trên Amazon S3 <br> - Tìm hiểu CORS (Cross-Origin Resource Sharing) <br> - Tìm hiểu cơ chế kiểm soát truy cập: <br>  + ACL <br>  + Bucket Policy <br>  + IAM Policy <br> - Tìm hiểu VPC Endpoint và S3 Versioning                                                                                                                                                       | 10/06/2026   | 10/06/2026      | https://cloudjourney.awsstudygroup.com/ <br> https://byvn.net/PcQc |
| 5   | - Tìm hiểu các giải pháp lưu trữ và di chuyển dữ liệu: <br>  + Snowball <br>  + Snowball Edge <br>  + Snowmobile <br> - Tìm hiểu AWS Storage Gateway: <br>  + File Gateway <br>  + Volume Gateway <br>  + Tape Gateway <br> - **Thực hành:** <br>  + Tạo Storage Gateway <br>  + Cấu hình File Sharing                                                                                                    | 11/06/2026   | 11/06/2026      | https://cloudjourney.awsstudygroup.com/ <br> https://byvn.net/PcQc |
| 6   | - Tìm hiểu Disaster Recovery trên AWS: <br>  + RTO (Recovery Time Objective) <br>  + RPO (Recovery Point Objective) <br>  + Backup & Restore <br>  + Pilot Light <br>  + Low Capacity Active <br>  + Full Capacity Active <br> - Tìm hiểu AWS Backup: <br>  + Backup Plan <br>  + Notification <br>  + Backup Monitoring <br> - **Thực hành:** <br>  + Tạo Backup Plan <br>  + Kiểm tra hoạt động sao lưu | 12/06/2026   | 12/06/2026      | https://cloudjourney.awsstudygroup.com/ <br> https://byvn.net/PcQc |


### Kết quả đạt được tuần 4:

* Xây dựng nền tảng kiến thức về Amazon S3 và hiểu cách dữ liệu được tổ chức, quản lý thông qua Bucket và Object.

* Tìm hiểu các tính năng nổi bật của Amazon S3, bao gồm:

  * Object Key
  * Multipart Upload
  * Event Notification
  * Access Point

* Nắm được đặc điểm và mục đích sử dụng của các Storage Class trong Amazon S3:

  * S3 Standard
  * S3 Standard-IA
  * S3 Intelligent-Tiering
  * S3 One Zone-IA
  * Glacier
  * Deep Archive

* Hiểu cách áp dụng Lifecycle Policy để tự động quản lý dữ liệu và tối ưu chi phí lưu trữ theo từng giai đoạn.

* Tìm hiểu quy trình triển khai và vận hành Static Website Hosting bằng Amazon S3.

* Nắm được nguyên lý hoạt động của CORS và cách áp dụng trong các ứng dụng web khi truy cập tài nguyên trên Amazon S3.

* Khám phá các cơ chế kiểm soát quyền truy cập đối với dữ liệu trên Amazon S3, bao gồm:

  * Access Control List (ACL)
  * Bucket Policy
  * IAM Policy

* Hiểu vai trò của VPC Endpoint trong việc thiết lập kết nối riêng tư và an toàn đến Amazon S3 thông qua mạng nội bộ của AWS.

* Tìm hiểu tính năng Versioning để bảo vệ dữ liệu và hỗ trợ khôi phục khi xảy ra xóa nhầm hoặc ghi đè ngoài ý muốn.

* Khám phá các giải pháp di chuyển dữ liệu dung lượng lớn của AWS, bao gồm:

  * AWS Snowball
  * AWS Snowball Edge
  * AWS Snowmobile

* Tìm hiểu kiến trúc lưu trữ kết hợp (Hybrid Storage) với AWS Storage Gateway, bao gồm:

  * File Gateway
  * Volume Gateway
  * Tape Gateway

* Nắm vững các khái niệm cốt lõi trong Disaster Recovery (DR), bao gồm:

  * Recovery Time Objective (RTO)
  * Recovery Point Objective (RPO)

Tìm hiểu các chiến lược khôi phục sau thảm họa trên AWS, bao gồm:

  * Backup & Restore
  * Pilot Light
  * Low Capacity Active
  * Full Capacity Active

* Tìm hiểu cách sử dụng AWS Backup để tự động hóa, quản lý và giám sát các tác vụ sao lưu dữ liệu.

* Hoàn thành các bài thực hành như:

  * Tạo và cấu hình Amazon S3 Bucket
  * Tải lên và quản lý dữ liệu trên Amazon S3
  * Triển khai Static Website trên Amazon S3
  * Cấu hình AWS Storage Gateway
  * Thiết lập Backup Plan
  * Theo dõi và xác minh quá trình sao lưu

* Phát triển khả năng lựa chọn giải pháp lưu trữ, sao lưu và khôi phục dữ liệu phù hợp với từng yêu cầu triển khai và vận hành hệ thống trên nền tảng AWS.