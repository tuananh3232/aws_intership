---
title: "Blog 2"
date: "2025-11-10"
weight: 1
chapter: false
pre: " <b> 3.2. </b> "
---
# Scaling Data Analytics Containers with Event-based Lambda Functions

by: Brian Maguire, Guy Bachar, and Mike Boyar

on 30 Aug 2021

Danh mục: **[Amazon API Gateway](https://aws.amazon.com/vi/blogs/architecture/category/application-services/amazon-api-gateway-application-services/)**, **[Amazon EC2](https://aws.amazon.com/vi/blogs/architecture/category/compute/amazon-ec2/)**, **[Amazon Elastic Container Service](https://aws.amazon.com/vi/blogs/architecture/category/compute/amazon-elastic-container-service/)**, **[Analytics](https://aws.amazon.com/vi/blogs/architecture/category/analytics/)**, **[Architecture](https://aws.amazon.com/vi/blogs/architecture/category/architecture/)**, **[AWS Elastic Beanstalk](https://aws.amazon.com/vi/blogs/architecture/category/compute/aws-elastic-beanstalk/)**, **[Intermediate (200)](https://aws.amazon.com/vi/blogs/architecture/category/learning-levels/intermediate-200/)**, **[Manufacturing](https://aws.amazon.com/vi/blogs/architecture/category/industries/manufacturing/)** 

The marketing industry collects and uses data from various stages of the customer journey. When they analyze this data, they establish metrics and develop actionable insights that are then used to invest in customers and generate revenue.

If you’re a data scientist or developer in the marketing industry, you likely often use containers for services like collecting and preparing data, developing machine learning models, and performing statistical analysis. Because the types and amount of marketing data collected are quickly increasing, you’ll need a solution to manage the scale, costs, and number of required data analytics integrations.

In this post, we provide a solution that can perform and scale with dynamic traffic and is cost optimized for on-demand consumption. It uses synchronous container-based data science applications that are deployed with asynchronous container-based architectures on **[AWS Lambda](https://aws.amazon.com/vi/lambda/)**. This serverless architecture automates data analytics workflows utilizing event-based prompts.

## Synchronous container applications
Data science applications are often deployed to dedicated container instances, and their requests are routed by an Amazon API Gateway or load balancer. Typically, an Amazon API Gateway routes HTTP requests as synchronous invocations to instance-based container hosts.

The target of the requests is a container-based application running a machine learning service (SciLearn). The service container is configured with the required dependency packages such as **[scikit-learn](http://c/Users/mccbonni/AppData/Local/Temp/scikit-learn.org)**, **[pandas](http://c/Users/mccbonni/AppData/Local/Temp/pandas.pydata.org)**, **[NumPy](https://numpy.org/)** and **[SciPy](https://scipy.org/)**.

Containers are commonly deployed on different targets such as on-premises, **[Amazon Elastic Container Service (Amazon ECS)](https://aws.amazon.com/vi/ecs/)**, **[Amazon Elastic Compute Cloud (Amazon EC2)](https://aws.amazon.com/vi/ec2/)** and **[AWS Elastic Beanstalk](https://aws.amazon.com/vi/elasticbeanstalk/)** These services run synchronously and scale through **[Amazon Auto Scaling groups](https://aws.amazon.com/vi/autoscaling/)** and a time-based consumption pricing model.

![Synchronous container applications diagram](/images/blog2/Lambdasync.png)
Figure 1. Synchronous container applications diagram

## Challenges with synchronous architectures
When using a synchronous architecture, you will likely encounter some challenges related to scale, performance, and cost:

- **Operation blocking**: The sender does not proceed until Lambda returns, and failure processing, such as retries, must be handled by the sender.
  
- **No native AWS service integrations**: You cannot use several native integrations with other AWS services such as **[Amazon Simple Storage Service (Amazon S3)](https://aws.amazon.com/vi/s3/)**, **[Amazon EventBridge](https://aws.amazon.com/vi/eventbridge/)** and **[Amazon Simple Queue Service (Amazon SQS)](https://aws.amazon.com/vi/sqs/)**.

- **Increased expense**: A 24/7 environment can result in increased expenses if resources are idle, not sized appropriately, and cannot automatically scale.
  
The **[“New for AWS Lambda – Container Image Support”](https://aws.amazon.com/vi/blogs/aws/new-for-aws-lambda-container-image-support/)** blog post offers a serverless, event-based architecture to address these challenges. This approach is explained in detail in the following section.

## Benefits of using Lambda Container Image Support
In our solution, we refactored the synchronous SciLearn application that was deployed on instance-based hosts as an asynchronous event-based application running on Lambda. This solution includes the following benefits:

- **Easier dependency management with Dockerfile**: Dockerfile allows you to install native operating system packages and language-compatible dependencies or use enterprise-ready container images.
  
- **Similar tooling**: The asynchronous and synchronous solutions use **[Amazon Elastic Container Registry (Amazon ECR)](https://aws.amazon.com/vi/ecr/)** to store application artifacts. Therefore, they have the same build and deployment pipeline tools to inspect Dockerfiles. This means your team will likely spend less time and effort learning how to use a new tool.

- **Performance and cost**: Lambda provides sub-second autoscaling that’s aligned with demand. This results in higher availability, lower operational overhead, and cost efficiency.

- **Integrations**: AWS provides more than 200 service integrations to deploy functions as container images on Lambda, without having to develop it yourself so it can be deployed faster.

- **Larger application artifact up to 10 GB**: This includes larger application dependency support, giving you more room to host your files and packages in oppose to hard limit of 250 MB of unzipped files for deployment packages.

## Scaling with asynchronous events
AWS offers two ways to asynchronously scale processing independently and automatically: **[Elastic Beanstalk worker environments](https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/concepts-worker.html)** and **[asynchronous invocation](https://docs.aws.amazon.com/lambda/latest/dg/invocation-async.html)** with Lambda. Both options offer the following:

- They put events in an SQS queue.

- They can be designed to take items from the queue only when they have the capacity available to process a task. This prevents them from becoming overwhelmed.

- They offload tasks from one component of your application by sending them to a queue and process them asynchronously.
  
These asynchronous invocations add default, tunable failure processing and retry mechanisms through “on failure” and “on success” event destinations, as described in the following section.

## Integrations with multiple destinations
“On failure” and “on success” events can be logged in an SQS queue, **[Amazon Simple Notification Service (Amazon SNS)](https://aws.amazon.com/vi/sns/)** topic, EventBridge event bus, or another Lambda function. All four are integrated with most AWS services.

“On failure” events are sent to an SQS dead-letter queue because they cannot be delivered to their destination queues. They will be reprocessed them as needed, and any problems with message processing will be isolated.

Figure 2 shows an asynchronous Amazon API Gateway that has placed an HTTP request as a message in an SQS queue, thus decoupling the components.

The messages within the SQS queue then prompt a Lambda function. This runs the machine learning service SciLearn container in Lambda for data analysis workflows, which are integrated with another SQS dead letter queue for failures processing.

![Example asynchronous-based container applications diagram](/images/blog2/Async.png)
Hình 2. Example asynchronous-based container applications diagram

When you deploy Lambda functions as container images, they benefit from the same operational simplicity, automatic scaling, high availability, and native integrations. This makes it an appealing architecture for our data analytics use cases.

## Design considerations

The following can be considered when implementing Docker Container Images with Lambda:
- Lambda supports container images that have manifest files that follow these formats:
  
  <span style="font-size: 1rem;">+ Docker image manifest V2, schema 2 (Docker version 1.10 and newer)</span>

  <span style="font-size: 1rem;">+ Open Container Initiative (OCI) specifications (v1.0.0 and up)</span>
- Storage in Lambda:

  <span style="font-size: 1rem;">+ Memory (128 MB to 10,240 MB)</span>

  <span style="font-size: 1rem;">+ /tmp space (512 MB)</span>

  <span style="font-size: 1rem;">+ Container images up to10 GB</span>

  <span style="font-size: 1rem;">+ Amazon S3 or <a href="https://aws.amazon.com/vi/efs/">Amazon Elastic File System (Amazon EFS)</a> làm lưu trữ ngoài.</span> as external storage.

- On create/update, Lambda will cache the image to speed up the cold start of functions during execution. Cold starts occur on an initial request to Lambda, which can lead to longer startup times. The first request will maintain an instance of the function for only a short time period. If Lambda has not been called during that period, the next invocation will create a new instance.

- Fine grain role policies are highly recommended for security purposes.

- Container images can use the **[Lambda Extensions](https://docs.aws.amazon.com/lambda/latest/dg/runtimes-extensions-api.html)** to integrate monitoring, security and other tools with the Lambda execution environment.
  
## Conclusion
We were able to architect this synchronous service based on a previously deployed on instance-based hosts and design it to become asynchronous on Amazon Lambda.

By using the new support for container-based images in Lambda and converting our workload into an asynchronous event-based architecture, we were able to overcome these challenges: 

- **Performance and security**:With batch requests, you can scale asynchronous workloads and handle failure records using SQS Dead Letter Queues and Lambda destinations. Using Lambda to integrate with other services (such as EventBridge and SQS) and using Lambda roles simplifies maintaining a granular permission structure. When Lambda uses an Amazon SQS queue as an event source, it can scale up to 60 more instances per minute, with a maximum of 1,000 concurrent invocations.

- **Cost optimization**: Compute resources are a critical component of any application architecture. Overprovisioning computing resources and operating idle resources can lead to higher costs. Because Lambda is serverless, it only incurs costs on when you invoke a function and the resources allocated for each request.

---
## By author

<div style="display:flex;align-items:center;gap:20px;border:1px solid #e0e0e0;border-radius:8px;padding:16px;background-color:#fff;max-width:900px;">

  <img src="/images/blog2/brian_maguire.png" alt="Brian Maguire" style="width:120px;height:auto;border-radius:6px;object-fit:cover;">

  <div style="flex:1;">
    <p style="margin:0;">
      <strong style="font-size:1.1rem;color:#0d1b2a;">Elizabeth Fuentes</strong><br>
      Brian Maguire là Principal Solutions Architect tại Amazon Web Services, nơi anh tập trung giúp khách hàng xây dựng ý tưởng của họ trên đám mây. Anh là một technologist, writer, teacher và student yêu thích việc học hỏi. Brian là đồng tác giả của cuốn sách Scalable Data Streaming with Amazon Kinesis.
    </p>
  </div>

</div>

<div style="display:flex;align-items:center;gap:20px;border:1px solid #e0e0e0;border-radius:8px;padding:16px;background-color:#fff;max-width:900px;">

  <img src="/images/blog2/guy_bachar.png" alt="Guy Bachar" style="width:120px;height:auto;border-radius:6px;object-fit:cover;">

  <div style="flex:1;">
    <p style="margin:0;">
      <strong style="font-size:1.1rem;color:#0d1b2a;">Elizabeth Fuentes</strong><br>
      Guy là Senior Solutions Architect tại AWS. Anh chuyên hỗ trợ người dùng trong Capital Markets và FinTech với các hành trình chuyển đổi lên cloud. Chuyên môn của anh bao gồm quản lý Danh tính (Identity), bảo mật (security) và truyền thông hợp nhất (unified communication).
    </p>
  </div>

</div>

<div style="display:flex;align-items:center;gap:20px;border:1px solid #e0e0e0;border-radius:8px;padding:16px;background-color:#fff;max-width:900px;">

  <img src="/images/blog2/mike_boyar.png" alt="Mike Boyar" style="width:120px;height:auto;border-radius:6px;object-fit:cover;">

  <div style="flex:1;">
    <p style="margin:0;">
      <strong style="font-size:1.1rem;color:#0d1b2a;">Elizabeth Fuentes</strong><br>
      Mike Boyar là Solutions Architect tại AWS. Trong thời gian rảnh, anh thích nướng bánh mì kiểu French country.
    </p>
  </div>

</div>