# AWS Dev Associate Practice Questions

## Part 1

1. ### Amazon SQS First-In-First-Out (FIFO)

- If your application needs to process a large amount of job requests, to ensure job requests are processed in order and only once, you should use an Amazon SQS First-In-First-Out (FIFO) queue. FIFO queues are designed specifically for scenarios where the order of message processing is critical and duplicate messages must be avoided.

2. ### Synchronous Express workflow in AWS Step Functions

- A Synchronous Express workflow in AWS Step Functions is a workflow type designed for high-throughput, low-latency applications that provide immediate execution results within a 5-minute limit, making it suitable for fast, short-duration tasks with built-in retries and error handling.

- To minimize overall processing time while efficiently handling potential errors and retries in a serverless banking system, you should use a Synchronous Express workflow in AWS Step Functions. This approach ensures low latency, immediate response upon completion, and built-in retry mechanisms, making it suitable for high-throughput applications where tasks complete quickly and require quick feedback.

- Standard Workflow: Ideal for long-running, durable executions, this workflow type provides robust error handling, retries, and supports complex workflows, making it suitable for critical applications requiring high reliability.

3. ### Dynamo DB Partition Key

- A partition key is a single attribute and is used as a primary key attribute to uniquely identify a record in the DynamoDB table. CustomerID is the best option for the partition key because each customer will have a unique ID. Since customers would very likely have multiple orders, you could use OrderID as a sort key.

4. ### Infrastructure as code

- To provision your serverless application components using an infrastructure as code approach, the two most suitable services or frameworks are:

  - AWS Serverless Application Model (AWS SAM): AWS SAM is specifically designed for building serverless applications. It extends AWS CloudFormation to provide a simplified way to define the Amazon API Gateway APIs, AWS Lambda functions, and other resources required for your serverless application.

  - AWS CloudFormation: AWS CloudFormation allows you to define and provision infrastructure as code. It can be used to manage the entire lifecycle of your infrastructure, including the Lambda functions and API Gateway endpoints, and integrates seamlessly with AWS SAM for serverless applications.

5. ### CodePipeline

- If youre using CI/CD pipeline CodePipeline to deploy containers to Elastic Kubernetes Service (EKS). To run a security check on the container image before deploying it to Elastic Kubernetes Service (EKS) in CodePipeline with the ability to fail the pipeline if the security check fails, you should:

  - Create a test stage with a test action that will happen before the deployment stage.

    - Explanation:

    - Test Stage with Test Action: By adding a separate test stage before the deployment stage, you can ensure that the container image undergoes a security scan before any deployment occurs. This stage can use tools like Amazon ECR image scanning, third-party security scanners, or custom scripts to perform the security checks.

    - Failing the Pipeline on Security Check Failure: If the security check fails, the test stage can fail, thus preventing the pipeline from proceeding to the deployment stage. This ensures that only secure images are deployed to your EKS cluster.

6. ### Dynamo db Composite Key

- If you have a website that saves user posts on DynamoDB, to efficiently query all posts by a particular user in chronological order, use a composite key with UserID as the partition key and timestamp as the sort key. This configuration ensures efficient querying and proper ordering of user posts.

7. ### Lambda Alias

- If you have a web application deployed using AWS Lambda and you update the code, ensure that the application is referencing the latest version of the Lambda function. Specifically, check if the application is using an alias that needs to be updated to point to the new version of the code to avoid using the original code.

8. ### Blue/Green deployment

- In blue/green deployment, the 'blue' environment is the current live production environment, and the 'green' environment is a replica with a newer version of the application. This approach allows for seamless updates and minimal downtime by switching user traffic between these two environments.

7. ### Dynamo DB Secondary index

- A secondary index allows you to create an alternate query path for your DynamoDB table. There are two types of secondary indexes in DynamoDB:

  - Global Secondary Index (GSI): This allows you to query on attributes that are different from the primary key. A GSI can have a different partition key and sort key from the table's primary key.
  - Local Secondary Index (LSI): This allows you to query on attributes that are different from the primary key but must share the same partition key as the table.

- For example, to enable querying a DynamoDB table by userId in addition to the primary key comment_id, add a Global Secondary Index (GSI) with userId as the partition key during table creation or update the table to include this index later. This allows efficient querying by both comment_id and userId.

