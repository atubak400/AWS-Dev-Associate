# AWS Dev Associate Practice Questions

## Deployment

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