<h1 align="center">📡 Self-Healing Linux Server Monitoring and Alerting System</h1>

<p align="center">
  <strong>Automated Linux Monitoring | Real-Time Alerts | Metrics Visualization</strong>
</p>

<p align="center">
  A Linux monitoring project that combines Bash automation, Prometheus, Node Exporter, and Grafana to detect server health issues and improve operational visibility.
</p>

<p align="center">
  <img src="https://img.shields.io/badge/OS-RHEL%20%7C%20CentOS-red?logo=redhat&logoColor=white" alt="Linux">
  <img src="https://img.shields.io/badge/Scripting-Bash-4EAA25?logo=gnubash&logoColor=white" alt="Bash">
  <img src="https://img.shields.io/badge/Monitoring-Prometheus-E6522C?logo=prometheus&logoColor=white" alt="Prometheus">
  <img src="https://img.shields.io/badge/Metrics-Node%20Exporter-6B8E23" alt="Node Exporter">
  <img src="https://img.shields.io/badge/Dashboards-Grafana-F46800?logo=grafana&logoColor=white" alt="Grafana">
  <img src="https://img.shields.io/badge/Automation-Cron-blue" alt="Cron">
</p>


## 📌 Overview
The Self-Healing Linux Server Monitoring and Alerting System is a Linux-based project designed to automate server health checks, detect common operational issues, and provide visibility into system performance.

The project combines Bash monitoring scripts with scheduled execution, notification mechanisms, and an open-source monitoring stack. It helps identify disk-space problems and service failures while providing system metrics and visual dashboards.

The project covers practical DevOps concepts such as Linux administration, shell scripting, task scheduling, monitoring, alerting, and troubleshooting.

---
## 🎯 Objectives
- Automate disk-usage monitoring and threshold checks.
- Detect stopped or unavailable system services.
- Send instant alerts
- Collect Linux system metrics using Node Exporter.
- Store and query metrics using Prometheus.
- Visualize server performance through Grafana dashboards.
- Reduce repetitive manual checks through scheduled automation.

---
## 🛠️ Technology Stack

