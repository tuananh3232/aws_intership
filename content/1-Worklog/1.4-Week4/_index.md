---
title: "Week 4 Worklog"
date: "2025-10-03"
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---



### Week 4 Objectives:

* Learn how to deploy VPC Peering between multiple VPCs.
* Learn how to configure Transit Gateway for large-scale inter-VPC connectivity.
* Practice advanced labs related to routing and DNS across VPCs.

### Tasks to be carried out this week:
| Day | Task                                                                                                                                                                                                              | Start Date | End Date   | Reference                          |
| --- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------- | ---------- | ---------------------------------- |
| 2   | - Learn the fundamentals of VPC Peering: how it works, limitations, routing behavior <br> - Learn about the concept of peering inside a VPC                                                                       | 29/09/2025 | 29/09/2025 | <https://000019.awsstudygroup.com> |
| 3   | - **Hands-on:** <br>&emsp; + Create EC2 instances in multiple VPCs and configure routing <br>&emsp; + Verify NACLs and Security Groups when using peering <br>&emsp; + Finalize the peering setup                 | 30/09/2025 | 30/09/2025 | <https://000019.awsstudygroup.com> |
| 4   | - Learn about Transit Gateway <br> - **Hands-on:** <br>&emsp; + Deploy a TGW <br>&emsp; + Set up routing between VPCs and the TGW                                                                                 | 01/10/2025 | 01/10/2025 | <https://000020.awsstudygroup.com> |
| 5   | - **Hands-on:** <br>&emsp; + Create a Transit Gateway connection <br>&emsp; + Create a TGW Route Table <br>&emsp; + Map VPC routes to the TGW <br>&emsp; + Final connectivity check between multiple VPCs via TGW | 02/10/2025 | 02/10/2025 | <https://000020.awsstudygroup.com> |
| 6   | - Clean up all lab resources <br> - Consolidate knowledge of Peering and Transit Gateway                                                                                                                          | 03/10/2025 | 03/10/2025 | <https://000020.awsstudygroup.com> |

### Week 4 Achievements:

* **Summary:**  
  * This week I explored multi-VPC connectivity models such as VPC Peering and Transit Gateway. I learned how inter-VPC networking works, how routing is handled via TGW, and how each component operates in a multi-VPC architecture.

* **Theory learned:**  
  * How VPC Peering works and the routing mechanics between two VPCs  
  * Transit Gateway and its hub-and-spoke connectivity model  
  * How to configure VPC route tables when connecting through Peering or TGW  

* **Hands-on labs:**  
  * Create VPC Peering connections and update route tables  
  * Configure Transit Gateway, create attachments (TGW connections), and set up routing  
  * Verify connectivity between subnets/VPCs after configuration  