# AWS Dev Associate Practice Questions 

## Part 1

1. ### CodeCommit

- CodeCommit is a managed source control service that enables teams to securely collaborate on code. Your code is secured using encryption in transit and at rest.

2. ### RDS Proxy

- RDS Proxy is a service provided by AWS that sits between your application and your AWS RDS database, which is a managed relational database service. The purpose of RDS Proxy is to manage database connections in a more efficient way. Here’s a simple breakdown of what it does and why it’s useful:

- Connection Pooling: Normally, every time an application needs to talk to a database, it opens a new connection, uses it, and then closes it. Opening and closing connections frequently can be slow and uses a lot of resources. RDS Proxy keeps a pool of connections open and allows multiple parts of your application to reuse these connections without having to open new ones each time. This is much faster and more efficient.
- Improved Scalability: Because RDS Proxy handles connections more efficiently, your application can handle more users or requests at the same time without overloading the database with too many connections. This makes your application scale better as it grows.
- Enhanced Security: RDS Proxy also helps with security because it manages connections to your database, which means it can also handle things like credentials and access management in a secure way.

- In simple terms, think of RDS Proxy as a smart middleman that helps your application talk to the database more efficiently, handle more load, and do so securely.

3. ### Lambda and AWS SDK Libraries

- When you're building an application that runs on AWS Lambda, start by only adding the necessary libraries that are really needed, instead of the entire AWS SDK library. This helps the function start faster because there's less code to load. It also makes your application safer and easier to handle because there's less code to manage. Once you've picked just the necessary libraries, if it is still slow, you can then put them(the libraries) in a Lambda layer. This lets you share these libraries across different functions, which can make your application run more smoothly and cost less. This approach makes sure your Lambda function is efficient, secure, and easy to manage.

4. ### Uploading codes to Lambda

- There are several ways to deploy code to AWS Lambda. You can directly upload your code(.zip file archive deployment package) through the AWS Lambda console, Create a .zip file archive deployment package, upload it to an S3 bucket, and have Lambda download it from S3, Copy and Paste in the AWS Lambda IDE, use the AWS Command Line Interface (CLI), or write scripts using AWS SDKs to automate the process. Tools like AWS CloudFormation or the Serverless Application Model (SAM) let you manage your Lambda functions as part of larger infrastructure setups. Each method offers different advantages depending on your project's needs, such as ease of use, automation, and integration with other AWS services. Understanding these options helps you choose the best way to deploy and manage your serverless applications efficiently.

5. ### Secrets Manager Vs Parameter Store

- Different AWS services that are suitable for securely managing sensitive information like database credentials and license keys. AWS Secrets Manager is the best choice for storing _RDS database credentials_ because it not only stores them securely but _also automatically rotates them to maintain security_. AWS Systems Manager Parameter Store is ideal for _storing static data like license keys_ because it provides secure and organized storage, although it _lacks automatic rotation_.

6. ### CodePipeline

- CodePipeline enables you to automate your software build, test, and release processes.

7. ### API Gateway

- API Gateway is an AWS service that allows you to create, publish, maintain, monitor, and secure APIs(REST APIs, WebSocket APIs and HTTP APIs) at any scale, acting as a front-end that manages and processes incoming API requests.

8. ### Lambda /tmp directory

- when building applications with AWS Lambda that need temporary storage during processing, you can use the /tmp directory for fast, local storage of data up to 512 MB. This directory is good for data that does not need to be saved after the function is done running, making it perfect for temporary needs. It's simple to use since it’s already part of Lambda, and it doesn't cost extra. 

- However, if you expect to need more space or want to keep the data after the function stops, other options like EFS might be better. This helps you choose the right storage option based on how much data you have and whether it needs to be saved long-term.

9. ### Codedeploy In-place and Blue-Green