8. ### Session State Management

- To manage user session state across a fleet of instances in a web application, use an ElastiCache cluster for fast, in-memory storage or DynamoDB for a scalable and durable solution. These options provide centralized, reliable, and high-performance session state management.

9. ### Serverless Web Application

- To build a serverless web application that serves both static and dynamic content, use Lambda for backend logic, API Gateway for routing and API management, and S3 for storing and serving static content. These services together provide a scalable, cost-effective, and fully managed serverless solution.

10. ### API Gateway Stage Variables

- If you have three separate environments in your AWS account and three corresponding stages in API Gateway, and you are using the API Gateway as an HTTP proxy to a backend endpoint, use stage variables and configure them in the HTTP integration request to dynamically interact with different backend endpoints, ensuring a streamlined and efficient approach to managing multiple environments.

11. ### create-stack API call

- If you have been asked to provision a new environment in a single Region using CloudFormation, use the create-stack API call to create the new CloudFormation stack with the provided template.

12. ### Dynamo DB Composite Key

- If you are creating a DynamoDB table to manage customer orders and want the ability to easily report the latest order from each customer, use CustomerID as the partition key and OrderTimestamp as the sort key for the composite primary key. This setup allows efficient querying and sorting of orders by each customer.

13. ### Lambda and SQS

- If you are deploying an application that runs in Lambda and processes messages from an SQS queue and you want to prevent duplicate messages from being processed, create a DynamoDB table to store the SQS message IDs of successfully processed messages, and configure the Lambda function to check this table before processing the sqs messages.

## Part 2

14. ### Low latency access to key-value data

- For a completely serverless application using Lambda and API Gateway that requires low latency access to key-value data, Amazon DynamoDB is the best option. It offers low latency, high scalability, and seamless integration with AWS serverless services.

15. ### Dynamo db Streams

- To capture a time-ordered sequence of modifications to items in your DynamoDB table over the past 24 hours, use DynamoDB Streams. This service provides a reliable way to monitor and respond to changes in your table data.

16. ### Enhance performance of application running on AWS Lambda

- To enhance the performance of your Node.js application running on AWS Lambda, configure more memory for your Lambda function. This will proportionally increase the CPU capacity and can lead to better execution speed and overall performance.

17. ### AWS X-Ray daemon

- To effectively troubleshoot performance issues in your Docker containers running on AWS Elastic Container Service, deploy the AWS X-Ray daemon as a new container alongside your application. This setup will allow you to capture detailed telemetry data and perform end-to-end tracing of your application.

18. ### Reverting your Lambda function

- To quickly revert your Lambda function to the stable production version, update your PROD alias to point to the previous version of the function. This method is efficient and minimizes downtime, allowing you to swiftly resolve the issues reported by the application support team.

19. ### Cloudformation

- In a CloudFormation template, the valid sections include Resources, Outputs, and Parameters. These sections help define the resources, output values, and input parameters for your infrastructure as code.

- Resources: This section is required in every CloudFormation template. It specifies the AWS resources that you want to create, such as EC2 instances, S3 buckets, and IAM roles.

- Outputs: This optional section declares output values that you can import into other stacks or return in response to API calls.

- Parameters: This optional section enables you to pass values into your template at runtime, making your templates more reusable.

20. ### Convert AWS CloudFormation file to AWS SAM file

- To identify an AWS CloudFormation template file as an AWS SAM template file, include the Transform section with the value "AWS::Serverless-2016-10-31". This section is required for AWS SAM templates.

21. ### Serverless applications

- To build, provision, and manage a serverless application consisting of Lambda functions and API Gateway endpoints in an orderly and predictable fashion, use CloudFormation and the AWS Serverless Application Model (AWS SAM). These tools provide the necessary infrastructure-as-code capabilities to streamline the deployment and management of your serverless resources.

22. ### Deploying Lambda-based application

To deploy your in-house application code using AWS Lambda, you can use AWS Serverless Application Model (AWS SAM), CloudFormation, and CodeDeploy. These services provide the tools and frameworks needed to efficiently manage and deploy Lambda-based applications.

