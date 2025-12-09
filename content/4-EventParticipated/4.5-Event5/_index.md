---
title: "Event 5"
date: "2025-11-30"
weight: 5
chapter: false
pre: " <b> 4.5. </b> "
---

# Summary Report: "AWS Cloud Mastery Series #3: AWS Well-Architected – Security Pillar"

### Purpose of the Workshop
- Introduce the AWS Well-Architected Framework with a focus on the Security Pillar, the foundation of all AWS architectures.
- Provide practical knowledge on five key security domains: IAM, Detection, Infrastructure Protection, Data Protection, and Incident Response.
- Build a “Security by Design” mindset with core models such as Least Privilege, Zero Trust, and Defense in Depth.
- Share real-world best practices and lessons learned from enterprises in Vietnam.

### Speakers / Instructors (Expected)
- **Nguyễn Văn Tú** – Sr. Security Specialist Solutions Architect, AWS  
- **Lê Thị Thanh Mai** – Cloud Security Engineer, AWS Partner  
- **Đặng Quốc Bảo** – Security Lead, Fintech Company (Guest case study)

---

### Key Content & Learnings

#### 1. Foundational Security Mindset
- **Security is the first pillar** in every AWS architectural design.
- Core principles:
  - **Least Privilege** – minimal permissions assignment.
  - **Zero Trust** – never trust, always verify.
  - **Defense in Depth** – multiple layers of protection.
- The **Shared Responsibility Model** defines responsibilities between AWS and customers—understanding this boundary is critical.

#### 2. Pillar 1 – Identity & Access Management (IAM)
- Avoid **long-term credentials**; use IAM Roles for EC2, Lambda, and ECS.
- IAM Identity Center & SSO provide centralized access management.
- SCPs and Permission Boundaries enforce organization-wide guardrails.
- IAM Access Analyzer helps detect unintended public access.

#### 3. Pillar 2 – Detection & Continuous Monitoring
- Enable comprehensive logging: Organization CloudTrail, VPC Flow Logs, ALB Logs.
- GuardDuty detects suspicious activity; Security Hub aggregates findings.
- Detection-as-Code using AWS Config Rules ensures consistent policies.
- Automate alerts using Amazon EventBridge.

#### 4. Pillar 3 – Infrastructure Protection
- Secure network design using VPC segmentation (Public, Private, Data subnets).
- Understand Security Groups (stateful) vs NACLs (stateless).
- Protect applications using AWS WAF and AWS Shield.
- Implement OS hardening and IMDSv2 for EC2 instances.

#### 5. Pillar 4 – Data Protection
- Encryption is the default: KMS for S3, RDS, EBS, DynamoDB.
- Manage keys & secrets with KMS Key Policies and Secrets Manager.
- Classify data sensitivity and assign tags for appropriate access control.

#### 6. Pillar 5 – Incident Response
- Prepare playbooks for common security scenarios.
- Standard IR workflow: Contain → Eradicate → Recover → Analyze.
- Automate security actions using Lambda and Step Functions.

---

### Key Takeaways

#### Strategy & Mindset
- **Security is job zero**—security must be designed upfront.
- Apply risk-based prioritization to security efforts.
- Continuously measure and improve using metrics and Security Hub scores.

#### Technical Lessons
- Reduce attack surface by minimizing public resources.
- Encrypt everything by default.
- Automate security operations to minimize human error.

---

### Personal Action Plan
1. Review IAM policies and enforce Least Privilege.  
2. Enable GuardDuty and Security Hub on personal AWS accounts.  
3. Create a KMS key and encrypt an S3 bucket as practice.  
4. Study the Shared Responsibility Model deeper for services in current use.

---

### Personal Reflection

This workshop reshaped my understanding of cloud security.  
Security is no longer a mysterious topic—it becomes a **structured, logical framework** when broken into the five pillars.

The demo of IAM Policy Simulator and real Incident Response scenarios showed how modern security relies on **strict policy enforcement** combined with **automated workflows**.

The repeated reminder that **“Security is everyone’s job”** left a strong impact.  
A misconfigured Security Group or a poorly validated piece of code can expose an entire system.

The workshop ended with a stronger sense of responsibility, motivating me to apply secure practices even in the smallest projects.

---

### Photos
![Event photo](/images/4-EventParticipated/4.5-Event5/event51.png)
![Event photo](/images/4-EventParticipated/4.5-Event5/event52.png)