| Technology | Purpose |
|---|---|
| ![Linux](https://img.shields.io/badge/Linux-FCC624?style=flat-square&logo=linux&logoColor=black) **Linux (RHEL/CentOS)** | Operating system for the monitoring environment |
| ![Bash](https://img.shields.io/badge/Bash-4EAA25?style=flat-square&logo=gnubash&logoColor=white) **Bash** | Runs disk and service monitoring scripts |
| ![Cron](https://img.shields.io/badge/Cron-4479A1?style=flat-square&logo=linux&logoColor=white) **Cron** | Executes monitoring scripts automatically |
| ![Prometheus](https://img.shields.io/badge/Prometheus-E6522C?style=flat-square&logo=prometheus&logoColor=white) **Node Exporter** | Exposes Linux system metrics |
| ![Prometheus](https://img.shields.io/badge/Prometheus-E6522C?style=flat-square&logo=prometheus&logoColor=white) **Prometheus** | Collects and stores system metrics |
| ![Grafana](https://img.shields.io/badge/Grafana-F46800?style=flat-square&logo=grafana&logoColor=white) **Grafana** | Displays system metrics through dashboards |
| ![Telegram](https://img.shields.io/badge/Telegram-26A5E4?style=flat-square&logo=telegram&logoColor=white) **Telegram Bot API** | Sends monitoring alerts to Telegram |
| ![Email](https://img.shields.io/badge/Email-EA4335?style=flat-square&logo=gmail&logoColor=white) **Email** | Sends email notifications when configured |
---

# 🏗 Project Architecture

# 🚀 Linux Server Monitoring & Alerting System

## 📌 Project Overview
This project implements an automated **Linux Server Monitoring System** using Bash scripting and open-source monitoring tools.  
The system continuously monitors critical server resources and services, sends alerts when problems occur, and provides a visual monitoring dashboard.

The solution integrates:

- Bash monitoring scripts
- Cron automation
- Telegram alerts
- Prometheus metrics collection
- Node Exporter system metrics
- Grafana dashboards

This project demonstrates **basic DevOps monitoring practices** used in real production environments.

---

# 🎯 Objectives
- Monitor disk usage automatically
- Detect service failures
- Send instant alerts
- Collect system metrics
- Visualize server performance using dashboards

---

# 🛠 Technologies Used

- Linux (RHEL / CentOS)
- Bash Scripting
- Cron Jobs
- Prometheus
- Node Exporter
- Grafana
- Telegram Bot API

---

# 🏗 Project Architecture

                        +---------------------+
                        |     Linux Server    |
                        | (RHEL / CentOS VM)  |
                        +----------+----------+
                                   |
                                   |
                    +--------------v--------------+
                    |        Node Exporter        |
                    |  (Collects System Metrics)  |
                    |  CPU, RAM, Disk, Network    |
                    +--------------+--------------+
                                   |
                                   |
                        +----------v----------+
                        |     Prometheus      |
                        |  Metrics Collector  |
                        |  & Time-Series DB   |
                        +----------+----------+
                                   |
                        Scrapes Metrics
                                   |
                                   v
                        +----------+----------+
                        |       Grafana       |
                        |  Monitoring &       |
                        |  Visualization      |
                        +----------+----------+
                                   |
                                   |
                        Dashboards & Graphs
                                   |
                                   v
                     System Performance Monitoring


------------------------------------------------------------

             +----------------------------------+
             |        Bash Monitoring Scripts   |
             |                                  |
             |  • disk_monitor.sh               |
             |  • service_monitor.sh            |
             |  • apache_monitor.sh             |
             +----------------+-----------------+
                              |
                              |
                       Runs Every 5 Minutes
                          (Cron Job)
                              |
                              v
                     System Health Checking
                              |
                  +-----------+------------+
                  |                        |
                  v                        v
         Disk Usage Check          Service Status Check
                  |                        |
                  v                        v
         Threshold Exceeded?        Service Stopped?
                  |                        |
                  +-----------+------------+
                              |
                              v
                       Send Alert
                              |
             +----------------+----------------+
             |                                 |
             v                                 v
     Telegram Notification              Email Notification

## 📁 Project Structure

```
linux-server-monitoring/
│
├── README.md
├── .gitignore
│
├── disk_monitor.sh
├── disk_telegram_alert.sh
├── service_monitor.sh
├── apache_monitor.sh
│
├── prometheus/
│   └── prometheus.yml
│
└── Screenshots/
    ├── grafana-dashboard.png
    ├── node-exporter.png
    └── prometheus-ui.png
```

---

# ⚙ Installation & Setup

## 1️⃣ Clone Repository

```bash
git clone https://github.com/SAI-GODGE/Major Project.git
cd self-healing-linux-server
```

# 2️⃣ Make Scripts Executable

```bash
chmod +x *.sh
```

# 3️⃣ Setup Cron Job

```bash
crontab -e
```

Add monitoring task
```bash
*/10 * * * * /path/to/disk_monitor.sh >> /home/its_sai/linux-server-monitoring/monitor.log 2>&1
*/10 * * * * /path/to/service_monitor.sh >> /home/its_sai/linux-server-monitoring/monitor.log 2>&1
```

This runs monitoring every **10 minutes**.

---

# 📊 Monitoring Stack Setup

## Install Node Exporter

```bash
sudo dnf install node_exporter -y
sudo systemctl enable node_exporter
sudo systemctl start node_exporter
```

Check in browser:
http://localhost:9100/metrics

---

## Install Prometheus

Configure `prometheus.yml`:

```yaml
scrape_configs:
  - job_name: "node_exporter"
    static_configs:
      - targets: ["localhost:9100"]
```

Access Prometheus:
http://localhost:9090

---

## Install Grafana

```bash
sudo dnf install grafana -y
sudo systemctl enable grafana-server
sudo systemctl start grafana-server
```

Access Grafana:
http://localhost:3000

Add Prometheus as Data Source  
Import Dashboard: **Node Exporter Full (ID: 1860)**

---


---

# 📸 Screenshots

### Grafana Dashboard

![Grafana Dashboard](Screenshots/grafana-dashboard.png)

### Node Exporter Metrics

![Node Exporter](Screenshots/node-exporter.png)

### Prometheus UI

![Prometheus](Screenshots/prometheus-ui.png)

---

# 🔔 Alert System

The monitoring scripts send alerts when:

- Disk usage exceeds defined threshold
- Important services stop running

Alerts are sent using:

- Telegram Bot notifications
- Email Notifications

---

### Alerts are triggered when:

- Disk usage exceeds defined threshold  
- A monitored service stops running  

---


# 📈 Features

✔ Disk space monitoring  
✔ Service monitoring  
✔ Telegram alerts & Email Alerts  
✔ Automated cron execution  
✔ Prometheus metrics collection  
✔ Grafana monitoring dashboard

---

## 📌 Conclusion

This project demonstrates automation, monitoring, and self-healing capabilities in Linux systems using open-source tools.

By integrating Bash scripting with Prometheus, Node Exporter, and Grafana, the system ensures:

- Improved server uptime  
- Reduced manual intervention  
- Real-time monitoring and alerting  
- Faster issue detection and recovery  

The Self-Healing Linux Server enhances reliability and operational efficiency in Linux-based environments.

---

## 👨‍💻 Authors

**Tejas Kanade**  
**Saiprasad Godge**  
**Omkar Ghongde**  

Major Project – Self-Healing Linux Server Monitoring & Alerting System
B.Tech Computer Science

---






