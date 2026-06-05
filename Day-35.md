# Day 35 - Introduction to Helm

## What I Learned
- Helm is a package manager for Kubernetes
- It simplifies the deployment and management of Kubernetes applications
- Helm uses packages called Charts
- Helm helps automate Kubernetes deployments and updates
- It reduces the complexity of managing multiple Kubernetes YAML files

## What is Helm
- Helm is an open-source package manager for Kubernetes
- It allows users to define, install, and upgrade applications on Kubernetes clusters
- Helm packages applications into reusable units called Charts

Helm is often referred to as the package manager for Kubernetes because it simplifies application deployment and lifecycle management.

## Why Helm is Important
- Simplifies Kubernetes deployments
- Reduces repetitive YAML configurations
- Makes application upgrades easier
- Supports versioning and rollback
- Improves consistency across environments

## Key Components of Helm

### Chart
- A Helm package containing Kubernetes resource definitions
- Includes templates, configuration files, and metadata

### Release
- A deployed instance of a Helm Chart
- Multiple releases can be created from the same chart

### Repository
- A collection of Helm Charts
- Similar to package repositories in Linux

### Values File
- Stores configuration values
- Allows customization without modifying templates

## Helm Architecture

### Helm Client
- User interacts with Helm using CLI commands

### Kubernetes Cluster
- Helm deploys resources directly to the cluster

### Chart Repository
- Stores and distributes Helm Charts

## Installing Helm

### Verify Installation
```bash
helm version
```

### Add Helm Repository
```bash
helm repo add bitnami https://charts.bitnami.com/bitnami
```

### Update Repository
```bash
helm repo update
```

### Searching for Charts
Search Repository
```bash
helm search repo nginx
```

### List Repositories
```bash
helm repo list
```

### Installing an Application
Install Nginx Chart
```bash
helm install my-nginx bitnami/nginx
```

### List Releases
```bash
helm list
```

### Upgrading a Release
```bash
helm upgrade my-nginx bitnami/nginx
```

### Rolling Back a Release
```bash
helm rollback my-nginx 1
```

### What Rollback Does
 - Restores a previous version of an application
 - Helps recover from failed deployments

### Uninstalling a Release
```bash
helm uninstall my-nginx
```

### Benefits of Helm
 - Faster application deployment
 - Simplified configuration management
 - Easy upgrades and rollbacks
 - Reusable deployment templates
 - Better Kubernetes application management

### Helm Chart Structure
my-chart/
├── Chart.yaml
├── values.yaml
├── charts/
└── templates/

### Chart.yaml
 - Contains chart metadata

### values.yaml
 - Contains configurable values

### templates/
Contains Kubernetes resource templates

### Real Use Case
A company deploys a microservices application:
 - Each service requires multiple Kubernetes YAML files
 - Helm packages everything into a single Chart
 - Deployment, upgrade, and rollback become much easier
This reduces operational complexity and improves deployment consistency.

### Helm vs Kubernetes YAML
| Helm	                         |  Kubernetes YAML               |
| -----------------------------  |  ----------------------------  |
| Uses reusable templates	     |  Static configuration files    |
| Supports versioning	         |  Manual version management     |
| Easy upgrades and rollbacks	 |  Manual updates                |
| Better scalability	         |  More configuration overhead   |

### Summary
Helm is the package manager for Kubernetes that simplifies application deployment, configuration management, upgrades, and rollbacks. It helps DevOps teams manage Kubernetes applications efficiently using reusable and version-controlled Charts.

### My Learning Reflection
Today I learned how Helm simplifies Kubernetes application management. I explored Charts, Releases, Repositories, and common Helm commands used for deploying and managing applications in Kubernetes environments.