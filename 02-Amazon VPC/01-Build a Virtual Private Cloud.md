<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Build a Virtual Private Cloud

**Project Link:** [View Project](https://nextwork.ai/projects/7f907ac7-2473-5c15-a8be-edb36581cdba)

**Author:** Mojtaba Zarifi  
**Email:** mojtabazarifi86@gmail.com

---

![Image](https://nextwork.ai/lively_brown_mysterious_lion/uploads/7f907ac7-2473-5c15-a8be-edb36581cdba_2facf927)

## Introducing Today's Project!

In this project, I will demonstrate how to create a VPC and subnets and set up an internet gateway. I am doing this project to learn how to configure a Virtual Private Cloud (VPC) using Amazon VPC, create subnets that act like neighborhoods within a city, each with its own access rules, and set up an internet gateway to enable internet connectivity.

## Virtual Private Clouds (VPCs)

### What I did in this step

In this step, I will create a VPC because VPCs are the reason why resources can be made private to me. I also get control over resources in a VPC, so I can organize how they communicate and integrate with each other without the public internet.

### How VPCs work

VPC is a foundational networking service that lets us provision a logically isolated, private section of the Amazon Web Services (AWS) cloud. It acts like our own traditional on-premises data center running inside AWS, giving us full control over our virtual networking environment, including IP addresses, subnets, route tables, and network gateways.

### Why there is a default VPC in AWS accounts

There was already a default VPC in my account when I created my AWS account. This is because AWS automatically creates a default VPC to allow me to launch resources, such as Amazon EC2 instances, immediately without having to configure a network manually.

![Image](https://nextwork.ai/lively_brown_mysterious_lion/uploads/7f907ac7-2473-5c15-a8be-edb36581cdba_2facf927)

### Defining IPv4 CIDR blocks

To set up my VPC, I had to define an IPv4 CIDR block, which is a method for allocating IP addresses and routing internet traffic more efficiently. Instead of rigid address classes, it uses a suffix (like /24) to define the network portion of an address, allowing for flexible, variable-sized network blocks that reduce routing table bloat.

## Subnets

### What I did in this step

In this step, I will create a subnet to start planning where different resources will be deployed and operate within my VPC.

### Creating and configuring subnets

Subnets are smaller, segmented pieces of a larger network. By dividing a network into subnets, we improve performance and security by grouping related devices together and controlling how traffic flows between them.
There are already subnets existing in my account, one for every availability zone.

### Public vs private subnets

The difference between public and private subnets are how they connect to the internet. A public subnet has a direct route to the internet via an Internet Gateway, while a private subnet does not have a direct path to the internet For a subnet to be considered public, it has to connect to an internet gateway.

![Image](https://nextwork.ai/lively_brown_mysterious_lion/uploads/7f907ac7-2473-5c15-a8be-edb36581cdba_157c4219)

### Auto-assigning public IPv4 addresses

Once I created my subnet, I enabled auto-assign public IPv4 addresses. This setting makes sure any EC2 instance launched in that subnet will instantly get a public IP address.

## Internet gateways

### What I did in this step

In this step, I will connect my VPC to the internet using a internet gateway.

### Setting up internet gateways

Internet gateways are key to making applications available on the internet. By attaching an internet gateway, our instances can access the internet and be accessible to external users.

Attaching an internet gateway means resources in our VPC can now access the internet. The EC2 instances with public IP addresses also become accessible to users, so our applications hosted on those servers become public too.

![Image](https://nextwork.ai/lively_brown_mysterious_lion/uploads/7f907ac7-2473-5c15-a8be-edb36581cdba_4ae90410)

## Using the AWS CLI

### What I'm doing in this extension

In this project extension, I will open a handy tool (called AWS CloudShell) to run commands to set up a VPC, subnet and internet gateway because it is a faster and more efficient way to do this.

### Exploring CloudShell and CLI

VPC resources could also be created with CloudShell, which is a browser-based terminal accessible directly inside the AWS Management Console. AWS CLI is  is a downloadable software application that we install locally on our own computer. It requires manual setup, including the configuration of security access keys to connect to our AWS account.

### Debugging my setup

To set up a VPC or a subnet, you can use the command. Make sure to avoid errors by including correct CIDR block.

![Image](https://nextwork.ai/lively_brown_mysterious_lion/uploads/7f907ac7-2473-5c15-a8be-edb36581cdba_9b2465411)

### Comparing CloudShell vs AWS Console

Compared to using the AWS Console, an advantage of using commands is that they allow me to automate tasks, work more efficiently, and repeat configurations easily. An advantage of using the Console is that it provides a visual interface that makes it easier to navigate AWS services and understand how resources are configured.

---

*Built with [NextWork](https://nextwork.ai) - [View this project](https://nextwork.ai/projects/7f907ac7-2473-5c15-a8be-edb36581cdba)*