23. ### CloudFormation nested stacks

- To ensure consistent configuration and reduce code duplication across multiple environments in CloudFormation, use nested stacks. This approach allows you to maintain modular, reusable templates for different components of your application, minimizing the risk of errors and streamlining the deployment process.

- Nested stacks allow you to break down your CloudFormation templates into reusable components. You can create separate templates for each type of resource (e.g., web servers, load balancers, databases) and then reference these templates in your main environment-specific templates using the AWS::CloudFormation::Stack resource. This approach promotes modularity and reuse, reducing duplication and the potential for human error.

24. ### CodePipeline

- To automatically build, test, and release new software whenever a developer makes an update to their code, use AWS CodePipeline. It provides a complete CI/CD workflow by integrating with other services like CodeBuild, CodeCommit, and CodeDeploy to automate the software release process.

25. ### Jenkins VS Codepipeline

- Both Jenkins and AWS CodePipeline can automate the build, test, and release process for your software. Jenkins offers extensive flexibility and plugin support for various CI/CD tasks, while AWS CodePipeline provides a managed service that integrates seamlessly with AWS resources and reduces the management burden. The choice between them depends on your specific requirements, preferences, and the existing infrastructure.

26. ### Globally targeted video rental website

To develop a globally targeted website for private video rentals, combine Amazon S3 to store the videos and Amazon CloudFront with signed URLs to securely distribute the content. This combination provides a scalable, secure, and cost-effective solution for managing and delivering your video content to users.

27. ### AWS Step Finction

- To build a scalable data management solution that ingests, processes, and transforms large volumes of climate change data with robust error handling and minimal maintenance, AWS Step Functions is the ideal service. It provides the necessary orchestration, error handling, and scalability to meet the company's requirements.

- AWS Step Functions is a serverless orchestration service that makes it easy to coordinate multiple AWS services into serverless workflows. It allows you to define workflows as state machines, which can include sequential, parallel, and branching steps. Step Functions also handle retries and error handling, making it ideal for managing complex business logic and reprocessing data when errors occur.

28. ### Dynamo db TTL

- To automatically delete items from a DynamoDB table and reduce storage costs, use the DynamoDB TTL feature. This ensures that data is removed according to the specified expiry time, helping to manage and optimize storage usage.

29. ### EventBridge event bus

- To efficiently collect and process EC2 instance lifecycle events across multiple AWS accounts, configure the EventBridge event bus in the main account to receive events from all other accounts. Set up EventBridge rules in each account to send events to the main account's event bus, and then create a rule in the main account to forward these events to an Amazon SQS queue. This method ensures scalability, security, and centralized processing of lifecycle events.

## Part 3

30. ### Using S3 and IAM Roles for Shared Storage Access

- If you are migrating a restaurant booking application to AWS and need shared storage for a large number of images and documents, store the files in Amazon S3 and use an IAM instance role to grant your EC2 instances permissions to access the shared files. This approach ensures secure and scalable access to the shared storage without the need to manage credentials manually.

31. ### Invalidating CloudFront Edge Caches

- If you have updated your website content and users are still seeing the old content, you should invalidate the files from the CloudFront edge caches. This action ensures that CloudFront fetches the latest version of your content from the origin, updating the edge caches and serving the updated content to your users. This is the most effective way to ensure the latest version of your website is being delivered promptly.

32. ### Defining Lambda Resources in CloudFormation

- When deploying Lambda functions using CloudFormation, you should define your Lambda resources in the Resources section of the template. This section is where you specify the properties and configurations for the AWS resources you want to create and manage with CloudFormation.

33. ### Simulating AZ Failure for RDS Multi-AZ

- If you need to demonstrate the impact of a failed Availability Zone (AZ) on an RDS Multi-AZ deployment for disaster recovery testing, simulate an AZ failure by performing a reboot with forced failover on the RDS instance. This method effectively tests the failover capabilities and ensures your disaster recovery plan is robust without causing unnecessary disruptions.

32. ### Managing Shards and Instances with Kinesis and KCL

- If your Kinesis stream has more shards than EC2 instances, it is not necessary to increase the number of instances to match the number of shards. One worker can process any number of shards, so it's fine if the number of shards exceeds the number of instances. The Kinesis Client Library (KCL) will manage the distribution of shards among the available worker instances, ensuring efficient data processing without the need for a one-to-one mapping of instances to shards.

