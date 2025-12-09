---
title: "Blog 2"
date: "2025-11-10"
weight: 1
chapter: false
pre: " <b> 3.2. </b> "
---
# Mở rộng quy mô (Scaling) Container Phân tích Dữ liệu bằng Hàm AWS Lambda dựa trên sự kiện

Tác giả: Brian Maguire, Guy Bachar, and Mike Boyar

Ngày đăng: ngày 30 tháng 8, 2021

Danh mục: **[Amazon API Gateway](https://aws.amazon.com/vi/blogs/architecture/category/application-services/amazon-api-gateway-application-services/)**, **[Amazon EC2](https://aws.amazon.com/vi/blogs/architecture/category/compute/amazon-ec2/)**, **[Amazon Elastic Container Service](https://aws.amazon.com/vi/blogs/architecture/category/compute/amazon-elastic-container-service/)**, **[Analytics](https://aws.amazon.com/vi/blogs/architecture/category/analytics/)**, **[Architecture](https://aws.amazon.com/vi/blogs/architecture/category/architecture/)**, **[AWS Elastic Beanstalk](https://aws.amazon.com/vi/blogs/architecture/category/compute/aws-elastic-beanstalk/)**, **[Intermediate (200)](https://aws.amazon.com/vi/blogs/architecture/category/learning-levels/intermediate-200/)**, **[Manufacturing](https://aws.amazon.com/vi/blogs/architecture/category/industries/manufacturing/)** 

Ngành tiếp thị  thu thập và sử dụng dữ liệu từ nhiều giai đoạn khác nhau trong hành trình của khách hàng. Khi phân tích dữ liệu này, họ thiết lập các chỉ số (metrics) và phát triển các thông tin chi tiết có thể hành động (actionable insights), sau đó được sử dụng để đầu tư vào khách hàng và tạo ra doanh thu.

Nếu bạn là một nhà khoa học dữ liệu hoặc nhà phát triển trong lĩnh vực tiếp thị, bạn có thể thường xuyên sử dụng các containers cho các dịch vụ như thu thập và chuẩn bị dữ liệu, phát triển mô hình machine learning, và thực hiện phân tích thống kê. Do loại và khối lượng dữ liệu tiếp thị được thu thập ngày càng tăng nhanh, bạn sẽ cần một giải pháp để quản lý quy mô (scale), chi phí (costs), và số lượng tích hợp phân tích dữ liệu (data analytics integrations) cần thiết.

Trong bài viết này, chúng tôi cung cấp một giải pháp có thể hoạt động và mở rộng với lưu lượng động và được tối ưu hóa chi phí cho việc tiêu thụ theo nhu cầu. Giải pháp này sử dụng các ứng dụng khoa học dữ liệu dựa trên container đồng bộ (synchronous container-based) được triển khai với các kiến trúc dựa trên container bất đồng bộ (asynchronous container-based architectures) trên **[AWS Lambda](https://aws.amazon.com/vi/lambda/)**. Kiến trúc serverless này tự động hóa các quy trình công việc phân tích dữ liệu (data analytics workflows) bằng cách sử dụng các prompts dựa trên sự kiện (event-based prompts).

## Ứng dụng container đồng bộ 
Các ứng dụng khoa học dữ liệu (data science applications) thường được triển khai tới các container instance chuyên dụng (dedicated container instances), và các yêu cầu của chúng được định tuyến bởi Amazon API Gateway hoặc một bộ cân bằng tải (load balancer). Thông thường, Amazon API Gateway định tuyến các yêu cầu HTTP như các lần gọi đồng bộ tới các container host dựa trên instance.

Mục tiêu của các yêu cầu này là một ứng dụng dựa trên container chạy dịch vụ machine learning (SciLearn). Service container được cấu hình với các dependency packages cần thiết như **[scikit-learn](http://c/Users/mccbonni/AppData/Local/Temp/scikit-learn.org)**, **[pandas](http://c/Users/mccbonni/AppData/Local/Temp/pandas.pydata.org)**, **[NumPy](https://numpy.org/)** và **[SciPy](https://scipy.org/)**.

Các container thường được triển khai trên các mục tiêu (targets) khác nhau như tại chỗ (on-premises), **[Amazon Elastic Container Service (Amazon ECS)](https://aws.amazon.com/vi/ecs/)**, **[Amazon Elastic Compute Cloud (Amazon EC2)](https://aws.amazon.com/vi/ec2/)** và **[AWS Elastic Beanstalk](https://aws.amazon.com/vi/elasticbeanstalk/)**. ác dịch vụ này chạy đồng bộ (synchronously) và mở rộng quy mô (scale) thông qua các nhóm **[Amazon Auto Scaling groups](https://aws.amazon.com/vi/autoscaling/)** của Amazon và một mô hình định giá tiêu thụ dựa trên thời gian (time-based consumption pricing model).

![Sơ đồ ứng dụng container đồng bộ](/images/blog2/Lambdasync.png)
Figure 1. Sơ đồ ứng dụng container đồng bộ

## Thách thức với kiến trúc đồng bộ 
Khi sử dụng kiến trúc đồng bộ, bạn có thể gặp một số thách thức liên quan đến khả năng mở rộng, hiệu năng và chi phí:

- **Chặn hoạt động**: Bên gửi không tiếp tục cho đến khi Lambda trả về, và việc xử lý lỗi (failure processing), chẳng hạn như thử lại (retries), phải được xử lý bởi bên gửi.
  
- **Không tích hợp gốc (native) với dịch vụ AWS**: không thể sử dụng nhiều tích hợp gốc với các dịch vụ AWS khác như **[Amazon Simple Storage Service (Amazon S3)](https://aws.amazon.com/vi/s3/)**, **[Amazon EventBridge](https://aws.amazon.com/vi/eventbridge/)** và **[Amazon Simple Queue Service (Amazon SQS)](https://aws.amazon.com/vi/sqs/)**.

- **Chi phí tăng**: môi trường hoạt động 24/7 có thể làm tăng chi phí nếu tài nguyên nhàn rỗi (idle), không được định cỡ phù hợp và không thể tự động mở rộng.
  
Bài viết **[“New for AWS Lambda – Container Image Support”](https://aws.amazon.com/vi/blogs/aws/new-for-aws-lambda-container-image-support/)** giới thiệu một kiến trúc serverless dựa trên sự kiện (serverless, event-based architecture) để giải quyết các thách thức này.

## Lợi ích của việc sử dụng Lambda Container Image Support
Trong giải pháp của chúng tôi, chúng tôi đã tái cấu trúc (refactored) ứng dụng SciLearn đồng bộ (synchronous) vốn được triển khai trên các host dựa trên instance (instance-based hosts) thành một ứng dụng bất đồng bộ dựa trên sự kiện (asynchronous event-based application) chạy trên Lambda. Giải pháp này mang lại các lợi ích sau:

- **Quản lý dependencies dễ dàng hơn với Dockerfile**: Dockerfile cho phép bạn cài đặt các gói hệ điều hành gốc (native operating system packages) và các dependencies tương thích ngôn ngữ (language-compatible dependencies) hoặc sử dụng các container image sẵn sàng cho doanh nghiệp (enterprise-ready container images).
  
- **Công cụ tương tự**: cả hai giải pháp đồng bộ và bất đồng bộ đều sử dụng **[Amazon Elastic Container Registry (Amazon ECR)](https://aws.amazon.com/vi/ecr/)** để lưu trữ các tệp tạo tác ứng dụng (application artifacts). Do đó, cả hai đều sử dụng cùng các công cụ đường ống xây dựng và triển khai (build and deployment pipeline) để kiểm tra Dockerfile, giúp nhóm của bạn ít tốn thời gian và công sức học công cụ mới hơn.

- **Hiệu năng và chi phí**: Lambda cung cấp khả năng mở rộng tự động trong vòng dưới một giây (sub-second autoscaling) phù hợp với nhu cầu. Điều này mang lại tính khả dụng (availability) cao hơn, chi phí vận hành thấp hơn và hiệu quả chi phí (cost efficiency).

- **Tích hợp**: AWS cung cấp hơn 200 tích hợp dịch vụ (service integrations) để triển khai các hàm (functions) dưới dạng container image trên Lambda mà không cần tự phát triển, giúp triển khai nhanh hơn.

- **Artifact ứng dụng lớn hơn, lên đến 10 GB**: Điều này bao gồm hỗ trợ dependency ứng dụng lớn hơn (larger application dependency support), cho bạn nhiều không gian hơn để lưu trữ file và gói so với giới hạn cứng là 250 MB đối với file đã giải nén cho các gói triển khai (deployment packages).


## Mở rộng với sự kiện bất đồng bộ 
AWS cung cấp hai cách để mở rộng xử lý bất đồng bộ độc lập và tự động: **[Elastic Beanstalk worker environments](https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/concepts-worker.html)** và lời gọi **[bất đồng bộ (asynchronous invocation)](https://docs.aws.amazon.com/lambda/latest/dg/invocation-async.html)** với Lambda. Cả hai tùy chọn đều cung cấp các tính năng sau:

- Chúng đưa các sự kiện vào SQS queue

- Chúng có thể được thiết kế để chỉ lấy các item từ queue khi có đủ sức chứa để xử lý tác vụ. Điều này giúp ngăn chúng bị quá tải.

- Chúng giảm tải (offload) các tác vụ khỏi một thành phần của ứng dụng sang queue và xử lý chúng một cách bất đồng bộ.
  
Các lời gọi bất đồng bộ (asynchronous invocations) này bổ sung các cơ chế xử lý lỗi (failure processing) và thử lại (retry mechanisms) mặc định, có thể điều chỉnh (tunable) thông qua các điểm đến sự kiện (event destinations) “on failure” và “on success”, như được mô tả trong phần tiếp theo.

## Tích hợp với nhiều điểm đến
Các sự kiện “on failure” và “on success” có thể được ghi vào SQS queue, **[Amazon Simple Notification Service (Amazon SNS)](https://aws.amazon.com/vi/sns/)** topic, EventBridge event bus hoặc một Lambda function khác. Cả bốn đều được tích hợp với hầu hết các AWS services.

Các sự kiện “on failure” được gửi đến một hàng đợi SQS dead-letter (SQS dead-letter queue) vì chúng không thể được chuyển đến các hàng đợi đích (destination queues). Chúng sẽ được xử lý lại khi cần thiết, và bất kỳ vấn đề nào trong quá trình xử lý message sẽ được cô lập.

Hình 2 mô tả một Amazon API Gateway bất đồng bộ đặt một HTTP request dưới dạng một message vào SQS queue, qua đó tách rời (decoupling) các thành phần (components).

Các tin nhắn (messages) trong SQS queue sau đó kích hoạt một Lambda function. Function này chạy container dịch vụ machine learning SciLearn trong Lambda cho các quy trình công việc phân tích dữ liệu (data analysis workflows), vốn được tích hợp với một SQS dead-letter queue khác để xử lý lỗi (failures processing).

![Sơ đồ ví dụ các ứng dụng container dựa trên bất đồng bộ](/images/blog2/Async.png)
Hình 2. Sơ đồ ví dụ các ứng dụng container dựa trên bất đồng bộ

Khi bạn triển khai các Lambda functions dưới dạng container images, chúng được hưởng lợi từ cùng sự đơn giản trong vận hành (operational simplicity), khả năng mở rộng tự động (automatic scaling), tính khả dụng cao (high availability), và các tích hợp gốc (native integrations). Điều này làm cho kiến trúc này trở nên hấp dẫn cho các trường hợp sử dụng phân tích dữ liệu của chúng tôi.

## Các cân nhắc khi thiết kế

Khi triển khai Docker Container Images với Lambda, cần xem xét:
- Lambda hỗ trợ các container image có tệp kê khai (manifest files) tuân theo các định dạng sau:
  
  <span style="font-size: 1rem;">+ Docker image manifest V2, schema 2 (Docker version 1.10 trở lên)</span>

  <span style="font-size: 1rem;">+ Open Container Initiative (OCI) specifications (v1.0.0 trở lên)</span>
- Lưu trữ trong Lambda:

  <span style="font-size: 1rem;">+ Memory: 128 MB – 10,240 MB</span>

  <span style="font-size: 1rem;">+ /tmp space: 512 MB</span>

  <span style="font-size: 1rem;">+ Container image: tối đa 10 GB</span>

  <span style="font-size: 1rem;">+ Có thể sử dụng Amazon S3 hoặc <a href="https://aws.amazon.com/vi/efs/">Amazon Elastic File System (Amazon EFS)</a> làm lưu trữ ngoài.</span>

- Khi tạo/cập nhật, Lambda sẽ lưu vào bộ nhớ đệm (cache) image để tăng tốc độ khởi động lạnh (cold start) của các hàm trong quá trình thực thi (execution). Khởi động lạnh xảy ra khi có yêu cầu ban đầu (initial request) gửi đến Lambda, điều này có thể dẫn đến thời gian khởi động lâu hơn. Yêu cầu đầu tiên sẽ duy trì một instance của hàm chỉ trong một khoảng thời gian ngắn. Nếu Lambda không được gọi trong khoảng thời gian đó, lần gọi tiếp theo sẽ tạo một instance mới.

- Các chính sách vai trò phân quyền chi tiết (Fine-grained role policies) được khuyến nghị cao cho mục đích bảo mật.

- Container images có thể dùng **[Lambda Extensions](https://docs.aws.amazon.com/lambda/latest/dg/runtimes-extensions-api.html)** API để tích hợp monitoring, security và các công cụ khác với môi trường thực thi Lambda (Lambda execution environment).
  
## Kết luận
Chúng tôi đã có thể thiết kế kiến trúc (architect) lại dịch vụ đồng bộ (synchronous) này (vốn trước đây được triển khai trên các host dựa trên instance (instance-based hosts)) và thiết kế (design) nó để trở thành dịch vụ bất đồng bộ (asynchronous) trên Amazon Lambda.

Bằng cách sử dụng hỗ trợ mới cho container-based images trong Lambda và chuyển đổi workload của chúng tôi thành một kiến trúc bất đồng bộ dựa trên sự kiện (asynchronous event-based architecture), chúng tôi đã có thể khắc phục những thách thức sau:

- **Hiệu năng và bảo mật**:Với các yêu cầu hàng loạt (batch requests), bạn có thể mở rộng quy mô (scale) các workload bất đồng bộ (asynchronous workloads) và xử lý các bản ghi lỗi (failure records) bằng cách sử dụng SQS Dead Letter Queues và Lambda destinations. Việc sử dụng Lambda để tích hợp với các dịch vụ khác (như EventBridge và SQS) và sử dụng Lambda roles giúp đơn giản hóa việc duy trì cấu trúc phân quyền chi tiết (granular). Khi Lambda sử dụng một Amazon SQS queue làm nguồn sự kiện (event source), nó có thể mở rộng quy mô (scale) lên đến 60 instance (instances) nữa mỗi phút, với tối đa 1.000 lời gọi đồng thời (concurrent invocations).

- **Tối ưu chi phí**: Tài nguyên tính toán là thành phần quan trọng trong bất kỳ kiến trúc ứng dụng nào. Việc cung cấp thừa (overprovisioning) tài nguyên tính toán và vận hành các tài nguyên nhàn rỗi (idle) có thể dẫn đến chi phí cao hơn. Vì Lambda là serverless, chi phí chỉ phát sinh khi bạn gọi một hàm (function) và dựa trên các tài nguyên được phân bổ (allocated) cho mỗi yêu cầu.

---
## Về tác giả

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