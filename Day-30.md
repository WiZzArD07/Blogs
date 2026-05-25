# Day 30 - Automation Scripts in DevOps

## What I Learned
- Automation scripts are used to automate repetitive tasks in DevOps
- Shell scripts are commonly used for automation in Linux environments
- Automation improves efficiency, consistency, and reliability
- Scripts can automate deployments, backups, monitoring, and server setup
- Automation is a core principle of DevOps

## What is Automation in DevOps
- Automation means using scripts or tools to perform tasks automatically
- It reduces manual intervention and human errors
- DevOps teams use automation for faster and reliable software delivery

Automation is one of the core practices in DevOps and helps streamline development and operations workflows. :contentReference[oaicite:0]{index=0}

## Why Automation is Important
- Saves time
- Reduces manual errors
- Improves consistency
- Speeds up deployment process
- Enhances productivity

Shell scripting is widely used for automating repetitive system administration and deployment tasks. :contentReference[oaicite:1]{index=1}

## Common Automation Tasks
- Server setup
- Application deployment
- Backup creation
- Log monitoring
- Health checks
- Scheduled jobs

## Example 1 - Backup Automation Script
```bash
#!/bin/bash

SOURCE="/home/ubuntu/project"
BACKUP="/home/ubuntu/backup"

mkdir -p $BACKUP

cp -r $SOURCE $BACKUP

echo "Backup completed successfully"
```

### What This Script Does
 - Creates backup directory if it does not exist
 - Copies project files into backup folder
 - Displays success message

### Example 2 - Disk Usage Monitoring Script
```bash
#!/bin/bash

THRESHOLD=80

USAGE=$(df -h / | awk 'NR==2 {print $5}' | sed 's/%//')

if [ $USAGE -gt $THRESHOLD ]
then
    echo "Disk usage is above threshold"
else
    echo "Disk usage is normal"
fi
```
### What This Script Does
 - Checks disk usage percentage
 - Compares usage with threshold
 - Displays alert message if storage is high

### Example 3 - Deployment Automation Script
```bash
#!/bin/bash

echo "Pulling latest code"

git pull origin main

echo "Installing dependencies"

npm install

echo "Starting application"

pm2 restart app
```
### Benefits of Automation Scripts
 - Faster task execution
 - Reliable operations
 - Easy repeatability
 - Reduced operational overhead
 - Better infrastructure management

Shell scripts are frequently integrated into CI/CD pipelines and infrastructure automation workflows.

### Real Use Case
A DevOps engineer manages multiple servers:
 - Uses scripts to automate deployments
 - Monitors disk usage automatically
 - Schedules backups using cron jobs
This reduces manual work and improves system reliability.

### Summary
Automation scripts are an essential part of DevOps practices. They help automate repetitive operational tasks, improve efficiency, and ensure consistent infrastructure and deployment workflows.

### My Learning Reflection
Today I learned how automation scripts simplify DevOps operations. I practiced scripts for backups, monitoring, and deployment automation, which are important for real-world infrastructure management.

