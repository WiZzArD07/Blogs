# Day 13 - Kubernetes Pods and Nodes

## What I Learned
- Pods and Nodes are the core building blocks of Kubernetes
- A Pod is the smallest deployable unit in Kubernetes
- A Node is a machine that runs Pods
- Pods contain one or more containers
- Nodes provide resources like CPU, memory, and storage

## What is a Pod
- A Pod is the smallest unit in Kubernetes
- It can contain one or more containers
- Containers inside a Pod share network and storage
- Pods are used to run applications

## What is a Node
- A Node is a physical or virtual machine in a Kubernetes cluster
- It is responsible for running Pods
- Each Node is managed by the Kubernetes control plane
- Nodes provide resources required by Pods

## Relationship Between Pods and Nodes
- Pods always run on Nodes
- A Node can run multiple Pods
- Kubernetes automatically schedules Pods on Nodes based on available resources
- Pods cannot exist without Nodes

## Key Differences

| Aspect        | Pod                                | Node                                 |
|--------------|------------------------------------|--------------------------------------|
| Definition    | Smallest deployable unit           | Machine that runs Pods               |
| Role          | Runs application containers        | Provides infrastructure              |
| Level         | Application level                  | Infrastructure level                 |
| Composition   | One or more containers             | CPU, memory, storage resources       |
| Dependency    | Runs on Nodes                      | Hosts Pods                           |

## How Kubernetes Manages Them
- Kubernetes scheduler assigns Pods to Nodes
- It checks available resources before scheduling
- If a Pod fails, Kubernetes creates a new one
- If a Node fails, Pods are moved to another Node

## Basic Commands
```bash
kubectl get nodes
kubectl get pods
kubectl describe pod <pod_name>
kubectl describe node <node_name>
```

### Real Use Case
In a web application:
 - Multiple Pods run different services (backend, frontend)
 - These Pods are distributed across multiple Nodes
 - If one Node fails, Kubernetes moves Pods to another Node automatically

### Summary
Pods and Nodes are fundamental components of Kubernetes. Pods run applications, while Nodes provide the infrastructure to run them. Kubernetes efficiently manages their interaction to ensure reliability and scalability.

### My Learning Reflection
Today I understood the relationship between Pods and Nodes and how Kubernetes manages application deployment. This concept is important for understanding Kubernetes architecture.