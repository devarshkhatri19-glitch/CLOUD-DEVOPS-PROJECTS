# 🌩️ Devarsh CloudCore DevOps — End-to-End CI/CD with Azure, Terraform & Flask

![Azure](https://img.shields.io/badge/Azure-DevOps-blue?logo=microsoft-azure)
![Terraform](https://img.shields.io/badge/Terraform-IaC-purple?logo=terraform)
![Docker](https://img.shields.io/badge/Docker-Containerized-blue?logo=docker)
![Python](https://img.shields.io/badge/Python-Flask-yellow?logo=python)
![License](https://img.shields.io/badge/License-MIT-green)

A **production-grade DevOps project** demonstrating continuous integration and continuous deployment (CI/CD) of a **Flask API** to **Azure App Service** using **Azure DevOps**, **Terraform (IaC)**, **Docker**, and **PowerShell automation** for cloud cost optimization.

---

## 🧭 Overview

This repository contains a **complete, cloud-native automation stack**:

- **Infrastructure provisioning** via Terraform (Azure resources + remote backend)
- **CI/CD automation** with Azure DevOps YAML pipelines
- **Containerized Python app** deployed through Azure Container Registry
- **PowerShell automation** for Azure cost optimization
- **Architecture diagrams + documentation** for GitHub showcase

---

## 🧱 Architecture Diagram

```text
┌────────────────────────────────────────────────────────────┐
│                        Developer                           │
│          Pushes code to GitHub (main branch)               │
└──────────────┬─────────────────────────────────────────────┘
               │
               ▼
┌────────────────────────────────────────────────────────────┐
│                    Azure DevOps Pipeline                   │
│   1️⃣ Build Stage → Install dependencies, run tests         │
│   2️⃣ Docker Stage → Build & push Docker image to ACR       │
│   3️⃣ Deploy Stage → Deploy to Azure Web App (Container)    │
└──────────────┬─────────────────────────────────────────────┘
               │
               ▼
┌────────────────────────────────────────────────────────────┐
│                    Azure Infrastructure                    │
│    Provisioned via Terraform IaC (Remote Backend)           │
│   - Resource Group: cloudcore-devops-rg                     │
│   - Storage Account (TF state): cloudcoretfstate            │
│   - App Service Plan: cloudcore-service-plan                │
│   - Web App: cloudcore-api                                  │
│   - Container Registry: cloudcorecontainerregistry          │
└──────────────┬─────────────────────────────────────────────┘
               │
               ▼
┌────────────────────────────────────────────────────────────┐
│                     CloudCore Flask API                    │
│   - / → Welcome Message                                    │
│   - /health → Health Check                                 │
│   - /api/data → Accepts JSON & returns response             │
└────────────────────────────────────────────────────────────┘
               │
               ▼
┌────────────────────────────────────────────────────────────┐
│                   scripts/cleanup.ps1                      │
│   - Scheduled cleanup of unused Azure resources             │
│   - Reduces cloud cost automatically                        │
└────────────────────────────────────────────────────────────┘
