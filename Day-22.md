# Day 22 - Amazon EC2 (Elastic Compute Cloud)

## What I Learned
- Amazon EC2 is a cloud computing service provided by AWS
- EC2 allows users to launch virtual servers called instances
- It provides scalable and on-demand computing capacity
- Users can choose CPU, memory, storage, and operating systems based on requirements
- EC2 is widely used for hosting applications, websites, and backend services

## What is Amazon EC2
- Amazon EC2 stands for Elastic Compute Cloud
- It provides virtual machines in the AWS cloud
- These virtual machines are called EC2 instances
- EC2 allows developers to deploy applications without managing physical servers

Amazon EC2 provides scalable virtual servers that help users deploy applications quickly without hardware limitations. :contentReference[oaicite:0]{index=0}

## Why EC2 is Important
- No need to purchase physical servers
- Easy scalability based on demand
- Pay only for resources used
- Fast deployment of applications
- Supports multiple operating systems

## Key Components of EC2

### Instance
- A virtual server running in AWS cloud
- Used to host applications

### AMI (Amazon Machine Image)
- Template used to launch EC2 instances
- Includes operating system and software configuration

### Instance Type
- Defines CPU, memory, storage, and networking capacity
- Different types are available for different workloads

### Security Group
- Acts as a virtual firewall
- Controls incoming and outgoing traffic

### Key Pair
- Used for secure login into EC2 instances
- Includes public key and private key

## Steps to Launch an EC2 Instance
1. Login to AWS Console
2. Open EC2 Dashboard
3. Click "Launch Instance"
4. Choose AMI
5. Select Instance Type
6. Configure Security Group
7. Launch Instance using Key Pair

## Basic EC2 Features
- On-demand virtual servers
- Auto Scaling support
- Load balancing integration
- Monitoring with CloudWatch
- Multiple pricing options

EC2 supports features like auto scaling, monitoring, and flexible pricing for cloud applications. :contentReference[oaicite:1]{index=1}

## Common Use Cases
- Hosting web applications
- Running backend APIs
- Deploying DevOps projects
- Running databases
- Testing and development environments

## Advantages of EC2
- Scalable infrastructure
- Flexible pricing
- High availability
- Easy deployment
- Global accessibility

## Real Use Case
A company wants to deploy a Node.js web application:
- Launches an EC2 instance
- Installs required software
- Deploys application on the server
- Users access the application through public IP

This avoids purchasing and maintaining physical servers.

## Summary
Amazon EC2 is a cloud computing service that provides scalable virtual servers in AWS. It enables developers to deploy and manage applications efficiently without managing physical infrastructure.

## My Learning Reflection
Today I learned how EC2 instances work and why they are important in cloud computing and DevOps. I understood concepts like AMI, security groups, and instance types which are essential for deploying applications on AWS.