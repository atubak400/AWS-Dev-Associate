# AWS Dev Associate Practice Questions

## Security

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

This policy denies the ability to delete any objects with log in the name from the mycustomerdata bucket, while allowing all other S3 actions.

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