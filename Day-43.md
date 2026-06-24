# Day 43 - Kubernetes Security Basics

## What I Learned
- Kubernetes security involves protecting clusters, applications, and data from unauthorized access
- Security should be implemented at every layer of the Kubernetes environment
- Authentication and authorization control access to cluster resources
- Network policies help secure communication between Pods
- Security is a shared responsibility between administrators and developers

## What is Kubernetes Security

- Kubernetes security is the practice of protecting Kubernetes clusters, workloads, and infrastructure
- It includes securing containers, APIs, networking, secrets, and access control
- Strong security measures help prevent attacks and data breaches

Kubernetes security focuses on securing cluster components, workloads, networking, and access controls to protect cloud-native applications.

## Why Kubernetes Security is Important

- Prevents unauthorized access
- Protects sensitive data
- Reduces security vulnerabilities
- Ensures compliance requirements
- Improves application reliability

## The Four Layers of Kubernetes Security

### Cloud Infrastructure Layer
- Secures underlying cloud resources
- Includes virtual machines and networking

### Cluster Layer
- Protects Kubernetes control plane and worker nodes

### Container Layer
- Secures container images and runtimes

### Application Layer
- Protects application code and APIs

## Authentication in Kubernetes

Authentication verifies user identity before granting access.

Common authentication methods:

- Client certificates
- Service accounts
- OpenID Connect (OIDC)
- External identity providers

## Authorization in Kubernetes

Authorization determines what actions a user can perform.

Kubernetes uses:

### RBAC (Role-Based Access Control)

- Most common authorization method
- Assigns permissions based on roles

Example:

```yaml
apiVersion: rbac.authorization.k8s.io/v1
kind: Role

metadata:
  namespace: default
  name: pod-reader

rules:
- apiGroups: [""]
  resources: ["pods"]
  verbs: ["get", "list"]
```

## What is RBAC

RBAC allows administrators to:

- Define permissions
- Assign roles to users
- Restrict access to resources

RBAC is the recommended authorization mechanism for controlling access within Kubernetes clusters.

## Network Policies

Network Policies control Pod-to-Pod communication.

Benefits:

- Restrict unnecessary traffic
- Improve security
- Reduce attack surface

Example:

```yaml id="z6w2fk"
apiVersion: networking.k8s.io/v1
kind: NetworkPolicy

metadata:
  name: deny-all

spec:
  podSelector: {}
  policyTypes:
  - Ingress
```

## Kubernetes Secrets

Secrets store sensitive information such as:

- Passwords
- API Keys
- Database Credentials
- Tokens

Create a Secret:

```bash
kubectl create secret generic db-secret \
--from-literal=password=MyPassword123
```

View Secrets:

```bash id="h8t9xa"
kubectl get secrets
```

## Pod Security

Best practices:

- Avoid running containers as root
- Use read-only file systems when possible
- Define resource limits
- Use trusted container images

## Image Security

Container images should:

- Be scanned for vulnerabilities
- Come from trusted registries
- Be updated regularly
- Use minimal base images

Popular image scanning tools:

- Trivy
- Clair
- Snyk

## Security Context Example

```yaml id="b2f6pq"
securityContext:
  runAsNonRoot: true
  readOnlyRootFilesystem: true
```

## Kubernetes Security Best Practices

### Enable RBAC
- Restrict user permissions

### Use Network Policies
- Control traffic between Pods

### Protect Secrets
- Avoid storing secrets in code

### Regularly Update Clusters
- Patch security vulnerabilities

### Scan Container Images
- Detect known vulnerabilities

### Enable Audit Logging
- Track cluster activity

## Common Security Risks

### Privileged Containers
- Can access host resources

### Exposed Dashboards
- May allow unauthorized access

### Weak Access Controls
- Increase security risks

### Unpatched Components
- Vulnerable to exploits

## Real Use Case

A company deploys applications on Kubernetes:

Without security controls:
- Developers receive excessive permissions
- Secrets are stored in configuration files

With proper Kubernetes security:
- RBAC limits permissions
- Secrets are managed securely
- Network policies restrict communication

This reduces security risks and improves compliance.

## Kubernetes Security Tools

### Falco
- Runtime security monitoring

### Trivy
- Container vulnerability scanning

### kube-bench
- CIS Kubernetes benchmark checks

### Kyverno
- Kubernetes policy management

## Summary

Kubernetes security is essential for protecting cloud-native applications and infrastructure. By implementing RBAC, network policies, secret management, image scanning, and security best practices, organizations can build secure and resilient Kubernetes environments.

## My Learning Reflection

Today I learned the fundamentals of Kubernetes security. I explored authentication, authorization, RBAC, network policies, secrets management, and security best practices that help protect modern Kubernetes workloads and infrastructure.