- When deploying an application to a new fleet of EC2 instances that are not yet serving users, an In-place deployment strategy with AWS CodeDeploy is effective and straightforward. This method involves installing and updating the application directly on the new instances without impacting live traffic, as there is no existing user load. It simplifies the deployment process since you can install the application, test it extensively, and then direct user traffic to these instances once they're fully configured and tested. This approach minimizes risk, avoids downtime typically associated with updating live systems, and is cost-effective since it doesn’t require maintaining multiple environments during the deployment.

- Blue/Green deployment offers superior risk mitigation for updates in live environments by providing a robust rollback strategy and minimal downtime, the In-place approach is often chosen for new, inactive instances due to its simplicity, cost efficiency, and adequacy for setups where immediate user impact is not a concern.

10. ### ElastiCache for Redis

- To enhance a MySQL RDS database operations, you should use caching solutions like ElastiCache for Redis, which not only improves read performance by reducing database load but also supports complex operations like sorting and ranking directly within the cache.


11. ### Software project new features

- The best practice for developing a new feature while keeping it separate from production-ready code in a software project is to create a branch from the default branch in AWS CodeCommit, allowing for isolated development and easy integration upon completion.

12. ### CPU-Bound Lambda

- When an AWS Lambda function is described as "CPU-bound," it means that the function's performance and speed are primarily limited by the amount of CPU power available to it, rather than by memory or input/output constraints.

- When we say an AWS Lambda function is CPU-bound, it implies that the performance and completion time of the function are primarily restricted by the CPU resources available to it.

- In AWS Lambda, the CPU power allocated to your function scales linearly with the amount of memory configured. By increasing the memory allocation, you not only provide more memory but also increase the CPU resources available to your function. This helps speed up processing for CPU-intensive tasks.

13. ### API Mock integration 

- Mock integration in the context of API development, particularly when using services like AWS API Gateway, refers to a method where you configure the API Gateway to return predefined responses to API requests without the need for an actual backend service. This technique is used to simulate the behavior of backend APIs during the development and testing phases, allowing developers to ensure that the front-end or client-side of an application can handle API interactions correctly.

- When discussing mock integrations or API Gateway, the term API generally refers to the interface exposed for interaction, and the backend would be the system implementing the logic and data handling that responds to those API calls.

14. ### Lifecycle hooks for in-place deployment using CodeDeploy

- The correct run order for lifecycle hooks for an in-place deployment using CodeDeploy is:
    ApplicationStop, BeforeInstall, AfterInstall, ApplicationStart, ValidateService
    - ApplicationStop: This hook is used to gracefully stop the application service before updating it. It's the first step in ensuring that there are no ties to the resources that might need updating, such as files that need to be replaced or database connections that need to be reset.
    - BeforeInstall: This runs after the application is stopped but before the new application version is installed. This hook is often used to perform tasks like backing up the current version, prepping configuration files, or setting up necessary dependencies.
    - AfterInstall: After the new application version has been installed, this hook can be used to configure additional components, change permissions, or perform any other setup required before the application starts running again.
    - ApplicationStart: This hook starts the application service with the new version in place. It ensures that the application is up and running correctly with all the new updates.
    - ValidateService: Finally, this hook is used to validate that the new deployment is functioning as expected. This can involve health checks, integration testing, or any other validation processes necessary to confirm the success of the deployment.

15. ### Kinesis Firehose, Lambda and Athena
- If you are designing an application that consumes a large amount of unstructured streaming data that needs to be processed and then stored persistently so that a team of analysts can generate reports by running SQL queries on the data. You should:

 - Use Kinesis Firehose to capture the streaming data, use Lambda to process the data, and store the processed data in S3. Use Athena to run the SQL queries.

  - Kinesis Firehose is a service that can be used to capture streaming data for further processing. Lambda is able to consume data from Kinesis, process it, and store the results in S3. Athena is a service that enables you to run standard SQL queries on data that is stored in S3.


16. ### Step Functions

- Step Functions enables you to build and model your serverless application as a visual workflow consisting of a series of steps where the output of one stage can be input into another.

17. ### In-place upgrade using AWS CodeDeploy

