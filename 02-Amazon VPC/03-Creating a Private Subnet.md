
# Creating a Private Subnet

**Author:** Mojtaba Zarifi  
**Email:** mojtabazarifi86@gmail.com

---

![Image](https://nextwork.ai/lively_brown_mysterious_lion/uploads/4e96e29d-98b8-551e-ae93-da39c36e30fd_afe1fdbd)

## Introducing Today's Project!

### What is Amazon VPC?

Amazon VPC is a service that allows me to create a logically isolated virtual network in AWS. It is useful because it gives me control over IP addresses, subnets, route tables, and network security settings, allowing me to securely deploy AWS resources and control how they communicate with each other.

### How I used Amazon VPC in this project

In today's project, I used Amazon VPC to create a private subnet, a dedicated private route table, and a custom network ACL. I configured these resources to control how network traffic flows within my VPC and to understand how to isolate and secure resources in a private subnet.

### One thing I didn't expect in this project was...

One thing I didn't expect in this project was how much control network ACLs and route tables provide over network traffic. I learned that route tables determine where traffic is directed, while network ACLs control which traffic is allowed or denied at the subnet level.

### This project took me...

This project took me about one hour, including documentation.

## Private vs Public Subnets

The difference between public and private subnets is that a public subnet has a direct route to the internet through an Internet Gateway, while a private subnet does not have a direct route to the internet.

Having private subnets is useful because they allow me to keep resources isolated from direct internet access and control how traffic flows to and from those resources.

My private and public subnets cannot have the same CIDR block because each subnet must have a unique IP address range within the same VPC.

![Image](https://nextwork.ai/lively_brown_mysterious_lion/uploads/4e96e29d-98b8-551e-ae93-da39c36e30fd_afe1fdbd)

## A dedicated route table

By default, my private subnet is associated with the VPC's main route table.

I had to set up a new route table because I wanted to control how traffic from my private subnet is routed and ensure that it does not have a direct route to the internet through an Internet Gateway.

My private subnet's dedicated route table only has one inbound and one outbound rule that allows traffic to flow within the VPC through the local route, without providing a direct route to the internet.

![Image](https://nextwork.ai/lively_brown_mysterious_lion/uploads/4e96e29d-98b8-551e-ae93-da39c36e30fd_b4b904b5)

## A new network ACL

By default, my private subnet is associated with the VPC's default network ACL.

I set up a dedicated network ACL for my private subnet because I wanted to control inbound and outbound traffic at the subnet level and add an extra layer of security to my AWS network.

My new network ACL has two simple rules: one inbound rule and one outbound rule, both of which deny all traffic.

![Image](https://nextwork.ai/lively_brown_mysterious_lion/uploads/4e96e29d-98b8-551e-ae93-da39c36e30fd_1ed2cb07)

---

*Built with [NextWork](https://nextwork.ai) - [View this project](https://nextwork.ai/projects/4e96e29d-98b8-551e-ae93-da39c36e30fd)*
