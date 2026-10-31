## Introducing Today's Project!

In this project, I will demonstrate how to create and manage encryption keys in AWS KMS, encrypt a DynamoDB table using an encryption key, add data to my encrypted table, use a test user to validate the encryption, and grant my test user access to encryption operations. The goal is to understand how AWS KMS helps protect sensitive data, manage encryption keys securely, and control access to encrypted resources using IAM permissions.

### ✍️ What are we doing in this step?

In this step, I will create an encryption key and set up the key administrators and users because properly managing key access is essential for maintaining security, controlling who can encrypt and decrypt data, and ensuring that only authorized users can manage the encryption key.

### Tools and concepts

Services I used include AWS KMS, Amazon DynamoDB, and AWS IAM. Key concepts I learnt include encryption, symmetric keys, customer-managed keys, key policies, transparent data encryption, and access control through IAM permissions.'

### Project reflection

This project took me about one hour, including documentation.

I chose to do this project today because I wanted to understand how AWS protects sensitive data using encryption and how to manage access to encryption keys securely.

## Encryption and KMS

Encryption is the process of converting readable data into an unreadable format to protect it from unauthorized access. Companies and developers do this to keep sensitive information safe and prevent data leaks. Encryption keys are like digital keys that help lock and unlock data, allowing only authorized users to access it.

AWS KMS is a managed service that helps me create, manage, and use encryption keys to protect my data in AWS. Key management systems are important because they help keep encryption keys secure, control who can access them, and make it easier to protect sensitive information.

Encryption keys are broadly categorized as symmetric and asymmetric keys. I set up a symmetric key because it uses the same key to encrypt and decrypt data, making it a simple and efficient choice for protecting my DynamoDB table.

![Encryption and KMS](https://nextwork.ai/lively_brown_mysterious_lion/uploads/716e7f81-84d1-51d6-8945-d4860caebf77_a2b3c4d5)

### ✍️ What are we doing in this step?

In this step, I will create a DynamoDB table and set up my table's encryption with KMS because I want to protect the data stored in my table and make sure that sensitive information can only be accessed by authorized users.

## Encrypting Data

My encryption key will safeguard data in DynamoDB, which is a fully managed NoSQL database service that allows me to store and retrieve data quickly and easily without managing database servers.

The different encryption options in DynamoDB include AWS owned keys, AWS managed keys, and customer managed keys. Their differences are based on who manages the encryption keys and how much control users have over them. I selected a customer managed key because it gives me more control over key management, access permissions, and encryption settings.

### ✍️ What are we doing in this step?

In this step, I will add data to my DynamoDB table and verify whether I can see the encrypted data because I want to understand how encryption works in practice and make sure my data is protected while still being accessible to authorized users.

![Encrypting Data](https://nextwork.ai/lively_brown_mysterious_lion/uploads/716e7f81-84d1-51d6-8945-d4860caebf77_q8r9s0t1)

## Data Visibility

Rather than controlling who has access to the key directly, KMS manages user permissions by using key policies and IAM policies to determine who can use the key and perform encryption or decryption operations.

Despite encrypting my DynamoDB table, I could still see the table's items because DynamoDB automatically decrypts the data when an authorized user accesses it. DynamoDB uses transparent data encryption, which means data is encrypted when stored and automatically decrypted when accessed, so I don't need to manually encrypt or decrypt it.

### ✍️ What are we doing in this step?

In this step, I will create a test user using IAM and grant the user full access to DynamoDB but not to my KMS key because I want to test how AWS handles access to encrypted data and understand the difference between database permissions and encryption key permissions.

![Data Visibility](https://nextwork.ai/lively_brown_mysterious_lion/uploads/716e7f81-84d1-51d6-8945-d4860caebf77_c0d1e2f3)

## Denying Access

I configured a new IAM user to test how access permissions work when using an encrypted DynamoDB table. The permission policies I granted this user provide full access to DynamoDB but do not allow access to my KMS key.

### ✍️ What are we doing in this step?

In this step, I will log into AWS as the test user and try to view items in the encrypted DynamoDB table because I want to test whether having full access to DynamoDB is enough to view encrypted data without permission to use the KMS key.

After accessing the DynamoDB table as the test user, I encountered an access denied error when trying to view the encrypted data because the user had permission to access DynamoDB but not to use the KMS encryption key. This confirmed that access to an encrypted table also depends on having the correct permissions to use its encryption key.

![Denying Access](https://nextwork.ai/lively_brown_mysterious_lion/uploads/716e7f81-84d1-51d6-8945-d4860caebf77_w0x1y2z3)

## EXTRA: Granting Access

To let my test user use the encryption key, I updated the KMS key policy to grant the user the required permissions. My key's policy was updated to allow the test user to use the key for encryption and decryption while keeping key management permissions restricted to the administrator.

Using the test user, I retried accessing the encrypted items in my DynamoDB table. I observed that I could now view the data without any access errors, which confirmed that granting the correct KMS permissions allows authorized users to access encrypted data securely.

Encryption secures data instead of controlling who can access it. I could combine encryption with IAM policies and access controls to protect sensitive information while making sure that only authorized users can access it.

![EXTRA: Granting Access](https://nextwork.ai/lively_brown_mysterious_lion/uploads/716e7f81-84d1-51d6-8945-d4860caebf77_feffb2fb8)