- Unlike Blue-Green upgrade, in In-place upgrade using AWS CodeDeploy, the original instances are updated directly, meaning there are no separate instances running the old version to fall back on. Therefore, if a deployment fails, the best options for a quick is redeploying the previous version of the application manually.

- Only a Blue/Green upgrade allows you to keep the original instances and roll back by routing all requests to the original instances.

18. ### Lambda and scheduled event triggers

-  AWS Lambda, combined with scheduled event triggers (like those from Amazon CloudWatch Events), is a highly efficient and cost-effective solution for running simple, stateless tasks that execute on a periodic schedule, such as processing data from an S3 bucket. This approach minimizes operational overhead and costs by charging only for the compute time used, making it ideal for tasks with predictable, short runtimes that do not require continuous compute resources.

19. ### Lambda and database connections

- Establishing database connections within Lambda execution environment allows them to be reused the next time the function is invoked, which saves time and improves the performance of your function. 

- Reusing database connections across Lambda invocations can significantly reduce the overhead of establishing these connections for each function call, enhancing performance, especially for frequently invoked functions.


## Part 2

20. ### Lambda ephemeral and shared files

- For a Lambda function that needs to store ephemeral data up to 1 GB and persistently store and dynamically update shared files, the combination of using /tmp for ephemeral files and EFS for shared files is the optimal solution. This setup leverages the strengths of each storage solution, ensuring efficient and robust data handling for your application.

21. ### Cognito and IAM

- To decouple user authentication from application servers and manage secure access user permission to S3 buckets for your meme-sharing application, use Amazon Cognito for user sign-up and sign-in and AWS IAM to manage user permissions. This approach leverages the strengths of both services to provide a secure, scalable, and manageable solution.

22. ### CodeCommit email notification

- If you want users to receive an email notification whenever they push code to their AWS CodeCommit repositories, configure notifications in the CodeCommit console. This setup will create an Amazon EventBridge (formerly CloudWatch Events) rule to send a notification to an SNS topic, which will trigger an email to be sent to the user. This approach ensures ease of setup, automation, and scalability for your notification system.

23. ### DynamoDB ProvisionedThroughputExceededException Error

- To handle ProvisionedThroughputExceededException errors in DynamoDB, ensure your application is using exponential backoff. This strategy helps to reduce immediate pressure on the database by progressively waiting longer before retrying failed operations, providing a more efficient and cost-effective way to manage throughput issues without immediately increasing the provisioned capacity.

24. ### Lambda environment variables

- To dynamically change the behavior of an AWS Lambda function, use environment variables. This method allows you to modify configuration settings such as message strings without updating or redeploying the function code, providing flexibility and ease of management.

25. ### Lambda layer

- To consistently manage and update shared libraries across multiple AWS Lambda functions, create a Lambda layer containing the necessary libraries and associate it with your functions. This approach simplifies dependency management, ensures consistency, and allows for easy updates.

26. ### SQS

- To decouple application components and enable them to fail independently, use Amazon SQS (Simple Queue Service). SQS allows asynchronous message passing between components, ensuring that the failure of one component does not directly impact others, thereby enhancing the application's resilience and scalability.

27. ### CodeDeploy AppSpec file

- In the CodeDeploy AppSpec file, hooks are used to specify code, scripts, or functions to be executed at defined points in the deployment lifecycle. This enables you to customize and control the deployment process by running custom logic at various stages, ensuring a smooth and tailored deployment experience.

28. ### API Gateway mock integrations

- To test your user interface workflow when backend components are not yet ready, use API Gateway mock integrations. This approach allows you to simulate backend responses, ensuring that your frontend development and testing can proceed without dependency on the backend, facilitating parallel development and testing efforts.

29. ### Lifecycle Hooks

- In CodeDeploy for EC2 and On-Premises deployments, the correct sequence of lifecycle hooks is "Application Stop - Before Install - After Install - Application Start." This order ensures a smooth deployment by stopping the application, installing new code, performing post-installation tasks, and then restarting the application.

