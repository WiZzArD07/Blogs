# Day 29 - Shell Scripting Basics

## What I Learned
- Shell scripting is used to automate repetitive tasks in Linux systems
- A shell script is a file containing Linux commands executed sequentially
- Shell scripting is widely used in DevOps for automation and server management
- Bash is the most commonly used shell in Linux
- Scripts help save time and reduce manual errors

## What is Shell Scripting
- Shell scripting is writing a series of commands in a file to automate tasks
- Scripts are executed by the shell interpreter
- Bash (Bourne Again Shell) is the default shell in many Linux systems

Shell scripting helps automate system administration and repetitive command-line tasks in Linux environments. 

## Why Shell Scripting is Important
- Automates repetitive tasks
- Simplifies server management
- Reduces human errors
- Saves development and deployment time
- Commonly used in DevOps pipelines

## Structure of a Shell Script

### Example Script
```bash
#!/bin/bash

echo "Hello, World"
```

### Explanation
 - #!/bin/bash
    - Called shebang
    - Specifies script should run using Bash shell
 - echo
    - Prints output to terminal

### Steps to Run a Shell Script
Step 1 - Create Script File
```bash
touch script.sh
```

Step 2 - Add Execute Permission
```bash
chmod +x script.sh
```

Step 3 - Run Script
```bash
./script.sh
```

### Variables in Shell Script
```bash
#!/bin/bash

name="DevOps"

echo "Welcome to $name"
```

### User Input Example
```bash
#!/bin/bash

echo "Enter your name:"
read name

echo "Hello $name"
```

### Conditional Statements
```bash
#!/bin/bash

num=10

if [ $num -gt 5 ]
then
    echo "Number is greater than 5"
fi
```

### Loop Example
```bash
#!/bin/bash

for i in 1 2 3 4 5
do
    echo $i
done
```

### Common Use Cases
 - Automating deployments
 - Monitoring servers
 - Backup automation
 - Managing logs
 - Running scheduled tasks

Shell scripts are commonly used for automation in system administration and DevOps workflows.

### Advantages of Shell Scripting
 - Easy automation
 - Faster task execution
 - Minimal resource usage
 - Works well with Linux tools
 - Useful for DevOps and cloud operations

### Real Use Case
A DevOps engineer needs daily backups:
 - Creates a shell script for backup
 - Schedules script using cron jobs
 - Backup process runs automatically every day
This reduces manual work and improves reliability.

### Summary
Shell scripting is a powerful automation tool in Linux environments. It helps automate repetitive tasks, manage servers, and improve operational efficiency in DevOps workflows.

### My Learning Reflection
Today I learned the basics of shell scripting and how scripts automate Linux tasks. I practiced variables, conditions, loops, and script execution which are essential for DevOps automation.