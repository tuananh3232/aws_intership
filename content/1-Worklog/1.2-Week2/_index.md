---
title: "Week 2 Worklog"
date: "2025-09-19"
weight: 2
chapter: false
pre: " <b> 1.2. </b> "
---


### Week 2 Objectives:

* Learn about Amazon VPC and its core components such as Subnet, Internet Gateway, and NAT Gateway.
* Learn about key security concepts such as Security Group and NACL.
* Get familiar with launching EC2 instances and basic networking configurations.

### Tasks to be carried out this week:
| Day | Task                                                                                                                                                                                                                                         | Start Date | End Date   | References                                                                                                                                                                 |
| --- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------- | ---------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 2   | - Watch the theoretical videos of Module 2 to get an overall understanding of VPC <br> - Define concepts such as Subnet, Route Table, Internet Gateway, NAT Gateway, Security Group, and NACL <br> - Review the VPC architecture model       | 15/09/2025 | 15/09/2025 | <https://youtu.be/O9Ac_vGHquM?si=wDWqr_lJUjK2csDt> <br><br> <https://youtu.be/BPuD1l2hEQ4?si=Qaig6saCCVKiqe0H> <br><br> <https://youtu.be/CXU8D3kyxIc?si=TiZqHi0uB5mCif3L> |
| 3   | - **Hands-on:** <br>&emsp; + Create VPC <br>&emsp; + Create Subnet <br>&emsp; + Configure Route Table for the public subnet <br>&emsp; + Attach Internet Gateway to the VPC <br>&emsp; + Verify the route table to confirm IGW functionality | 16/09/2025 | 16/09/2025 | <https://000003.awsstudygroup.com>                                                                                                                                         |
| 4   | - Learn about Security Groups in VPC <br> - Learn about Network ACLs <br> - Review inbound/outbound rules of Security Groups <br> - Review NACL rules in the subnet                                                                          | 17/09/2025 | 17/09/2025 | <https://000003.awsstudygroup.com>                                                                                                                                         |
| 5   | - **Hands-on:** <br>&emsp; + Launch EC2 instance in the public subnet <br>&emsp; + Create key pair to connect to EC2 <br>&emsp; + Review EC2 Security Group <br>&emsp; + Review EC2 Route Table and subnet mapping                           | 18/09/2025 | 18/09/2025 | <https://000003.awsstudygroup.com>                                                                                                                                         |
| 6   | - **Hands-on:** <br>&emsp; + Test SSH connection to EC2 <br>&emsp; + Final verification of Security Group rules <br> - Summarize all Module 2 theoretical content                                                                            | 19/09/2025 | 19/09/2025 | <https://000003.awsstudygroup.com>                                                                                                                                         |

### Week 2 Achievements:

* Overview:
  * This week I became familiar with fundamental networking concepts in AWS and learned how to build a simple VPC. The main focus was understanding how VPC creates an isolated environment, how subnets are divided, and how IGW, routing, and security work together.

* Theory learned:
  * Overview of VPC and how it operates within AWS
  * Subnet (Public / Private) and subnet segmentation
  * Internet Gateway & Route Table
  * Security Group & Network ACL
  * VPC Peering, VPN, Direct Connect

* Hands-on labs:
  * Practiced creating a VPC
  * Created subnets according to the lab design (public/private)
  * Created and attached an Internet Gateway to the VPC
  * Created Route Table and configured routes for the subnets
  * Reviewed VPC structure after deployment