30. ### Lambda and private VPC

- To enable a Lambda function to communicate with an RDS database in a private VPC, you must configure the function to connect to the VPC by providing the appropriate subnet and security group details. This setup ensures the function can access the RDS instance within the VPC securely and efficiently.

31. ###  AWS CodeBuild environment variables

- To manage a large number of environment variables for AWS CodeBuild, use Systems Manager Parameter Store. This service provides a secure and scalable way to store and reference configuration data, helping to avoid exceeding character limits in the buildspec file and ensuring efficient parameter management.

32. ### CloudWatch Logs Insights

- To efficiently query and analyze application logs stored in CloudWatch Logs, use CloudWatch Logs Insights. This service provides a robust query language and visualization tools, enabling effective debugging and troubleshooting of application failures.

33. ### Lambda aliases and stage variables

- A Lambda alias is like a pointer to a specific function version. Users can access the function version using the alias Amazon Resource Name (ARN).

- To configure API Gateway stages and associate them with different Lambda function variants for prod, dev, and test environments, use Lambda aliases and stage variables. Lambda aliases help manage different function versions, while stage variables allow API Gateway stages to reference the appropriate Lambda function for each environment.

34. ### Lambda performance

- To improve the performance of a slow-running Lambda function, consider increasing the function memory, which also increases CPU allocation. Additionally, include large libraries and dependencies as a Lambda layer, reducing deployment package size and improving cold start performance. These actions can significantly enhance the efficiency and speed of your Lambda function.

35. ### Lambda & Kinesis stream

- To improve the processing speed of your Lambda function that handles data from a Kinesis stream and writes to a DynamoDB table, increase the number of shards in the Kinesis Data Stream, boost the provisioned throughput (RCUs and WCUs) of the DynamoDB table, and allocate more memory to the Lambda function. These actions will enhance parallel processing, prevent throughput errors, and provide more computational resources, resulting in better performance.

36. ### Lambda failed Invocations

- To handle errors in asynchronous Lambda invocations effectively, use a dead-letter queue to capture and store failed invocations for reprocessing. Additionally, configure a Lambda destination to receive invocation records of failures, enabling automated handling, notification, or logging of errors. These strategies ensure robust error management and improve the reliability of your application.

37. ### Storing Session Data

- To provide a scalable and shared session state storage for your web application, consider using ElastiCache or DynamoDB. Both services offer high availability, scalability, and low-latency access, ensuring that session state data is efficiently managed and accessible across multiple web servers.

38. ### Sorting and ranking of the data

- To enhance the performance of your leaderboard application, configure ElastiCache for Redis and point your Lambda function at the ElastiCache cluster. Redis offers in-memory data processing capabilities that are ideal for fast read operations and complex operations like sorting and ranking, ensuring efficient handling of your growing user base and their data.

- ElastiCache for Redis is well-suited for use cases that require fast, in-memory data processing with complex operations like sorting and ranking. Redis provides data structures that can efficiently handle leaderboard functionalities, such as sorted sets, which can store the scores and automatically rank them.

39. ###  Configuring API Gateway based on deployment stages

- To categorize and configure your APIs based on deployment stages like sandbox, test, or prod, use stage variables in API Gateway. Stage variables enable you to define and reference configuration attributes dynamically, ensuring flexibility and customization in your API setup and mapping templates. This approach allows you to manage different backend endpoints or settings efficiently across various stages of your application lifecycle.

- Stage variables in API Gateway allow you to define key-value pairs that can be used to configure and customize the behavior of your API stages. These variables can be referenced in your API setup and mapping templates, enabling you to interact with different backend endpoints or configurations based on the deployment stage (sandbox, test, prod).

## Part 3

40. ### API Gateway Caching
To optimize the performance of your online hotel booking application that frequently requests the same travel-related add-on services, implement API caching in API Gateway. This caches the endpoint's responses for the most popular requests, reducing latency and the load on your backend services, resulting in improved overall application performance.