33. ### Shards in Amazon Kinesis

- Shards are the basic units of capacity in an Amazon Kinesis stream. They determine the throughput of the stream, with each shard capable of ingesting and emitting data at a defined rate. Shards can be dynamically managed to scale your stream's capacity. The Kinesis Client Library (KCL) efficiently distributes shards among worker instances, ensuring balanced and scalable data processing.

34. ### Using SQS Delay Queues to Manage Timing Issues

- If you encounter timing issues where confirmation emails are being processed before the stock control database is updated, modify the SQS queue to become a delay queue by setting the delivery delay to 5 seconds. This approach allows the database to update before the confirmation emails are processed, quickly resolving the issue without requiring extensive re-engineering of the application.

35. ### Using MemoryDB for Redis for High-Performance, Low-Latency Applications

- If you need a high-performance, low-latency solution that delivers microsecond read and single-digit millisecond write latency for database operations, store the entire dataset in MemoryDB for Redis. This service is optimized for such performance requirements, supports your dataset size, and ensures both fast access and data durability.

36. ### Optimizing Latency with ElastiCache and CloudFront

- If you need to reduce latency and retrieve information faster for a web application, focus on using ElastiCache for in-memory caching and CloudFront for content delivery. These two services together will provide significant improvements in performance by minimizing latency and ensuring fast data access and content delivery

37. ### Using CodeBuild for Compiling Java Code

- If a developer needs to compile Java code to produce a deployment artifact, they should use AWS CodeBuild. CodeBuild is a fully managed service that compiles source code, runs tests, and creates deployment-ready artifacts, streamlining the build process and ensuring consistent, reliable builds.

38. ### Handling Increased Kinesis Shards with EC2 Instances

- When increasing the number of Kinesis shards, evaluate the processing capacity of your current EC2 instance(s). Start with one instance in us-east-1a and one instance in us-east-1b for redundancy and balanced load distribution. Adjust the number of instances based on actual load and performance metrics to ensure efficient processing and high availability.

39. ### Using DynamoDB to Persist Session State

- If you need to persist session state and prevent users from losing their sessions when an EC2 instance crashes, use DynamoDB. DynamoDB provides low latency, scalability, and high availability, making it an excellent choice for storing session data and ensuring a seamless user experience even in the event of server failures.

40. ### Installing the X-Ray Daemon on Elastic Beanstalk Instances

- To configure your application deployed on Elastic Beanstalk to send data to AWS X-Ray, install the X-Ray daemon on the EC2 instances inside your Elastic Beanstalk environment. Use an .ebextensions configuration file to automate the installation and ensure your application is properly instrumented to capture and send trace data.

41. ### Efficient Data Retrieval from DynamoDB

- If you need to retrieve data from a DynamoDB table and want to minimize the consumption of provisioned capacity units, use a Query request with eventual consistency. This approach is the most efficient in terms of capacity usage, leveraging primary key access and reducing read costs with eventual consistency.

42. ### Scheduling Lambda Functions with Amazon EventBridge

- If you need to schedule a Lambda function to run at 10-minute intervals, use Amazon EventBridge. EventBridge allows you to create rules that can trigger Lambda functions based on a fixed schedule, ensuring your function runs automatically at the specified interval. This method is efficient, serverless, and integrates seamlessly with other AWS services.

43. ### Using RDS Proxy for Connection Pooling

- If your application is experiencing latency due to frequently opening and closing connections to an RDS database, use RDS Proxy to provide connection pooling. RDS Proxy helps reduce connection overhead, improves application performance, and enhances scalability by reusing database connections efficiently. This solution ensures that your application remains performant and scalable, even under high load conditions.

44. ### Using CloudFormation Change Sets to Preview Stack Updates

- If a developer wants to know if any existing resources will be deleted or replaced before applying updates to a CloudFormation template, they should use CloudFormation change sets. Change sets provide a preview of the modifications that will be made, allowing the developer to review and understand the impact of the changes before they are applied. This feature helps ensure that updates are made safely and without unexpected disruptions.
