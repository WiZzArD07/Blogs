# Day 20 - CI/CD Pipeline Practical Example

## What I Learned
- A CI/CD pipeline is a sequence of automated steps that build, test, and deploy code
- It starts when code is pushed to a repository
- Automation reduces manual effort and errors
- Pipelines ensure faster and reliable software delivery
- GitHub Actions can be used to create real CI/CD pipelines

## What is a CI/CD Pipeline
- A CI/CD pipeline is an automated workflow that takes code from development to production
- It includes stages like build, test, and deploy
- Each stage runs automatically after a code change

CI/CD pipelines automate build, testing, and deployment processes, making delivery faster and more reliable.

## Pipeline Flow (Step by Step)
1. Developer writes code
2. Code is pushed to GitHub
3. Pipeline is triggered automatically
4. Application is built
5. Tests are executed
6. Code is deployed

## Practical Example Using GitHub Actions

### Step 1: Create Workflow File
Create file:

.github/workflows/ci-cd.yml

### Step 2: Add Pipeline Code
```yaml
name: CI/CD Pipeline

on:
  push:
    branches: [ "main" ]

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
    - name: Checkout Code
      uses: actions/checkout@v3

    - name: Setup Node.js
      uses: actions/setup-node@v3
      with:
        node-version: "18"

    - name: Install Dependencies
      run: npm install

    - name: Run Tests
      run: npm test

    - name: Build Application
      run: npm run build

    - name: Deploy (Example)
      run: echo "Deploying application..."
```

### How This Pipeline Works
 - When code is pushed → workflow starts
 - Code is fetched from repository
 - Dependencies are installed
 - Tests are executed automatically
 - Application is built
 - Deployment step runs

GitHub Actions allows automation of build, test, and deployment workflows directly from a repository

### Key Pipeline Stages
Build
 - Compiles application
 - Prepares code for testing
Test
 - Runs automated tests
 - Ensures code quality
Deploy
 - Moves application to server or cloud
 - Can be automatic or manual
Benefits of This Pipeline
 - Faster development cycles
 - Early bug detection
 - Reduced manual work
 - Reliable deployments
 - Continuous feedback to developers

### Real Use Case
A developer pushes code to GitHub:
 - CI/CD pipeline runs automatically
 - Tests verify code quality
 - If successful, application is deployed

This ensures quick and reliable updates without manual effort.

### Summary
A CI/CD pipeline automates the entire process of building, testing, and deploying applications. Using GitHub Actions, developers can create powerful pipelines that improve speed, reliability, and efficiency.

### My Learning Reflection
Today I built a practical CI/CD pipeline using GitHub Actions. This is one of the most important DevOps concepts and is widely used in real-world projects.