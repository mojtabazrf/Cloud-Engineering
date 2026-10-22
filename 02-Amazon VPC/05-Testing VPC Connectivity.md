
# Testing VPC Connectivity

**Author:** Mojtaba Zarifi  
**Email:** mojtabazarifi86@gmail.com

---

![Image](https://nextwork.ai/lively_brown_mysterious_lion/uploads/da091986-ef01-5973-a070-b15e174f59d8_8ee57662)

## Introducing Today's Project!

### What is Amazon VPC?

Amazon VPC is a logically isolated virtual network in AWS, and it is useful because it allows you to control how your AWS resources communicate with each other and with external networks.

### How I used Amazon VPC in this project

In today's project, I used Amazon VPC to configure a virtual network, deploy public and private EC2 instances, and test connectivity between servers and the internet.

### One thing I didn't expect in this project was...

One thing I didn't expect in this project was that even when two EC2 instances are in the same VPC, they might not be able to communicate because of security group rules or network ACL configurations.

### This project took me...

This project took me about one hour, including documentation.

## Connecting to an EC2 Instance

Connectivity is how effectively network components communicate with each other and with external networks. It enables smooth data flow and is essential for reliable and efficient network-based systems, from simple web hosting to large-scale platforms like Netflix.

My first connectivity test was whether I could connect to my public server.

![Image](https://nextwork.ai/lively_brown_mysterious_lion/uploads/da091986-ef01-5973-a070-b15e174f59d8_88727bef)

## EC2 Instance Connect

I connected to my EC2 instance using EC2 Instance Connect, which is a browser-based method for securely connecting to an EC2 instance using SSH without managing SSH keys manually.

My first attempt to connect directly to my public server resulted in an error because I hadn't allowed SSH traffic on port 22 in the inbound rules of my public security group.

I fixed the error by allowing SSH traffic on port 22 in the inbound rules of my public security group.

![Image](https://nextwork.ai/lively_brown_mysterious_lion/uploads/da091986-ef01-5973-a070-b15e174f59d8_1cbb1b88)

## Connectivity Between Servers

Ping is a network utility used to test whether two devices can communicate with each other over a network. I used ping to test the connectivity between my public and private EC2 instances.

The ping command I ran was ping 10.0.1.58

The first ping returned no reply. This meant there was no connection between the two servers using the ICMP protocol.

![Image](https://nextwork.ai/lively_brown_mysterious_lion/uploads/da091986-ef01-5973-a070-b15e174f59d8_defghijk)

## Troubleshooting Connectivity

I troubleshot this issue by allowing ICMP traffic in the network ACL and security group.

![Image](https://nextwork.ai/lively_brown_mysterious_lion/uploads/da091986-ef01-5973-a070-b15e174f59d8_4a9e8014)

## Connectivity to the Internet

Curl is a command-line tool used to transfer data to and from servers over network protocols such as HTTP and HTTPS.

I used curl to test the connectivity between my public server and internet.

### Ping vs Curl

Ping and curl are different because ping tests basic network connectivity using ICMP, while curl tests application-level connectivity by communicating with services such as HTTP or HTTPS.

## Connectivity to the Internet

I ran the curl command curl google.com which returned:
<HTML><HEAD><meta http-equiv="content-type" content="text/html;charset=utf-8">
<TITLE>301 Moved</TITLE></HEAD><BODY>
<H1>301 Moved</H1>
The document has moved
<A HREF="http://www.google.com/">here</A>.
</BODY></HTML>

![Image](https://nextwork.ai/lively_brown_mysterious_lion/uploads/da091986-ef01-5973-a070-b15e174f59d8_8ee57662)

---

*Built with [NextWork](https://nextwork.ai) - [View this project](https://nextwork.ai/projects/da091986-ef01-5973-a070-b15e174f59d8)*
