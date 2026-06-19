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

# Local Development Setup

## Clone Repository

```bash
git clone <repository_url>
cd CI-CD_pipeline
```

---

## Create Virtual Environment

```bash
python3 -m venv venv
```

Activate:

```bash
source venv/bin/activate
```

---

## Install Dependencies

```bash
pip install -r requirements.txt
```

---

## Run Application

```bash
uvicorn app.main:app --reload --host 0.0.0.0 --port 5000
```

Open:

```text
http://localhost:5000
```

---

# Run With Docker

Build image:

```bash
docker build -t fastapi-app -f docker/Dockerfile .
```

Run container:

```bash
docker run -d -p 5000:5000 fastapi-app
```

Open:

```text
http://localhost:5000
```

---

# Run Full Stack

Move to docker directory:

```bash
cd docker
```

Start all services:

```bash
docker compose up -d --build
```

Stop services:

```bash
docker compose down
```

---

# AWS EC2 Deployment

## Create EC2 Instance

Recommended:

```text
Ubuntu Server 24.04 LTS
t3.micro
Free Tier Eligible
```

---

## Install Docker

```bash
sudo apt update

sudo apt install docker.io -y

sudo systemctl enable docker

sudo systemctl start docker
```

---

## Clone Repository

```bash
git clone <repository_url>
```

---

## Start Services

```bash
cd docker

docker compose up -d --build
```

---

# Domain Configuration

Current implementation uses:

```text
DuckDNS
```

Example:

```text
https://your-domain.duckdns.org
```

Domain points to EC2 Public IP.

---

# HTTPS Configuration

Install Certbot:

```bash
sudo apt install certbot python3-certbot-nginx
```

Generate certificate:

```bash
sudo certbot --nginx
```

Certificate location:

```text
/etc/letsencrypt/
```

---

# CI/CD Pipeline

The project uses GitHub Actions.

Deployment flow:

```text
Developer
    │
    ▼
git push
    │
    ▼
GitHub Actions
    │
    ▼
SSH EC2
    │
    ▼
docker compose down
docker compose up -d --build
```

After pushing code:

```bash
git add .
git commit -m "update"
git push
```

Deployment happens automatically.

---

# Monitoring

## Prometheus

Access:

```text
http://SERVER_IP:9090
```

or

```text
http://DOMAIN:9090
```

---

## Grafana

Access:

```text
http://SERVER_IP:3000
```

or

```text
http://DOMAIN:3000
```

Default credentials:

```text
Username: admin
Password: admin
```

---

# Useful Commands

## View Running Containers

```bash
docker ps
```

---

## View Logs

FastAPI:

```bash
docker logs -f fastapi_app
```

Nginx:

```bash
docker logs -f nginx_proxy
```

Prometheus:

```bash
docker logs -f prometheus_monitor
```

Grafana:

```bash
docker logs -f grafana_monitor
```

---

## Restart Services

```bash
docker compose restart
```

---

## Rebuild Services

```bash
docker compose down

docker compose up -d --build
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
