# Day 8 - Introduction to Docker

## What I Learned
- Docker is a containerization platform used to package applications with their dependencies
- It ensures consistency across different environments (development, testing, production)
- Containers are lightweight and faster compared to virtual machines
- Docker helps in easy deployment and scaling of applications
- It is widely used in DevOps for building and shipping software

## What is a Container
- A container is a lightweight, standalone package of software
- It includes code, runtime, libraries, and dependencies
- Runs consistently across different environments

## Docker vs Virtual Machines

| Feature           | Docker (Containers)        | Virtual Machines            |
|------------------|--------------------------|-----------------------------|
| Size             | Lightweight              | Heavy                       |
| Startup Time     | Fast                     | Slow                        |
| Resource Usage   | Low                      | High                        |
| OS Requirement   | Shared OS                | Separate OS per VM          |

## Key Docker Components
- Docker Engine: Runs and manages containers
- Docker Image: Blueprint of an application
- Docker Container: Running instance of an image
- Docker Hub: Repository for storing images

## Basic Docker Workflow
- Create a Dockerfile
- Build an image
- Run a container

## Basic Commands
```bash
docker --version
docker pull nginx
docker images
docker run -d -p 8080:80 nginx
docker ps
```
### Benefits of Docker
 - Consistent environments
 - Faster deployment
 - Easy scaling
 - Isolation of applications
 - Efficient resource usage

### Real Use Case
A developer builds an application on their local machine. Without Docker, it may fail on another system due to missing dependencies.

With Docker:

 - The application is packaged into an image
 - The same image runs on any system without issues

### Summary
Docker is a powerful containerization tool that helps developers package applications with dependencies, ensuring consistency and faster deployment across environments.

### My Learning Reflection
Today I learned the basics of Docker and how containers differ from virtual machines. I will explore Docker commands and Dockerfile in the next steps.