# Day 25 - Deploying an Application on AWS EC2

## What I Learned
- AWS EC2 can be used to host and deploy applications
- Applications can be accessed publicly using the EC2 public IP address
- Deployment involves launching an EC2 instance, installing software, and running the application
- Security Groups are used to allow network traffic
- EC2 deployment is commonly used in DevOps workflows

## What is Application Deployment
- Deployment means making an application available for users
- In cloud computing, applications are deployed on virtual servers like EC2
- AWS EC2 provides scalable infrastructure for hosting applications

Deploying applications on EC2 allows developers to host web applications in the cloud without managing physical servers. 

## Steps to Deploy an Application on EC2

### Step 1 - Launch EC2 Instance
- Open AWS Console
- Navigate to EC2 Dashboard
- Launch a new instance
- Select Ubuntu AMI
- Choose instance type (t2.micro for free tier)

### Step 2 - Configure Security Group
Allow these ports:
- Port 22 → SSH access
- Port 80 → HTTP traffic
- Port 3000 → Application access (if required)

### Step 3 - Connect to EC2 Instance
```bash
ssh -i my-key.pem ubuntu@<public-ip>
```
### Step 4 - Update System
```bash
sudo apt update
sudo apt upgrade -y
```

### Step 5 - Install Node.js
```bash
sudo apt install nodejs -y
sudo apt install npm -y
```

### Step 6 - Clone Application Repository
```bash
git clone https://github.com/username/project.git
```

### Step 7 - Install Dependencies
```bash
cd project
npm install
```

### Step 8 - Run Application
```bash
node index.js
```

### Step 9 - Access Application
Open browser
Visit:
```bash
http://<public-ip>:3000
```

### Using PM2 for Background Process
PM2 is used to keep applications running continuously.

Install PM2
```bash
sudo npm install -g pm2
```

Start Application
```bash
pm2 start index.js
```

Check Running Processes
```bash
pm2 list
```

PM2 helps manage Node.js applications in production environments by keeping them alive and restarting on failures.

### Benefits of Deploying on EC2
 - Easy cloud deployment
 - Scalable infrastructure
 - Global accessibility
 - Cost-effective hosting
 - Full control over server configuration

### Real Use Case
A company develops a Node.js backend application:
 - Application is deployed on EC2
 - Users access the service using public IP or domain
 - PM2 keeps the application running continuously
This enables reliable hosting in the cloud.

### Summary
AWS EC2 allows developers to deploy and host applications in the cloud easily. By configuring servers, installing dependencies, and running applications, developers can create scalable and reliable deployment environments.

### My Learning Reflection
Today I learned how to deploy an application on AWS EC2 step by step. I understood how cloud servers are configured and how applications are hosted publicly using EC2 instances.