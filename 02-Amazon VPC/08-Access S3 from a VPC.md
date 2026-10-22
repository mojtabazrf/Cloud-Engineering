
# Access S3 from a VPC

**Author:** Mojtaba Zarifi  
**Email:** mojtabazarifi86@gmail.com

---

![Image](https://nextwork.ai/lively_brown_mysterious_lion/uploads/36d7dc8f-3a9f-51ff-91ae-662077ea9920_3e1e79a2)

## Introducing Today's Project!

### What is Amazon VPC?

Amazon VPC is a logically isolated virtual network in AWS that allows me to control IP address ranges, subnets, route tables, and network security. It is useful because it enables me to securely deploy and connect AWS resources while controlling how they communicate with each other and access external services.

### How I used Amazon VPC in this project

In today's project, I used Amazon VPC to deploy an EC2 instance in a virtual network and test its connectivity to Amazon S3 by configuring AWS CLI and uploading a file to an S3 bucket.

### One thing I didn't expect in this project was...

One thing I didn't expect in this project was that I could use the AWS CLI to upload files to Amazon S3 directly from my EC2 instance, which helped me understand how AWS resources interact with each other.

### This project took me...

This project took me about one hour, including documentation.

## In the first part of my project...

### Step 1 - Architecture set up

In this step, I will set up my VPC and EC2 instance because I need a private network environment to demonstrate how resources in a VPC can securely interact with S3.

### Step 2 - Connect to my EC2 instance

In this step, I will connect to my EC2 instance and try to access an AWS service because I want to test whether resources in my VPC can access AWS services and identify any connectivity issues.

### Step 3 - Set up access keys

In this step, I will configure access keys to allow my EC2 instance to access my AWS environment.

## Architecture set up

I started my project by launching a VPC and an EC2 instance.

I set up a bucket in Amazon S3.

![Image](https://nextwork.ai/lively_brown_mysterious_lion/uploads/36d7dc8f-3a9f-51ff-91ae-662077ea9920_4334d777)

## Running CLI commands

AWS CLI is a command-line tool that allows me to interact with AWS services and manage AWS resources. I have access to AWS CLI because it is installed and configured on my EC2 instance.

The first command I ran was `aws s3 ls`. This command is used to list the S3 buckets that are accessible to my AWS account.

The second command I ran was aws configure. This command is used to configure AWS CLI by setting the AWS access key ID, secret access key, default AWS Region, and output format.

![Image](https://nextwork.ai/lively_brown_mysterious_lion/uploads/36d7dc8f-3a9f-51ff-91ae-662077ea9920_e7fa8776)

## Access keys

### Credentials

To set up my EC2 instance to interact with my AWS environment, I configured the AWS access key ID, secret access key, default AWS Region, and output format using the aws configure command.

Access keys are credentials consisting of an access key ID and a secret access key that allow the AWS CLI and other tools to authenticate with AWS and make API requests based on the associated IAM user's or role's permissions.

Secret access keys are confidential credentials used alongside access key IDs to authenticate AWS API requests and verify the identity of the user or application making them.

### Best practice

Although I'm using access keys in this project, a best practice alternative is to use an IAM role attached to the EC2 instance, which provides temporary security credentials without requiring long-term access keys.

## In the second part of my project...

### Step 4 - Set up an S3 bucket

In this step, I will create a bucket in Amazon S3 because I need a storage location to store and manage objects and test connectivity between my EC2 instance and Amazon S3.

### Step 5 - Connecting to my S3 bucket

In this step, I will connect to my S3 bucket because I want to verify that my EC2 instance can successfully access Amazon S3 and interact with the objects stored in the bucket.

## Connecting to my S3 bucket

The first command I ran was `aws s3 ls`. This command is used to list the S3 buckets that are accessible to my AWS account.

When I ran the command aws s3 ls again, the terminal responded with a list of my S3 buckets. This indicated that my AWS CLI was successfully configured and that my credentials had sufficient permissions to list the buckets.

![Image](https://nextwork.ai/lively_brown_mysterious_lion/uploads/36d7dc8f-3a9f-51ff-91ae-662077ea9920_4334d778)

## Connecting to my S3 bucket

Another CLI command I ran was aws s3 ls s3://cloudlab-vpc-mojtaba, which returned a list of objects stored in the specified S3 bucket.

![Image](https://nextwork.ai/lively_brown_mysterious_lion/uploads/36d7dc8f-3a9f-51ff-91ae-662077ea9920_4334d779)

## Uploading objects to S3

To upload a new file to my bucket, I first ran the command sudo touch /tmp/test.txt. This command creates an empty file named test.txt in the /tmp directory if it doesn't already exist, or updates its timestamps if it does.

The second command I ran was aws s3 cp /tmp/test.txt s3://cloudlab-vpc-mojtaba. This command will upload the local file /tmp/test.txt to the specified S3 bucket.

The third command I ran was aws s3 ls s3://cloudlab-vpc-mojtaba, which validated that the file was successfully uploaded to the S3 bucket and that my EC2 instance could list the bucket's contents.

![Image](https://nextwork.ai/lively_brown_mysterious_lion/uploads/36d7dc8f-3a9f-51ff-91ae-662077ea9920_3e1e79a2)

---

*Built with [NextWork](https://nextwork.ai) - [View this project](https://nextwork.ai/projects/36d7dc8f-3a9f-51ff-91ae-662077ea9920)*
