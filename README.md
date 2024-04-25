# AWS DEV Associate Practice Questions

## Development

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

14. ### 



