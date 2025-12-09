---
title: "Worklog Tuần 6"
date: "2025-10-17"
weight: 6
chapter: false
pre: " <b> 1.6. </b> "
---



### Mục tiêu tuần 6:

* Tìm hiểu tổng quan các dịch vụ lưu trữ trên AWS (S3, Glacier, Backup, Storage Gateway, Snow Family).
* Nắm rõ cách S3 hoạt động: access point, storage class, CORS, static website hosting.
* Thực hành toàn bộ quy trình với S3, Backup, Storage Gateway, File System.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                                                                                                                                                                                                                         |
| --- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 2   | - Tìm hiểu tổng quan các dịch vụ lưu trữ AWS: S3, EBS, Backup, Storage Gateway, Snow Family <br> - Tìm hiểu Access Point, Storage Class và các mô hình truy cập dữ liệu <br> - Nắm rõ S3 static website, CORS, Object key, Glacier                                                                                                                                                                                                                                                                                                                       | 13/10/2025   | 13/10/2025      | <https://youtu.be/hsCfP0IxoaM?si=O3vMWs7Trr1fugJD> <br><br> <https://youtu.be/_yunukwcAwc?si=ZhkTKr-_OkyUNImI> <br><br> <https://youtu.be/mPBjB6Ltl_Q?si=qs6j0n7AeD2Mxwbz> <br><br> <https://youtu.be/YXn8Q_Hpsu4?si=XojTnkR_LLC1KwEv> |
| 3   | **Thực hành:** <br>&emsp; + Create S3 bucket <br>&emsp; + Deploy hạ tầng backup <br>&emsp; + Create backup plan và set up notification <br>&emsp; + Test restore và Dọn dẹp tài nguyên backup                                                                                                                                                                                                                                                                                                                                                            | 14/10/2025   | 14/10/2025      | <https://000013.awsstudygroup.com>                                                                                                                                                                                                     |
| 4   | - Tìm hiểu VMware Workstation <br> - **Thực hành:** <br>&emsp; + Export VM từ on-prem <br>&emsp; + Upload VM lên AWS <br>&emsp; + Import thành EC2 <br>&emsp; + Export lại thành AMI <br>&emsp; + Dọn dẹp môi trường import/export                                                                                                                                                                                                                                                                                                                       | 15/10/2025   | 15/10/2025      | <https://000014.awsstudygroup.com>                                                                                                                                                                                                     |
| 5   | - **Thực hành:** <br>&emsp; + Create Storage Gateway <br>&emsp; + Create File Share nâng cao <br>&emsp; + kết nối File Share trên máy on-prem <br>&emsp; + Dọn dẹp Storage Gateway + File Shares                                                                                                                                                                                                                                                                                                                                                         | 16/10/2025   | 16/10/2025      | <https://000024.awsstudygroup.com>                                                                                                                                                                                                     |
| 6   | - **Thực hành(lab25):** <br>&emsp; + Create FSx file system (SSD/HDD, Multi-AZ) <br>&emsp; + Create và cấu hình file shares <br>&emsp; + Test và giám sát hiệu năng <br>&emsp; + Quản lý user sessions + quotas <br> - **Thực hành(lab57):** <br>&emsp; + Create bucket, upload dữ liệu, bật static website <br>&emsp; + Cấu hình public access + set quyền đối tượng <br>&emsp; + Create và cấu hình CloudFront phân phối nội dung<br>&emsp; + Enable versioning và replication object <br> - Dọn dẹp môi trường(lab25) bucket, CloudFront, replication | 17/10/2025   | 17/10/2025      | <https://000025.awsstudygroup.com> <br><br> <https://000057.awsstudygroup.com>                                                                                                                                                         |


### Kết quả đạt được tuần 6:
* Tổng quát: 
  * Trong tuần này, tôi đã nắm được tổng quan về hệ sinh thái lưu trữ của AWS, bao gồm S3, Glacier, AWS Backup, Storage Gateway và các loại file system. Tôi tập trung vào việc thực hành để hiểu rõ cách quản lý dữ liệu, cơ chế backup–restore và các mô hình lưu trữ phổ biến trên AWS.  
  

* Lý thuyết đã học:
  * Khái niệm về S3 Storage Classes, Access Point, và CORS configuration.

  * Tìm hiểu về Glacier, lifecycle policy và các khái niệm liên quan đến AWS Backup.

 * Kiến trúc và cơ chế hoạt động của AWS Storage Gateway và các loại file system trên AWS.

 * Cơ chế import/export máy ảo lên AWS.

  
* Thực hành với bài lab:
  * Backup & restore
  * Import máy ảo on-prem lên AWS
  * Tạo file system Multi-AZ
  * Xây dựng static website bằng S3, tích hợp CloudFront, bật versioning và replication.
  * Thực hành với Storage Gateway: tạo file share, kết nối thử và kiểm tra truyền dữ liệu giữa on-prem và AWS.