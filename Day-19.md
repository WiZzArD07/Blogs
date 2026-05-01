# Day 19 - GitHub Actions Deep Dive

## What I Learned
- GitHub Actions is a CI/CD and automation platform integrated with GitHub
- It automates tasks like build, test, and deployment
- Workflows are defined using YAML files
- It runs workflows based on events like push or pull request
- It helps in automating the entire software development lifecycle

## What is GitHub Actions
- GitHub Actions is a CI/CD platform that automates workflows directly inside a repository
- It allows developers to build, test, and deploy code automatically :contentReference[oaicite:0]{index=0}
- Workflows are stored in `.github/workflows/` directory
- It eliminates the need for external CI/CD tools

## Key Components of GitHub Actions

### Workflow
- A workflow is an automated process
- Defined in a YAML file
- Triggered by events

### Events
- Actions that trigger workflows
- Examples:
  - push
  - pull request
  - schedule

### Jobs
- A workflow contains one or more jobs
- Jobs run on virtual machines (runners)
- Can run in parallel or sequentially

### Steps
- Each job contains steps
- Steps execute commands or actions

### Actions
- Reusable units of code
- Can be created or used from GitHub Marketplace

## Workflow Structure Example
```yaml
name: CI Pipeline

on: [push]

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout Code
        uses: actions/checkout@v3

      - name: Run Script
        run: echo "Hello, GitHub Actions"
```
### How GitHub Actions Works
 - Developer pushes code to repository
 - Event triggers workflow
 - Workflow runs jobs on GitHub runners
 - Jobs execute steps like build, test, deploy

Workflows are triggered by events and executed in jobs with multiple steps

### Benefits of GitHub Actions
 - Fully integrated with GitHub
 - Automates repetitive tasks
 - Supports multiple languages and environments
 - Scalable using GitHub-hosted runners
 - Improves development speed and reliability

### Real Use Case
A developer pushes code to GitHub:
 - GitHub Actions triggers a workflow
 - Code is built and tested automatically
 - If tests pass, application is deployed
This ensures fast and reliable software delivery.

### Summary
GitHub Actions is a powerful automation tool that enables CI/CD pipelines directly within GitHub. It simplifies development workflows by automating build, test, and deployment processes.

### My Learning Reflection
Today I learned how GitHub Actions works and its key components like workflows, jobs, and steps. This is essential for implementing CI/CD pipelines in real-world DevOps projects.