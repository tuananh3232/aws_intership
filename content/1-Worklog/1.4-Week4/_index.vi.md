---
title: "Worklog Tuần 4"
date: "2025-10-03"
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---


### Mục tiêu tuần 4:

* Tìm hiểu về triển khai mô hình VPC Peering giữa nhiều VPC.
* Tìm hiểu về cấu hình Transit Gateway để kết nối liên VPC ở quy mô lớn.
* Thực hành các lab nâng cao về routing, DNS giữa các VPC.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc                                                                                                                                                                                                 | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                     |
| --- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ---------------------------------- |
| 2   | - Tìm hiểu tổng quan VPC Peering: cơ chế hoạt động, giới hạn, cách route <br> - Tìm hiểu về khái niệm peering trong VPC                                                                                   | 29/09/2025   | 29/09/2025      | <https://000019.awsstudygroup.com> |
| 3   | - **Thực hành:** <br>&emsp; + Create EC2 trong các VPC, cấu hình route <br>&emsp; + Kiểm tra NACL, Security Group khi dùng peering <br>&emsp; + Hoàn thiện phần peering                                   | 30/09/2025   | 30/09/2025      | <https://000019.awsstudygroup.com> |
| 4   | - Tìm hiểu về Transit Gateway<br> - **Thực hành:** <br>&emsp; + Triển khai TGW <br>&emsp; + Setup routing giữa VPC và TGW                                                                                 | 01/10/2025   | 01/10/2025      | <https://000020.awsstudygroup.com> |
| 5   | - **Thực hành:** <br>&emsp; + Create Transit Gateway kết nối <br>&emsp; + Create TGW Route Table <br>&emsp; + Mapping route của VPC vào TGW <br>&emsp; + Kiểm tra lần cuối kết nối giữa nhiều VPC qua TGW | 02/10/2025   | 02/10/2025      | <https://000020.awsstudygroup.com> |
|     | - Dọn dẹp lại toàn bộ các resources của lab <br> - Hệ thống lại kiến thức Peering và Transit Gateway | 02/10/2025   | 02/10/2025      | <https://000020.awsstudygroup.com> |
| 6   |                                                                                                       | 03/10/2025   | 03/10/2025      | |


### Kết quả đạt được tuần 4:

* Tổng quát: 
  * Trong tuần này, tôi đã tìm hiểu các mô hình kết nối giữa nhiều VPC như VPC Peering và Transit Gateway. Qua đó, tôi nắm được cách thiết lập kết nối mạng giữa các VPC, cách định tuyến thông qua Transit Gateway, và hiểu rõ vai trò của từng thành phần trong kiến trúc multi-VPC.
  

* Lý thuyết đã học:
  * Nguyên lý hoạt động của VPC Peering và cơ chế định tuyến giữa hai VPC
  * Kiến trúc và chức năng của Transit Gateway (TGW) trong việc kết nối nhiều VPC theo mô hình hub-and-spoke
  * Cách cấu hình route table khi sử dụng Peering hoặc Transit Gateway để đảm bảo các mạng có thể giao tiếp đúng hướng.

  
* Thực hành với bài lab:
  * Thiết lập VPC Peering connection giữa các VPC và cập nhật route table để kích hoạt truyền thông liên VPC. 
  * Cấu hình Transit Gateway, tạo các TGW attachments, thiết lập route và kiểm tra định tuyến.
  * Kiểm thử khả năng giao tiếp giữa các subnet và các VPC sau khi hoàn tất cấu hình.