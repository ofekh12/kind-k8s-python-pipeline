# Ephemeral Microservice Stack 🚀



A fully automated CI/CD pipeline for a Python API and PostgreSQL stack, deployed on Kubernetes using Helm and GitHub Actions.



## 🌟 Overview

This project demonstrates an "End-to-End" DevOps workflow, creating a temporary (ephemeral) environment for every code change to ensure reliability and consistency.



## 🏗️ Architecture

- **App**: Python Flask/FastAPI application.

- **Database**: PostgreSQL for persistent storage.

- **Orchestration**: Kubernetes (Kind cluster).

- **Package Management**: Helm Charts.



## 🤖 CI/CD Pipeline

The GitHub Actions pipeline automates the building, loading, and deployment of the stack.



### 🚀 Pipeline Status

![Pipeline Success](Screenshot from 2026-01-29 19-42-15.png](https://github.com/ofekh12/kind-k8s-python-pipeline/blob/main/Screenshot%20from%202026-01-29%2019-42-15.png?raw=true)

*Figure 1: Successful end-to-end deployment and integration test in GitHub Actions.*



### Pipeline Steps:

1. **Containerization**: Builds a Docker image of the Python application.

2. **Infrastructure Setup**: Spins up a Kind (Kubernetes-in-Docker) cluster.

3. **Image Loading**: Sideloads the local Docker image into the Kind nodes.

4. **Deployment**: Deploys the entire stack using Helm.

5. **Integration Testing**: Executes a Kubernetes Job that verifies the API-to-Database connectivity.



## 🧪 Integration Testing

To ensure the stack is functional, a dedicated test job runs a `curl` command to:

- Write data to the Python API.

- Verify the API can successfully communicate with the PostgreSQL database.

- Confirm the deployment is healthy and ready for production by waiting for the `condition met` status.



## 🛠️ Tech Stack

- **Docker** & **Kubernetes (Kind)**

- **Helm**

- **GitHub Actions**

- **Python** & **PostgreSQL**
