# Cloud-Native FastAPI Deployment Project

## Overview

This project demonstrates an end-to-end deployment pipeline for a Python web application using modern DevOps and Cloud technologies.

The application is developed with FastAPI, containerized with Docker, deployed on AWS EC2, exposed through Nginx Reverse Proxy with HTTPS, automatically deployed using GitHub Actions CI/CD, and monitored by Prometheus and Grafana.

The goal of this project is to simulate a real-world production environment and provide hands-on experience with the complete application lifecycle.

---

# Architecture

```text
Developer
    │
    ▼
GitHub Repository
    │
    ▼
GitHub Actions CI/CD
    │
    ▼
AWS EC2 (Ubuntu 24.04)
    │
    ▼
Docker Compose
 ├── FastAPI Application
 ├── Nginx Reverse Proxy
 ├── Prometheus
 └── Grafana
    │
    ▼
HTTPS Domain
    │
    ▼
End Users
```

---

# Features

* FastAPI Web Application
* Docker Containerization
* Multi-container Architecture
* Nginx Reverse Proxy
* HTTPS SSL/TLS (Let's Encrypt)
* DuckDNS Domain
* AWS EC2 Deployment
* GitHub Actions CI/CD
* Prometheus Monitoring
* Grafana Dashboard
* Automatic Deployment Pipeline

---

# Technology Stack

| Component        | Technology              |
| ---------------- | ----------------------- |
| Backend          | FastAPI                 |
| Template Engine  | Jinja2                  |
| Web Server       | Uvicorn                 |
| Containerization | Docker                  |
| Orchestration    | Docker Compose          |
| Reverse Proxy    | Nginx                   |
| Cloud Provider   | AWS EC2                 |
| Operating System | Ubuntu Server 24.04     |
| CI/CD            | GitHub Actions          |
| SSL Certificate  | Certbot + Let's Encrypt |
| Monitoring       | Prometheus              |
| Visualization    | Grafana                 |
| Version Control  | Git + GitHub            |

---

# Project Structure

```text
CI-CD_pipeline/
│
├── app/
│   ├── main.py
│   └── templates/
│       └── index.html
│
├── docker/
│   ├── Dockerfile
│   └── docker-compose.yml
│
├── nginx/
│   └── default.conf
│
├── monitoring/
│   ├── prometheus.yml
│   ├── alert.rules.yml
│   └── alertmanager.yml
│
├── .github/
│   └── workflows/
│       └── deploy.yml
│
├── requirements.txt
│
└── README.md
```

---




# Current Status

Completed:

* FastAPI Application
* Docker Containerization
* Nginx Reverse Proxy
* HTTPS
* AWS EC2 Deployment
* GitHub Actions CI/CD
* Prometheus
* Grafana

Planned:

* FastAPI Metrics Exporter
* Alertmanager
* Telegram Notifications
* Login Failure Detection
* Advanced Dashboards
* Log Aggregation

---

# Author

ThanhTruyen

Cloud-Native FastAPI Deployment Project

AWS • Docker • Nginx • CI/CD • Prometheus • Grafana
