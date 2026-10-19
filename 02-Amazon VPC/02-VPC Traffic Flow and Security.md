<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# VPC Traffic Flow and Security

**Project Link:** [View Project](https://nextwork.ai/projects/fe5ed473-5874-57e1-a58f-d9b3d652330c)

**Author:** Mojtaba Zarifi  
**Email:** mojtabazarifi86@gmail.com

---

![Image](https://nextwork.ai/lively_brown_mysterious_lion/uploads/fe5ed473-5874-57e1-a58f-d9b3d652330c_92b0b0b4)

## Introducing Today's Project!

### What is Amazon VPC?

Amazon VPC is a service that allows you to create a logically isolated virtual network in AWS, and it is useful because it lets you securely launch and manage AWS resources, control network traffic, and configure IP addresses, subnets, route tables, and security settings.

### How I used Amazon VPC in this project

In today's project, I used Amazon VPC to create a route table, a security group, and a network ACL.

### One thing I didn't expect in this project was...

One thing I didn't expect in this project was how many different networking components Amazon VPC provides to control and secure network traffic, such as route tables, security groups, and network ACLs.

### This project took me...

This project took me about one hour.

## Route tables

Route tables is a set of rules (called routes) that control where network traffic is directed from our subnets or gateways in an Amazon Virtual Private Cloud (VPC).

Routes tables are needed to make a subnet public because the route table determines where traffic from that subnet goes. In AWS, a subnet is considered public when its associated route table has a route to an Internet Gateway (IGW).

![Image](https://nextwork.ai/lively_brown_mysterious_lion/uploads/fe5ed473-5874-57e1-a58f-d9b3d652330c_0a07b191)

## Route destination and target

Routes are defined by their destination and target, which mean:
Destination: The range of IP addresses (usually written as a CIDR block like 10.0.0.0/16 or 0.0.0.0/0 for all IPv4 addresses) that the traffic is trying to reach.
Target: The gateway, interface, or connection (such as an Internet Gateway, NAT Gateway, or Local network) where the router sends the matching traffic next.

The route in my route table that directed internet-bound traffic to my internet gateway had a destination of 0.0.0.0/0 and a target of my VPC's internet gateway.

![Image](https://nextwork.ai/lively_brown_mysterious_lion/uploads/fe5ed473-5874-57e1-a58f-d9b3d652330c_0a07b191)

## Security groups

A security group is virtual firewall that controls inbound and outbound network traffic for resources.

### Inbound vs Outbound rules

Inbound rules are rules that control which incoming traffic is allowed to reach my AWS resources. I configured an inbound rule that allows HTTP traffic over TCP on port 80 from any IPv4 address (0.0.0.0/0), allowing users from anywhere on the internet to access my web server using HTTP.

Outbound rules are rules that control which outgoing traffic is allowed from my AWS resources to other destinations. By default, my security group's outbound rule allows all outbound traffic to any IPv4 address

![Image](https://nextwork.ai/lively_brown_mysterious_lion/uploads/fe5ed473-5874-57e1-a58f-d9b3d652330c_92b0b0b4)

## Network ACLs

Network ACLs are virtual firewalls in AWS that control inbound and outbound traffic at the subnet level. They determine which traffic is allowed or denied based on rules that specify protocols, port numbers, IP addresses, and rule numbers.

### Security groups vs. network ACLs

Security groups and network ACLs both act as firewalls, but they operate at different levels and handle traffic differently. Security groups act as a firewall for individual resources, such as EC2 instances. Network ACLs act as a firewall for subnets, controlling traffic entering and leaving the subnet.

## Default vs Custom Network ACLs

### Similar to security groups, network ACLs use inbound and outbound rules

By default, a network ACL's inbound and outbound rules will allow all traffic to enter and leave the subnet, respectively. This means all inbound and outbound traffic is allowed unless other network rules or security controls restrict it.

In contrast, a custom network ACL’s inbound and outbound rules are automatically set to deny all traffic by default. We must add rules to explicitly allow the traffic we want to permit into or out of the subnet.

![Image](https://nextwork.ai/lively_brown_mysterious_lion/uploads/fe5ed473-5874-57e1-a58f-d9b3d652330c_4faeb056)

## Tracking VPC Resources

I created an additional VPC, security group, and internet gateway. Instead of using my usual region, I deployed them in another AWS Region. Teams would use multiple regions to improve application availability, increase fault tolerance, reduce latency for users in different geographical locations, and support disaster recovery.

EC2 Global View is a tool where you can find and monitor your EC2 resources across all AWS Regions, including instances, VPCs, security groups, and internet gateways. I could even narrow down my search by selecting a specific AWS Region or filtering resources by type. Without EC2 Global View, you'd have to switch between regions and check each one individually to find and manage your resources.

Now that I've learned about EC2 Global View, I'd use it again to monitor and manage my AWS resources across multiple regions, quickly locate specific resources, and verify that my VPCs, security groups, and internet gateways are configured correctly.

![Image](https://nextwork.ai/lively_brown_mysterious_lion/uploads/fe5ed473-5874-57e1-a58f-d9b3d652330c_b03ea6162)

---

*Built with [NextWork](https://nextwork.ai) - [View this project](https://nextwork.ai/projects/fe5ed473-5874-57e1-a58f-d9b3d652330c)*
