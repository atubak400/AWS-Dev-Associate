# AWS Dev Associate Practice Questions

## Part 1

1. ### IAM Policy

- {
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": "s3:*",
            "Resource":   [
            "arn:aws:s3:::mycustomerdata/*”,
            "arn:aws:s3:::mycustomerdata/”
    ]
        },
     {
            "Sid": "DenyS3Logs",
            "Effect": "Deny",
            "Action": "s3:DeleteObject",
            "Resource": "arn:aws:s3:::mycustomerdata/*log*”
        }
    ]
}

- This policy denies the ability to delete any objects with log in the name from the mycustomerdata bucket, while allowing all other S3 actions.

2. ### AMI

- An AMI is a pre-configured template used to create virtual servers, providing the necessary operating system, software, and configurations in one package.

- It is not possible to encrypt an AMI after it has been created. You will need to create a copy of the AMI and add encryption for the copy.

3. ### EC2 and S3

- If your EC2 instance needs to access files located in an S3 bucket, Create an IAM role with read access to S3, and assign the role to the EC2 instance.

- Using an IAM role associated with the EC2 instance is the recommended way; storing credentials locally is not recommended.


4. ### IAM User

 - The most secure approach to grant a junior developer access to an Elastic Load Balancer in a custom VPC for their initial AWS usage is by creating a new IAM user with minimal permissions tailored to the task, ensuring adherence to the principle of least privilege. Once the task is completed, promptly deleting the IAM user mitigates potential security risks associated with prolonged access.

 - It's always best practice to grant users access via IAM roles and groups. In this case, we would not assign the junior dev to an existing group, as most dev groups will have more access than is required for this dev to perform the single task they have been asked to accomplish.

5. ### CloudFront Viewer Protocol Policy

- The CloudFront Viewer Protocol Policy is a configuration setting in Amazon CloudFront that determines whether end users can access content through HTTP or HTTPS protocols when accessing your website or application via CloudFront distributions.

6. ### S3 Encryption

- There are a few different ways to enforce that any files stored in S3 must be encrypted; one of them is the use of a bucket policy to reject requests that do not include encryption in their header is the best answer.

7. ### EC2 accessing S3

- Applications that run on an EC2 instance, and that need access to AWS resources, such as S3 buckets or a DynamoDB table, must have security credentials to make programmatic requests to AWS. By creating a role with the proper permissions and attaching it to the EC2 instance, the application running on the instance will have the necessary permissions by assuming the role attached to the instance.

- Create an instance role that includes policies that grant read permissions to the bucket. Attach the role to the instance.

8. ### Lambda

- In order for a Lambda function to write to a DynamoDB table, the Lambda function *execution role* needs to be configured with the proper permissions to write to the table; otherwise, a permission denied error will be thrown.

9. ### Cognito

- To configure a mobile application to allow users to sign in and sign up to your application via Facebook, use Cognito as an identity broker between your application and the web identity provider.

10. ### Inline Policy

- AWS inline policy is a policy that is directly associated with a specific AWS identity or resource and is defined within the configuration of that entity. This means that an inline policy is tightly coupled with the identity or resource it's attached to, and it cannot be reused or shared across multiple entities. Inline policies offer more granular control and customization, allowing you to define permissions specific to a particular user, group, or role without affecting others.

11. ### Codecommit

- AWS allows you to use the following secure connections (either the HTTPS or the SSH protocol) to connect to CodeCommit repositories.

12. ### Lambda and Secret Manager

- AWS Secrets Manager is the current AWS-recommended way to securely provide database credentials to Lambda functions. AWS Secrets Manager aids in the managing and rotating of the RDS database passwords.

13. ### AWS Certificate Manager

- When using AWS Certificate Manager (ACM) with CloudFront, the certificate must be created in the us-east-1 (N. Virginia) Region. CloudFront only supports custom SSL/TLS certificates provided by ACM in this specific region. 

14. ### To set up your website on Amazon S3, you need to:

- Create an S3 bucket in the region nearest to most of your users, using a bucket name that matches with your domain name.
  - This ensures that users can access your website quickly with minimal latency by selecting a region close to them.

