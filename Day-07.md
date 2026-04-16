# Day 7 - CI/CD Basics

## What I Learned

- CI/CD stands for Continuous Integration and Continuous Deployment/Delivery
- It is a core practice in DevOps to automate software development workflows
- CI ensures code is integrated and tested frequently
- CD ensures code is automatically deployed to production or staging
- It reduces manual work and improves software quality

## Continuous Integration (CI)

- Developers regularly push code to a shared repository
- Each commit triggers an automated build and test process
- Helps detect bugs early
- Ensures code consistency

## Continuous Delivery (CD)

- Code changes are automatically prepared for release
- Deployment to production requires manual approval
- Ensures software is always in a deployable state

## Continuous Deployment (CD)

- Code is automatically deployed to production without manual intervention
- Requires strong testing and monitoring
- Enables very fast releases

## CI/CD Pipeline Stages

- Source Code (GitHub)
- Build (Compile application)
- Test (Run automated tests)
- Deploy (Release to server or cloud)
- Monitor (Track performance and errors)

## Benefits of CI/CD

- Faster development and release cycles
- Early bug detection
- Reduced manual errors
- Improved collaboration
- Reliable and consistent deployments

## Common Tools

- Version Control: Git
- CI/CD: GitHub Actions
- Build Tools: Maven, Gradle
- Containerization: Docker
- Orchestration: Kubernetes

## Real Use Case

A developer pushes code to GitHub. This triggers a CI/CD pipeline:

- The application is built automatically
- Tests are executed
- If tests pass, the application is deployed

This process reduces manual effort and ensures faster delivery.

## Summary

CI/CD automates the process of integrating, testing, and deploying code. It is a key DevOps practice that improves speed, quality, and reliability of software delivery.

## My Learning Reflection

Today I learned how CI/CD pipelines work and how they automate the development process. I will explore GitHub Actions in more detail in upcoming days.
