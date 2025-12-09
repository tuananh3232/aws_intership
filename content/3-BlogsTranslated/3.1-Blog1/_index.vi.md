---
title: "Blog 1"
date: "2025-11-10"
weight: 1
chapter: false
pre: " <b> 3.1. </b> "
---
# Nâng cao trải nghiệm phát triển có trợ giúp của AI với Amazon ECS, Amazon EKS và AWS Serverless MCP server

Tác giả: Elizabeth Fuentes

Ngày 29 tháng 5, 2025 

Danh mục: **[Amazon Elastic Container Service](https://aws.amazon.com/vi/blogs/aws/category/compute/amazon-elastic-container-service/)**, **[Amazon Elastic Kubernetes Service](https://aws.amazon.com/vi/blogs/aws/category/compute/amazon-kubernetes-service/)**, **[Amazon Q](https://aws.amazon.com/vi/blogs/aws/category/amazon-q/)**, **[Amazon Q Developer](https://aws.amazon.com/vi/blogs/aws/category/amazon-q/amazon-q-developer/)**, **[AWS Lambda](https://aws.amazon.com/vi/blogs/aws/category/compute/aws-lambda/)**, **[Compute](https://aws.amazon.com/vi/blogs/aws/category/compute/)**, **[Featured](https://aws.amazon.com/vi/blogs/aws/category/featured/)**, **[Launch](https://aws.amazon.com/vi/blogs/aws/category/news/launch/)**, **[News](https://aws.amazon.com/vi/blogs/aws/category/news/)**, **[Serverless](https://aws.amazon.com/vi/blogs/aws/category/serverless/)**

Hôm nay, chúng tôi giới thiệu các máy chủ **[Model Context Protocol (MCP)](https://github.com/modelcontextprotocol)** chuyên biệt dành cho **[Amazon Elastic Container Service (Amazon ECS)](https://aws.amazon.com/vi/ecs/)**, **[Amazon Elastic Kubernetes Service (Amazon EKS)](https://aws.amazon.com/vi/eks/)** và **[AWS Serverless](https://aws.amazon.com/vi/serverless/)**, hiện đã có sẵn trong repository **[AWS Labs GitHub](https://github.com/awslabs/mcp)**. Các giải pháp mã nguồn mở này mở rộng khả năng của các trợ lý phát triển AI với các phản hồi theo ngữ cảnh và thời gian thực, vượt xa kiến thức được tiền huấn luyện (pre-trained) của chúng. Trong khi các Mô hình Ngôn ngữ Lớn (**[Large Language Models - LLM](https://aws.amazon.com/what-is/large-language-model/)**) bên trong các trợ lý AI dựa vào tài liệu công khai, thì các máy chủ MCP cung cấp ngữ cảnh hiện tại và hướng dẫn cụ thể cho từng dịch vụ để giúp bạn ngăn ngừa các lỗi triển khai (deployment) thường gặp và cung cấp các tương tác dịch vụ chính xác hơn.

Bạn có thể sử dụng các giải pháp mã nguồn mở này để phát triển ứng dụng nhanh hơn, với kiến thức cập nhật về khả năng và cấu hình của **[Amazon Web Services (AWS)](https://aws.amazon.com/vi/)** trong suốt quá trình xây dựng và triển khai. Dù bạn đang viết mã trong **[môi trường phát triển tích hợp (integrated development environment - IDE)](https://ap-southeast-1.console.aws.amazon.com/console/home?region=ap-southeast-1)** hay gỡ lỗi các sự cố trong môi trường production, các MCP server này hỗ trợ các trợ lý lập trình AI (AI code assistants) với hiểu biết sâu về khả năng của Amazon ECS, Amazon EKS và AWS Serverless, giúp tăng tốc hành trình từ mã nguồn đến triển khai thực tế. Chúng hoạt động với các IDE có hỗ trợ AI phổ biến, bao gồm [Amazon Q Developer trên command line (CLI)](https://docs.aws.amazon.com/amazonq/latest/qdeveloper-ug/command-line.html), giúp bạn xây dựng và triển khai ứng dụng bằng các lệnh ngôn ngữ tự nhiên.
- **[Amazon ECS MCP Server](https://awslabs.github.io/mcp/servers/ecs-mcp-server/)** đóng gói và triển khai ứng dụng lên Amazon ECS chỉ trong vài phút bằng cách cấu hình tất cả các tài nguyên AWS liên quan, bao gồm bộ cân bằng tải (load balancers), cấu hình mạng (networking), auto-scaling (tự động mở rộng quy mô), monitoring (giám sát), Amazon ECS task definitions, và services. Bằng các hướng dẫn bằng ngôn ngữ tự nhiên, bạn có thể quản lý hoạt động cụm (cluster operations), triển khai các chiến lược tự động mở rộng quy mô (auto-scaling strategies), và sử dụng khả năng xử lý sự cố (troubleshooting) thời gian thực để nhanh chóng xác định và giải quyết các vấn đề triển khai (deployment issues).
  
- Đối với môi trường Kubernetes, **[Amazon EKS MCP Server](https://awslabs.github.io/mcp/servers/eks-mcp-server/)** cung cấp cho trợ lý AI thông tin theo ngữ cảnh, cập nhật mới nhất về môi trường EKS cụ thể của bạn. Nó mang lại quyền truy cập vào các tính năng EKS, cơ sở tri thức và thông tin trạng thái cụm mới nhất. Điều này cung cấp cho các trợ lý mã nguồn AI (AI code assistants) hướng dẫn chính xác và được tùy chỉnh hơn trong suốt vòng đời ứng dụng (application lifecycle), từ thiết lập ban đầu (initial setup) đến triển khai lên môi trường sản xuất (production deployment).
  
- **[AWS Serverless MCP Server](https://awslabs.github.io/mcp/servers/aws-serverless-mcp-server/)** nâng cao trải nghiệm phát triển không máy chủ bằng cách cung cấp cho trợ lý AI lập trình (AI coding assistants) kiến thức toàn diện về các mẫu serverless (serverless patterns), các giải pháp tốt nhất (best practices) và các dịch vụ AWS. Với tích hợp **[AWS Serverless Application Model Command Line Interface (AWS SAM CLI)](https://docs.aws.amazon.com/serverless-application-model/latest/developerguide/using-sam-cli.html)**, bạn có thể xử lý sự kiện và triển khai cơ sở hạ tầng trong khi áp dụng các mẫu kiến trúc đã được chứng minh. Sự tích hợp này giúp đơn giản hóa vòng đời hàm, tích hợp dịch vụ và yêu cầu vận hành trong suốt quá trình phát triển ứng dụng. Server này cũng cung cấp hướng dẫn theo ngữ cảnh cho các quyết định về cơ sở hạ tầng dưới dạng mã (infrastructure as code), các phương pháp hay nhất (best practices) dành riêng cho **[AWS Lambda](https://aws.amazon.com/vi/lambda/)**, và event schemas (lược đồ sự kiện) cho AWS Lambda event source mappings.

## Hãy cùng xem nó hoạt động như thế nào

Nếu đây là lần đầu bạn sử dụng AWS MCP servers, hãy truy cập **[Installation and Setup guide trong AWS Labs GitHub repository](https://github.com/awslabs/mcp?tab=readme-ov-file#installation-and-setup)** để xem hướng dẫn cài đặt. Sau khi cài đặt, thêm cấu hình MCP server sau vào thiết lập cục bộ:

Cài đặt **[Amazon Q for command line (CLI)](https://docs.aws.amazon.com/amazonq/latest/qdeveloper-ug/command-line-installing.html)** và thêm cấu hình vào <span style="color:#d6336c;font-style:italic;background-color:#f5f5f5;padding:2px 6px;border-radius:4px">~/.aws/amazonq/mcp.json</span>. Nếu bạn đã là người dùng Amazon Q CLI, chỉ cần thêm phần cấu hình.

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
Đối với bản demo này, tôi sử dụng Amazon Q CLI để tạo một ứng dụng có khả năng hiểu video, sử dụng tệp **[02_using_converse_api.ipynb](https://github.com/aws-samples/amazon-nova-samples/blob/main/multimodal-understanding/getting-started/02_using_converse_api.ipynb)** từ **[Amazon Nova model cookbook repository](https://github.com/aws-samples/amazon-nova-samples)** làm mã mẫu.

```ymal
I want to create a backend application that automatically extracts metadata and understands the content of images and videos uploaded to an S3 bucket and stores that information in a database. I'd like to use a serverless system for processing. Could you generate everything I need, including the code and commands or steps to set up the necessary infrastructure, for it to work from start to finish? - Use 02_using_converse_api.ipynb as example code for the image and video understanding.
```
Amazon Q CLI xác định các công cụ cần thiết, bao gồm MCP server <span style="color:#d6336c;font-style:italic;background-color:#f5f5f5;padding:2px 6px;border-radius:4px">awslabs.aws-serverless-mcp-server</span>. Chỉ với một lần tương tác, AWS Serverless MCP server xác định tất cả yêu cầu và giải pháp tốt nhất (best practices) để xây dựng một kiến trúc vững chắc (robust architecture).

![Amazon Q CLI](/images/blog1/new_serveless.png)

Tôi yêu cầu Amazon Q CLI build và test ứng dụng, nhưng gặp lỗi. Amazon Q CLI nhanh chóng khắc phục sự cố bằng các công cụ sẵn có. Tôi xác minh thành công bằng cách kiểm tra bản ghi được tạo trong bảng **[Amazon DynamoDB](https://aws.amazon.com/vi/dynamodb/)** và kiểm thử ứng dụng với tệp **[dog2.jpeg](https://raw.githubusercontent.com/aws-samples/amazon-nova-samples/refs/heads/main/multimodal-understanding/getting-started/media/dog2.jpeg)**.

![Azmazon DynamDB](/images/blog1/amazon_dynamoDB.png)

Để nâng cao khả năng xử lý video, tôi quyết định chuyển ứng dụng phân tích media của mình sang kiến trúc được container hóa (containerized architecture).


```ymal
I'd like you to create a simple application like the media analysis one, but instead of being serverless, it should be containerized. Please help me build it in a new CDK stack.
```

Amazon Q Developer bắt đầu xây dựng ứng dụng. Tôi tranh thủ đi pha cà phê, và khi quay lại, ứng dụng đã sẵn sàng. Để đảm bảo mọi thứ tuân thủ tiêu chuẩn mới nhất, tôi chỉ cần yêu cầu:


```ymal
please review the code and all app using the awslabsecs_mcp_server tools
```


![ecs_review](/images/blog1/ecs_review.png)

Amazon Q Developer CLI đưa ra bản tóm tắt với các cải tiến và kết luận.

![ecs_conclusion](/images/blog1/ecs_conclusion.png)

Tôi yêu cầu nó thực hiện mọi thay đổi cần thiết, sau đó dùng Amazon Q Developer CLI để triển khai ứng dụng trong tài khoản của mình – tất cả bằng các lệnh ngôn ngữ tự nhiên.

Sau vài phút, tôi kiểm tra thấy mình đã có một ứng dụng được container hóa hoàn chỉnh, từ S3 bucket đến toàn bộ phần networking cần thiết.

![media_anlysis_container_stack](/images/blog1/media_anlysis_container_stack.png)

Tôi yêu cầu Amazon Q Developer CLI test ứng dụng, gửi tệp video **[the-sea.mp4]()** và nhận lỗi timed out. Amazon Q CLI quyết định dùng công cụ <span style="color:#d6336c;font-style:italic;background-color:#f5f5f5;padding:2px 6px;border-radius:4px">fetch_task_logs</span> từ <span style="color:#d6336c;font-style:italic;background-color:#f5f5f5;padding:2px 6px;border-radius:4px">awslabsecs_mcp_server</span> để xem xét các bản ghi nhật ký (bản ghi nhật ký), xác định lỗi và khắc phục.

![error_eks](/images/blog1/error_eks.png)

Sau khi triển khai lại, tôi thử lại và ứng dụng xử lý video thành công.

Tôi có thể thấy bản ghi trong bảng Amazon DynamoDB.

![amazon_dynamoDB1](/images/blog1/amazon_dynamoDB1.png)

Để thử nghiệm Amazon EKS MCP server, tôi có mã cho một web app (ứng dụng web) trong thư mục auction-website-main, và muốn xây dựng một ứng dụng mạnh mẽ hơn. Tôi yêu cầu Amazon Q CLI bằng prompt:

``` ymal
Create a web application using the existing code in the auction-website-main folder. This application will grow, so I would like to create it in a new EKS cluster
```

Khi tệp Docker file được tạo, Amazon Q CLI xác định công cụ <span style="color:#d6336c;font-style:italic;background-color:#f5f5f5;padding:2px 6px;border-radius:4px">generate_app_manifests</span> từ <span style="color:#d6336c;font-style:italic;background-color:#f5f5f5;padding:2px 6px;border-radius:4px">awslabseks_mcp_server</span> là một công cụ đáng tin cậy để tạo Kubernetes manifests (tệp cấu hình Kubernetes) cho ứng dụng.

![docker_1](/images/blog1/docker_1.png)

Sau đó, nó tạo một cụm EKS (EKS cluster) mới bằng công cụ <span style="color:#d6336c;font-style:italic;background-color:#f5f5f5;padding:2px 6px;border-radius:4px">manage_eks_staks</span>.

![docker_2](/images/blog1/docker_2.png)

Khi ứng dụng sẵn sàng, Amazon Q CLI triển khai nó và cung cấp cho tôi một bản tóm tắt về những gì đã được tạo. 

![docker_3](/images/blog1/docker_3.png)

Tôi có thể xem trạng thái cluster trong Console.

![console_eks](/images/blog1/console_eks.png)

Sau vài phút, và sau khi giải quyết một số vấn đề bằng công cụ <span style="color:#d6336c;font-style:italic;background-color:#f5f5f5;padding:2px 6px;border-radius:4px">search_eks_troubleshoot_guide</span> ứng dụng đã sẵn sàng sử dụng.

![eks_done](/images/blog1/eks_done.png)

Giờ đây, tôi có một Kitties marketplace web app được triển khai trên Amazon EKS, chỉ bằng các lệnh bằng ngôn ngữ tự nhiên thông qua Amazon Q CLI.


## Bắt đầu ngay hôm nay

Hãy truy cập **[AWS Labs GitHub repository](https://github.com/awslabs/mcp?tab=readme-ov-file#installation-and-setup)** để bắt đầu sử dụng các AWS MCP servers này và nâng cao khả năng phát triển được hỗ trợ bởi AI. Kho lưu trữ này bao gồm các hướng dẫn triển khai (implementation guides), cấu hình mẫu (sample configurations), và các máy chủ chuyên biệt bổ sung **[để chạy AWS Lambda function](https://github.com/awslabs/mcp/tree/main?tab=readme-ov-file#aws-lambda-mcp-server)**, công cụ này biến các AWS Lambda functions hiện có của bạn thành những công cụ AI có thể truy cập được mà không cần sửa đổi mã. Ngoài ra còn có **[Amazon Bedrock Knowledge Bases Retrieval MCP server](https://github.com/awslabs/mcp/tree/main?tab=readme-ov-file#amazon-bedrock-knowledge-bases-retrieval-mcp-server)**, giúp truy cập liền mạch vào các Amazon Bedrock knowledge bases của bạn. Các **[AWS specialized servers](https://github.com/awslabs/mcp?tab=readme-ov-file#installation-and-setup)** khác trong kho lưu trữ này cũng bao gồm tài liệu, cấu hình mẫu và hướng dẫn triển khai để giúp bạn bắt đầu xây dựng ứng dụng với tốc độ nhanh hơn và độ tin cậy cao hơn.

Để tìm hiểu thêm về MCP Servers dành cho AWS Serverless và Containers, cũng như cách chúng có thể thay đổi quy trình phát triển ứng dụng được hỗ trợ bởi AI của bạn, hãy truy cập các bài phân tích chuyên sâu sau: **[Introducing AWS Serverless MCP Server: AI-powered development for modern applications](https://aws.amazon.com/vi/blogs/compute/introducing-aws-serverless-mcp-server-ai-powered-development-for-modern-applications/)**, **[Automating AI-assisted container deployments with the Amazon ECS MCP Server](https://aws.amazon.com/vi/blogs/containers/automating-ai-assisted-container-deployments-with-amazon-ecs-mcp-server/)**, **[Accelerating application development with the Amazon EKS MCP](https://aws.amazon.com/vi/blogs/containers/accelerating-application-development-with-the-amazon-eks-model-context-protocol-server/)** server deep-dive— **[Eli](https://www.linkedin.com/in/lizfue/)**

---
## Về tác giả

<div style="display:flex;align-items:center;gap:20px;border:1px solid #e0e0e0;border-radius:8px;padding:16px;background-color:#fff;max-width:900px;">

  <img src="/images/blog1/Elizabeth-Fuentas.png" alt="Elizabeth Fuentes" style="width:120px;height:auto;border-radius:6px;object-fit:cover;">

  <div style="flex:1;">
    <p style="margin:0;">
      <strong style="font-size:1.1rem;color:#0d1b2a;">Elizabeth Fuentes</strong><br>
      Sứ mệnh của tôi là phân tích và truyền đạt những khái niệm phức tạp thành các lời giải thích dễ hiểu, truyền cảm hứng cho các nhà phát triển không ngừng mở rộng kỹ năng và kiến thức của họ. Thông qua các hội thảo, hướng dẫn và tài nguyên trực tuyến, tôi chia sẻ chuyên môn của mình với cộng đồng nhà phát triển toàn cầu, cung cấp cho họ các công cụ và sự tự tin để đạt được tiềm năng tối đa. Với cách tiếp cận thực tiễn và cam kết đơn giản hóa những điều phức tạp, tôi nỗ lực trở thành chất xúc tác cho sự phát triển và học hỏi trong thế giới công nghệ AWS
    </p>
  </div>

</div>