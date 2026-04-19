# Day 9 - Docker Commands

## What I Learned
- Docker commands are used to manage images and containers
- They help in building, running, stopping, and removing containers
- Understanding commands is essential for working with Docker efficiently
- Containers can be controlled easily using simple CLI commands

## Basic Docker Commands

### Check Docker Version

```bash
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
