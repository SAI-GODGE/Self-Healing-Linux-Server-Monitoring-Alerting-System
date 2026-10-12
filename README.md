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

## 🎯 Objectives
- Automate disk-usage monitoring and threshold checks.
- Detect stopped or unavailable system services.
- Send instant alerts
- Collect Linux system metrics using Node Exporter.
- Store and query metrics using Prometheus.
- Visualize server performance through Grafana dashboards.
- Reduce repetitive manual checks through scheduled automation.

## 🛠️ Technology Stack

| Technology | Purpose |
|---|---|
| <img src="https://cdn.simpleicons.org/linux/FCC624" width="22" height="22" alt="Linux"/> **Linux (RHEL/CentOS)** | Server operating system |
| <img src="https://cdn.simpleicons.org/gnubash/4EAA25" width="22" height="22" alt="Bash"/> **Bash** | Monitoring scripts |
| <img src="https://img.icons8.com/fluency/48/clock.png" width="22" height="22" alt="Cron"/> **Cron** | Scheduled checks |
| <img src="https://img.icons8.com/fluency/48/server.png" width="22" height="22" alt="Node Exporter"/> **Node Exporter** | Exposes system metrics |
| <img src="https://cdn.simpleicons.org/prometheus/E6522C" width="22" height="22" alt="Prometheus"/> **Prometheus** | Metrics collection and storage |
| <img src="https://cdn.simpleicons.org/grafana/F46800" width="22" height="22" alt="Grafana"/> **Grafana** | Monitoring dashboards |
| <img src="https://cdn.simpleicons.org/telegram/26A5E4" width="22" height="22" alt="Telegram"/> **Telegram Bot API** | Instant alerts |
| <img src="https://cdn.simpleicons.org/gmail/EA4335" width="22" height="22" alt="Email"/> **Email** | Email notifications |

## 🏗️ Architecture

The system has two workflows:

- **Health checks and alerts:** Cron runs Bash scripts to check disk usage and service status. If a problem is detected, the scripts trigger Telegram or email notifications.
- **Metrics and dashboards:** Node Exporter exposes Linux system metrics, Prometheus collects them, and Grafana displays them in dashboards.

```mermaid
flowchart TB
    subgraph SERVER["🖥️ Linux Server — RHEL / CentOS"]
        direction TB
        CRON(["⏱️ Cron Scheduler"])
        SCRIPTS["⚙️ Bash Monitoring Scripts"]
        DISK["💾 Disk Usage Check"]
        SERVICE["🔧 Service Health Check"]
        NODE["📡 Node Exporter"]

        CRON --> SCRIPTS
        SCRIPTS --> DISK
        SCRIPTS --> SERVICE
    end

    subgraph NOTIFY["🔔 Alerting Workflow"]
        direction LR
        TELEGRAM["✈️ Telegram Bot API"]
        EMAIL["📧 Email Notifications"]
    end

    subgraph MONITOR["📊 Metrics Monitoring Workflow"]
        direction LR
        PROM["🔥 Prometheus"]
        GRAFANA["📈 Grafana Dashboard"]
        PROM --> GRAFANA
    end

    DISK -->|"Threshold exceeded"| TELEGRAM
    SERVICE -->|"Service unavailable"| TELEGRAM
    DISK -->|"Threshold exceeded"| EMAIL
    SERVICE -->|"Service unavailable"| EMAIL

    NODE -->|"System metrics"| PROM

    classDef scheduler fill:#1D4ED8,stroke:#60A5FA,color:#FFFFFF
    classDef scripts fill:#334155,stroke:#94A3B8,color:#FFFFFF
    classDef checks fill:#854D0E,stroke:#FBBF24,color:#FFFFFF
    classDef exporter fill:#115E59,stroke:#2DD4BF,color:#FFFFFF
    classDef alerts fill:#831843,stroke:#F472B6,color:#FFFFFF
    classDef monitoring fill:#7C2D12,stroke:#FB923C,color:#FFFFFF
    classDef dashboard fill:#166534,stroke:#4ADE80,color:#FFFFFF

    class CRON scheduler
    class SCRIPTS scripts
    class DISK,SERVICE checks
    class NODE exporter
    class TELEGRAM,EMAIL alerts
    class PROM monitoring
    class GRAFANA dashboard

```
### 🔄 Workflow Summary

| Step | Component | What happens |
|---|---|---|
| 1 | Cron | Runs monitoring scripts at scheduled intervals |
| 2 | Bash scripts | Check disk usage and service status |
| 3 | Alerting | Sends notifications when configured checks fail |
| 4 | Node Exporter | Exposes Linux system metrics |
| 5 | Prometheus | Scrapes and stores metrics |
| 6 | Grafana | Displays metrics in dashboards |

✨ Key Features

<table>
  <tr>
    <td width="50%">
      <h3>🖥️ System Monitoring</h3>
      Automated checks for disk usage and service status.
    </td>
    <td width="50%">
      <h3>🔔 Alert Notifications</h3>
      Telegram and email notifications for configured conditions.
    </td>
  </tr>
  <tr>
    <td width="50%">
      <h3>📊 Metrics Visualization</h3>
      Grafana dashboards powered by Prometheus metrics.
    </td>
    <td width="50%">
      <h3>⚙️ Task Automation</h3>
      Cron-based execution of monitoring scripts.
    </td>
  </tr>
  <tr>
    <td width="50%">
      <h3>🐧 Linux Administration</h3>
      Practical service management, filesystem monitoring, and troubleshooting.
    </td>
    <td width="50%">
      <h3>📈 Operational Visibility</h3>
      CPU, memory, disk, and network metrics exposed by Node Exporter.
    </td>
  </tr>
</table>

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






