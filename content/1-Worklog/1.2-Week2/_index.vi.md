---
title: "Worklog Tuần 2"
date: 2026-05-29
weight: 1
chapter: false
pre: " <b> 1.2. </b> "
---

### Mục tiêu tuần 2:

* Xây dựng nền tảng kiến thức về kiến trúc mạng trên AWS thông qua Amazon VPC.
* Thực hành triển khai và cấu hình các thành phần mạng cốt lõi như Subnet, Route Table, Internet Gateway, NAT Gateway và Security Group.
* Tìm hiểu các giải pháp kết nối mạng cũng như dịch vụ cân bằng tải trên AWS nhằm nâng cao khả năng sẵn sàng và hiệu suất của hệ thống.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc                                                                                                                                                                                   | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                            |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | ------------ | ----------------------------------------- |
| 2   | - Tìm hiểu Amazon VPC và các khái niệm cơ bản:        <br>&emsp; + VPC  <br>&emsp; + CIDR Block <br>&emsp; + Available Zone  <br>&emsp; + Subnet <br> - Tìm hiểu Public Subnet và Private Subnet                                                                                      | 25/05/2026   | 25/05/2026      |<https://cloudjourney.awsstudygroup.com/> <br> <https://byvn.net/PcQc> | 
| 3   | - Tìm hiểu cơ chế định tuyến trong VPC: <br>&emsp; + Route Table <br>&emsp; + Internet Gateway <br>&emsp; + NAT Gateway <br> - **Thực hành:**    <br>&emsp; + Tạo VPC    <br>&emsp; + Tạo Public Subnet và Private Subnet  <br>&emsp; + Cấu hình Route Table                                | 26/05/2026   | 26/05/2026      | <https://cloudjourney.awsstudygroup.com/> <br> <https://byvn.net/PcQc>|
| 4   | - Tìm hiểu các thành phần mạng trong VPC:  <br>&emsp; + Elastic Network Interface (ENI)   <br>&emsp; + Elastic IP Address (EIP) <br>&emsp; + VPC Endpoint <br> - Tìm hiểu bảo mật mạng với Security Group và NACL <br> - **Thực hành:** <br>&emsp; + Cấu hình Security Group <br>&emsp; + Cấu hình Network ACL | 27/05/2026    | 27/05/2026       | <https://cloudjourney.awsstudygroup.com/> <br> <https://byvn.net/PcQc> |
| 5   | - Tìm hiểu VPC Flow Logs và giám sát lưu lượng mạng <br> - Tìm hiểu các phương thức kết nối mạng: <br>&emsp; + VPC Peering <br>&emsp; + Transit Gateway <br>&emsp; + Site-to-Site VPN <br>&emsp; + Client VPN  <br>&emsp; + Direct Connect           | 28/05/2026   | 28/05/2026      | <https://cloudjourney.awsstudygroup.com/> <br> <https://byvn.net/PcQc> |
| 6   | - Tìm hiểu Elastic Load Balancing (ELB) <br> - Phân biệt các loại Load Balancer: <br>&emsp; + Application Load Balancer (ALB) <br>&emsp; + Network Load Balancer (NLB) <br>&emsp; + Classic Load Balancer (CLB) <br>&emsp; + Gateway Load Balancer (GWLB) <br> - **Thực hành:** <br>&emsp; + Triển khai và kiểm thử Load Balancer                                                                                        | 29/05/2026   | 29/05/2026      | <https://cloudjourney.awsstudygroup.com/> <br> <https://byvn.net/PcQc> |


### Kết quả đạt được tuần 2:

* Xây dựng nền tảng kiến thức về kiến trúc mạng trên AWS và hiểu vai trò của Amazon VPC trong việc tạo ra môi trường mạng riêng, an toàn và linh hoạt trên nền tảng đám mây.

* Tìm hiểu các thành phần cốt lõi của Amazon VPC, bao gồm:
  
  * VPC
  * Subnet
  * Route Table
  * Internet Gateway
  * NAT Gateway
  * VPC Endpoint
  
* Nắm được nguyên tắc thiết kế và triển khai Public Subnet và Private Subnet nhằm đáp ứng các yêu cầu kết nối và bảo mật trong môi trường AWS.

* Tìm hiểu cơ chế định tuyến và các thành phần hỗ trợ kết nối mạng trên AWS, bao gồm:

  * Route Table
  * Internet Gateway
  * NAT Gateway
  * Elastic Network Interface (ENI)
  * Elastic IP Address (EIP)

* Nâng cao hiểu biết về các giải pháp bảo mật mạng trên AWS thông qua:

  * Security Group
  * Network Access Control List (NACL)
  * VPC Flow Logs

* Khám phá các phương thức kết nối mạng giữa các VPC và giữa AWS với hệ thống bên ngoài, bao gồm:

  *VPC Peering
  * AWS Transit Gateway
  *AWS Site-to-Site VPN
  *AWS Client VPN
  *AWS Direct Connect

* Tìm hiểu nguyên lý hoạt động của Elastic Load Balancing (ELB) và vai trò của dịch vụ này trong việc nâng cao tính sẵn sàng, hiệu năng và khả năng mở rộng của ứng dụng.

*Phân biệt đặc điểm, ưu điểm và trường hợp sử dụng của các loại Load Balancer trên AWS:

  * Application Load Balancer (ALB)
  * Network Load Balancer (NLB)
  * Classic Load Balancer (CLB)
  * Gateway Load Balancer (GWLB)

* Hoàn thành các bài thực hành triển khai và cấu hình VPC, Subnet, Route Table, Security Group, Network ACL (NACL) và Load Balancer để củng cố kiến thức thực tế.

* Phát triển kỹ năng thiết kế, triển khai và quản lý một kiến trúc mạng AWS cơ bản, đáp ứng các yêu cầu về kết nối, bảo mật, hiệu suất và khả năng mở rộng.


