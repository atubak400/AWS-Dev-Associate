# AWS Dev Associate Practice Questions

## Troubleshooting & Optimization

1. ### Codecommit-EventBridge-Lambda

- If you are using CodeCommit to store the source code for your application and want to trigger a Lambda function to save details of pull requests in a DynamoDB table, use EventBridge to trigger the Lambda function whenever a pullRequestCreated event or a pullRequestSourceBranchUpdated event is detected. This setup ensures that your Lambda function is automatically invoked to handle pull request events and update the DynamoDB table accordingly.

2. ### Cloudwatch Custom Metric

- If you are designing a serverless online banking application with a Lambda function that processes credit checks, to notify the support team when the credit check encounters errors with rate that exceeds 10% in any given hour, you should publish _custom metrics_ to CloudWatch to record the failures, and configure a CloudWatch alarm to notify an SNS topic when the error rate exceeds the specified rate. This approach is more efficient and simpler than querying CloudWatch Logs and handling notifications with additional Lambda functions.

3. ### EC2 Image Builder

- If you want to launch EC2 instances faster during scale-out events because the UserData script is taking too long to complete, it is recommended to remove the commands that install the application, its dependencies, and the required security patches from the UserData script. Instead, create a pre-baked AMI using EC2 Image Builder that includes the latest version of the application, its dependencies, and required security patches. This approach ensures quick instance readiness with all necessary components included in the AMI, reducing initialization time and increasing consistency.

4. ### Kinesis stream ProvisionedThroughputExceededException

- If your Kinesis stream is frequently throwing ProvisionedThroughputExceededException errors due to increased traffic, the best solutions are to reshard your stream to increase its capacity and reduce the frequency or size of your requests to manage the load more effectively. Provisioning a second stream and merging data introduces unnecessary complexity and management overhead, making it less suitable for this scenario.

5. ### CloudWatch Logs Insights

- If your application is sending log data to CloudWatch Logs and you need to assist the application support team in reviewing the 25 most recently added log events and identifying the most expensive Lambda requests, use CloudWatch Logs Insights to interactively query and analyze the log data. This tool provides a flexible and powerful way to perform real-time analysis directly within the CloudWatch Logs environment.

- CloudWatch Logs Insights is designed for interactive querying and analysis of log data. It allows users to write queries to search, filter, and visualize log data in real-time.

- CloudWatch Logs Metric Filters are used to extract specific patterns from log data and create CloudWatch metrics based on those patterns.
They are used to track specific numerical data points over time, such as CPU usage, disk I/O, or the number of requests. However, they do not provide the interactive querying and detailed analysis capabilities needed to review specific log events or identify trends and issues within log data.

6. ### DynamoDB slow performance

- If your company is experiencing slower performance with DynamoDB queries and scans during peak times, and the database queries and scans are taking much longer to complete than expected, implement the following strategies to make them more efficient:

    - Reduce the page size to return fewer items per results page: This helps manage the read throughput more effectively by consuming fewer read capacity units per request, reducing spikes in read activity and improving overall efficiency.
    - Run parallel scans: This technique divides the table into multiple segments and scans each segment concurrently, significantly speeding up the scan process by leveraging more read capacity and distributing the load across multiple threads.

7. ### API Gateway Timeouts

- If you are experiencing frequent timeouts with your API Gateway while the Lambda function completes successfully when called directly, check the IntegrationLatency and Latency metrics in Amazon CloudWatch. These metrics will help you identify where the delay is occurring, whether within the API Gateway itself or in the communication between API Gateway and the Lambda function.

    - IntegrationLatency measures the time between when API Gateway relays a request to the backend (in this case, your Lambda function) and when it receives a response from the backend.
    - Latency measures the total time between when API Gateway receives a request from a client and when it returns a response to the client. This includes the integration latency plus the overhead of API Gateway itself.

8. ### DAX

- If your DynamoDB table is experiencing slower performance and potential throttling due to increased traffic, configure a DAX (DynamoDB Accelerator) cluster and point your DynamoDB API calls at the DAX cluster. This will improve read performance by caching frequently accessed data, reducing read latency, and alleviating the load on your DynamoDB table, enabling it to handle high traffic more efficiently.

9. ### Dynamo DB ProvisionedThroughputExceededException

- In Dynamo DB, the ProvisionedThroughputExceededException means that you exceeded your maximum allowed provisioned throughput for a table or for one or more global secondary indexes.

10. ### AWS X-Ray

- To analyze and debug distributed applications, identify issues, and locate performance bottlenecks, use AWS X-Ray. It provides detailed insights into the operation of your application, allowing you to trace requests and diagnose problems effectively.

11. ### Long Polling

- Enabling long polling in SQS allows your application to wait for messages to arrive, rather than continuously polling the queue at regular intervals (short polling). Long polling reduces the number of empty responses and the number of API requests, thereby lowering costs and improving performance. With long polling, SQS will only return a response when a message arrives in the queue or the long poll times out.

- To optimize cost and performance when using SQS to send and receive messages, enable long polling. Long polling reduces the frequency of empty responses, lowers the number of API requests, and ensures that messages are received as soon as they arrive, making the architecture more cost-efficient and responsive.

12. ### Increasing your SQS Message Visibility Timeout

- The visibility timeout is the period of time during which a message is invisible to other consumers after it has been received by a consumer. By default, the visibility timeout is set to 30 seconds. Since it takes your application between 20 and 40 seconds to process a message, the default visibility timeout may not be sufficient, causing the message to become visible again and be picked up by another server before the original processing is complete.

- To prevent multiple application servers from processing the same SQS message, increase the message visibility timeout to be slightly longer than the maximum time it takes to process a message. This adjustment ensures that messages remain invisible to other consumers while they are being processed, reducing the likelihood of duplicate processing.

