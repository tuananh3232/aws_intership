---
title: "Worklog Tuần 2"
date: "2025-09-19"
weight: 2
chapter: false
pre: " <b> 1.2. </b> "
---



### Mục tiêu tuần 2:

* Tìm hiểu về Amazon VPC, các thành phần chính như Subnet, Internet Gateway, Nat Gateway.
* Tìm hiểu về các khái niệm bảo mật như Security Group, NACL.
* Làm quen với các thao tác tạo EC2 và các thiết lập mạng cơ bản.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc                                                                                                                                                                                                                             | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                                                                                                                                                               |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 2   | - Xem các video lý thuyết của module 2 để có cái nhìn tổng quan về vpc <br> - Định nghĩa các khái niệm như Subnet, Route Table, Internet Gateway, NAT Gateway, Security Group và NACL <br> - Hệ thống lại mô hình VPC                 | 15/09/2025   | 15/09/2025      | <https://youtu.be/O9Ac_vGHquM?si=wDWqr_lJUjK2csDt> <br> <br> <https://youtu.be/BPuD1l2hEQ4?si=Qaig6saCCVKiqe0H> <br> <br> <https://youtu.be/CXU8D3kyxIc?si=TiZqHi0uB5mCif3L> |
| 3   | - **Thực hành:** <br>&emsp; + Create VPC <br>&emsp; + Create Subnet <br>&emsp; + Route Table cho public subnet <br>&emsp; + Internet Gateway và kết nối vào VPC <br>&emsp; + Kiểm tra lại bảng route để confirm IGW đã hoạt động <br> | 16/09/2025   | 16/09/2025      | <https://000003.awsstudygroup.com>                                                                                                                                           |
| 4   | - Tìm hiểu Security Group trong VPC <br> - Tìm hiểu NACL <br> - Kiểm tra rule inbound/outbound của Security Group <br> - Kiểm tra rule Network ACL trong subnet                                                                       | 17/09/2025   | 17/09/2025      | <https://000003.awsstudygroup.com>                                                                                                                                           |
| 5   | - **Thực hành:** <br>&emsp; + Create EC2 trong public subnet <br>&emsp; + Tạo key pair để kết nối EC2 <br>&emsp; + Kiểm tra Security Group của EC2 <br>&emsp; + Kiểm tra Route Table và subnet mapping của EC2                        | 18/09/2025   | 18/09/2025      | <https://000003.awsstudygroup.com>                                                                                                                                           |
| 6   | - **Thực hành:** <br>&emsp; + Kiểm tra kết nối SSH vào EC2 <br>&emsp; + Kiểm tra lần cuối Security Group <br> - Tổng hợp lại phần lý thuyết đã học của Module 2                                                                       | 19/09/2025   | 19/09/2025      | <https://000003.awsstudygroup.com>                                                                                                                                           |


### Kết quả đạt được tuần 2:

* Tổng quát: 
  * Trong tuần này tôi làm quen với các khái niệm cơ bản của mạng trong AWS và cách tạo một VPC đơn giản. Chủ yếu hiểu VPC dùng để tạo môi trường riêng trong AWS và nắm được cách chia subnet, gắn IGW, route, security
  

* Lý thuyết đã học:
  * Tổng quan VPC và cách VPC hoạt động trong AWS
  * Subnet (Public / Private) và cách phân chia mạng con
  * Internet Gateway & Route Table
  * Security Group & Network ACL
  * VPC Peering, VPN, Direct Connect

* Thực hành với bài lab:
  * Làm quen với thao tác tạo VPC
  * Tạo subnet theo mô hình lab, phân loại public/private
  * Tạo và gán Internet Gateway cho VPC
  * Tạo Route Table và cấu hình route cho subnet
  * Kiểm tra lại cấu trúc VPC sau khi tạo



