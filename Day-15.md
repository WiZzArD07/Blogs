# Day 15 - Kubernetes Services

## What I Learned
- A Service in Kubernetes is used to expose applications running in Pods
- It provides a stable network endpoint to access Pods
- Services enable communication between different components of an application
- They provide load balancing across multiple Pods
- Services solve the problem of changing Pod IP addresses

## What is a Kubernetes Service
- A Service is an abstraction that defines a logical set of Pods and a way to access them
- It provides a stable IP address and DNS name
- Even if Pods are created or destroyed, the Service remains constant

## Why Services are Needed
- Pods are temporary and their IP addresses change frequently
- Direct communication with Pods is unreliable
- Services provide a stable endpoint for accessing Pods
- They simplify communication between application components 

## Key Features of Services
- Stable IP address and DNS name
- Load balancing across Pods
- Service discovery within the cluster
- Decouples Pods from clients

## Types of Kubernetes Services

### ClusterIP
- Default service type
- Accessible only inside the cluster

### NodePort
- Exposes service on a specific port of each node
- Accessible from outside the cluster using node IP

### LoadBalancer
- Exposes service externally using a cloud provider load balancer

### ExternalName
- Maps service to an external DNS name

## How Service Works
- Service selects Pods using labels
- Traffic is routed to one of the matching Pods
- Load balancing is automatically handled by Kubernetes
- Clients communicate with the Service instead of individual Pods
## Basic Service YAML Example
```yaml
apiVersion: v1
kind: Service
metadata:
  name: my-app-service
spec:
  selector:
    app: my-app
  ports:
    - protocol: TCP
      port: 80
      targetPort: 80
  type: NodePort
```

### Apply Service
kubectl apply -f service.yaml

### Check Services
kubectl get services

### Real Use Case
A web application has multiple backend Pods:
 - A Service exposes all backend Pods under one endpoint
 - Users access the Service instead of individual Pods
 - Traffic is distributed automatically across Pods

### Summary
Kubernetes Services provide a stable and reliable way to access applications running in Pods. They enable communication, load balancing, and service discovery, making them essential for scalable applications.

### My Learning Reflection
Today I learned how Kubernetes Services expose applications and ensure reliable communication between Pods. This completes the core understanding of Pods, Deployments, and Services.