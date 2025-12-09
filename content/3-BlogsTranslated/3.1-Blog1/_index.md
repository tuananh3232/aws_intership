---
title: "Blog 1"
date: "2025-11-10"
weight: 1
chapter: false
pre: " <b> 3.1. </b> "
---
# Enhance AI-assisted development with Amazon ECS, Amazon EKS and AWS Serverless MCP server

by: Elizabeth Fuentes

on 29 May 2025 

in: **[Amazon Elastic Container Service](https://aws.amazon.com/vi/blogs/aws/category/compute/amazon-elastic-container-service/)**, **[Amazon Elastic Kubernetes Service](https://aws.amazon.com/vi/blogs/aws/category/compute/amazon-kubernetes-service/)**, **[Amazon Q](https://aws.amazon.com/vi/blogs/aws/category/amazon-q/)**, **[Amazon Q Developer](https://aws.amazon.com/vi/blogs/aws/category/amazon-q/amazon-q-developer/)**, **[AWS Lambda](https://aws.amazon.com/vi/blogs/aws/category/compute/aws-lambda/)**, **[Compute](https://aws.amazon.com/vi/blogs/aws/category/compute/)**, **[Featured](https://aws.amazon.com/vi/blogs/aws/category/featured/)**, **[Launch](https://aws.amazon.com/vi/blogs/aws/category/news/launch/)**, **[News](https://aws.amazon.com/vi/blogs/aws/category/news/)**, **[Serverless](https://aws.amazon.com/vi/blogs/aws/category/serverless/)**

Today, we’re introducing specialized **[Model Context Protocol (MCP)](https://github.com/modelcontextprotocol)** servers for **[Amazon Elastic Container Service (Amazon ECS)](https://aws.amazon.com/vi/ecs/)**, **[Amazon Elastic Kubernetes Service (Amazon EKS)](https://aws.amazon.com/vi/eks/)** and **[AWS Serverless](https://aws.amazon.com/vi/serverless/)**, now available in the **[AWS Labs GitHub](https://github.com/awslabs/mcp)**. These open source solutions extend AI development assistants capabilities with real-time, contextual responses that go beyond their pre-trained knowledge. While (**[Large Language Models - LLM](https://aws.amazon.com/what-is/large-language-model/)**) within AI assistants rely on public documentation, MCP servers deliver current context and service-specific guidance to help you prevent common deployment errors and provide more accurate service interactions.

You can use these open source solutions to develop applications faster, using up-to-date knowledge of **[Amazon Web Services (AWS)](https://aws.amazon.com/vi/)** capabilities and configurations during the build and deployment process. Whether you’re writing code in your **[integrated development environment - IDE)](https://ap-southeast-1.console.aws.amazon.com/console/home?region=ap-southeast-1)** or debugging production issues, these MCP servers support AI code assistants with deep understanding of Amazon ECS, Amazon EKS, and AWS Serverless capabilities, accelerating the journey from code to production. They work with popular AI-enabled IDEs, including **[Amazon Q Developer trên command line (CLI)](https://docs.aws.amazon.com/amazonq/latest/qdeveloper-ug/command-line.html)**,to help you build and deploy applications using natural language commands.
- The **[Amazon ECS MCP Server](https://awslabs.github.io/mcp/servers/ecs-mcp-server/)** containerizes and deploys applications to Amazon ECS within minutes by configuring all relevant AWS resources, including load balancers, networking, auto-scaling, monitoring, Amazon ECS task definitions, and services. Using natural language instructions, you can manage cluster operations, implement auto-scaling strategies, and use real-time troubleshooting capabilities to identify and resolve deployment issues quickly.
  
- For Kubernetes environments, the **[Amazon EKS MCP Server](https://awslabs.github.io/mcp/servers/eks-mcp-server/)** provides AI assistants with up-to-date, contextual information about your specific EKS environment. It offers access to the latest EKS features, knowledge base, and cluster state information. This gives AI code assistants more accurate, tailored guidance throughout the application lifecycle, from initial setup to production deployment.
  
- The **[AWS Serverless MCP Server](https://awslabs.github.io/mcp/servers/aws-serverless-mcp-server/)** enhances the serverless development experience by providing AI coding assistants with comprehensive knowledge of serverless patterns, best practices, and AWS services. Using **[AWS Serverless Application Model Command Line Interface (AWS SAM CLI)](https://docs.aws.amazon.com/serverless-application-model/latest/developerguide/using-sam-cli.html)**integration, you can handle events and deploy infrastructure while implementing proven architectural patterns. This integration streamlines function lifecycles, service integrations, and operational requirements throughout your application development process. The server also provides contextual guidance for infrastructure as code decisions, **[AWS Lambda](https://aws.amazon.com/vi/lambda/)** specific best practices, and event schemas for AWS Lambda event source mappings.

## Let’s see it in action

If this is your first time using AWS MCP servers, visit the **[Installation and Setup guide trong AWS Labs GitHub repository](https://github.com/awslabs/mcp?tab=readme-ov-file#installation-and-setup)** to installation instructions. Once installed, add the following MCP server configuration to your local setup:

Install **[Amazon Q for command line (CLI)](https://docs.aws.amazon.com/amazonq/latest/qdeveloper-ug/command-line-installing.html)** and add the conﬁguration to <span style="color:#d6336c;font-style:italic;background-color:#f5f5f5;padding:2px 6px;border-radius:4px">~/.aws/amazonq/mcp.json</span>. Nyou’re already an Amazon Q CLI user, add only the configuration.

```json
JSON
{
  "mcpServers": {
    "awslabs.aws-serverless-mcp": {
      "command": "uvx",
      "args": ["awslabs.aws-serverless_mcp_server@latest"]
    },
    "awslabs.ecs-mcp-server": {
      "disabled": false,
      "command": "uvx",
      "args": ["awslabs.ecs-mcp-server@latest"]
    },
    "awslabs.eks-mcp-server": {
      "disabled": false,
      "command": "uv",
      "args": ["awslabs.eks-mcp-server@latest"]
    }
  }
}
```
For this demo I’m going to use the Amazon Q CLI to create an application that understands video using **[02_using_converse_api.ipynb](https://github.com/aws-samples/amazon-nova-samples/blob/main/multimodal-understanding/getting-started/02_using_converse_api.ipynb)** from **[Amazon Nova model cookbook repository](https://github.com/aws-samples/amazon-nova-samples)** as sample code. To do this, I send the following prompt:.

```ymal
I want to create a backend application that automatically extracts metadata and understands the content of images and videos uploaded to an S3 bucket and stores that information in a database. I'd like to use a serverless system for processing. Could you generate everything I need, including the code and commands or steps to set up the necessary infrastructure, for it to work from start to finish? - Use 02_using_converse_api.ipynb as example code for the image and video understanding.
```
Amazon Q CLI identifies the necessary tools, including the MCP server <span style="color:#d6336c;font-style:italic;background-color:#f5f5f5;padding:2px 6px;border-radius:4px">awslabs.aws-serverless-mcp-server</span>. Through a single interaction, the AWS Serverless MCP server determines all requirements and best practices for building a robust architecture.

![Amazon Q CLI](/images/blog1/new_serveless.png)

I ask to Amazon Q CLI that build and test the application, but encountered an error. Amazon Q CLI quickly resolved the issue using available tools. I verified success by checking the record created in the **[Amazon DynamoDB](https://aws.amazon.com/vi/dynamodb/)** table and testing the application with the **[dog2.jpeg](https://raw.githubusercontent.com/aws-samples/amazon-nova-samples/refs/heads/main/multimodal-understanding/getting-started/media/dog2.jpeg)**.

![Azmazon DynamDB](/images/blog1/amazon_dynamoDB.png)

To enhance video processing capabilities, I decided to migrate my media analysis application to a containerized architecture. I used this prompt:


```ymal
I'd like you to create a simple application like the media analysis one, but instead of being serverless, it should be containerized. Please help me build it in a new CDK stack.
```

Amazon Q Developer begins building the application. I took advantage of this time to grab a coffee. When I returned to my desk, coffee in hand, I was pleasantly surprised to find the application ready. To ensure everything was up to current standards, I simply asked:


```ymal
please review the code and all app using the awslabsecs_mcp_server tools
```


![ecs_review](/images/blog1/ecs_review.png)

Amazon Q Developer CLI gives me a summary with all the improvements and a conclusion.

![ecs_conclusion](/images/blog1/ecs_conclusion.png)

I ask it to make all the necessary changes, once ready I ask Amazon Q developer CLI to deploy it in my account, all using natural language.

After a few minutes, I review that I have a complete containerized application from the S3 bucket to all the necessary networking.

![Amedia_anlysis_container_stack](/images/blog1/media_anlysis_container_stack.png)

I ask Amazon Q developer CLI to test the app send it **[the-sea.mp4]()** and received a timed out error, so Amazon Q CLI decides to use the <span style="color:#d6336c;font-style:italic;background-color:#f5f5f5;padding:2px 6px;border-radius:4px">fetch_task_logs</span> from <span style="color:#d6336c;font-style:italic;background-color:#f5f5f5;padding:2px 6px;border-radius:4px">awslabsecs_mcp_server</span> tool to review the logs, identify the error and then fix it.

![error_eks](/images/blog1/error_eks.png)

After a new deployment, I try it again, and the application successfully processed the video file

I can see the records in my Amazon DynamoDB table.

![error_eks](/images/blog1/amazon_dynamoDB1.png)

To test the Amazon EKS MCP server, I have code for a web app in the auction-website-main folder and I want to build a web robust app, for that I asked Amazon Q CLI to help me with this prompt:

``` ymal
Create a web application using the existing code in the auction-website-main folder. This application will grow, so I would like to create it in a new EKS cluster
```

Once the Docker file is created, Amazon Q CLI identifies <span style="color:#d6336c;font-style:italic;background-color:#f5f5f5;padding:2px 6px;border-radius:4px">generate_app_manifests</span> from <span style="color:#d6336c;font-style:italic;background-color:#f5f5f5;padding:2px 6px;border-radius:4px">awslabseks_mcp_server</span> as a reliable tool to create a Kubernetes manifests for the application.

![docker_1](/images/blog1/docker_1.png)

Then create a new EKS cluster using the <span style="color:#d6336c;font-style:italic;background-color:#f5f5f5;padding:2px 6px;border-radius:4px">manage_eks_staks</span> tool.

![docker_2](/images/blog1/docker_2.png)

Once the app is ready, the Amazon Q CLI deploys it and gives me a summary of what it created.

![docker_3](/images/blog1/docker_3.png)

I can see the cluster status in the console.

![console_eks](/images/blog1/console_eks.png)

After a few minutes and resolving a couple of issues using the <span style="color:#d6336c;font-style:italic;background-color:#f5f5f5;padding:2px 6px;border-radius:4px">search_eks_troubleshoot_guide</span> tool the application is ready to use.

![eks_done](/images/blog1/eks_done.png)

Now I have a Kitties marketplace web app, deployed on Amazon EKS using only natural language commands through Amazon Q CLI.


## Get started today

Visit **[AWS Labs GitHub repository](https://github.com/awslabs/mcp?tab=readme-ov-file#installation-and-setup)** to start using these AWS MCP servers and enhance your AI-powered developmen there. The repository includes implementation guides, example configurations, and additional specialized servers **[to run AWS Lambda function](https://github.com/awslabs/mcp/tree/main?tab=readme-ov-file#aws-lambda-mcp-server)**, which transforms your existing AWS Lambda functions into AI-accessible tools without code modifications, and **[Amazon Bedrock Knowledge Bases Retrieval MCP server](https://github.com/awslabs/mcp/tree/main?tab=readme-ov-file#amazon-bedrock-knowledge-bases-retrieval-mcp-server)**,which provides seamless access to your Amazon Bedrock knowledge bases. Other **[AWS specialized servers](https://github.com/awslabs/mcp?tab=readme-ov-file#installation-and-setup)** in the repository include documentation, example configurations, and implementation guides to begin building applications with greater speed and reliability.

To learn more about MCP Servers for AWS Serverless and Containers and how they can transform your AI-assisted application development, visit the **[Introducing AWS Serverless MCP Server: AI-powered development for modern applications](https://aws.amazon.com/vi/blogs/compute/introducing-aws-serverless-mcp-server-ai-powered-development-for-modern-applications/)**, **[Automating AI-assisted container deployments with the Amazon ECS MCP Server](https://aws.amazon.com/vi/blogs/containers/automating-ai-assisted-container-deployments-with-amazon-ecs-mcp-server/)**, **[Accelerating application development with the Amazon EKS MCP](https://aws.amazon.com/vi/blogs/containers/accelerating-application-development-with-the-amazon-eks-model-context-protocol-server/)** server deep-dive— **[Eli](https://www.linkedin.com/in/lizfue/)**

---
## About author
<div style="display:flex;align-items:center;gap:20px;border:1px solid #e0e0e0;border-radius:8px;padding:16px;background-color:#fff;max-width:900px;">

  <img src="/images/blog1/Elizabeth-Fuentas.png" alt="Elizabeth Fuentes" style="width:120px;height:auto;border-radius:6px;object-fit:cover;">

  <div style="flex:1;">
    <p style="margin:0;">
      <strong style="font-size:1.1rem;color:#0d1b2a;">Elizabeth Fuentes</strong><br>
      My mission is to break down complex concepts into easily digestible explanations, inspiring developers to continually expand their skills and knowledge.
      Through conferences, tutorials, and online resources, I share my expertise with the global developer community, providing them with the tools and confidence
      to reach their full potential. With a hands-on approach and a commitment to simplifying the complex, I strive to be a catalyst for growth and learning in
      the world of AWS technology.
    </p>
  </div>

</div>