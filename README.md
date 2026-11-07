# Prometheus-and-Grafana
# Monitoring EC2 Instances Using Prometheus and Grafana

## Project Overview

In this project, I implemented a monitoring solution using **Prometheus and Grafana** to monitor multiple Amazon EC2 instances running Amazon Linux 2023.

The main objective of this project is to monitor CPU utilization, memory usage, disk utilization, server performance, and application logs from multiple EC2 instances using a centralized monitoring server.

I also integrated **Loki and Promtail** for centralized log monitoring and configured Grafana email alerts to receive notifications when system resources cross defined thresholds.

## Architecture

The project uses three EC2 instances:

- **Monitoring Server:** Prometheus, Grafana, Node Exporter, Loki and Promtail.
- **Worker Node 1:** Node Exporter.
- **Worker Node 2:** Node Exporter.

Prometheus collects metrics from all three instances, and Grafana displays the metrics through dashboards.

Loki stores and provides access to logs collected by Promtail.

## Tools and Technologies

| Tool | Purpose |
|---|---|
| AWS EC2 | Cloud infrastructure |
| Amazon Linux 2023 | Operating system |
| Prometheus | Metrics collection and monitoring |
| Grafana | Metrics visualization and dashboards |
| Node Exporter | Collects Linux server metrics |
| Loki | Log aggregation |
| Promtail | Log collection agent |
| Docker | Runs Loki and Promtail containers |
| SMTP | Email notifications |

## EC2 Instance Configuration

| Instance | Purpose | Instance Type |
|---|---|---|
| Monitoring Server | Prometheus and Grafana | Larger instance |
| Worker Node 1 | Metrics monitoring | t3.micro |
| Worker Node 2 | Metrics monitoring | t3.micro |

## Important Ports

| Service | Port |
|---|---|
| Prometheus | 9090 |
| Grafana | 3000 |
| Node Exporter | 9100 |
| Loki | 3100 |

## Project Implementation

### 1. Launch EC2 Instances

- Launch three EC2 instances.
- Select Amazon Linux 2023.
- Configure the monitoring server and two worker nodes.
- Configure the required security group rules.

### 2. Install Prometheus

- Download and install Prometheus.
- Create Prometheus configuration directories.
- Configure `prometheus.yml`.
- Add monitoring targets.
- Create a Prometheus systemd service.
- Enable and start Prometheus.

### 3. Install Grafana

- Add the official Grafana repository.
- Import the Grafana GPG key.
- Install Grafana.
- Start and enable the Grafana service.

### 4. Install Node Exporter

- Install Node Exporter on the monitoring server.
- Install Node Exporter on both worker nodes.
- Configure Node Exporter as a systemd service.
- Verify that Node Exporter is running.

### 5. Configure Prometheus Targets

- Configure the worker node IP addresses.
- Add worker node hostnames to `/etc/hosts` on the monitoring server.
- Update Prometheus scrape targets.
- Restart or reload Prometheus.
- Verify all targets from the Prometheus Targets page.

### 6. Configure Grafana Dashboards

- Open Grafana.
- Add Prometheus as a data source.
- Configure the Prometheus server URL.
- Import the Node Exporter Full dashboard (Dashboard ID: 1860).
- Monitor CPU, memory, disk, network, and system performance.

### 7. Configure Loki and Promtail

- Install Docker on the monitoring server.
- Download Loki configuration.
- Download Promtail configuration.
- Run Loki using Docker.
- Run Promtail using Docker.
- Connect Loki to Grafana as a data source.
- Explore and filter logs through Grafana.

### 8. Configure Grafana Email Alerts

- Configure SMTP settings in `grafana.ini`.
- Configure Gmail SMTP using an App Password.
- Restart Grafana.
- Create an email contact point.
- Test email notifications.
- Configure alert rules for CPU utilization.

### 9. Additional Monitoring Activities

- Create manual Grafana dashboards.
- Integrate Grafana alerts with Slack.
- Monitor system resource utilization.
- Generate CPU load using the stress utility.
- Verify alert notifications.

## Monitoring URLs

| Service | URL |
|---|---|
| Prometheus | http://MONITORING-SERVER-IP:9090 |
| Grafana | http://MONITORING-SERVER-IP:3000 |
| Node Exporter | http://WORKER-NODE-IP:9100 |
| Loki Ready Check | http://MONITORING-SERVER-IP:3100/ready |

Replace the IP placeholders with your actual EC2 private or public IP addresses, depending on your network configuration.

## What I Learned

- How to implement centralized monitoring using Prometheus.
- How to monitor multiple EC2 instances.
- How to configure Node Exporter on Linux servers.
- How Prometheus scrapes metrics from different targets.
- How to create Grafana dashboards.
- How to integrate Loki and Promtail for log monitoring.
- How to run monitoring components using Docker.
- How to configure Grafana email alerts.
- How to monitor CPU utilization and server performance.
- How to troubleshoot monitoring targets.

## Project Outcome

Successfully implemented a centralized monitoring environment using Prometheus, Grafana, Loki, and Promtail to monitor multiple AWS EC2 instances.

This project provided practical experience with cloud monitoring, infrastructure observability, metrics collection, centralized logging, and alert management.

## Skills Demonstrated

`AWS EC2` `Linux` `Prometheus` `Grafana` `Node Exporter` `Loki` `Promtail` `Docker` `Monitoring` `Logging` `Alerting` `DevOps`

---

**Project Category:** DevOps / Cloud Monitoring

**Environment:** AWS EC2 – Amazon Linux 2023
