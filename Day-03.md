#  Day 3: High CPU Usage Runbook (DevOps Blog Series)

##  Introduction

High CPU usage is one of the most common issues in production systems. It can slow down applications, increase response time, and even cause downtime.

In this blog, I will walk through a **real-world DevOps runbook** to identify and fix high CPU usage.

---

##  Problem Statement

Server CPU usage is consistently high (>80%), leading to poor performance.

---

##  Possible Causes

* Infinite loops in application code
* Heavy background jobs
* Too many running processes
* Unoptimized queries or memory leaks

---

##  Step-by-Step Troubleshooting

### 1️ Check CPU Usage

```bash id="cpu1"
top
```

or

```bash id="cpu2"
htop
```

---

### 2️ Identify High CPU Processes

```bash id="cpu3"
ps aux --sort=-%cpu | head
```

---

### 3️ Analyze the Process

* Note the **PID**
* Identify which application/service is consuming CPU

---

### 4️ Kill the Problematic Process (if required)

```bash id="cpu4"
kill -9 <PID>
```

---

### 5️ Restart the Application

```bash id="cpu5"
sudo systemctl restart nginx
```

---

### 6️ Check Logs for Root Cause

```bash id="cpu6"
journalctl -xe
```

---

### 7️ Monitor Again

```bash id="cpu7"
top
```

---

##  Real Output Example

###  Before Fix

```bash id="cpu8"
%Cpu(s): 92.5 us, 5.0 sy, 2.5 id
```

High CPU process:

```bash id="cpu9"
PID USER   %CPU COMMAND
2345 root  85.2 java
```

---

###  Action Taken

```bash id="cpu10"
kill -9 2345
```

---

###  After Fix

```bash id="cpu11"
%Cpu(s): 35.0 us, 3.0 sy, 62.0 id
```

---

##  Root Cause (Example)

A Java-based service was stuck in an infinite loop, consuming excessive CPU.

---

##  Solution Summary

* Identified high CPU process
* Terminated faulty process
* Restarted service
* Verified system stability

---

##  Key Learnings

* Always monitor CPU regularly
* Use tools like `top` and `htop`
* Logs help identify deeper issues
* Automating alerts can prevent downtime

---

##  Next Blog (Day 4)

 Disk Full Issue Runbook

---

##  Connect With Me

I am documenting my DevOps journey daily and building real-world projects 🚀
Follow along for practical learning!

---
