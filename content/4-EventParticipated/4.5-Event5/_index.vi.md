---
title: "Event 5"
date: "2025-11-30"
weight: 5
chapter: false
pre: " <b> 4.5. </b> "
---

# Bài Thu Hoạch Workshop "AWS Cloud Mastery Series #3: Theo AWS Well-Architected Security Pillar"

### Mục Đích Của Sự Kiện
- Giới thiệu Well-Architected Framework, tập trung vào Security Pillar – nền tảng cho mọi hệ thống AWS.
- Cung cấp kiến thức thực tiễn về 5 lĩnh vực bảo mật: IAM, Detection, Infrastructure Protection, Data Protection, Incident Response.
- Trang bị tư duy “Security by Design” cùng các mô hình như Least Privilege, Zero Trust, Defense in Depth.
- Chia sẻ kinh nghiệm triển khai thực tế từ các doanh nghiệp tại Việt Nam.

### Diễn Giả / Người Hướng Dẫn (Dự kiến)
- **Nguyễn Văn Tú** – Sr. Security Specialist Solutions Architect, AWS  
- **Lê Thị Thanh Mai** – Cloud Security Engineer, Đối tác AWS  
- **Đặng Quốc Bảo** – Security Lead, Fintech Company (Case study khách mời)

---

### Nội Dung Nổi Bật & Bài Học Chính

#### 1. Nền Tảng Bảo Mật Trên Cloud
- **Security là Pillar hàng đầu** trong mọi thiết kế kiến trúc AWS.
- Ba nguyên tắc cốt lõi:
  - **Least Privilege**: Cấp quyền tối thiểu cần thiết.
  - **Zero Trust**: Không tin tưởng điều gì, luôn xác minh.
  - **Defense in Depth**: Nhiều lớp bảo vệ chồng lấn.
- **Shared Responsibility Model**: AWS bảo mật “của” cloud, khách hàng bảo mật “trên” cloud.

#### 2. Pillar 1 – Identity & Access Management (IAM)
- Hạn chế dùng **long-term credentials**; ưu tiên IAM Roles cho EC2, Lambda, ECS.
- IAM Identity Center & SSO giúp quản lý truy cập tập trung.
- SCPs và Permission Boundaries để đặt giới hạn quyền toàn tổ chức.
- IAM Access Analyzer phát hiện tài nguyên public ngoài ý muốn.

#### 3. Pillar 2 – Detection & Continuous Monitoring
- Bật log toàn diện: Organization CloudTrail, VPC Flow Logs, ALB Logs.
- GuardDuty phát hiện hành vi bất thường; Security Hub tổng hợp findings.
- Detection-as-Code với AWS Config Rules.
- Tự động hóa alert bằng EventBridge.

#### 4. Pillar 3 – Infrastructure Protection
- Thiết kế mạng an toàn: phân đoạn VPC (Public, Private, Data).
- Hiểu sự khác biệt giữa Security Groups (stateful) và NACLs (stateless).
- Bảo vệ ứng dụng bằng AWS WAF và Shield.
- Hardening OS, dùng IMDSv2 cho EC2.

#### 5. Pillar 4 – Data Protection
- Mã hóa mặc định (KMS) cho S3, RDS, EBS, DynamoDB.
- Quản lý keys & secrets bằng KMS Key Policies và Secrets Manager.
- Phân loại dữ liệu để gắn tag và kiểm soát truy cập phù hợp.

#### 6. Pillar 5 – Incident Response
- Chuẩn bị playbook cho các tình huống phổ biến.
- Quy trình IR: Ngăn chặn → Loại bỏ → Phục hồi → Phân tích.
- Tự động hóa phản ứng bằng Lambda & Step Functions.

---

### Những Gì Học Được (Key Takeaways)

#### Về Tư Duy & Chiến Lược
- **Security is job zero** – bảo mật phải được thiết kế từ ban đầu.
- Ưu tiên bảo mật theo mức độ rủi ro.
- Luôn đo lường và cải thiện Security posture.

#### Về Kỹ Thuật
- Giảm bề mặt tấn công bằng cách tối thiểu public resources.
- Mã hóa mọi thứ.
- Tự động hóa quy trình bảo mật để giảm lỗi con người.

---

### Kế Hoạch Hành Động Cá Nhân
1. Rà soát IAM policies và áp dụng Least Privilege ngay lập tức.  
2. Kích hoạt GuardDuty và Security Hub trên tài khoản cá nhân.  
3. Tạo KMS key và thử mã hóa một S3 bucket.  
4. Nghiên cứu sâu Shared Responsibility Model cho từng dịch vụ AWS đang dùng.

---

### Trải Nghiệm Cá Nhân

Workshop Security Pillar giúp em hiểu rõ rằng bảo mật không phải là thứ “phức tạp và xa vời”, mà là một **hệ thống tư duy rõ ràng** nếu tiếp cận đúng.  
Phần demo IAM Policy Simulator và kịch bản Incident Response khiến em nhận ra: bảo mật hiện đại là sự kết hợp giữa **quy tắc chính xác** và **tự động hóa thông minh**.

Điều khiến em tâm đắc nhất là khẩu hiệu **“Security is everyone’s job.”**  
Một dòng code thiếu kiểm tra input, một Security Group mở quá mức… đều có thể trở thành lỗ hổng nghiêm trọng.

Buổi học giúp em có cái nhìn chín chắn hơn và ý thức mạnh mẽ hơn về trách nhiệm của mình khi xây dựng hệ thống trên cloud.

---

### Hình Ảnh
![anh5 event](/images/event-image5.png)
![anh6 event](/images/event-image6.png)
