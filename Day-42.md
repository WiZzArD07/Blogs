# Day 42 - Argo CD Fundamentals

## What I Learned
- Argo CD is a GitOps continuous delivery tool for Kubernetes
- It automatically deploys applications from Git repositories
- Argo CD ensures the Kubernetes cluster matches the desired state stored in Git
- It provides visibility into deployments and application health
- Argo CD is one of the most popular GitOps tools in cloud-native environments

## What is Argo CD
- Argo CD is a declarative GitOps continuous delivery tool for Kubernetes
- It monitors Git repositories containing Kubernetes manifests
- It automatically synchronizes cluster state with Git configurations

Argo CD follows GitOps principles by using Git as the source of truth for Kubernetes deployments.

## Why Argo CD is Important
- Automates Kubernetes deployments
- Reduces manual configuration changes
- Improves deployment reliability
- Provides deployment visibility
- Enables easy rollback through Git

## Key Features of Argo CD

### GitOps-Based Deployments
- Git repositories act as the source of truth

### Automatic Synchronization
- Keeps cluster state aligned with Git

### Rollback Support
- Revert changes using Git history

### Application Health Monitoring
- Tracks deployment status and health

### Multi-Cluster Support
- Manages multiple Kubernetes clusters

## How Argo CD Works
1. Developer updates configuration in Git
2. Changes are pushed to repository
3. Argo CD detects changes
4. Argo CD synchronizes cluster state
5. Application is updated automatically

## Argo CD Architecture

### Git Repository
- Stores Kubernetes manifests and Helm charts

### Argo CD API Server
- Provides UI and API access

### Repository Server
- Fetches manifests from Git

### Application Controller
- Monitors cluster state
- Performs synchronization

### Kubernetes Cluster
- Runs deployed applications

## Installing Argo CD

### Create Namespace
```bash
kubectl create namespace argocd
```

### Install Argo CD
```bash id="u0z2jv"
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
```

### Verify Installation
```bash id="lyms3k"
kubectl get pods -n argocd
```

## Access Argo CD UI

### Port Forward Service
```bash id="x3j6jb"
kubectl port-forward svc/argocd-server -n argocd 8080:443
```

### Open Browser
```text
https://localhost:8080
```

## Creating an Application
Example Application Manifest:

```yaml
apiVersion: argoproj.io/v1alpha1
kind: Application

metadata:
  name: demo-app

spec:
  destination:
    namespace: default
    server: https://kubernetes.default.svc

  source:
    repoURL: https://github.com/example/repo
    path: manifests
    targetRevision: HEAD

  project: default

  syncPolicy:
    automated: {}
```

## Synchronization Modes

### Manual Sync
- User triggers deployment manually

### Automatic Sync
- Argo CD deploys changes automatically

## Benefits of Automatic Sync
- Faster deployments
- Reduced operational overhead
- Improved consistency
- Lower risk of configuration drift

## Application Health States

### Healthy
- Application running correctly

### Progressing
- Deployment is ongoing

### Degraded
- Application issues detected

### Missing
- Resource not found

## Benefits of Argo CD
- Git-based deployment workflow
- Easy rollback capabilities
- Kubernetes-native architecture
- Improved deployment visibility
- Strong GitOps support

## Argo CD vs Traditional CI/CD
| Argo CD | Traditional CI/CD |
|----------|------------------|
| Git is source of truth | Pipelines push directly to clusters |
| Continuous reconciliation | Deployment occurs during pipeline execution |
| Detects configuration drift | Limited drift detection |
| Kubernetes focused | General-purpose deployment |
| Strong GitOps support | Traditional deployment model |

## Real Use Case
A company manages multiple Kubernetes environments:

Without Argo CD:
- Engineers manually deploy applications
- Environment drift occurs

With Argo CD:
- Configurations are stored in Git
- Argo CD continuously synchronizes clusters
- Deployments become automated and reliable

This improves consistency and reduces deployment errors.

## Best Practices
- Store manifests in Git repositories
- Use automated synchronization carefully
- Organize applications by projects
- Monitor application health regularly
- Protect Git repositories with access controls

## Summary
Argo CD is a powerful GitOps continuous delivery tool for Kubernetes. By using Git as the source of truth and continuously synchronizing cluster state, Argo CD improves deployment reliability, visibility, and operational efficiency.

## My Learning Reflection
Today I learned how Argo CD enables GitOps-based deployments for Kubernetes. I explored its architecture, synchronization process, application management, and real-world benefits that help DevOps teams automate cloud-native deployments efficiently.