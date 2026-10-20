<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# VPC Peering

**Project Link:** [View Project](https://nextwork.ai/projects/fd75209e-d2a1-5bdd-90e8-bdb9ee49de16)

**Author:** Mojtaba Zarifi  
**Email:** mojtabazarifi86@gmail.com

---

![Image](https://nextwork.ai/lively_brown_mysterious_lion/uploads/fd75209e-d2a1-5bdd-90e8-bdb9ee49de16_88727bef)

## Introducing Today's Project!

### What is Amazon VPC?

Amazon VPC (Virtual Private Cloud) is a logically isolated virtual network in AWS where you can launch and manage cloud resources, and it is useful because it allows you to control IP address ranges, subnets, route tables, and network security to build a secure and scalable cloud infrastructure.

### How I used Amazon VPC in this project

In today's project, I used Amazon VPC to create two isolated virtual networks, configure their routing tables, and establish a VPC peering connection to enable private communication between EC2 instances in both VPCs.

### One thing I didn't expect in this project was...

One thing I didn't expect in this project was that establishing a VPC peering connection alone wouldn't enable communication between the two EC2 instances; I also had to configure route tables and security group rules to allow traffic between them.

### This project took me...

This project took me about one hour, including documentation.

## In the first part of my project...

### Step 1 - Set up my VPC

In this step, I will create two VPCs from scratch because I want to design and configure the VPCs before connecting them using VPC Peering.

### Step 2 - Create a Peering Connection

In this step, I will connect my two VPCs using a VPC Peering connection because I want to enable private communication between resources in the two VPCs without routing traffic over the public internet.

### Step 3 - Update Route Tables

In this step, I will configure routes to allow traffic from VPC 1 to reach VPC 2 and vice versa because a VPC peering connection alone does not enable traffic routing; each VPC's route table must contain a route to the other VPC's CIDR block through the peering connection.

### Step 4 - Launch EC2 Instances

In this step, I will launch an EC2 instance in each VPC, so we can use them to test our VPC peering connection later.

## Multi-VPC Architecture

I started my project by creating two VPCs, each with one public subnet in a single Availability Zone (AZ) and a different IPv4 CIDR block.

The CIDR blocks for VPCs 1 and 2 are 10.1.0.0/16 and 10.2.0.0/16, respectively. They have to be unique because overlapping IP address ranges can cause routing conflicts and prevent proper communication between the VPCs through VPC Peering.

### I also launched 2 EC2 instances

I didn't configure key pairs for these EC2 instances because I've already learned how to set them up in the previous two projects, so there's no need to repeat the process this time.

![Image](https://nextwork.ai/lively_brown_mysterious_lion/uploads/fd75209e-d2a1-5bdd-90e8-bdb9ee49de16_11111111)

## VPC Peering

A VPC peering connection is a private networking connection between two VPCs that allows resources in them to communicate using private IP addresses, provided that the appropriate routes and security rules are configured.

VPCs would use peering connections to enable private communication between resources in different VPCs, such as EC2 instances, without sending traffic over the public internet.

The difference between a Requester and an Accepter in a peering connection is that the Requester initiates the VPC peering connection, while the Accepter is the VPC owner who must accept the request to establish the connection.

![Image](https://nextwork.ai/lively_brown_mysterious_lion/uploads/fd75209e-d2a1-5bdd-90e8-bdb9ee49de16_1cbb1b88)

## Updating route tables

After accepting a peering connection, my VPCs' route tables need to be updated because the peering connection alone does not automatically route traffic between the VPCs; each VPC needs a route to the other VPC's CIDR block through the peering connection.

My VPCs' new routes have the other VPC's IPv4 CIDR block as the destination, and the peering connection as the target.

![Image](https://nextwork.ai/lively_brown_mysterious_lion/uploads/fd75209e-d2a1-5bdd-90e8-bdb9ee49de16_4a9e8014)

## In the second part of my project...

### Step 5 - Use EC2 Instance Connect

In this step, I will use EC2 Instance Connect to connect to the first EC2 instance and attempt to communicate with the other one.

### Step 6 - Connect to EC2 Instance 1

In this step, I will use EC2 Instance Connect to connect to Instance 1 once again because I want to verify that the connection works after associating an Elastic IP address with the instance.

### Step 7 - Test VPC Peering

In this step, I will send test messages from Instance 1 to Instance 2 and troubleshoot any connectivity issues until Instance 2 can successfully send messages back to Instance 1. I will do this because I want to verify that bidirectional communication between the two EC2 instances works correctly through the VPC peering connection.

## Troubleshooting Instance Connect

Next, I used EC2 Instance Connect to access the first EC2 instance and test network connectivity to the second instance through the VPC peering connection.

I couldn't use EC2 Instance Connect because my instance didn't have a public IP address to connect to.

![Image](https://nextwork.ai/lively_brown_mysterious_lion/uploads/fd75209e-d2a1-5bdd-90e8-bdb9ee49de16_7685490c)

## Elastic IP addresses

To resolve this error, I set up Elastic IP addresses. Elastic IP addresses are static public IPv4 addresses provided by AWS that can be associated with supported resources, such as EC2 instances, to provide a consistent public IP address even when an instance is stopped and started.

Associating an Elastic IP address resolved the error because it provided my EC2 instance with a public IPv4 address, allowing me to connect to it using EC2 Instance Connect, provided the necessary network and security configurations were in place.

![Image](https://nextwork.ai/lively_brown_mysterious_lion/uploads/fd75209e-d2a1-5bdd-90e8-bdb9ee49de16_45663498)

## Troubleshooting ping issues

To verify connectivity through the VPC peering connection, I used the ping command to test communication between the two EC2 instances.

A successful ping test would validate my VPC peering connection because it confirms that the two EC2 instances can exchange ICMP packets over the peering connection, provided the appropriate routes and security rules are configured.

I had to update the security group of my second EC2 instance because there was no inbound rule allowing ICMP packets. Therefore, I added a new rule to allow ICMP traffic.

![Image](https://nextwork.ai/lively_brown_mysterious_lion/uploads/fd75209e-d2a1-5bdd-90e8-bdb9ee49de16_7a29d352)

---

*Built with [NextWork](https://nextwork.ai) - [View this project](https://nextwork.ai/projects/fd75209e-d2a1-5bdd-90e8-bdb9ee49de16)*