- Enable static website hosting.
  - This tells AWS that the bucket will serve static website content.

- Configure the permissions on the objects within the bucket to allow public access.
  - Even though enabling static website hosting makes the bucket accessible for website hosting, you still need to configure permissions to allow public access to the objects within the bucket.

- Create an index and error document.
  - These documents define the default page users see when they visit your website and the page displayed in case of errors, respectively.

15. ### Federated users

-  These are users who are authenticated by an external identity provider, such as social media accounts (like Google or Facebook) or a corporate directory system. Instead of creating and managing user accounts directly within AWS Identity and Access Management (IAM), federated users authenticate outside of AWS and are then granted temporary access to AWS resources through an IAM role. This approach allows organizations to centralize user management and authentication processes while providing secure access to AWS services based on established identities from trusted sources.

- To securely let a mobile app read data from DynamoDB, the recommended way by AWS is to make an IAM role. This role is designed for apps that work with federated users. These are users who log in through outside systems like Google or Facebook. When these users sign in, they get temporary permission to use AWS services, including reading from DynamoDB.

- This approach involves setting up an IAM role specifically for the mobile application, allowing it to securely access DynamoDB. Federated users authenticate against an identity provider (such as Amazon Cognito or an external identity provider like Google or Facebook), and upon successful authentication, they assume the IAM role, which grants them the necessary permissions to interact with DynamoDB.

16. ### Lambda and VPC

- To enable an existing Lambda function to access EC2 instances that are located in a private VPC, configure the Lambda function's ( i.e. choose the correct subnets and security groups)and ensure that its Lambda execution role has the necessary permissions to access EC2 instances.


## Part 2

17. ### Secrets Manager and KMS key

- For an e-commerce application running on an autoscaling group of EC2 instances that needs to securely store and retrieve an access token for sending instant messages via a proprietary API, using AWS Secrets Manager with a KMS key is the optimal solution. This setup ensures secure, encrypted storage of the access token, easy access management across multiple AWS accounts, and minimal management overhead.

18. ### Lambda and Dynamo db

- To enable a Lambda function to read from a DynamoDB table securely and efficiently, configure the Lambda execution role with the necessary permissions to access the DynamoDB table. This method adheres to best practices for security and access management within AWS, avoiding hardcoding credentials and ensuring seamless interaction between the Lambda function and DynamoDB.

19. ### Parameter Store and Cloudtrail

- To ensure that your application secrets are encrypted and all decryption activities are audited, use AWS Systems Manager Parameter Store to store secrets as SecureString parameters, and utilize AWS CloudTrail to audit the API calls related to decryption. This setup guarantees secure storage of secrets and provides a comprehensive audit trail for compliance.

20. ### EC2 and S3

- To securely and efficiently enable an EC2 instance to access an S3 bucket for reading and writing data, use an IAM role with the appropriate permissions. This approach ensures security best practices by avoiding the need to hardcode or locally store AWS credentials.

21. ### Web Identity Federation and Amazon Cognito

- Amazon Cognito is the AWS service that enables users to authenticate using social media accounts and provides them with temporary access to AWS resources, leveraging web identity federation to integrate with various identity providers.

- While the concept of web identity federation refers to the ability to use web identity providers for authentication, Amazon Cognito is the specific AWS service that implements this functionality.

22. ### AWS Cross-account Access 

- To securely allow another AWS account to access resources in your AWS account, configure cross-account access by creating an IAM role with the necessary permissions and allow the third-party account to assume the role using their account ID and unique external ID. This approach ensures secure, granular access control.

23. ### Management of database connection strings

- For secure and scalable management of database connection strings in your e-commerce application, use AWS Systems Manager Parameter Store. This service securely stores and encrypts the credentials, allowing your application to retrieve them dynamically as needed.

24. ### Cant access CloudWatch metrics

- If you cannot access CloudWatch metrics but your colleague can, the issue is likely due to your IAM user lacking the necessary permissions. Check and update your IAM policies to ensure you have the appropriate permissions to view CloudWatch metrics.
 