13. ### Lambda Execution Role Permissions

- If your Lambda function is executing successfully but there is no log data in CloudWatch, check and update the execution role for the Lambda function to ensure it has the necessary permissions to write log data to CloudWatch Logs. This will enable proper logging and visibility into your function's execution.


14. ### Enable CloudTrail for Lambda

- To log all API calls made to and from Lambda functions in a production environment, enable CloudTrail for Lambda. This will provide a detailed and comprehensive log of all API activity, meeting the customer's requirements for auditing and security purposes.

15. ### AWS CloudTrail

- To retain a history of all EC2 API calls made on your account for security analysis and operational troubleshooting, use AWS CloudTrail. CloudTrail provides comprehensive logging of all API activity, helping you meet security and operational requirements.

16. ### Server-Side Error Within Your AWS Infrastructure

- An HTTP 504 status code typically indicates a server-side issue where a gateway or proxy server (such as a load balancer) does not receive a timely response from an upstream server. 

17. ### AWS X-Ray

- To diagnose a performance problem with your serverless application and investigate the source of a potentially slow Lambda function, use AWS X-Ray. X-Ray provides detailed tracing and insights into the execution of your Lambda functions, helping you identify and address performance bottlenecks effectively

18. ### 500-Type Server-Side Error

- The error message "AmazonS3Exception: Internal Error; Service: Amazon S3;" is a 500-type error, indicating a server-side issue. This means that the problem is on the AWS S3 service side, and typically, the best course of action is to retry the request after some time, as these issues are usually temporary. If the problem persists, checking the AWS Service Health Dashboard for any ongoing issues or contacting AWS Support may be necessary.

19. ### Using DynamoDB Streams and Lambda for Real-Time Processing

- If you need to process appointment data in real time when it is added or modified in a DynamoDB table, use DynamoDB Streams to capture data modifications and trigger a Lambda function to process the data and store the results in S3. This solution ensures real-time processing and storage of processed information efficiently and seamlessly.

20. ### Improving RDS Performance with ElastiCache and Read Replicas

- To enhance the performance of your application during periods of intensive read activity, consider adding an ElastiCache cluster to cache frequently accessed data and adding read replicas to distribute read traffic. These strategies help offload read operations from the primary RDS instance, reduce latency, and improve overall application performance.

21. ### Using X-Ray for Tracing and Grouping by Environment

- To effectively record and analyze HTTP requests and component latency across multiple application environments, use AWS X-Ray. 

22. ### Identifying Performance Issues with X-Ray Service Map

- If a web application running on AWS services is experiencing performance declines, use the X-Ray service map to view the average latency between the services that make up the application. The X-Ray service map provides a visual overview of your application's components, highlighting areas with high latency and helping you quickly identify and address performance bottlenecks.

23. ### Handling 4XX HTTP Response Codes from API Gateway

If you encounter 4XX HTTP response codes from API Gateway, it indicates a client error. You should fix the issue in your application and retry the request. This involves reviewing API Gateway logs, validating the request format, checking authentication and authorization, and ensuring proper rate limiting. Addressing these client-side issues will help resolve the errors and improve your application's interaction with the API Gateway.

24. ### Creating a Single CloudWatch Dashboard for Multi-Region Metrics

To effectively monitor system metrics for applications hosted across multiple Regions using CloudWatch, create a single dashboard that includes metrics for each application and region. This approach provides a centralized, comprehensive view of your infrastructure, simplifying monitoring and enabling quicker identification and resolution of issues

25. ### Monitoring Legacy RedHat Instances with CloudWatch

- To monitor legacy RedHat instances in your data center using CloudWatch and notify the support team of errors in the application log file, install the CloudWatch agent on the Linux servers, configure it to monitor the application log file, and create a CloudWatch alarm to trigger an SNS notification when an error appears. This approach ensures comprehensive monitoring and timely alerts for error conditions.

26. ### Centralizing Application Logs with CloudWatch Logs

To access application logs from multiple EC2 instances in a single central location, configure the CloudWatch agent to send the application logs to CloudWatch Logs. This approach provides centralized logging, enables easy search and analysis, and allows for setting up alarms and notifications based on log data.

27. ### Centralizing Application Logs with CloudWatch

To collect application logs from all EC2 instances into a central location like CloudWatch Logs, ensure the instance role has the necessary permissions to write to CloudWatch and that the CloudWatch agent is installed and running on each instance. These steps will enable centralized logging, making it easier to monitor and analyze application performance across multiple servers.

28. ### Tracking and Monitoring Transaction Completion Times with CloudWatch

To track the average transaction completion time and notify the support team if it exceeds three seconds, record transaction completion times in an application log file, use the CloudWatch agent to send these logs to CloudWatch Logs, create a metric filter to extract and monitor the completion times, and configure a CloudWatch alarm with an SNS notification. This setup ensures comprehensive monitoring and timely alerts for performance issues.

29. ### Tracking and Monitoring Transaction Completion Times with CloudWatch

To track the average transaction completion time and notify the support team if it exceeds three seconds, record transaction completion times in an application log file, use the CloudWatch agent to send these logs to CloudWatch Logs, create a metric filter to extract and monitor the completion times, and configure a CloudWatch alarm with an SNS notification. This setup ensures comprehensive monitoring and timely alerts for performance issues.

30. ### Setting Up AWS X-Ray for Troubleshooting and Performance Analysis

To send data to AWS X-Ray for your application running on EC2 and Linux virtual machines, install the X-Ray SDK and the X-Ray daemon, then instrument your application to send data to X-Ray. This setup provides detailed insights into your application’s performance and helps in troubleshooting issues efficiently.