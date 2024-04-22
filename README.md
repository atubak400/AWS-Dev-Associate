# AWS DEV Associate Practice Questions

## Development

1. ### CodeCommit

CodeCommit is a managed source control service that enables teams to securely collaborate on code. Your code is secured using encryption in transit and at rest.

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