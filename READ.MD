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
