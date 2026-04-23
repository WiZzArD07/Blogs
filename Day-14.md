# Day 14 - Kubernetes Deployments

## What I Learned
- A Deployment is a Kubernetes object used to manage applications
- It ensures the desired number of Pods are always running
- Deployments help in scaling, updating, and managing applications
- They provide automation for application lifecycle management
- Deployments are commonly used for stateless applications

## What is a Deployment
- A Deployment is a resource object in Kubernetes
- It manages a set of identical Pods
- It ensures the system always matches the desired state defined by the user
- It automates creation, updating, and deletion of Pods

## Why Deployments are Needed
- Pods are temporary and can fail
- Manual management of Pods is difficult
- Deployments automatically maintain the required number of Pods
- They simplify scaling and updates of applications

## Key Features of Deployments
- Maintains desired number of replicas
- Automatically replaces failed Pods
- Supports rolling updates (update without downtime)
- Allows rollback to previous versions
- Enables easy scaling of applications

## How Deployment Works
- User defines a desired state in a YAML file
- Kubernetes creates Pods based on this configuration
- If a Pod fails, Kubernetes automatically replaces it
- If scaling is needed, Kubernetes adjusts the number of Pods

## Basic Deployment YAML Example
```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: my-app
spec:
  replicas: 2
  selector:
    matchLabels:
      app: my-app
  template:
    metadata:
      labels:
        app: my-app
    spec:
      containers:
      - name: my-container
        image: nginx
        ports:
        - containerPort: 80
```

### Apply Deployment
```bash
kubectl apply -f deployment.yaml
```

### Check Deployment
```bash
kubectl get deployments
kubectl get pods
```
### Scale Deployment
```bash
kubectl scale deployment my-app --replicas=4
```
### Real Use Case
A web application needs to handle high traffic:

 - Deployment ensures multiple instances (Pods) are running
 - If one Pod crashes, a new one is created automatically
 - During updates, new version is deployed without downtime

### Summary
A Kubernetes Deployment manages application Pods and ensures they run in the desired state. It provides features like scaling, self-healing, and rolling updates, making it essential for modern DevOps workflows.

### My Learning Reflection
Today I learned how Deployments manage Pods and automate application lifecycle. This is a key concept for understanding how real-world applications run on Kubernetes.