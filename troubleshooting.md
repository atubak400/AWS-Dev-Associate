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

10. ### 