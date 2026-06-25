# Day 44 - Introduction to DevSecOps

## What I Learned
- DevSecOps stands for Development, Security, and Operations
- It integrates security into every phase of the Software Development Life Cycle (SDLC)
- Security becomes a shared responsibility among developers, security teams, and operations teams
- DevSecOps automates security testing within CI/CD pipelines
- The goal is to identify and fix vulnerabilities as early as possible

## What is DevSecOps

- DevSecOps is the practice of embedding security into the DevOps lifecycle rather than treating it as a separate phase
- It combines development, operations, and security into a single collaborative workflow
- Security checks are automated throughout the CI/CD pipeline

DevSecOps integrates security into every stage of software development by making it a shared responsibility and automating security testing throughout the delivery pipeline. 

## Why DevSecOps is Important

- Detects vulnerabilities early
- Reduces security risks
- Speeds up secure software delivery
- Improves collaboration between teams
- Supports regulatory compliance

## DevOps vs DevSecOps

| DevOps | DevSecOps |
|---------|------------|
| Focuses on speed and automation | Focuses on speed with built-in security |
| Security often performed later | Security integrated from the beginning |
| Manual security reviews | Automated security testing |
| Separate security team | Shared security responsibility |

## Shift Left Security

One of the main principles of DevSecOps is **Shift Left Security**.

This means:
- Perform security checks during development
- Detect vulnerabilities before deployment
- Fix issues when they are cheaper and easier to resolve

The OWASP DevSecOps Guideline promotes shift-left security to detect vulnerabilities as early as possible in the development lifecycle.
## DevSecOps Lifecycle

1. Plan
2. Develop
3. Build
4. Test
5. Release
6. Deploy
7. Monitor
8. Improve

Security is integrated into every stage instead of being added only before production.

## Security Testing in DevSecOps

### SAST (Static Application Security Testing)
- Scans source code for vulnerabilities
- Performed during development

### DAST (Dynamic Application Security Testing)
- Tests running applications
- Finds runtime vulnerabilities

### SCA (Software Composition Analysis)
- Detects vulnerable third-party libraries
- Identifies outdated dependencies

### IaC Scanning
- Scans Infrastructure as Code
- Detects cloud and Kubernetes misconfigurations

OWASP recommends integrating SAST, DAST, SCA, IaC scanning, and compliance checks into secure DevSecOps pipelines. :contentReference[oaicite:2]{index=2}

## Common DevSecOps Tools

| Category | Examples |
|----------|----------|
| Source Control | Git, GitHub |
| CI/CD | Jenkins, GitHub Actions, GitLab CI |
| SAST | SonarQube, Semgrep |
| DAST | OWASP ZAP |
| Dependency Scanning | Snyk, Trivy |
| Container Security | Trivy, Clair |
| Infrastructure Scanning | Checkov, tfsec |
| Monitoring | Prometheus, Grafana |

## Example DevSecOps Pipeline

```text
Developer
     │
     ▼
Git Push
     │
     ▼
CI Pipeline
     │
     ├── Code Build
     ├── Unit Tests
     ├── SAST Scan
     ├── Dependency Scan
     ├── IaC Scan
     ├── Container Scan
     ▼
Deploy
     ▼
DAST Scan
     ▼
Production
     ▼
Continuous Monitoring
```

## Benefits of DevSecOps

- Early vulnerability detection
- Secure software delivery
- Reduced remediation costs
- Faster deployments
- Better compliance
- Stronger collaboration
- Improved software quality

## Challenges of DevSecOps

- Cultural change across teams
- Learning new security tools
- Managing false positives
- Integrating security into existing pipelines
- Continuous monitoring requirements

## Real Use Case

A company develops an online banking application.

Without DevSecOps:
- Security testing occurs just before release.
- Critical vulnerabilities delay deployment.

With DevSecOps:
- Code is scanned during every commit.
- Dependencies are automatically checked.
- Container images are scanned before deployment.
- Security issues are fixed before production.

This results in faster releases with fewer vulnerabilities.

## DevSecOps Best Practices

- Adopt Shift Left Security
- Automate security testing
- Scan container images regularly
- Use least privilege access
- Monitor applications continuously
- Keep dependencies updated
- Secure Infrastructure as Code
- Perform regular security audits

## Summary

DevSecOps extends DevOps by integrating security into every phase of software development. Through automation, continuous monitoring, and shared responsibility, organizations can deliver secure applications faster while reducing security risks and maintaining compliance.

## My Learning Reflection

Today I learned how DevSecOps integrates security into the DevOps lifecycle. I explored concepts like Shift Left Security, automated security testing, secure CI/CD pipelines, and common DevSecOps tools that help organizations build and deploy secure software efficiently.