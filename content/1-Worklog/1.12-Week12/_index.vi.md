---
title: "Worklog Tuần 12"
date: "2025-11-28"
weight: 12"
chapter: false
pre: " <b> 1.12. </b> "
---

### Mục tiêu tuần 12 (Nền tảng DevOps trước khi triển khai AWS)

Sau khi hoàn thành backend local ở tuần 10 và tích hợp FE–BE ở tuần 11,  
tuần 12 tập trung xây dựng kiến thức nền tảng AWS để chuẩn bị cho các tuần triển khai thực tế (Lambda, API Gateway, DynamoDB, CloudFront).

Mục tiêu gồm:

- Hiểu các dịch vụ AWS cốt lõi sẽ dùng trong triển khai TaskHub.
- Thiết lập tài khoản AWS Free Tier + IAM đúng chuẩn DevOps.
- Làm quen giao diện AWS Console & AWS CLI.
- Học kiến thức compute/networking cơ bản để hiểu kiến trúc cloud trước khi chuyển sang serverless.

---

### Các công việc triển khai trong tuần

| Thứ | Công việc                                                                                                                 | Bắt đầu    | Hoàn thành |
| --- | ------------------------------------------------------------------------------------------------------------------------- | ---------- | ---------- |
| 2   | - Onboarding cùng thành viên FCJ <br> - Nắm quy định và workflow DevOps trong dự án                                       | 08/11/2025 | 08/11/2025 |
| 3   | - Học nhóm dịch vụ AWS: Compute, Storage, Networking, Database, IAM <br> - Liên kết các dịch vụ này với kiến trúc TaskHub | 08/12/2025 | 08/12/2025 |
| 4   | - Tạo tài khoản AWS Free Tier <br> - Cài đặt & cấu hình AWS CLI <br> - Thực hành truy vấn tài nguyên qua CLI              | 08/13/2025 | 08/13/2025 |
| 5   | - Học EC2: AMI, Instance Types, EBS, Security Groups, Elastic IP <br> - Nắm các khái niệm networking cloud (VPC/Subnets)  | 08/14/2025 | 08/15/2025 |
| 6   | - Thực hành: Launch EC2, SSH kết nối, attach EBS volume <br> - So sánh quy trình Console vs CLI dưới góc nhìn DevOps      | 08/15/2025 | 08/15/2025 |

---

### Kết quả đạt được tuần 12

#### Tổng quát
Tiếp nối tuần 10 (xây dựng backend local) và tuần 11 (FE–BE integration),  
tuần 12 giúp tôi nắm vững kiến thức AWS nền tảng để sẵn sàng triển khai backend lên AWS ở tuần 13.

Tôi đã hiểu cách AWS tổ chức dịch vụ, cách DevOps vận hành tài nguyên qua Console/CLI,  
và chuẩn bị môi trường đầy đủ để bước vào giai đoạn deploy thực tế.

---

### Lý thuyết đã học

- **Kiến thức AWS cơ bản dành cho DevOps**
  - Compute, Storage, Networking, Database, IAM.
  - Liên hệ EC2/VPC với kiến trúc serverless (Lambda, API Gateway).

- **Thiết lập tài khoản & IAM**
  - Tạo tài khoản Free Tier.
  - Cấu hình IAM user + Access Key/Secret Key.
  - Thiết lập region mặc định cho AWS CLI.

- **Sử dụng AWS CLI**
  - Kiểm tra cấu hình tài khoản.
  - Liệt kê region, dịch vụ, thông tin EC2.
  - Tạo và quản lý key pair.
  - Làm quen workflow DevOps qua CLI.

- **Thực hành EC2**
  - Launch EC2 instance.
  - SSH vào máy ảo.
  - Gắn & quản lý EBS volume.
  - Hiểu vòng đời compute trong cloud trước khi chuyển sang serverless.

---

### Thực hành / Sản phẩm

- Hoàn chỉnh tài khoản AWS + IAM cho DevOps.
- AWS CLI sẵn sàng dùng cho pipeline triển khai.
- Thực hành EC2 để hiểu compute trước khi làm Lambda.
- Bộ ghi chú nền tảng chuẩn bị cho triển khai tuần 13.
