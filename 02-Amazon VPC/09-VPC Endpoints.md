
# VPC Endpoints

**Author:** Mojtaba Zarifi  
**Email:** mojtabazarifi86@gmail.com

---

![Image](https://nextwork.ai/lively_brown_mysterious_lion/uploads/749fab76-0a0b-5822-9b31-c7863050c9bd_09bcaa8a)

## Introducing Today's Project!

### What is Amazon VPC?

Amazon VPC is a logically isolated virtual network in AWS that allows me to control IP addressing, subnets, route tables, and network security. It is useful because it enables me to build secure cloud environments and control how resources communicate with AWS services and the internet.

### How I used Amazon VPC in this project

In today's project, I used Amazon VPC to configure an S3 Gateway Endpoint, enable private connectivity between my EC2 instance and Amazon S3, and restrict bucket access using VPC endpoint policies and S3 bucket policies.

### One thing I didn't expect in this project was...

One thing I didn't expect in this project was that a VPC Endpoint could provide private access to Amazon S3 without requiring an internet gateway or NAT gateway, while its endpoint policy and the S3 bucket policy could independently control access.

### This project took me...

This project took me about one hour, including documentation.

## In the first part of my project...

### Step 1 - Architecture set up

In this step, I will set up my architecture because I need to create a secure and private connection between my VPC and AWS services.

### Step 2 - Connect to EC2 instance

In this step, I will connect directly to my EC2 instance because I need to verify that it can access AWS services through the VPC Endpoint without using the public internet.

### Step 3 - Set up access keys

In this step, I will create an access key because I need to authenticate the AWS CLI and interact with AWS services programmatically.

### Step 4 - Interact with S3 bucket

In this step, I will get my EC2 instance to access my S3 bucket.

## Architecture set up

I started my project by launching a VPC and an EC2 instance.

I also set up an Amazon S3 bucket.

![Image](https://nextwork.ai/lively_brown_mysterious_lion/uploads/749fab76-0a0b-5822-9b31-c7863050c9bd_4334d777)

## Access keys

### Credentials

To set up my EC2 instance to interact with my AWS environment, I configured:
-Access key ID: Identifies the IAM user making AWS API requests.
-Secret access key: Authenticates requests by signing them.
-Default AWS Region: Specifies the AWS Region where requests are sent by default.
-Default output format: Determines how the AWS CLI displays command output, such as JSON, YAML, text, or a table.

Access keys are credentials used to authenticate and authorize programmatic access to AWS resources through the AWS CLI, SDKs, and APIs.

Secret access keys are confidential credentials used alongside access key IDs to sign AWS API requests and authenticate programmatic access to AWS services.

### Best practice

Although I'm using access keys in this project, a best practice alternative is to use IAM roles with temporary security credentials, which eliminate the need to store long-term access keys on EC2 instances.

## Connecting to my S3 bucket

The command I ran was `aws s3 ls`. This command is used to list the S3 buckets available in my AWS account.

The terminal responded with my bucket name. This indicated that the access keys I set up were configured correctly and that my AWS CLI could authenticate with AWS and access my S3 bucket.

![Image](https://nextwork.ai/lively_brown_mysterious_lion/uploads/749fab76-0a0b-5822-9b31-c7863050c9bd_4334d778)

## Connecting to my S3 bucket

I also tested the command "aws s3 ls s3://cloudlab-vpc-mojtaba" which returned a list of objects stored in the specified S3 bucket.

![Image](https://nextwork.ai/lively_brown_mysterious_lion/uploads/749fab76-0a0b-5822-9b31-c7863050c9bd_4334d779)

## Uploading objects to S3

To upload a new file to my bucket, I first ran the command sudo touch /tmp/test.txt. This command creates an empty file named test.txt in the /tmp directory if it doesn't already exist, or updates its timestamps if it does.

The second command I ran was aws s3 cp /tmp/test.txt s3://cloudlab-vpc-mojtaba. This command will upload the local file /tmp/test.txt to the specified S3 bucket.

The third command I ran was aws s3 ls s3://cloudlab-vpc-mojtaba, which validated that the file was successfully uploaded to the S3 bucket and that my EC2 instance could list the bucket's contents.

![Image](https://nextwork.ai/lively_brown_mysterious_lion/uploads/749fab76-0a0b-5822-9b31-c7863050c9bd_3e1e79a2)

## In the second part of my project...

### Step 5 - Set up a Gateway

In this step, I will create a VPC Endpoint because I want my EC2 instance to access Amazon S3 privately without routing traffic through the public internet.

### Step 6 - Bucket policies

In this step, I will restrict access to my S3 bucket to traffic coming only through my VPC endpoint to improve security and prevent unauthorized access.

### Step 7 - Update route tables

In this step, I will test my EC2 instance's connectivity to my S3 bucket because I want to verify that the VPC Endpoint allows private communication between my EC2 instance and Amazon S3 without using the public internet.

### Step 8 - Validate endpoint conection

In this step, I will access my S3 bucket one last time because I want to verify that my EC2 instance can successfully access the bucket through the VPC Endpoint and that my private connectivity is working as expected.

## Setting up a Gateway

I set up an S3 Gateway Endpoint, which is a VPC endpoint that allows resources in my VPC to access Amazon S3 privately without requiring an internet gateway or NAT gateway.

### What are endpoints?

An endpoint is a connection point that enables resources in my VPC to access AWS services privately without requiring traffic to travel over the public internet.

![Image](https://nextwork.ai/lively_brown_mysterious_lion/uploads/749fab76-0a0b-5822-9b31-c7863050c9bd_09bcaa8a)

## Bucket policies

A bucket policy is a resource-based policy attached to an Amazon S3 bucket that defines who can access the bucket and what actions they can perform on it.

My bucket policy will deny all actions (`s3:*`) on our S3 bucket and its objects to everyone (`Principal: "*"`) unless the requests come through the VPC endpoint specified by the `aws:sourceVpce` condition.
In other words, only requests coming through our specified VPC endpoint will be allowed to access our S3 bucket!

![Image](https://nextwork.ai/lively_brown_mysterious_lion/uploads/749fab76-0a0b-5822-9b31-c7863050c9bd_7316a13d)

## Bucket policies

Right after saving my bucket policy, my S3 bucket page showed “Access Denied” warnings. This was because my bucket policy restricted access to requests coming through the specified VPC endpoint, and my browser requests were not coming through that endpoint.

I also had to update my endpoint route table because the route table associated with my EC2 instance's subnet needed a route to direct Amazon S3 traffic through the S3 Gateway Endpoint.

![Image](https://nextwork.ai/lively_brown_mysterious_lion/uploads/749fab76-0a0b-5822-9b31-c7863050c9bd_4ec7821f)

## Route table updates

To update my route table, I added a route to the route table associated with my VPC's public subnet.

After updating my public subnet's route table, my terminal could return the name of my S3 bucket, confirming that my EC2 instance could successfully access Amazon S3 through the VPC Gateway Endpoint.

![Image](https://nextwork.ai/lively_brown_mysterious_lion/uploads/749fab76-0a0b-5822-9b31-c7863050c9bd_d116818e)

## Endpoint policies

An endpoint policy is a resource-based policy attached to a VPC endpoint that controls which AWS principals can access which resources and perform which actions through that endpoint.

I updated my endpoint's policy by changing the Effect parameter from Allow to Deny. I could see the effect of this right away because my EC2 instance could no longer access the S3 bucket through the VPC Endpoint.

![Image](https://nextwork.ai/lively_brown_mysterious_lion/uploads/749fab76-0a0b-5822-9b31-c7863050c9bd_3e1e79a3)

---

*Built with [NextWork](https://nextwork.ai) - [View this project](https://nextwork.ai/projects/749fab76-0a0b-5822-9b31-c7863050c9bd)*
