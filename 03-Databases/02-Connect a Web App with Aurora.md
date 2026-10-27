
# Connect a Web App with Aurora

**Author:** Mojtaba Zarifi  
**Email:** mojtabazarifi86@gmail.com

---

![Image](https://nextwork.ai/lively_brown_mysterious_lion/uploads/921d7b78-ffa4-5e41-a5b5-aed76c78efad_1709b26b)

## Introducing Today's Project!

### What is Amazon Aurora?

Amazon Aurora is a fully managed relational database service compatible with MySQL and PostgreSQL, and it is useful because it provides high performance, scalability, and high availability for applications that need reliable data storage and management.

### How I used Amazon Aurora in this project

In today's project, I used Amazon Aurora to store and manage application data, connect a PHP web application running on an EC2 instance to a MySQL database, and verify that data could be inserted and updated successfully.

### One thing I didn't expect in this project was...

One thing I didn't expect in this project was how important it was to configure the security groups and database connection details correctly to allow my PHP web application on EC2 to communicate with my Aurora database securely.

### This project took me...

This project took me about one hour, including documentation.

## Creating a Web App

![Image](https://nextwork.ai/lively_brown_mysterious_lion/uploads/921d7b78-ffa4-5e41-a5b5-aed76c78efad_b7999168)

To connect to my EC2 instance, I used SSH, my `.pem` file, and the public IPv4 address of my EC2 instance.

To create my web app, I first installed `httpd`, `php`, `php-mysqli`, and `mariadb105`.

## Connecting my Web App to Aurora

I configured the database connection details for my EC2 instance by creating an `inc` folder under `/var/www`, creating a file named `dbinfo.inc`, and adding the following PHP code to the file:
<?php

define('DB_SERVER', '');
define('DB_USERNAME', '');
define('DB_PASSWORD', '');
define('DB_DATABASE', '');

?>

![Image](https://nextwork.ai/lively_brown_mysterious_lion/uploads/921d7b78-ffa4-5e41-a5b5-aed76c78efad_1709b25b)

## My Web App Upgrade

Next, I enhanced my web app by creating a sample file in `/var/www/html` and writing PHP code in it.

![Image](https://nextwork.ai/lively_brown_mysterious_lion/uploads/921d7b78-ffa4-5e41-a5b5-aed76c78efad_2709b25b)

## Testing my Web App

To make sure my web app was working correctly, I used the MySQL CLI to connect to my Aurora database and verify that the data was being inserted and updated correctly.

![Image](https://nextwork.ai/lively_brown_mysterious_lion/uploads/921d7b78-ffa4-5e41-a5b5-aed76c78efad_1409z22b)

---

*Built with [NextWork](https://nextwork.ai) - [View this project](https://nextwork.ai/projects/921d7b78-ffa4-5e41-a5b5-aed76c78efad)*
