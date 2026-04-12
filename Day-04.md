#  Day 4: Disk Full Issue Runbook (DevOps Blog Series)

##  Introduction

Disk space issues are silent killers in production systems. When a server runs out of disk space, applications can crash, logs stop writing, and deployments fail.

In this blog, I will walk through a **real-world DevOps runbook** to troubleshoot and fix disk full issues.

---

##  Problem Statement

Server disk usage has reached 100%, causing application failures and system instability.

---

##  Possible Causes

* Large log files not rotated
* Unused Docker images and containers
* Temporary files accumulation
* Backup files not cleaned

---

##  Step-by-Step Troubleshooting

### 1️ Check Disk Usage

```bash id="disk1"
df -h
```

---

### 2️ Identify Large Files & Directories

```bash id="disk2"
du -ah / | sort -rh | head -20
```

---

### 3️ Check Log Files

```bash id="disk3"
cd /var/log
ls -lh
```

---

### 4️ Clear Large Log Files

```bash id="disk4"
truncate -s 0 /var/log/syslog
```

---

### 5️ Remove Temporary Files

```bash id="disk5"
rm -rf /tmp/*
```

---

### 6️ Clean Docker (if used)

```bash id="disk6"
docker system prune -a
```

---

### 7️ Verify Disk Space

```bash id="disk7"
df -h
```

---

##  Real Output Example

###  Before Fix

```bash id="disk8"
Filesystem      Size  Used Avail Use%
/dev/sda1        50G   50G     0G 100%
```

---

###  Action Taken

* Cleared logs
* Removed temporary files
* Cleaned Docker images

---

###  After Fix

```bash id="disk9"
Filesystem      Size  Used Avail Use%
/dev/sda1        50G   30G    20G  60%
```

---

##  Root Cause (Example)

Log files in `/var/log` were not rotated, consuming the entire disk space.

---

##  Solution Summary

* Identified disk usage issue
* Removed unnecessary files
* Cleared logs and temporary data
* Verified system recovery

---

##  Key Learnings

* Monitor disk usage regularly
* Implement log rotation (`logrotate`)
* Clean unused Docker resources
* Set alerts for disk thresholds

---

##  Next Blog (Day 5)

 Deployment Rollback Runbook

---

##  Connect With Me

I am sharing my DevOps journey daily and building real-world runbooks 🚀
Follow along to learn practically!

---
