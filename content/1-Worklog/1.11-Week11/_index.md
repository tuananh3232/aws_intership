---
title: "Week 11 Worklog"
date: "2025-11-21"
weight: 11
chapter: false
pre: " <b> 1.11. </b> "
---

### Week 11 Objectives

- Support the team in completing FE–BE integration and ensure API contracts are consistent across environments.
- Perform end-to-end testing from FE → API Gateway (local mock) → Backend to verify system readiness before cloud deployment.
- Begin learning and validating the deployment workflow: CI/CD pipeline, Lambda packaging, API Gateway configuration, S3 + CloudFront setup.
- Prepare DevOps notes for Week 12 documentation (deployment guide, environment setup, troubleshooting).

---

### Tasks to Be Carried Out This Week

| Day | Task                                                                                                                                                        | Start Date | End Date   |
| --- | ----------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------- | ---------- |
| 2   | - Work with FE team to finalize UI components <br> - Review API contracts and ensure consistent payload & response formats                                  | 17/11/2025 | 17/11/2025 |
| 3   | - FE integrates full CRUD API flows <br> - Resolve schema mismatches, payload formatting issues, and incorrect status codes                                 | 18/11/2025 | 18/11/2025 |
| 4   | - Perform full E2E testing: List → Create → Update → Delete <br> - Refine validation rules and response models for eventual Lambda deployment               | 19/11/2025 | 19/11/2025 |
| 5   | - Study deployment workflow: .NET packaging → Lambda, API Gateway routes, CI/CD (GitLab Runner), FE deploy to S3 + CloudFront <br> - Take notes for Week 12 | 20/11/2025 | 20/11/2025 |
| 6   | - Summarize FE–BE integration issues <br> - Review backend codebase to ensure it is ready for cloud migration (env variables, logging, error handling)      | 21/11/2025 | 21/11/2025 |

---

### Week 11 Achievements

#### Overview
This week I mainly assisted the FE team in completing the UI and ensuring smooth integration with the backend. As backend logic had been completed in Week 10, my role focused on **API contract consistency**, **bug fixing**, and **end-to-end validation**.

In addition, I studied the team’s deployment workflow, including **Lambda deployment**, **API Gateway mapping**, **CloudFront hosting**, and **GitLab CI/CD**, in preparation for Week 12 documentation.

---

### Knowledge Acquired

- How FE interacts with CRUD APIs and how to debug requests/responses.
- Principles of API contract consistency: input/output schema structure, error model, status code conventions.
- Deployment workflow overview:
  - Packaging .NET into Lambda (zip bundle, handler configuration).
  - API Gateway routing and authorizer setup.
  - FE hosting via S3 + CloudFront.
  - GitLab CI/CD deployment flow.
- How to prepare code for deployment: environment variables, structured logging, error handling, configuration separation.

---

### Practical Work / Deliverables

- Worked with FE team to finalize List/Create/Update/Delete screens.
- Updated backend response schemas, validations, and status codes for FE alignment.
- Completed end-to-end testing between FE ↔ BE in the local environment.
- Documented the Lambda + API Gateway + CloudFront deployment workflow for Week 12.
- Compiled integration issues and added them to the team backlog for tracking.