41. ### API Gateway Integration with Lambda
- To handle the high volume of concurrent requests from your online hotel booking application, integrate API Gateway with a 
Lambda function. This allows you to scale your backend services efficiently, as Lambda automatically provisions and manages the
compute resources needed to handle the increased load, ensuring high availability and reliability.

42. ### Implement a FIFO Queue in SQS

- Amazon SQS FIFO (First-In-First-Out) queues are designed to ensure exactly-once processing and prevent the addition of duplicate messages to the queue. While FIFO queues are typically used to maintain the order of message processing, they also provide deduplication capabilities which ensure that no duplicate jobs are added to the queue.

- To ensure that duplicate jobs do not appear in the queue and maintain efficiency, implement a First-In-First-Out (FIFO) queue in SQS. FIFO queues provide deduplication features that prevent duplicate messages from being added, while the order of processing can be disregarded if it is not a requirement.

43. ### Schedule a Trigger Using EventBridge
- To trigger a Lambda function once every 24 hours, schedule a trigger using EventBridge. EventBridge allows you to define a schedule with a rate or cron expression and ensures reliable invocation of your Lambda function at the specified interval. This method is straightforward, serverless, and fully managed

44. ### Exponential Backoff
- When your application is experiencing a large number of failed requests to the S3 API, the AWS SDKs use exponential backoff to manage error retries. This strategy helps in reducing contention and managing flow control effectively by gradually increasing the wait time between retries and adding random jitter to distribute retry attempts more evenly.

45. ### Amazon API Gateway

- To build a REST API service for quick access to stock levels without spending time provisioning and managing servers, use Amazon API Gateway. It provides a fully managed solution to create and manage APIs, and when integrated with AWS Lambda, it allows for a serverless architecture that is scalable and cost-effective.

46. ### CodeDeploy Deployment Integrations

- CodeDeploy can manage deployments to On-premises servers, Lambda, EC2, and ECS Fargate. These integrations allow you to automate and streamline the deployment process across a variety of environments, both in the cloud and on-premises.

47. ### Using Parameter Store for Environment Variables

- Parameter Store: Use Parameter Store for the environment variables and reference the parameters in the application code. This approach provides a secure, centralized, and easy-to-manage solution for storing and accessing configuration data across multiple applications running on EC2. It ensures secure access, centralized management, and straightforward integration into your application code.

48. ### DynamoDB Sort Key Data Types

- When creating a DynamoDB table with an index sort key, the developer can use the following data types: String, Number, and Binary. These data types provide flexibility in defining the sort key based on different kinds of data that the application might need to query and sort by.

49. ### Using DynamoDB TTL for Automatic Deletion

- To automatically delete session data from a DynamoDB table after the session has expired and help minimize costs, configure a Time To Live (TTL) based on the session expiry time. This approach simplifies the management of expired data, as DynamoDB handles the deletion process automatically.

50. ### Updating the Prod Alias

- To ensure your serverless application uses the updated Lambda Node.js code, update the Prod alias to reference the new version of your function. This change will make sure that any calls to the function using the "Prod" alias will invoke the new version of the code.

51. ### SAM Handler

- In a SAM template, the Handler property defines the point in a Lambda function's code where execution begins. It specifies the entry point of your function, formatted as file.method, to correctly route the execution to the appropriate code segment.

52. ### DynamoDB persisting user state data

- For persisting user state data in a serverless application, DynamoDB is the recommended choice. It provides durable, scalable, and low-latency storage, ensuring that user data is reliably maintained and easily accessible.

53. ### EC2 Instance Profile Role

- To allow CodeDeploy to deploy an application to EC2 with the source code stored in AWS CodeCommit, create an IAM policy with the codecommit:GitPull action on the required repository and attach this policy to the EC2 instance profile role. This setup ensures that the EC2 instances have the necessary permissions to pull the code from CodeCommit during the deployment process.

54. ### Using DynamoDB TTL for Automatic Purging