25. ### SQS messages Encryption

- For ensuring that confidential data in your SQS messages is encrypted and centrally managed, use AWS Key Management Service (KMS). KMS provides robust encryption key management and integrates seamlessly with SQS to secure your data.

26. ### x-amz-server-side-encryption

- To ensure that your data is encrypted using SSE when uploading an object to S3 via the AWS REST API, include the x-amz-server-side-encryption request header. This header ensures that S3 will encrypt your object using the specified server-side encryption method.

- The x-amz prefix in AWS headers indicates AWS-specific HTTP headers used to provide additional information and instructions to AWS services. These headers are essential for configuring and controlling various aspects of AWS service operations, such as server-side encryption, access permissions, and custom metadata.

27. ### User Pools

- Amazon Cognito uses User pools to manage sign-up and sign-in functionality for mobile and web applications.

28. ### AssumeRoleWithWebIdentity API Call

- A successful API call to AssumeRoleWithWebIdentity returns a set of temporary credentials (access key ID, secret access key, and security token) that provide temporary access to AWS services. These credentials are used to enable users authenticated via a web identity provider to interact with AWS resources securely.

## Part 3

29. ### Using Macie and SSE-KMS for PII Identification and Encryption

- Identify PII: Use AWS Macie to automatically discover and classify files containing personally identifiable information (PII) in your S3 buckets.
- Encrypt with SSE-KMS: Create and use a KMS key managed by the security team for encrypting files with SSE-KMS, ensuring that the key is automatically rotated on an annual basis. This approach ensures that sensitive customer data is securely encrypted and managed in compliance with security policies.

30. ### Using Macie and SSE-KMS for PII Identification and Encryption

- Identify PII: Use AWS Macie to automatically discover and classify files containing personally identifiable information (PII) in your S3 buckets.

- Encrypt with SSE-KMS: Create and use a KMS key managed by the security team for encrypting files with SSE-KMS, ensuring that the key is automatically rotated on an annual basis. This approach ensures that sensitive customer data is securely encrypted and managed in compliance with security policies.

31. ### Using Cognito for Device Tracking

- Use Cognito to efficiently manage user identities and track when users access your site using different devices. Cognito provides built-in features for device tracking, user session management, and robust security, making it an ideal solution for identifying and managing user access across multiple devices.

32. ### Using AWS Encryption SDK for Client-Side Encryption

- To protect sensitive files being uploaded to S3 in a Python Lambda function, use the AWS Encryption SDK for client-side encryption. This ensures that the files are encrypted before being sent to S3, providing robust security for your sensitive data.

33. ### Using Cognito for Sign-In and DynamoDB Access

- If youre adding sign-in functionality to a web application running in AWS, and after users have successfully signed in to your application, they need the ability to update their contact details and other user profile data that is stored in a DynamoDB table, the use:

- Cognito User Pool: Provides user sign-up and sign-in functionality. (i.e. It authenticates).

- Cognito Identity Pool: Provides temporary AWS credentials for accessing AWS resources. It maps authenticated users (from the user pool or other federated identity providers) to IAM roles, which define their permissions. (i.e. It authorizes)

- IAM Role: Defines the permissions for DynamoDB access.

- This approach leverages AWS Cognito for secure and scalable user management and integrates seamlessly with DynamoDB for storing and updating user profile data.

34. ### Using Athena to Query CloudTrail Logs

- If you need to review CloudTrail logs to identify any API calls made by an IAM user over the past 48 hours, use Athena to perform a SQL query on the CloudTrail data stored in S3. This approach provides efficient and powerful ad-hoc querying capabilities, allowing you to quickly identify specific API activities and investigate security incidents.

- Ensure CloudTrail is configured to deliver logs to an S3 bucket and set up Athena to query these logs using SQL for detailed analysis.

35. ### Configuring EC2 Instance Access to Encrypted Files

- If your EC2 instance needs to access files encrypted with KMS, ensure that:

- The EC2 instance has an instance role with permission to run the kms:Decrypt operation.
- The key policy allows the instance role to use the CMK for decryption.
- This configuration allows the EC2 instance to decrypt and access the encrypted files securely.

