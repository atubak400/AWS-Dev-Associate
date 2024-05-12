# AWS Dev Associate Practice Questions

## Security

## Security

1. ### IAM Policy

{
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

8. ### 



