---
title: "Week 3 Worklog"
date: "2025-09-26"
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---
### Week 3 Objectives:

* Learn about EC2 within a VPC.
* Understand NAT Gateway & network security.
* Learn how to set up DNS and Route 53.

### Tasks to be carried out this week:
| Day | Task                                                                                                                                                                                                                                                               | Start Date | End Date   | References                                                                                                                                                                 |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------- | ---------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 2   | - Review theory about EC2 in a VPC and NAT Gateway <br> - Summarize the flow Public Subnet -> Private Subnet -> NAT -> IGW <br> - Consolidate understanding of how NAT works                                                                                       | 22/09/2025 | 22/09/2025 | <https://youtu.be/N58agSU4O8o?si=QVRiT5MDt9VN5el4> <br><br> <https://youtu.be/B1qxOQLmavQ?si=3ALVG-HGI0sbL8bM> <br><br> <https://youtu.be/GVDsDu9dOFY?si=ki8qJYmPxwxLgYxd> |
| 3   | - **Hands-on:** <br>&emsp; + Launch EC2 instance in the public subnet <br>&emsp; + Verify Security Group settings <br>&emsp; + Review subnet mapping and Route Table <br>&emsp; + Test EC2 Instance Connect                                                        | 23/09/2025 | 23/09/2025 | <https://000003.awsstudygroup.com>                                                                                                                                         |
| 4   | - **Hands-on:** <br>&emsp; + Create NAT Gateway <br>&emsp; + Check private subnet routes <br>&emsp; + Test outbound traffic from private subnet to confirm NAT functionality                                                                                       | 24/09/2025 | 24/09/2025 | <https://000003.awsstudygroup.com>                                                                                                                                         |
| 5   | - Learn about Hybrid DNS with Route 53 <br> - **Hands-on:** <br>&emsp; + Create key pair <br>&emsp; + Create CloudFormation template                                                                                                                               | 25/09/2025 | 25/09/2025 | <https://000010.awsstudygroup.com>                                                                                                                                         |
| 6   | - **Hands-on:** <br>&emsp; + Configure Security Groups <br>&emsp; + Connect to RDGW <br>&emsp; + Create Outbound and Inbound Endpoints <br>&emsp; + Create Resolver Rules and test DNS <br> - Clean up all lab resources <br> - Summarize EC2 – NAT – DNS concepts | 26/09/2025 | 26/09/2025 | <https://000010.awsstudygroup.com>                                                                                                                                         |

### Week 3 Achievements:

* Overview:
  * This week I learned how EC2 operates inside a VPC, understood the architecture of public/private subnets, NAT Gateway, and the security model. I also practiced extensively with EC2 and networking configurations.

* Theory learned:
  * How EC2 connects with subnets, route tables, and security groups
  * How NAT Gateway enables Internet connectivity for private subnets
  * How Security Groups control inbound/outbound traffic
  * How NACL filters traffic at the subnet level
  * DNS Resolver and how Route 53 handles hybrid DNS

* Hands-on labs:
  * Launched EC2 instances in different types of subnets
  * Tested connectivity using EC2 Instance Connect
  * Created NAT Gateway and verified outbound connections
  * Continued practicing through DNS lab exercises to reinforce concepts
