
# Load Data into DynamoDB

**Author:** Mojtaba Zarifi  
**Email:** mojtabazarifi86@gmail.com

---

![Image](https://nextwork.ai/lively_brown_mysterious_lion/uploads/8bd82466-f5ee-569e-9125-2c4c6ce7a07f_b481c730)

## Introducing Today's Project!

### What is Amazon DynamoDB?

Amazon DynamoDB is a fully managed, serverless NoSQL database service provided by AWS. It is useful because it offers fast, low-latency performance, flexible data models, and automatic scaling, making it suitable for applications that need to handle large amounts of data and high request volumes.

### How I used Amazon DynamoDB in this project

In today's project, I used Amazon DynamoDB to create tables, load data from JSON files using the AWS CLI, and view and update items to understand how a NoSQL database stores and manages data.

### One thing I didn't expect in this project was...

One thing I didn't expect in this project was that AWS CloudShell provides up to 1 GB of persistent storage!

### This project took me...

This project took me about one hour, including documentation.

## Create a DynamoDB table

DynamoDB tables organize data using items and attributes, with primary keys used to uniquely identify each item.

An attribute is a piece of data that describes an item in a DynamoDB table, similar to a column in a relational database.

![Image](https://nextwork.ai/lively_brown_mysterious_lion/uploads/8bd82466-f5ee-569e-9125-2c4c6ce7a07f_a3cefee0)

## Read and Write Capacity

Read capacity units (RCUs) and write capacity units (WCUs) are the units DynamoDB uses to measure and manage the read and write capacity of a table.

Amazon DynamoDB's Free Tier covers 25 WCUs and 25 RCUs per month. I turned off auto scaling because I wanted to keep the capacity fixed and avoid unnecessary usage or charges while working on this project.

![Image](https://nextwork.ai/lively_brown_mysterious_lion/uploads/8bd82466-f5ee-569e-9125-2c4c6ce7a07f_ef47dd8f)

## Using CLI and CloudShell

AWS CloudShell is a browser-based shell that provides pre-installed command-line tools, including the AWS CLI, allowing you to manage AWS resources without installing or configuring tools on your local machine.

AWS CLI (Command Line Interface) is a tool that allows you to manage and interact with AWS services by running commands in a terminal instead of using the AWS Management Console.

I ran a CLI command in AWS CloudShell to execute a script that creates four tables in Amazon DynamoDB, each with specific key attributes and settings.
The four tables created are:
- ContentCatalog Table: This table has a numeric attribute called `Id`.
- Forum Table: This table has a partition key called `Name`.
- Post Table: This table has a partition key called `ForumName` and a sort key called `Subject`. I'll explain sort keys in more detail later.
- Comment Table: This table has a partition key called `Id` and a sort key called `CommentDateTime`.

![Image](https://nextwork.ai/lively_brown_mysterious_lion/uploads/8bd82466-f5ee-569e-9125-2c4c6ce7a07f_81e0258b)

## Loading Data with CLI

I ran a CLI command in AWS CloudShell that loaded data from four JSON files into their corresponding DynamoDB tables using the AWS CLI.

![Image](https://nextwork.ai/lively_brown_mysterious_lion/uploads/8bd82466-f5ee-569e-9125-2c4c6ce7a07f_791c600b)

## Observing Item Attributes

![Image](https://nextwork.ai/lively_brown_mysterious_lion/uploads/8bd82466-f5ee-569e-9125-2c4c6ce7a07f_b481c731)

I checked an item in the `ContentCatalog` table, which contained the following attributes:
- Id: `1` (Number, partition key)
- Authors: A list of authors (List)
- ContentType: `Project` (String)
- Difficulty: `Easy peasy` (String)
- Price: `0` (Number)
- ProjectCategory: `Storage` (String)
- Published:`True` (Boolean)
- Title: `Host a Website on Amazon S3` (String)
- URL: `aws-host-a-website-on-s3` (String)

I checked another item in the ContentCatalog table, which had a different set of attributes and values, demonstrating that items in DynamoDB can have different attributes within the same table.

## Benefits of DynamoDB

A benefit of DynamoDB over relational databases is flexibility, because items in the same table can have different attributes, allowing the database to handle varying data structures without requiring a fixed schema.

Another benefit over relational databases is speed, because DynamoDB is designed to provide fast, predictable, low-latency performance at scale without requiring you to manage database servers.

![Image](https://nextwork.ai/lively_brown_mysterious_lion/uploads/8bd82466-f5ee-569e-9125-2c4c6ce7a07f_b481c730)

---

*Built with [NextWork](https://nextwork.ai) - [View this project](https://nextwork.ai/projects/8bd82466-f5ee-569e-9125-2c4c6ce7a07f)*
