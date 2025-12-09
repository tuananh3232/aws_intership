---
title: "Worklog Tuần 11"
date: "2025-11-21"
weight: 11
chapter: false
pre: " <b> 1.11. </b> "
---

### Mục tiêu tuần 11 (Góc nhìn DevOps)

- Hỗ trợ nhóm hoàn thiện việc tích hợp FE–BE và đảm bảo API contract thống nhất trên toàn hệ thống.
- Thực hiện kiểm thử end-to-end từ FE → API Gateway (local mock) → Backend để đánh giá mức độ sẵn sàng trước khi deploy lên AWS.
- Tìm hiểu quy trình deploy: đóng gói .NET → Lambda, cấu hình API Gateway, CI/CD bằng GitLab Runner, deploy FE lên S3 + CloudFront.
- Chuẩn bị ghi chú DevOps cho tuần 12 (tài liệu deploy, tài liệu môi trường, checklist khắc phục lỗi).

---

### Các công việc triển khai trong tuần

| Thứ | Công việc                                                                                                                            | Bắt đầu    | Hoàn thành |
| --- | ------------------------------------------------------------------------------------------------------------------------------------ | ---------- | ---------- |
| 2   | - Làm việc với FE để hoàn thiện UI còn lại <br> - Rà soát API contract, payload và response                                          | 17/11/2025 | 17/11/2025 |
| 3   | - FE tích hợp toàn bộ CRUD API <br> - Fix các lỗi mismatch schema, payload format, status code                                       | 18/11/2025 | 18/11/2025 |
| 4   | - Kiểm thử end-to-end: List → Create → Update → Delete <br> - Điều chỉnh validation và response model để sẵn sàng chuyển sang Lambda | 19/11/2025 | 19/11/2025 |
| 5   | - Tìm hiểu quy trình deploy: Lambda, API Gateway, GitLab CI/CD, S3 + CloudFront <br> - Ghi chú chuẩn bị cho tuần 12                  | 20/11/2025 | 20/11/2025 |
| 6   | - Tổng hợp lỗi FE ↔ BE tuần này <br> - Rà soát toàn bộ backend để đảm bảo readiness trước khi deploy (env, logging, error)           | 21/11/2025 | 21/11/2025 |

---

### Kết quả đạt được tuần 11

#### Tổng quát
Tuần này tôi hỗ trợ team FE hoàn thiện UI và kết nối API. Backend đã ổn định từ tuần 10 nên tôi tập trung vào việc **điều chỉnh API contract**, **fix lỗi**, và **kiểm thử E2E**.

Bên cạnh đó, tôi tìm hiểu quy trình triển khai thực tế của nhóm gồm **Lambda**, **API Gateway**, **CloudFront**, và **GitLab CI/CD**, làm nền tảng cho tài liệu và tổng kết tuần 12.

---

### Lý thuyết đã học

- Cách FE gọi CRUD API và debug request/response.
- Nguyên tắc thống nhất API Contract: input/output schema, error model, status code.
- Quy trình triển khai:
  - Đóng gói .NET → Lambda (zip, handler).
  - Routing API Gateway + Authorizer.
  - Deploy FE qua S3 + CloudFront.
  - CI/CD bằng GitLab Runner.
- Chuẩn bị code trước khi deploy: env variables, structured logging, error-handling.

---

### Thực hành / Sản phẩm

- Hỗ trợ FE hoàn thiện chức năng List/Create/Update/Delete.
- Điều chỉnh BE để đồng bộ với FE (schema, validation, status code).
- Kiểm thử đầy đủ end-to-end giữa FE ↔ BE trên môi trường local.
- Viết tài liệu mô tả quy trình deploy Lambda + API Gateway + CloudFront cho tuần 12.
- Tổng hợp lỗi & backlog của tuần, cập nhật cho nhóm.

