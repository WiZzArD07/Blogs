# Day 33 - Introduction to Grafana

## What I Learned
- Grafana is an open-source visualization and monitoring platform
- It is used to create dashboards for monitoring systems and applications
- Grafana connects with data sources like Prometheus, MySQL, and Elasticsearch
- It helps visualize metrics using graphs, charts, and alerts
- Grafana is widely used in DevOps and cloud-native environments

## What is Grafana
- Grafana is a dashboard and analytics platform
- It allows users to visualize time-series data from different monitoring systems
- Grafana is commonly used with Prometheus for monitoring Kubernetes and cloud infrastructure

Grafana is an open-source platform for monitoring and observability that provides interactive dashboards and visualization tools. 

## Why Grafana is Important
- Converts raw metrics into visual dashboards
- Makes monitoring easier and more understandable
- Helps identify trends and performance issues
- Supports real-time monitoring and alerting
- Integrates with multiple monitoring tools

Grafana helps teams visualize and analyze metrics collected from monitoring systems like Prometheus. 

## Key Features of Grafana
- Interactive dashboards
- Real-time monitoring
- Alerting system
- Multiple data source support
- Custom visualization panels
- Team collaboration support

## How Grafana Works
1. Monitoring tools collect metrics
2. Grafana connects to data sources
3. Metrics are visualized using dashboards
4. Alerts are triggered based on conditions
5. Teams analyze system performance

## Common Data Sources
- Prometheus
- MySQL
- PostgreSQL
- Elasticsearch
- InfluxDB
- AWS CloudWatch

## Installing Grafana with Docker
```bash
docker run -d \
-p 3000:3000 \
--name grafana \
grafana/grafana
```

### Access Grafana Dashboard
```bash
http://localhost:3000
```

### Default Login Credentials
```bash
Username: admin
Password: admin
```

### Connecting Prometheus to Grafana
 - Open Grafana 
 - Go to Data Sources
 - Select Prometheus
 - Add Prometheus URL
 - Save and Test connection

### Creating a Dashboard
 - Click "Create Dashboard"
 - Add a panel
 - Select Prometheus query
 - Choose visualization type
 - Save dashboard

### Example Prometheus Query
```bash
rate(http_requests_total[1m])
```

### What This Query Does
 - Calculates request rate per second
 - Helps monitor application traffic

### Grafana Alerting
 - Alerts notify teams when metrics exceed thresholds
 - Alerts can be sent through:
   - Email
   - Slack
   - Microsoft Teams

### Benefits of Grafana
 - Easy data visualization
 - Centralized monitoring dashboards
 - Real-time insights
 - Flexible integrations
 - Improved troubleshooting

### Real Use Case
 - A company runs applications on Kubernetes:
 - Prometheus collects metrics
 - Grafana visualizes CPU and memory usage
 - Alerts are triggered if resources exceed limits
 - This helps teams monitor infrastructure efficiently and prevent downtime.

### Grafana vs Prometheus
| Grafana	                    |    Prometheus                             |
| ----------------------------  | ----------------------------------------  |
| Visualization tool	        |    Monitoring and metrics collection tool |
| Creates dashboards	        |    Collects and stores metrics            |
| Supports multiple data sources|	 Uses PromQL queries                    |
| Focuses on visualization	    |    Focuses on monitoring                  |

Grafana visualizes metrics while Prometheus collects and stores them. They are commonly used together in DevOps environments.

### Summary
Grafana is a powerful visualization platform used for monitoring and observability. It helps DevOps teams analyze metrics through interactive dashboards and integrates with tools like Prometheus for real-time infrastructure monitoring.

### My Learning Reflection
Today I learned how Grafana works and how it visualizes monitoring data using dashboards and graphs. I understood how Grafana integrates with Prometheus to provide complete observability in DevOps environments.