- To automatically purge event data older than 30 days in a DynamoDB table, enable Time to Live (TTL) on the DynamoDB table and store the expiration timestamp in the TTL attribute in the epoch time format. This approach is optimal as it is built-in, efficient, and requires minimal maintenance.

55. ### API Gateway Parameter Mapping and Request Transformation

- Parameter mapping in API Gateway allows you to modify the request and response parameters, such as headers, path variables, query strings, and request bodies, before passing them to the backend service or client. This process is essential for customizing and controlling the data flow in your API Gateway integrations.

- To modify the HTTP request header for requests processed by API Gateway, use parameter mapping with a request transformation. This allows you to add, modify, or remove headers before forwarding the request to the backend service, enabling you to track and correlate requests effectively with your application logs.

- By effectively tracking and correlating requests with application logs, you enhance your ability to monitor, debug, and optimize your application, ensuring a better user experience and more reliable system performance.

56. ### Amazon SNS

- For a messaging-oriented application where multiple subscribers need to receive push notifications of time-critical messages via various transport protocols such as HTTP, Amazon SQS, and email, Amazon SNS is the best service to use.

57. ### Using SNS for Failed Lambda Invocations

- To email the invocation record of any failed Lambda invocations to the support team, configure an SNS topic as a destination for failed invocations and subscribe the support team email address to this SNS topic. This approach ensures that detailed failure information is promptly sent to the support team for investigation.

58. ### Using DeletionPolicy to Retain Resources

- To ensure that a database resource is saved for backup purposes upon stack deletion, set the DeletionPolicy to Retain in the CloudFormation template. This configuration prevents the deletion of the database when the stack is deleted, allowing you to preserve critical data for future use.

59. ### Potential Reasons for Using Original/Old Lambda Code

- Qualified ARN typically refers to a fully specified Amazon Resource Name. An ARN uniquely identifies AWS resources, and it's essential in the management of permissions and resource identification in AWS environments. ARNs are a standardized way to refer to AWS resources, which can include anything from EC2 instances and S3 buckets to IAM roles and Lambda functions. e.g., arn:aws:lambda:region:account-id:function:function-name:version, arn:aws:s3:::my_corporate_bucket/exampleobject.png etc.

- Qualified ARN Pointing to Previous Version: The application might be referencing a qualified ARN that still points to the old version of the code.

- Forgot to Publish the New Version: The new code changes were uploaded but not published as a new version, so the $LATEST version is not being used by any aliases or qualified ARNs.

- Alias Pointing to Previous Version: The application could be using an alias that has not been updated to point to the new version of the Lambda function. Ensure the alias is updated to reflect the new version to solve this issue.

60. ### Reference the function using a qualified ARN and the $LATEST suffix.

- When you create a Lambda function, there is only one version called $LATEST. You can refer to the function using its qualified ARN (i.e. Amazon Resource Name (ARN) plus a version suffix (e.g., $LATEST)) or the unqualified ARN, which is the function ARN without the version suffix. The function version for an unqualified function always maps to $LATEST, so you can access the latest version using the unqualified function ARN.

61. ### Ensuring Lambda Access to EC2 Instances in Private Subnets

- VPC Subnet Configuration: Configure the Lambda function to connect to the private subnets used by the EC2 instances.

- ENI Management Permissions: Configure the Lambda execution role to have permissions for managing an ENI within the VPC.

- Security Group Configuration: Configure the Lambda's security group so it has access to the EC2 instances. This involves setting appropriate inbound and outbound rules to enable communication between the Lambda function and the EC2 instances.

62. ### Configuring ENI Management for Lambda Execution Role

- Elastic Network Interface (ENI) is a virtual network card in a VPC that allows network communication within the VPC. It is essential for Lambda functions running in a VPC to communicate with other resources like EC2 instances.

- IAM Role Configuration: The Lambda execution role must have permissions to manage ENIs (create, describe, attach, detach, delete). This configuration ensures the Lambda function can establish and manage network connections to access resources within the VPC, enabling secure and isolated communication.