---
title: "Event 4"
date: "2025-11-16"
weight: 4
chapter: false
pre: " <b> 4.4. </b> "
---
# Bài Thu Hoạch Workshop "AWS Cloud Mastery Series #2: DevOps on AWS"

### Mục Đích Của Sự Kiện
- Cung cấp cái nhìn toàn diện về văn hóa, nguyên tắc và thực hành DevOps trên nền tảng AWS.
- Hướng dẫn xây dựng pipeline CI/CD hoàn chỉnh từ source control đến deployment tự động.
- Giới thiệu các công cụ Infrastructure as Code (IaC) chính trên AWS và cách áp dụng chúng.
- Trang bị kiến thức về containerization, observability và các best practices để vận hành hệ thống ổn định.

### Diễn Giả / Người Hướng Dẫn Chính (Dự kiến)
- **Anh Đỗ Huy Thắng** – DevOps Lead, VNG  
- **Chị Nguyễn Thị Thu Hà** – Sr. DevOps Engineer, AWS  
- **Anh Phạm Tuấn Anh** – Solutions Architect, AWS  

---

### Nội Dung Nổi Bật & Bài Học Chính

#### 1. Văn Hóa & Nguyên Tắc DevOps
- DevOps không chỉ là công cụ mà là **văn hóa hợp tác** giữa Development và Operations.
- Các chỉ số DORA (Deployment Frequency, Lead Time, MTTR, Change Failure Rate) là **thước đo hiệu quả DevOps**.
- **Shift-left Testing & Security** giúp phát hiện lỗi sớm và giảm chi phí fix bugs.

#### 2. CI/CD Pipeline Trên AWS
- Bộ công cụ AWS DevTools (CodeCommit, CodeBuild, CodeDeploy, CodePipeline) hỗ trợ **tự động hóa hoàn toàn** quá trình release.
- Các chiến lược triển khai: **Blue/Green**, **Canary**, **Rolling Update**.
- Demo pipeline: từ commit → build → test → deploy lên EC2/ECS.

#### 3. Infrastructure as Code (IaC)
- **AWS CloudFormation**: IaC dạng declarative với YAML/JSON.
- **AWS CDK**: IaC dạng imperative sử dụng Python, TypeScript → dễ mở rộng & tái sử dụng.
- **Drift Detection** đảm bảo hạ tầng khớp với cấu hình định nghĩa.

#### 4. Container & Microservices
- Docker giúp đóng gói ứng dụng nhẹ, độc lập, dễ deploy.
- So sánh **ECS vs EKS** để chọn công cụ phù hợp.
- **AWS App Runner**: deploy container dạng serverless, ít quản lý.

#### 5. Monitoring & Observability
- **Amazon CloudWatch**: thu thập metrics, logs, alarms, dashboards.
- **AWS X-Ray**: tracing request xuyên suốt các microservices.
- Best practices: alert meaningful, dashboard theo SLO, quy trình postmortem.

---

### Những Gì Học Được (Takeaways)

#### Về Tư Duy & Văn Hóa
- DevOps là hành trình liên tục cải tiến.
- Tự động hóa là cốt lõi của DevOps.
- Hướng tiếp cận “blameless postmortem” để học từ lỗi.

#### Về Kỹ Thuật
- CI/CD là thiết kế luồng deliver đáng tin cậy, không chỉ “chạy pipeline”.
- IaC mang lại tính nhất quán, kiểm soát version và khả năng tái tạo môi trường.
- Observability giúp hiểu nguyên nhân gốc rễ sự cố.

#### Về Nghề Nghiệp
- DevOps Engineer cần kiến thức đa lĩnh vực: networking, coding, security, operations.
- Kỹ năng phân tích & debug hệ thống phân tán rất quan trọng.

---

### Kế Hoạch Hành Động Cá Nhân
1. Tự xây dựng pipeline CI/CD với CodeCommit & CodePipeline.  
2. Học và thử nghiệm AWS CDK với Python.  
3. Đóng gói ứng dụng nhỏ bằng Docker và deploy lên ECS Fargate.  
4. Tạo dashboard CloudWatch theo dõi ứng dụng demo.

---

### Trải Nghiệm Cá Nhân

Workshop DevOps mang lại nhiều kiến thức thực chiến mà developer thường ít tiếp xúc.  
**Phần demo CI/CD và IaC gây ấn tượng mạnh**, cho thấy cách tự động hóa giúp giảm rủi ro và tăng tốc độ release.  
Các case study từ VNG và AWS giúp em hiểu rõ tầm quan trọng của monitoring và văn hóa DevOps trong thực tế.

---

### Hình Ảnh
![event3](/images/event-image3.png)
![event4](/images/event-image4.png)
