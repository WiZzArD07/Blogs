# Day 9 - Docker Commands

## What I Learned
- Docker commands are used to manage images and containers
- They help in building, running, stopping, and removing containers
- Understanding commands is essential for working with Docker efficiently
- Containers can be controlled easily using simple CLI commands

## Basic Docker Commands

```bash
### Check Docker Version
docker --version

### Pull an Image from Docker Hub
 - docker pull nginx

### List Images
 - docker images

### Run a Container
 - docker run -d -p 8080:80 nginx

### List Running Containers
 - docker ps

### List All Containers (including stopped)
 - docker ps -a

### Stop a Container
 - docker stop <container_id>

### Start a Container
 - docker start <container_id>

### Remove a Container
 - docker rm <container_id>

### Remove an Image
 - docker rmi <image_id>

```

### Important Concepts
 - -d runs the container in detached mode
 - -p maps ports between host and container
 - Each container has a unique ID
 - Images are templates used to create containers

### Benefits of Using Commands
 - Full control over container lifecycle
 - Easy debugging and monitoring
 - Efficient management of multiple containers

### Real Use Case
A developer wants to run a web server locally:

 - Pull the nginx image
 - Run it using Docker
 - Access it via browser on localhost
This allows quick setup without installing software manually.

### Summary
Docker commands are essential for managing containers and images. They provide a simple and powerful way to control application environments.

### My Learning Reflection
Today I practiced basic Docker commands and understood how to manage containers. I will learn Dockerfile next to create custom images.