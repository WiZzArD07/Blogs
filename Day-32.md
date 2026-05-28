# Day 32 - Introduction to Prometheus

## What I Learned
- Prometheus is an open-source monitoring and alerting tool
- It is widely used for monitoring applications and infrastructure
- Prometheus collects metrics from systems and services
- It stores metrics as time-series data
- Prometheus is commonly used with Kubernetes and cloud-native applications

## What is Prometheus
- Prometheus is a monitoring system developed for reliability and scalability
- It collects metrics from targets using HTTP endpoints
- It stores data with timestamps for analysis and alerting

Prometheus is an open-source systems monitoring and alerting toolkit designed for reliability and scalability. 

## Why Prometheus is Important
- Provides real-time monitoring
- Helps detect system failures early
- Supports powerful querying and alerting
- Works well with dynamic cloud environments
- Integrates with visualization tools like Grafana

Prometheus is widely used in DevOps and cloud-native ecosystems for monitoring distributed systems. 

## Key Features of Prometheus
- Time-series database
- Multi-dimensional data model
- Powerful query language (PromQL)
- Alerting support
- Service discovery
- Easy integration with Kubernetes

## How Prometheus Works
1. Applications expose metrics
2. Prometheus scrapes metrics periodically
3. Metrics are stored in time-series database
4. Queries and alerts are generated
5. Visualization tools display dashboards

## Core Components of Prometheus

### Prometheus Server
- Collects and stores metrics

### Exporters
- Expose metrics from systems
- Example:
  - Node Exporter
  - MySQL Exporter

### Alertmanager
- Handles alerts from Prometheus
- Sends notifications via email or Slack

### PromQL
- Query language used to analyze metrics

## Example Metrics
- CPU usage
- Memory usage
- Request count
- Application response time
- Disk utilization

## Installing Prometheus with Docker
```bash
docker run -d \
-p 9090:9090 \
--name prometheus \
prom/prometheus
```
### Access Prometheus Dashboard
http://localhost:9090

### Example PromQL Query
up

### What This Query Does
Checks whether monitored targets are running
Returns:
1 → Service is up
0 → Service is down
Node Exporter Example
docker run -d \
-p 9100:9100 \
--name node-exporter \
prom/node-exporter
Benefits of Prometheus
Open-source and lightweight
Powerful monitoring capabilities
Strong Kubernetes integration
Efficient alerting system
Flexible querying
Real Use Case

A company runs microservices on Kubernetes:

Prometheus collects CPU and memory metrics
Alerts are triggered if resource usage becomes high
DevOps team analyzes metrics to improve performance

This improves reliability and prevents downtime.

Prometheus vs Traditional Monitoring
Traditional Monitoring	Prometheus
Static infrastructure	Dynamic cloud-native systems
Limited scalability	Highly scalable
Simple monitoring	Advanced metrics and alerting
Less automation	Strong automation support
Summary

Prometheus is a powerful open-source monitoring and alerting system used in modern DevOps environments. It collects and stores metrics, supports alerting, and provides deep visibility into applications and infrastructure.

My Learning Reflection

Today I learned how Prometheus works and why it is widely used in DevOps and Kubernetes environments. I explored metrics collection, PromQL, exporters, and monitoring workflows used in real-world systems.