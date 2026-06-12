# Day 40 - Jenkins Fundamentals

## What I Learned
- Jenkins is an open-source automation server used for Continuous Integration and Continuous Delivery (CI/CD)
- It automates building, testing, and deploying applications
- Jenkins helps developers detect issues early in the development cycle
- It supports hundreds of plugins for integration with various tools
- Jenkins is widely used in DevOps pipelines

## What is Jenkins

- Jenkins is an automation server that helps automate software development workflows
- It enables Continuous Integration (CI) and Continuous Delivery (CD)
- Jenkins can automate tasks such as building code, running tests, and deploying applications

Jenkins is one of the most widely used automation servers for implementing CI/CD pipelines in software development and DevOps environments.

## Why Jenkins is Important

- Automates repetitive tasks
- Improves software quality
- Reduces manual errors
- Speeds up software delivery
- Supports DevOps practices

## Key Features of Jenkins

### Open Source
- Free to use
- Large community support

### Plugin Ecosystem
- Supports over a thousand plugins
- Integrates with Git, Docker, Kubernetes, AWS, and more

### Continuous Integration
- Automatically builds and tests code after changes

### Continuous Delivery
- Automates deployment workflows

### Distributed Builds
- Supports master-agent architecture
- Enables workload distribution

## Jenkins Architecture

### Jenkins Controller (Master)
- Manages jobs and configurations
- Schedules builds

### Jenkins Agent (Node)
- Executes build tasks
- Can run on multiple machines

### Jobs
- Tasks configured in Jenkins
- Examples:
  - Build applications
  - Run tests
  - Deploy software

## Installing Jenkins on Ubuntu

### Update Packages
```bash
sudo apt update
````

### Install Java

```bash
sudo apt install openjdk-17-jdk -y
```

### Verify Java

```bash
java -version
```

### Install Jenkins

```bash
sudo apt install jenkins -y
```

### Start Jenkins

```bash
sudo systemctl start jenkins
sudo systemctl enable jenkins
```

### Check Jenkins Status

```bash
sudo systemctl status jenkins
```

## Access Jenkins Dashboard

Open browser:

```text
http://<server-ip>:8080
```

Default Jenkins port:

```text
8080
```

## Jenkins Pipeline

A Jenkins Pipeline defines the automation workflow as code.

### Example Pipeline

```groovy
pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building Application'
            }
        }

        stage('Test') {
            steps {
                echo 'Running Tests'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying Application'
            }
        }
    }
}
```

## Pipeline Stages

### Build

* Compiles application code

### Test

* Runs automated tests

### Deploy

* Deploys application to target environment

## Common Jenkins Integrations

### GitHub

* Source code management

### Docker

* Containerized application deployment

### Kubernetes

* Container orchestration

### AWS

* Cloud deployments

### SonarQube

* Code quality analysis

## Benefits of Jenkins

* Automates CI/CD pipelines
* Improves deployment speed
* Supports infrastructure automation
* Large plugin ecosystem
* Easy integration with DevOps tools

## Real Use Case

A developer pushes code to GitHub:

1. GitHub webhook triggers Jenkins
2. Jenkins pulls latest code
3. Build process starts
4. Automated tests run
5. Application is deployed

This creates a fully automated CI/CD workflow.

## Jenkins vs GitHub Actions

| Jenkins                                | GitHub Actions                    |
| -------------------------------------- | --------------------------------- |
| Self-hosted automation server          | GitHub-native automation          |
| Extensive plugin ecosystem             | Built into GitHub                 |
| More setup and maintenance             | Easier to start                   |
| Highly customizable                    | Simpler workflows                 |
| Suitable for complex enterprise setups | Excellent for GitHub repositories |

## Summary

Jenkins is a powerful automation server that enables Continuous Integration and Continuous Delivery. It automates software development workflows, integrates with numerous DevOps tools, and helps teams deliver software faster and more reliably.

## My Learning Reflection

Today I learned the fundamentals of Jenkins and how it enables CI/CD automation. I explored Jenkins architecture, pipelines, installation, and integrations that make it one of the most important tools in the DevOps ecosystem.

