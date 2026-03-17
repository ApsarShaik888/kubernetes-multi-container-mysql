# 🐳 Multi-Container MySQL Database on Kubernetes

![Kubernetes](https://img.shields.io/badge/kubernetes-%23326ce5.svg?style=for-the-badge&logo=kubernetes&logoColor=white)
![MySQL](https://img.shields.io/badge/mysql-%2300f.svg?style=for-the-badge&logo=mysql&logoColor=white)
![Minikube](https://img.shields.io/badge/minikube-1C2C4F?style=for-the-badge&logo=kubernetes&logoColor=white)

## 📋 Project Overview

A hands-on Kubernetes project demonstrating a multi-container pod running MySQL database with a client sidecar container. This project showcases fundamental Kubernetes concepts including pod configuration, inter-container communication, and dependency management.

## 🏗️ Architecture
┌─────────────────────────────────────┐
│ Kubernetes Pod │
│ ┌────────────────┐ │
│ │ MySQL Server │ Port: 3306 │
│ │ Container │ localhost │
│ └────────┬───────┘ │
│ │ │
│ ┌────────▼───────┐ │
│ │ MySQL Client │ Waits for │
│ │ Container │ MySQL readiness │
│ └────────────────┘ │
└─────────────────────────────────────┘


## ✨ Features

- ✅ Multi-container pod design
- ✅ MySQL database with environment configuration
- ✅ Client container with readiness waiting logic
- ✅ Inter-container communication via localhost
- ✅ Proper container lifecycle management

## 🛠️ Prerequisites

- Minikube installed and configured
- kubectl command-line tool
- Basic understanding of YAML
- Docker Hub access (for pulling images)

## 📦 Component Details

### Container 1: MySQL Server
- **Image:** `mysql:latest`
- **Port:** 3306
- **Environment Variables:**
  - `MYSQL_DATABASE`: admintestdb
  - `MYSQL_ROOT_PASSWORD`: admin1234
- **Behavior:** Uses default MySQL entrypoint

### Container 2: MySQL Client
- **Image:** `mysql:latest`
- **Purpose:** Provides MySQL client access
- **Features:**
  - Waits for MySQL server readiness using connection testing
  - Stays alive with `tail -f /dev/null`
  - Ready for exec access
