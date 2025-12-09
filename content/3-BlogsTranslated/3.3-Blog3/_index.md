---
title: "Blog 3"
date: "2025-11-10"
weight: 1
chapter: false
pre: " <b> 3.3. </b> "
---
# Amazon OpenSearch Serverless: Cost-Effective Search at Any Scale

**Authors:** Satish Nandi and Jon Handler  
**Published:** August 2, 2024  

**Categories:**  
[Amazon OpenSearch Service](https://aws.amazon.com/opensearch-service/),  
[Announcements](https://aws.amazon.com/blogs/big-data/category/post-types/announcements/),  
[AWS Big Data](https://aws.amazon.com/blogs/big-data/category/big-data/),  
[Foundational (100)](https://aws.amazon.com/blogs/big-data/category/learning-levels/foundational-100/),  
[Price Reduction](https://aws.amazon.com/blogs/big-data/category/price-reduction/)

We are excited to announce a lower entry-level cost for **[Amazon OpenSearch Serverless](https://aws.amazon.com/opensearch-service/features/serverless/)**. With support for half (0.5) OpenSearch Compute Units (OCUs) for indexing and search workloads, the entry cost has been reduced by 50%. OpenSearch Serverless is a serverless deployment option for Amazon OpenSearch Service that allows you to run search and analytics workloads without managing infrastructure, shard tuning, or data lifecycle management. It automatically provisions and scales compute resources to provide consistent ingestion performance and millisecond-level query response times—even as your application usage patterns and requirements change.

OpenSearch Serverless provides three collection types to meet your needs: **time-series**, **search**, and **vector**. The new lower entry cost benefits all collection types. Vector collections, in particular, have emerged as the dominant workload when using OpenSearch Serverless as a knowledge base for **[Amazon Bedrock](https://aws.amazon.com/bedrock/)**. By introducing the 0.5 OCU baseline, the cost of small vector workloads is reduced by half. Time-series and search collections also benefit, especially for small workloads such as proof-of-concept (PoC) deployments and development/test environments.

A full OCU consists of 1 vCPU, 6 GB RAM, and 120 GB of storage. A half OCU provides 0.5 vCPU, 3 GB RAM, and 60 GB storage. OpenSearch Serverless scales from the first half OCU to a full OCU, then continues scaling in increments of one full OCU. Each OCU also uses Amazon Simple Storage Service (Amazon S3) as its backing store; you pay for S3 storage regardless of OCU size. The number of OCUs required depends on your collection type and your ingestion and search workloads. We will go deeper into these details and compare how the new 0.5 OCU baseline delivers cost benefits.

OpenSearch Serverless separates compute resources for indexing and search, deploying distinct sets of OCUs for each compute need. You can deploy OpenSearch Serverless in two ways:  
1) **Redundant deployment** for production, and  
2) **Non-redundant deployment** for development or testing.

> Note: Redundant deployments provision twice the compute resources for both indexing and search operations.

---

## Deployment Types in OpenSearch Serverless

The diagram below illustrates the architecture of OpenSearch Serverless in redundant mode.

![]()

In redundant mode, OpenSearch Serverless deploys two base OCUs for each compute group (indexing and search) across two Availability Zones. For small workloads under 60 GB, OpenSearch Serverless uses a half OCU as the baseline size. The minimum deployment equals four base units—two for indexing and two for search. This corresponds to approximately **$350 per month** (four half OCUs). All pricing is based on the US-East (N. Virginia) Region and assumes a 30-day month. Under normal operation, all OCUs actively serve traffic, and OpenSearch Serverless scales from this baseline as needed.

For **non-redundant deployments**, OpenSearch Serverless deploys a single base OCU for each compute group, costing approximately **$174 per month** (two half OCUs).

Redundant deployments are recommended for production to ensure high availability. If an Availability Zone fails, the remaining zone can still serve traffic. Non-redundant deployments are suitable for development and testing environments to reduce cost. In both configurations, you can set an upper limit on OCU usage to control costs. The system will scale up to—but never beyond—this limit during peak usage.

---

## Collections in OpenSearch Serverless and Resource Allocation

OpenSearch Serverless uses OCUs differently depending on your collection type and stores your data in Amazon S3. When ingesting data, the service writes to both local OCU disk and Amazon S3 before acknowledging the request, ensuring durability and performance. Depending on the collection type, it also stores data in local OCU storage and scales as needed.

**Time-series collections** are designed for cost efficiency by limiting how much data is stored locally while offloading older data to Amazon S3. The required number of OCUs depends on data volume and retention period. The system uses whichever is greater: the default minimum OCUs or the minimum OCUs required to store the most recent data per the **[OpenSearch Serverless data lifecycle policy](https://docs.aws.amazon.com/opensearch-service/latest/developerguide/serverless-lifecycle.html)**.

Example:  
If you ingest **1 TiB per day** and have a **30-day retention period**, the “recent data size” is 1 TiB. You would need:  
- **20 OCUs** for indexing (10 OCUs × 2 for redundancy)  
- **20 OCUs** for search (10 OCUs × 2)

(Each OCU provides 120 GiB of local disk storage.)  
Querying older data stored only in S3 will increase query latency. This is the trade-off between cost efficiency and older data retrieval times.

**Vector collections** use RAM to store vector graphs and disk to store indexes. Vector collections keep index data in local OCU memory. RAM limits are reached faster than disk limits, making vector workloads RAM-bound.

When using a full OCU, resource allocation typically includes:  
- **2 GB** for the operating system  
- **2 GB** for Java heap  
- **2 GB** for vector graph memory  
- **120 GB** of local disk for OpenSearch indexes

RAM requirements for a vector graph depend on vector dimensionality, vector count, and the algorithm chosen. Refer to **“Choose the k-NN algorithm for your billion-scale use case with OpenSearch”** for formulas and guidelines.

> Note: System behavior described here reflects the state as of June 2024. Ongoing improvements may further reduce costs.

---

## Supported AWS Regions

The new minimum OCU size (0.5 OCU) is available in all AWS Regions where OpenSearch Serverless is supported.  
See the **[AWS Regional Services List](https://docs.aws.amazon.com/general/latest/gr/opensearch-service.html#opensearch-service-regions)** for service availability details and documentation to **learn more about OpenSearch Serverless**.

---

## Conclusion

The introduction of 0.5 OCUs significantly reduces the baseline cost of Amazon OpenSearch Serverless. If you have small datasets or light workloads, you can now operate at a much lower cost. Combined with its simplicity and ability to handle search and analytics workloads without infrastructure management, OpenSearch Serverless provides seamless operations even as your traffic and usage patterns evolve.

---

## About the Authors

<div style="display:flex;align-items:center;gap:20px;border:1px solid #e0e0e0;border-radius:8px;padding:16px;background-color:#fff;max-width:900px;">

  <img src="/images/blog2/Satish_Nandi.png" alt="Satish Nandi" style="width:120px;height:auto;border-radius:6px;object-fit:cover;">

  <div style="flex:1;">
    <p style="margin:0;">
      <strong style="font-size:1.1rem;color:#0d1b2a;">Satish Nandi</strong><br>
      Satish Nandi is a Senior Product Manager for Amazon OpenSearch Service, focusing on OpenSearch Serverless and Geospatial. He has years of experience in computer networking, security, Machine Learning (ML), and Artificial Intelligence (AI). He holds a BEng in Computer Science and an MBA in Entrepreneurship. In his free time, he enjoys flying airplanes, paragliding, and motorcycling.
    </p>
  </div>

</div>

<div style="display:flex;align-items:center;gap:20px;border:1px solid #e0e0e0;border-radius:8px;padding:16px;background-color:#fff;max-width:900px;">

  <img src="/images/blog2/Jon_Handler.png" alt="Jon Handler" style="width:120px;height:auto;border-radius:6px;object-fit:cover;">

  <div style="flex:1;">
    <p style="margin:0;">
      <strong style="font-size:1.1rem;color:#0d1b2a;">Jon Handler</strong><br>
      Jon Handler is a Senior Solutions Architect at AWS. He supports Capital Markets and FinTech customers in their cloud transformation journeys. His areas of expertise include identity management, security, and unified communication systems.
    </p>
  </div>

</div>
