---
title: "Worklog Tuần 9"
date: "2025-11-07"
weight: 9
chapter: false
pre: " <b> 1.9. </b> "
---



### Mục tiêu tuần 9:

Hiểu kiến trúc AWS Serverless và xác định các thành phần cần quản lý ở tầng hạ tầng.

Thiết kế kiến trúc triển khai ứng dụng (Backend, Frontend, Auth, Edge Security) ở góc nhìn DevOps.

Tìm hiểu và thiết kế lớp bảo mật: CloudFront, Route 53, AWS WAF, API protection.

Nghiên cứu Cognito để tích hợp vào Authentication/Authorization pipeline.

Nắm quy trình CI/CD với CodePipeline, CodeBuild, GitLab Runner và hạ tầng IaC với CloudFormation.

Thiết lập cơ chế giám sát – quan sát: CloudWatch Log/Metrics, X-Ray, SNS Alerts.
  
### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc                                                                                                  | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | ---------------------------------------------------------------------------------------------------------- | ------------ | --------------- | -------------- |
| 2   | - Phân tích kiến trúc Serverless                     | 03/11/2025   | 03/11/2025      |
|     | - Cách vận hành API Gateway – Lambda – DynamoDB từ góc nhìn DevOps                     | 03/11/2025   | 03/11/2025      |
| 3   | - Thiết kế kiến trúc tổng thể (Infrastructure Level)                     | 03/11/2025   | 03/11/2025      |
|     | - Xác định deployment flow & môi trường chạy           | 04/11/2025   | 04/11/2025      |
|     |
| 4   | - Thiết kế lớp bảo mật Edge (CloudFront + WAF + Route 53)                         | 05/11/2025   | 05/11/2025      |                |
| 5   | - Tìm hiểu cơ chế Cognito Tokens                 | 06/11/2025   | 06/11/2025      |                |
| 6   | - Thiết kế CI/CD Pipeline (GitLab → AWS) | 07/11/2025   | 07/11/2025      |                |


### Kết quả đạt được tuần 9:

* Tổng quát:
  * Tuần này tập trung vào việc phân tích và thiết kế hạ tầng Serverless, đảm bảo các thành phần ứng dụng có thể được quản lý, giám sát và triển khai tự động. Tôi đã hiểu rõ cách API Gateway, Lambda và DynamoDB phối hợp từ góc độ DevOps: scaling, logging, retry, throttling, bảo mật và CI/CD pipeline.
    
  * Lý thuyết đã học:
    * Mô hình event-driven, autoscaling tự động.  
    * Hiểu trách nhiệm DevOps: logging, tracing, bảo mật, structure IAM.
    * Cách DevOps quản lý version, deployment, stage variables. 
    * CloudFront → WAF → API Gateway cách bảo vệ API.
    * CodePipeline + CodeBuild + CloudFormation.


  * Thực hành / Sản phẩm:
    * Thiết kế sơ đồ kiến trúc hạ tầng Serverless đầy đủ.
    * Xây dựng diagram flow request từ FE → CloudFront → WAF → API Gateway → Lambda → DynamoDB.
    * Vẽ pipeline deploy: GitLab CI/CD → AWS CLI → Lambda
                          GitLab → S3 + CloudFront
    * Thiết kế DevOps Auth flow: Cognito → Authorizer → API Gateway.
