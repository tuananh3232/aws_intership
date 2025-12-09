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
|     | - Clean up all lab resources <br> - Consolidate knowledge of Peering and Transit Gateway                                                                                                                          | 02/10/2025 | 02/10/2025 | <https://000020.awsstudygroup.com> |
| 6   |                                                                                                                                                                                                                   | 03/10/2025 | 03/10/2025 |                                    |

### Week 4 Achievements:

* **Summary:**  
  * During this week, I explored different models for connecting multiple VPCs, including VPC Peering and Transit Gateway. I gained a clear understanding of how inter-VPC networking works, how routing is performed through TGW, and how each component functions within a multi-VPC architecture.

* **Theory learned:**  
  * How VPC Peering operates and how routing is handled between two VPCs.
  * The architecture and capabilities of Transit Gateway (TGW) for connecting multiple VPCs in a hub-and-spoke topology
  * How to configure route tables in VPCs connected via Peering or Transit Gateway.

* **Hands-on labs:**  
  * Created VPC Peering connections and updated route tables to enable traffic between VPCs.
  * Configured a Transit Gateway, created TGW attachments, and set up routing between connected networks.
  *Tested connectivity across subnets and VPCs to validate the configuration.