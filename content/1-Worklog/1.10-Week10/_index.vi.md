---
title: "Worklog Tuần 10"
date: "2025-11-14"
weight: 10
chapter: false
pre: " <b> 1.10. </b> "
---

### Mục tiêu tuần 10

- Kiểm tra và hoàn thiện môi trường Backend & DevOps (.NET SDK, Docker Desktop, NoSQL Workbench).
- Thiết lập DynamoDB Local bằng Docker và xác thực mô hình dữ liệu bằng NoSQL Workbench.
- Thực hiện CRUD test trên DynamoDB Local để kiểm tra access pattern trước khi deploy lên AWS.
- Phối hợp với team FE kết nối API và kiểm thử end-to-end trên môi trường local.
- Chuẩn bị nền tảng vững chắc cho tuần 11 (chuyển backend sang Lambda & API Gateway).

---

### Các công việc cần triển khai

| Thứ | Công việc                                                                                               | Bắt đầu    | Hoàn thành |
| --- | ------------------------------------------------------------------------------------------------------- | ---------- | ---------- |
| 2   | - Kiểm tra môi trường BE: .NET SDK, Docker, NoSQL Workbench <br> - Nắm lại sơ đồ kiến trúc hệ thống     | 10/11/2025 | 10/11/2025 |
| 3   | - Setup DynamoDB Local (Docker) <br> - Kết nối NoSQL Workbench, test CRUD thủ công                      | 11/11/2025 | 11/11/2025 |
| 4   | - Viết Repository với AWSSDK.DynamoDBv2 <br> - Tích hợp DI vào Aspire AppHost <br> - Xây dựng logic BLL | 12/11/2025 | 12/11/2025 |
| 5   | - Viết Controllers CRUD <br> - Chạy unit test & integration test local                                  | 13/11/2025 | 13/11/2025 |
| 6   | - Phối hợp với team FE <br> - Dựng giao diện List/Create <br> - FE kết nối API Local và test end-to-end | 14/11/2025 | 14/11/2025 |

---

### Kết quả đạt được tuần 10

#### Tổng quát
Tuần này tôi đã hoàn thiện toàn bộ phần backend chạy local với Aspire AppHost, thiết lập DynamoDB Local, test CRUD và tích hợp frontend. Nhờ có môi trường local ổn định, tôi đã sẵn sàng chuyển backend lên Lambda và API Gateway trong tuần 11.

---

### Lý thuyết đã học

- Thiết kế DynamoDB theo mô hình Single-Table Design (PK/SK, access patterns).
- Sử dụng DynamoDB Local, Docker và NoSQL Workbench.
- Cách dùng AWSSDK.DynamoDBv2 trong .NET và tích hợp DI.
- Kiến trúc Backend: Controller → BLL → Repository.
- FE gọi API local, parse JSON và hiển thị dữ liệu.

---

### Thực hành / Sản phẩm

- Tạo DynamoDB Local bằng Docker và thiết kế schema bằng NoSQL Workbench.
- Xây dựng Repository + BLL + Controllers trong .NET 8 / Aspire AppHost.
- Hoàn thiện 5–6 API CRUD (POST/GET/PUT/DELETE/List).
- Viết unit test cho BLL và integration test cho API.
- Team FE hoàn thành giao diện List + Create và test thành công với API Local.
