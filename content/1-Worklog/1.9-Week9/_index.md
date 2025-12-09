---
title: "Week 9 Worklog"
date: "2025-11-07"
weight: 9
chapter: false
pre: " <b> 1.9. </b> "
---

### Week 9 Objectives

- Understand the AWS Serverless architecture and identify the infrastructure components that need to be managed.
- Design the application deployment architecture (Backend, Frontend, Auth, Edge Security) from a DevOps perspective.
- Research and design the security layer: CloudFront, Route 53, AWS WAF, and API protection.
- Study Amazon Cognito and its integration into the authentication/authorization pipeline.
- Understand the CI/CD workflow using CodePipeline, CodeBuild, GitLab Runner, and Infrastructure-as-Code (CloudFormation).
- Set up monitoring and observability mechanisms: CloudWatch Logs/Metrics, AWS X-Ray, SNS Alerts.

### Tasks to Be Completed This Week

| Day | Task                                                                          | Start Date | End Date   | Notes |
| --- | ----------------------------------------------------------------------------- | ---------- | ---------- | ----- |
| 2   | - Analyze Serverless architecture                                             | 03/11/2025 | 03/11/2025 |       |
|     | - Study how API Gateway – Lambda – DynamoDB operate from a DevOps perspective | 03/11/2025 | 03/11/2025 |       |
| 3   | - Design the overall architecture (Infrastructure Level)                      | 03/11/2025 | 03/11/2025 |       |
|     | - Define deployment flow and execution environments                           | 04/11/2025 | 04/11/2025 |       |
| 4   | - Design the Edge Security layer (CloudFront + WAF + Route 53)                | 05/11/2025 | 05/11/2025 |       |
| 5   | - Study Cognito Tokens and authentication flow                                | 06/11/2025 | 06/11/2025 |       |
| 6   | - Design the CI/CD Pipeline (GitLab → AWS)                                    | 07/11/2025 | 07/11/2025 |       |

### Week 9 Achievements

#### Overview
This week focused on analyzing and designing the Serverless infrastructure to ensure all application components can be properly managed, monitored, and automatically deployed. I gained a deep understanding of how API Gateway, Lambda, and DynamoDB interact from a DevOps standpoint, including scaling behavior, logging, retry mechanisms, throttling, security, and the CI/CD pipeline.

#### Topics Learned

- Event-driven Serverless model and automatic autoscaling.  
- DevOps responsibilities: logging, tracing, IAM structuring, and security.  
- Managing versions, deployments, and stage variables in API Gateway and Lambda.  
- Security architecture using CloudFront → WAF → API Gateway.  
- CI/CD automation with CodePipeline, CodeBuild, and CloudFormation.

#### Hands-on Work / Deliverables

- Designed a complete Serverless infrastructure architecture diagram.
- Built a request-flow diagram from FE → CloudFront → WAF → API Gateway → Lambda → DynamoDB.
- Created deployment pipeline designs:
  - GitLab CI/CD → AWS CLI → Lambda
  - GitLab → S3 + CloudFront
- Designed the DevOps authentication flow: Cognito → Authorizer → API Gateway.
