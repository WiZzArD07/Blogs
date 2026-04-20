# Day 6 - Dockerfile

## What I Learned
- A Dockerfile is a script used to create Docker images
- It contains a set of instructions to build an application environment
- It automates the process of setting up dependencies and running the application
- Dockerfile helps ensure consistency across different environments

## What is a Dockerfile
- A text file with instructions to build a Docker image
- Defines base image, dependencies, and commands to run the application
- Used with `docker build` to create images

## Common Dockerfile Instructions

```bash
### FROM
### Specifies the base image
FROM node:18

## WORKDIR
### Sets the working directory inside the container
WORKDIR /app

## COPY
### Copies files from local system to container
COPY . .

## RUN
### Executes commands during image build
RUN npm install

## CMD
### Defines default command to run the container
CMD ["node", "index.js"]

## Example Dockerfile
FROM node:18
WORKDIR /app
COPY . .
RUN npm install
CMD ["node", "index.js"]

### Build Docker Image
docker build -t my-app .

### Run Docker Container
docker run -p 3000:3000 my-app

```
### Benefits of Dockerfile
 - Automates environment setup
 - Ensures consistency across systems
 - Easy to share and reuse
 - Simplifies deployment process

### Real Use Case
A developer wants to deploy a Node.js application:

 - Writes a Dockerfile defining environment and dependencies
 - Builds an image using Dockerfile
 - Runs the container on any system without configuration issues

### Summary
Dockerfile is used to automate the creation of Docker images. It defines how an application is packaged and executed inside a container.

### My Learning Reflection
Today I learned how Dockerfile works and how it helps automate application setup. I will explore Docker Compose next.

