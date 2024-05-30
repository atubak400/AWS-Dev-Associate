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

- To provide a scalable and shared session state storage for your web application, consider using ElastiCache or DynamoDB. Both services offer high availability, scalability, and low-latency access, ensuring that session state d

38. ### Sorting and ranking of the data

- To enhance the performance of your leaderboard application, configure ElastiCache for Redis and point your Lambda function at the ElastiCache cluster. Redis offers in-memory data processing capabilities that are ideal for fast read operations and complex operations like sorting and ranking, ensuring efficient handling of your growing user base and their data.

- ElastiCache for Redis is well-suited for use cases that require fast, in-memory data processing with complex operations like sorting and ranking. Redis provides data structures that can efficiently handle leaderboard functionalities, such as sorted sets, which can store the scores and automatically rank them.

39. ###  Configuring API Gateway based on deployment stages

- To categorize and configure your APIs based on deployment stages like sandbox, test, or prod, use stage variables in API Gateway. Stage variables enable you to define and reference configuration attributes dynamically, ensuring flexibility and customization in your API setup and mapping templates. This approach allows you to manage different backend endpoints or settings efficiently across various stages of your application lifecycle.

- Stage variables in API Gateway allow you to define key-value pairs that can be used to configure and customize the behavior of your API stages. These variables can be referenced in your API setup and mapping templates, enabling you to interact with different backend endpoints or configurations based on the deployment stage (sandbox, test, prod).