---
title: "Worklog Tuần 3"
date: "2025-09-26"
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---

### Mục tiêu tuần 3:

* Tìm hiểu về EC2 trong VPC.
* Nắm bắt NAT Gateway & Security.
* Tìm hiểu về set up DNS và route 53.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc                                                                                                                                                                                                                                                              | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                                                                                                                                                               |
| --- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 2   | - Tổng quát lý thuyết về EC2 trong VPC và NAT Gateway <br> - Hệ thống lại flow Public subnet, Private subnet -> NAT -> IGW <br> - Tóm tắt lại cách NAT hoạt động tập                                                                                                   | 22/09/2025   | 22/09/2025      | <https://youtu.be/N58agSU4O8o?si=QVRiT5MDt9VN5el4> <br> <br> <https://youtu.be/B1qxOQLmavQ?si=3ALVG-HGI0sbL8bM> <br> <br> <https://youtu.be/GVDsDu9dOFY?si=ki8qJYmPxwxLgYxd> |
| 3   | - **Thực hành:**   <br>&emsp; + Create EC2 trong public subnet <br>&emsp; + Kiểm tra lại Security Group <br>&emsp; + Kiểm tra lại subnet mapping + Route Table <br>&emsp; + Kiểm tra tiến trình EC2 Instance Connect<br>                                               | 23/09/2025   | 23/09/2025      | <https://000003.awsstudygroup.com>                                                                                                                                           |
| 4   | - **Thực hành:**   <br>&emsp; + Create NAT Gateway <br>&emsp; + Kiểm tra route của private subnet <br>&emsp; + Ping outbound từ private subnet và kiểm tra xem NAT có hoạt động không                                                                                  | 24/09/2025   | 24/09/2025      | <https://000003.awsstudygroup.com>                                                                                                                                           |
| 5   | - Tìm hiểu về Hybrid DNS với Route 53 <br> - **Thực hành:** <br>&emsp; + Tạo key pair <br>&emsp; + Create template bằng CloudFormation                                                                                                                                 | 25/09/2025   | 25/09/2025      | <https://000010.awsstudygroup.com>                                                                                                                                           |
| 6   | - **Thực hành:** <br>&emsp; + Cấu hình Security Group <br>&emsp; + Kết nối RDGW <br>&emsp; + Tạo Outbound, InBound Endpoint <br>&emsp; + Tạo Resolver Rules và test DNS <br> - Dọn dẹp lại toàn bộ các resources của lab <br> - Tổng hợp lại lý thuyết EC2 - NAT - DNS | 26/09/2025   | 26/09/2025      | <https://000010.awsstudygroup.com>                                                                                                                                           |


### Kết quả đạt được tuần 3:

* Tổng quát: 
  * Trong tuần này tôi đã tìm hiểu và vận hành EC2 trong kiến trúc VPC, hiểu mô hình public/private subnet, NAT Gateway và cách security hoạt động. Thực hành nhiều với EC2 và các cấu hình mạng
  

* Lý thuyết đã học:
  * Cách EC2 liên kết với subnet, route table, SG
  * NAT Gateway hoạt động khi private subnet cần Internet
  * Cách Security Group kiểm soát traffic inbound/outbound
  * NACL lọc traffic theo subnet
  * DNS Resolver và cách Route 53 xử lý hybrid DNS
  
* Thực hành với bài lab:
  * Tạo EC2 theo từng loại subnet
  * Test connect bằng EC2 Instance Connect
  * Tạo NAT Gateway + kiểm tra outbound
  * Tiếp tục làm cho quen tay các thao tác bằng bài lab DNS
  