# Day 11 - Docker Compose

## What I Learned
- Docker Compose is a tool used to define and manage multi-container Docker applications
- It allows running multiple containers using a single configuration file
- It simplifies container orchestration for development and testing
- Instead of running multiple docker commands, we use one YAML file
- It helps in managing services, networks, and volumes easily

## What is Docker Compose
- Docker Compose uses a YAML file (docker-compose.yml)
- It defines services, images, ports, and dependencies
- Allows running multiple containers together with one command

## Why Docker Compose is Needed
- Running multiple containers manually is complex
- Managing dependencies between services becomes difficult
- Docker Compose simplifies this by centralizing configuration

## Basic Structure of docker-compose.yml
```yaml
version: "3"
services:
  web:
    image: nginx
    ports:
      - "8080:80"

```
### Example: Multi-Container Application
version: "3"
services:
  app:
    image: node:18
    working_dir: /app
    volumes:
      - .:/app
    command: node index.js
    ports:
      - "3000:3000"

  redis:
    image: redis

### Common Docker Compose Commands

```bash
## Start Services
docker-compose up

## Run in Background
docker-compose up -d

## Stop Services
docker-compose down

## View Running Services
docker-compose ps

```

### Key Benefits
 - Simplifies multi-container setup
 - Easy configuration using YAML
 - Saves time and reduces manual effort
 - Useful for development and testing environments

### Real Use Case
A web application requires:
 - Backend (Node.js)
 - Database (Redis)

Without Docker Compose:
 - You manually run multiple containers

With Docker Compose:
 - Define everything in one file
 - Run all services with a single command

### Summary
Docker Compose is a powerful tool that helps manage multiple containers using a single configuration file. It simplifies development workflows and improves productivity.

### My Learning Reflection
Today I learned how Docker Compose helps in managing multi-container applications. It makes development easier and reduces the complexity of running multiple services.
