
# Query Data with DynamoDB

**Author:** Mojtaba Zarifi  
**Email:** mojtabazarifi86@gmail.com

---

![Image](https://nextwork.ai/lively_brown_mysterious_lion/uploads/0001cf4c-8256-52ae-b09c-6e99ed36462f_733d9399)

## Introducing Today's Project!

### What is Amazon DynamoDB?

Amazon DynamoDB is a fully managed, serverless NoSQL database service provided by AWS. It stores data as key-value pairs and documents, and it is designed to deliver fast, predictable performance at scale.
It is useful because it automatically scales to handle changing workloads, provides high availability, and reduces the need to manage database servers. It also supports flexible data models, efficient queries using partition and sort keys, and transactions for updating multiple items atomically.

### How I used Amazon DynamoDB in this project

In today's project, I used Amazon DynamoDB to create tables, load and query data using the AWS CLI, understand partition and sort keys, and perform transactions to update related data across multiple tables atomically.

### One thing I didn't expect in this project was...

One thing I didn't expect in this project is that DynamoDB can update multiple related items across different tables atomically using transactions, ensuring that either all operations succeed or none of them are applied.

### This project took me...

This project took me about one hour, including documentation.

## Querying DynamoDB Tables

A partition key is an attribute that DynamoDB uses to determine where an item is stored and to uniquely identify items within a table.

A sort key is an attribute that DynamoDB uses to organize and sort items with the same partition key.

![Image](https://nextwork.ai/lively_brown_mysterious_lion/uploads/0001cf4c-8256-52ae-b09c-6e99ed36462f_d105b0b0)

## Limits of Using DynamoDB

I ran into an error when I queried the table to find records posted by a specific user. This was because the `ID` attribute, which is the partition key, cannot be empty.

Insights we could extract from our Comment table include all comments left on a single post.
Insights we can't easily extract from the Comment table include all comments made by a specific user.

![Image](https://nextwork.ai/lively_brown_mysterious_lion/uploads/0001cf4c-8256-52ae-b09c-6e99ed36462f_cb3e260c)

## Running Queries with CLI

A query I ran in CloudShell was 

aws dynamodb get-item \
    --table-name ContentCatalog \
    --key '{"Id":{"N":"202"}}' \
    --projection-expression "Title, ContentType, Services" \
    --return-consumed-capacity TOTAL 

This query will retrieve the item with the partition key Id set to 202 from the ContentCatalog table, return only the Title, ContentType, and Services attributes, and report the total consumed read capacity.

Query options I could add to my query are --consistent-read to get strongly consistent reads, --return-consumed-capacity to check read capacity usage, and --projection-expression to specify which attributes to return.

![Image](https://nextwork.ai/lively_brown_mysterious_lion/uploads/0001cf4c-8256-52ae-b09c-6e99ed36462f_733d9399)

## Transactions

A transaction is a group of database operations that are treated as a single unit, ensuring that either all operations succeed or none of them are applied.

I ran a transaction using AWS CLI commands in AWS CloudShell. This transaction performed two operations: first, it added a new item to the Comment table; then, it updated an item in the Forum table.

![Image](https://nextwork.ai/lively_brown_mysterious_lion/uploads/0001cf4c-8256-52ae-b09c-6e99ed36462f_2f65f83e)

---

*Built with [NextWork](https://nextwork.ai) - [View this project](https://nextwork.ai/projects/0001cf4c-8256-52ae-b09c-6e99ed36462f)*
