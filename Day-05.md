#  Day 5: Deployment Rollback Runbook (DevOps Blog Series)

##  Introduction

Deployments are exciting… until something breaks in production 😅

A bad release can cause downtime, errors, and unhappy users. That’s why every system should have a **rollback strategy**.

In this blog, I will walk through a **real-world DevOps runbook** to safely roll back a failed deployment.

---

##  Problem Statement

A new deployment caused application errors or downtime in production.

---

##  Possible Causes

* Buggy code release
* Configuration issues
* Dependency conflicts
* Incomplete testing

---

##  Step-by-Step Troubleshooting & Rollback

### 1 Identify Current Deployment Version

```bash id="rb1"
git log --oneline
```

---

### 2 Identify Last Stable Version

* Check previous commit
* Confirm working version from logs/monitoring

---

### 3 Rollback Using Git

```bash id="rb2"
git checkout <previous-commit-id>
```

---

### 4 If Using Docker

```bash id="rb3"
docker ps
docker run <previous-image-tag>
```

---

### 5 If Using Kubernetes

```bash id="rb4"
kubectl rollout undo deployment <app-name>
```

---

### 6 Restart Services

```bash id="rb5"
sudo systemctl restart nginx
```

---

### 7 Verify Application Health

```bash id="rb6"
curl http://server-ip
```

---

### 8 Check Logs for Stability

```bash id="rb7"
journalctl -u nginx
```

---

##  Real Output Example

###  Before Rollback

```bash id="rb8"
HTTP/1.1 500 Internal Server Error
```

---

###  Action Taken

* Reverted to previous stable version
* Restarted services

---

###  After Rollback

```bash id="rb9"
HTTP/1.1 200 OK
```

---

##  Root Cause (Example)

A recent deployment introduced a breaking change in the application configuration.

---

##  Solution Summary

* Identified faulty deployment
* Rolled back to stable version
* Restored application functionality
* Verified system stability

---

##  Key Learnings

* Always keep a rollback plan ready
* Never deploy without testing
* Versioning is critical in production
* Automate rollback in CI/CD pipelines

---

##  What’s Next?

 Moving towards **advanced DevOps projects (CI/CD + Monitoring + Kubernetes)**

---

##  Connect With Me

I am building and sharing my DevOps journey in public 🚀
Follow along for real-world learning!

---
