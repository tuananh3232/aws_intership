---
title: "Week 10 Worklog"
date: "2025-11-14"
weight: 10
chapter: false
pre: " <b> 1.10. </b> "
---

### Week 10 Objectives

- Validate and finalize the local development environment for Backend and DevOps workflows (.NET SDK, Docker Desktop, NoSQL Workbench).
- Set up DynamoDB Local using Docker and validate the data model using NoSQL Workbench.
- Perform CRUD testing on DynamoDB Local and confirm access patterns before deploying to AWS.
- Collaborate with the Frontend team to connect APIs and ensure end-to-end functionality in the local environment.
- Prepare a stable technical foundation before Week 11 (migrating Backend → Lambda & API Gateway).

---

### Tasks to Be Completed This Week

| Day | Task                                                                                                               | Start Date | End Date   |
| --- | ------------------------------------------------------------------------------------------------------------------ | ---------- | ---------- |
| 2   | - Re-validate Backend environment: .NET SDK, Docker, NoSQL Workbench <br> - Review system architecture             | 10/11/2025 | 10/11/2025 |
| 3   | - Set up DynamoDB Local via Docker <br> - Connect with NoSQL Workbench and test manual CRUD                        | 11/11/2025 | 11/11/2025 |
| 4   | - Implement Repository Layer using AWSSDK.DynamoDBv2 <br> - Integrate DI in Aspire AppHost <br> - Design BLL logic | 12/11/2025 | 12/11/2025 |
| 5   | - Implement CRUD API Controllers <br> - Run unit tests & integration tests locally                                 | 13/11/2025 | 13/11/2025 |
| 6   | - Work with FE team <br> - Build basic UI (List/Create) <br> - FE integrates Local API and tests E2E               | 14/11/2025 | 14/11/2025 |

---

### Week 10 Achievements

#### Overview
This week, I focused on building and validating the entire backend infrastructure in the local environment using Aspire AppHost. I successfully implemented DynamoDB Local, tested CRUD operations, and integrated the backend with the frontend. The stable local setup provides a strong foundation for moving backend services into AWS Lambda and API Gateway in Week 11.

---

### Knowledge Gained

- DynamoDB Single-Table Design: PK/SK, access patterns, and efficient item modeling.
- Setup and usage of DynamoDB Local, Docker, and NoSQL Workbench.
- Using AWSSDK.DynamoDBv2 in .NET and dependency injection within Aspire AppHost.
- Backend architecture: Controller → BLL → Repository.
- API integration with Frontend and handling JSON responses.

---

### Practical Work / Deliverables

- Deployed DynamoDB Local using Docker and modeled schema via NoSQL Workbench.
- Implemented Repository, BLL, and REST Controllers using .NET 8 / Aspire AppHost.
- Completed 5–6 CRUD APIs (POST / GET / PUT / DELETE / LIST).
- Wrote BLL unit tests and API integration tests.
- Frontend team successfully built List + Create pages and validated end-to-end flow with Local API.
