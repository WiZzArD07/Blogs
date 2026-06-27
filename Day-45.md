# Day 45 - Secrets Management in DevSecOps

## What I Learned
- Secrets are sensitive credentials such as passwords, API keys, access tokens, SSH keys, and certificates
- Secrets management is the practice of securely storing, accessing, rotating, and auditing these credentials
- Hardcoding secrets in source code is one of the most common security mistakes
- Modern DevSecOps pipelines use dedicated secrets management tools
- Proper secrets management reduces the risk of credential leaks and unauthorized access

## What is Secrets Management

- Secrets Management is the process of securely handling sensitive information used by applications, infrastructure, and CI/CD pipelines
- Secrets are stored in secure vaults instead of source code or configuration files
- Applications retrieve secrets securely at runtime

Secrets management is a fundamental DevSecOps practice that protects credentials throughout the software development lifecycle. :contentReference[oaicite:0]{index=0}

## Why Secrets Management is Important

- Prevents credential leaks
- Improves application security
- Supports compliance requirements
- Enables secure automation
- Simplifies secret rotation

## What Are Secrets?

Examples include:

- Database passwords
- API keys
- OAuth tokens
- SSH keys
- TLS certificates
- Cloud credentials
- Encryption keys

## Common Mistakes

❌ Hardcoding passwords in source code

```java
String password = "admin123";
```

❌ Storing API keys in Git repositories

❌ Sharing secrets through email or chat

❌ Using the same password across environments

These practices significantly increase the risk of security breaches.

## Secure Approach

Instead of hardcoding:

```python
import os

db_password = os.getenv("DB_PASSWORD")
```

Applications should retrieve secrets securely from a vault or environment variables.

## DevSecOps Secrets Workflow

```text
Developer
      │
      ▼
Git Repository
      │
      ▼
CI/CD Pipeline
      │
      ▼
Secrets Manager
      │
      ▼
Application
      │
      ▼
Cloud Infrastructure
```

Secrets are injected securely during runtime instead of being stored in code. :contentReference[oaicite:1]{index=1}

## Popular Secrets Management Tools

### HashiCorp Vault
- Dynamic secrets
- Secret rotation
- Encryption
- Fine-grained access control

### AWS Secrets Manager
- Secure storage for AWS credentials
- Automatic secret rotation
- IAM integration

### Azure Key Vault
- Stores secrets, certificates, and encryption keys
- Integrates with Azure services

### Google Secret Manager
- Secure storage for GCP applications
- Access control using IAM

### Kubernetes Secrets
- Stores sensitive data for Kubernetes workloads
- Often combined with external vault solutions for production

## Best Practices

### Never Hardcode Secrets
- Store secrets outside application code

### Use Least Privilege
- Grant only the minimum required permissions

### Rotate Secrets Regularly
- Replace credentials periodically
- Automate rotation whenever possible

### Audit Secret Access
- Record every access attempt
- Monitor suspicious activity

### Encrypt Secrets
- Encrypt secrets both at rest and in transit

### Use Centralized Secret Storage
- Avoid scattered credentials
- Manage secrets from a single platform

Industry guidance recommends centralized secret stores, automated rotation, least-privilege access, and continuous auditing. :contentReference[oaicite:2]{index=2}

## Secrets in CI/CD Pipelines

During CI/CD, secrets may be required for:

- Container registry authentication
- Cloud deployment
- Database connections
- Artifact repositories
- Kubernetes deployments

Secrets should be injected securely during pipeline execution instead of being stored in configuration files.

## Benefits of Secrets Management

- Improved security
- Reduced credential exposure
- Easier compliance
- Secure automation
- Better auditability

## Real Use Case

A company deploys applications using GitHub Actions.

Without Secrets Management:
- AWS credentials are stored in the repository.
- Credentials are accidentally exposed.

With Secrets Management:
- Credentials are stored in AWS Secrets Manager.
- GitHub Actions retrieves them securely during deployment.
- Secrets are rotated automatically.

This significantly reduces the risk of credential leakage.

## Challenges

- Managing secrets across multiple environments
- Secret rotation at scale
- Access control complexity
- Developer awareness
- Integration with legacy applications

## Summary

Secrets Management is a critical component of DevSecOps that protects sensitive credentials throughout the software development lifecycle. By using dedicated secrets management platforms, automating secret rotation, and following security best practices, organizations can build secure and reliable CI/CD pipelines. :contentReference[oaicite:3]{index=3}

## My Learning Reflection

Today I learned how Secrets Management secures credentials used in applications, infrastructure, and CI/CD pipelines. I explored common security mistakes, industry best practices, popular tools like HashiCorp Vault and AWS Secrets Manager, and how secure secret handling strengthens DevSecOps workflows.