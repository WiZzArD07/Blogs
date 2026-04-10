#  Day 2: Server Down Runbook (DevOps Blog Series)

##  Introduction

In production environments, server downtime is one of the most critical issues that can impact users and business operations.

In this blog, I will walk through a **real-world DevOps runbook** to troubleshoot and recover a server when it goes down.

---

##  Problem Statement

The production server is not responding and the application is unavailable.

---

## 🔍 Possible Causes

* Service crash (e.g., Nginx/Apache stopped)
* High CPU or memory usage
* Disk space full
* Network connectivity issues

---

##  Step-by-Step Troubleshooting

### 1️⃣ Check Server Reachability

```bash
ping <server-ip>
```

 If ping fails, there may be a network issue.

---

### 2️⃣ Connect to Server via SSH

```bash
ssh user@server-ip
```

---

### 3️⃣ Check Service Status

```bash
systemctl status nginx
```

---

### 4️⃣ Restart the Service

```bash
sudo systemctl restart nginx
```

---

### 5️⃣ Check Logs for Errors

```bash
journalctl -u nginx
```

---

### 6️⃣ Verify Application

```bash
curl http://server-ip
```

---

## 📸 Real Output Example

```bash
curl http://server-ip
```

Output before fix:

```bash
curl: (7) Failed to connect to server
```

Output after fix:

```bash
HTTP/1.1 200 OK
```

---

##  Root Cause (Example)

The Nginx service had crashed due to high memory usage.

---

##  Solution Summary

* Identified server issue
* Restarted failed service
* Verified logs and response

---

##  Key Learnings

* Always check connectivity first
* Logs are the most important debugging tool
* Automating recovery steps can save time

---

##  Next Blog (Day 3)

 High CPU Usage Runbook

---

##  Connect With Me

I am building in public and sharing my DevOps journey daily 🚀
Stay tuned for more runbooks!

---
