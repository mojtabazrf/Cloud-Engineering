<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Launching VPC Resources

**Project Link:** [View Project](https://nextwork.ai/projects/8f49d756-9e51-58c0-856a-e71e54f064ab)

**Author:** Mojtaba Zarifi  
**Email:** mojtabazarifi86@gmail.com

---

![Image](https://nextwork.ai/lively_brown_mysterious_lion/uploads/8f49d756-9e51-58c0-856a-e71e54f064ab_8ee57662)

## Introducing Today's Project!

### What is Amazon VPC?

Amazon VPC is a service that allows me to create a logically isolated virtual network in AWS, and it is useful because it gives me control over IP addresses, subnets, route tables, gateways, and network security settings, allowing me to securely deploy AWS resources and control how they communicate with each other.

### How I used Amazon VPC in this project

I used Amazon VPC to create and configure public and private subnets, set up route tables and an Internet Gateway, and control network traffic using security groups and network ACLs. This allowed me to launch EC2 instances in different subnets and understand how their network access and connectivity differ.

### One thing I didn't expect in this project was...

One thing I didn't expect in this project was how much the network configuration affects EC2 instances. I learned how subnets, route tables, and security groups work together to control connectivity and keep instances secure.

### This project took me...

This project took me about one hour, including documentation.

## Setting Up Direct VM Access

Directly accessing a virtual machine means connecting to it remotely, usually through SSH for Linux instances or Remote Desktop Protocol (RDP) for Windows instances, to manage and configure it.

### SSH is a key method for directly accessing a VM

SSH traffic means network traffic that uses Secure Shell (SSH), a protocol that allows me to securely connect to and manage remote servers over a network. SSH typically uses TCP port 22.

### To enable direct access, I set up key pairs

Key pairs are a set of security credentials consisting of a public key and a private key that allow me to securely connect to my EC2 instances. AWS stores the public key, while I keep the private key to authenticate my connection.

A private key's file format means the format in which the private key is stored and used by software. My private key's file format was .pem.

## Launching a public server

I changed my EC2 instance's networking settings by first selecting my VPC, then choosing my public subnet, and finally selecting the security group I had created earlier to act as my instance's firewall.

![Image](https://nextwork.ai/lively_brown_mysterious_lion/uploads/8f49d756-9e51-58c0-856a-e71e54f064ab_88727bef)

## Launching a private server

My private server has its own dedicated security group because I want to control inbound and outbound traffic specifically for that instance and allow only the necessary connections while reducing its attack surface.

My private server's security group's source is my public server's security group, which means that only resources associated with the public security group can initiate connections to my private server on the allowed ports.

![Image](https://nextwork.ai/lively_brown_mysterious_lion/uploads/8f49d756-9e51-58c0-856a-e71e54f064ab_4a9e8014)

## Speeding up VPC creation

I used an alternative way to set up an Amazon VPC! This time, I selected the “VPC and more” option to create a VPC along with its associated networking resources, such as public and private subnets, route tables, and an Internet Gateway, all in one step.

A VPC resource map is a visual representation of a VPC and its associated resources, such as subnets, route tables, and gateways, showing how they are connected and how network traffic flows between them.

My new VPC has a CIDR block of 10.0.0.0/16. It is possible for my new VPC to have the same IPv4 CIDR block as my existing VPC because VPCs are isolated from each other by default, so their IP addresses do not conflict unless connectivity is explicitly configured between them. However, it is best practice to use unique CIDR blocks for each VPC to avoid overlapping IP ranges and make connecting VPCs easier in the future.

![Image](https://nextwork.ai/lively_brown_mysterious_lion/uploads/8f49d756-9e51-58c0-856a-e71e54f064ab_1cbb1b88)

## Speeding up VPC creation

### Tips for using the VPC resource map

When determining the number of public subnets in my VPC, I only had two options: 0 or 2. This was because the AWS VPC wizard creates a public subnet in each of the two selected Availability Zones to provide redundancy and high availability. This helps keep my public resources available even if one Availability Zone goes down. The wizard limits the options to simplify the setup, but I can create additional subnets manually later if needed.

The setup page also offered to create NAT gateways, which are AWS networking components that allow resources in private subnets to access the internet for outbound connections, such as downloading software updates, without allowing unsolicited inbound connections from the internet.

![Image](https://nextwork.ai/lively_brown_mysterious_lion/uploads/8f49d756-9e51-58c0-856a-e71e54f064ab_8ee57662)

---

*Built with [NextWork](https://nextwork.ai) - [View this project](https://nextwork.ai/projects/8f49d756-9e51-58c0-856a-e71e54f064ab)*