36. ### Using IAM Policy Simulator for Access Testing

- If you are encountering an IAM_ROLE_PERMISSIONS error during a CodeDeploy deployment, and suspect that your EC2 instance role may not have permission to access the S3 bucket, use the IAM policy simulator to test the instance role permissions. This tool allows you to verify if the required S3 access permissions are correctly set, helping you identify and resolve any permission issues efficiently.

37. ### Using Cognito Identity Pools for Guest User Access

- If you want to allow guest users to easily try out your healthy-eating application, use Cognito identity pools. Cognito identity pools enable you to create unauthenticated identities for guest users, allowing them to access your application without signing in. This approach provides a seamless user experience while maintaining control over access permissions through IAM roles.

38. ### Storing Session State in ElastiCache

- If you want to prevent users from losing their sessions when an EC2 instance fails, store session state in Amazon ElastiCache. This solution centralizes session management, provides low-latency access to session data, and allows your application to handle requests across multiple instances seamlessly.

39. ### Enforcing KMS Encryption on S3 Bucket

- To enforce that all files stored in the top-secret-documents S3 bucket are encrypted using a customer master key stored in KMS, add a bucket policy that denies PUT operations that don't contain the HTTP header x-amz-server-side-encryption: aws:kms. This ensures that only objects encrypted with KMS are allowed in the bucket.

40. ### Using Default Encryption for S3 Buckets

- To ensure that all new objects stored in an S3 bucket are encrypted at rest, enable default encryption on the S3 bucket. This method automatically encrypts all new objects using the specified encryption method (SSE-S3 or SSE-KMS), providing a simple and effective way to protect sensitive customer information.

41. ### Using EC2 Image Builder for Custom AMIs

- If your company needs to create a new custom AMI based on the latest version of Amazon Linux with the latest security patches included, and you are currently experiencing issues with long UserData script execution times during auto scaling events, use EC2 Image Builder. This service automates the creation and updating of AMIs, ensuring that your instances launch quickly and consistently with the latest security updates, addressing concerns with lengthy UserData scripts during auto scaling events.

42. ### Using Cognito for Device Tracking and Management

- If you need to develop a video streaming application that tracks usage across different devices and limits the number of devices from which a user can stream content, use Cognito to track and remember the devices. Cognito provides the necessary tools to manage device registration, enforce device limits, and integrate seamlessly with your application to ensure compliance with device usage policies.

43. ### Envelope Encryption

- This is a method of encrypting data where the data is encrypted with a data key, and then the data key is encrypted with a master key. This approach ensures that the data key is protected and only accessible by authorized entities with access to the master key.

- If you need to encrypt sensitive data and ensure that the encryption key is itself encrypted under another key, use envelope encryption. This method involves encrypting the data with a data key and then encrypting the data key with a master key stored in AWS KMS. This approach provides strong security and allows for efficient encryption and decryption processes.

44. ### Using Secrets Manager for Database Password Rotation

- If you need to handle database password rotation in a way that allows applications to continue connecting to the database without interruption, use AWS Secrets Manager. This service automates password rotation, securely stores and retrieves database credentials, and ensures your application always uses the latest credentials. Update your application code to reference the secret in Secrets Manager, eliminating hardcoded credentials and enhancing security.

45. ### Encrypting Unencrypted AMIs

- If you discover unencrypted AMIs that are needed for scaling mission-critical applications, you should copy each unencrypted AMI and specify encryption during the copy process. This ensures the new AMIs are encrypted while preserving the data and configuration. After creating the encrypted copies, delete the original unencrypted AMIs to comply with the security mandate.

- You cannot add encryption to an existing AMI. Instead, will need to create a copy and specify that the copy has encryption enabled.

46. ### Granting Lambda Function Access to DynamoDB

- If your Lambda function is throwing Permission Denied errors when accessing a DynamoDB table, create an IAM access policy that grants the necessary permissions and attach it to the execution role of the function. This ensures that the function has the appropriate permissions to read from the DynamoDB table, resolving the permission issues.
















