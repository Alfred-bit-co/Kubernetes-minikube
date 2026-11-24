# Kubernetes with Minikube – Container Orchestration, Availability and Security

A practical project demonstrating how **Kubernetes** orchestrates containerized applications using **Minikube** in a local development environment.

## About the Project

This project explores Kubernetes through the deployment and management of a small web application built with **Flask** and **Redis**.

The goal is to understand the fundamentals of container orchestration and demonstrate how Kubernetes helps manage application deployment, availability, resource usage, and security.

The project is carried out in a local laboratory environment using Minikube.

## Project Objectives

- Understand Kubernetes architecture and its main components.
- Install and configure a local Kubernetes cluster with Minikube.
- Containerize a Flask application and a Redis service.
- Deploy and manage application components using Kubernetes.
- Demonstrate application availability through scaling and self-healing.
- Apply basic Kubernetes security practices.
- Document the deployment process so it can be reproduced.

## Application Architecture

The demonstration application uses two main components:

- **Flask:** Handles the web application and user requests.
- **Redis:** Stores and manages application data.

### Architecture overview

```text
             User
               |
               v
        Flask Application
               |
               v
             Redis
        (Internal Service)
```

Kubernetes manages the deployment and communication between these components.

## Technologies Used

| Technology | Purpose |
|---|---|
| Kubernetes | Container orchestration |
| Minikube | Local Kubernetes cluster |
| Docker | Containerization |
| kubectl | Kubernetes command-line management |
| Python / Flask | Web application |
| Redis | In-memory data storage |
| YAML | Kubernetes configuration |
| Git / GitHub | Version control and collaboration |

## Kubernetes Features Demonstrated

The project aims to demonstrate the following features:

### 1. Application Deployment
Deploy Flask and Redis using Kubernetes Deployments, Pods, and Services.

### 2. Self-Healing
Delete a running Pod and observe how Kubernetes automatically creates a replacement.

### 3. Scaling
Increase the number of Flask replicas to demonstrate horizontal scaling.

### 4. Rolling Updates and Rollbacks
Update the application progressively and demonstrate how to return to a previous version.

### 5. Security
Apply basic security practices, including:
- Kubernetes Secrets for sensitive configuration.
- Non-root container execution.
- CPU and memory resource limits.
- Network policies to restrict communication.
- Role-Based Access Control (RBAC).

## Project Structure

```text
kubernetes-minikube-project/
│
├── app/
│   ├── app.py
│   ├── requirements.txt
│   └── Dockerfile
│
├── kubernetes/
│   ├── flask-deployment.yaml
│   ├── flask-service.yaml
│   ├── redis-deployment.yaml
│   ├── redis-service.yaml
│   ├── redis-secret.yaml
│   └── network-policy.yaml
│
├── tests/
│   └── test-cases.md
│
├── docs/
│   └── architecture.md
│
└── README.md
```

*The repository structure may evolve as the project progresses.*

## Prerequisites

Before getting started, make sure you have installed:

- [Docker Desktop](https://www.docker.com/products/docker-desktop/)
- [Minikube](https://minikube.sigs.k8s.io/docs/start/)
- [kubectl](https://kubernetes.io/docs/tasks/tools/)
- [Git](https://git-scm.com/downloads)

## Getting Started

### 1. Start Minikube

```bash
minikube start
```

### 2. Check the cluster status

```bash
kubectl get nodes
```

### 3. Clone the repository

```bash
git clone https://github.com/YOUR-USERNAME/kubernetes-minikube-project.git
```

### 4. Enter the project directory

```bash
cd kubernetes-minikube-project
```

### 5. Deploy the application

```bash
kubectl apply -f kubernetes/
```

### 6. Check deployed resources

```bash
kubectl get pods
kubectl get services
kubectl get deployments
```

*Note: The deployment commands will be fully usable once the Kubernetes manifests and application files have been created.*

## Testing and Evaluation

The project includes tests designed to evaluate:

- Successful application deployment.
- Communication between Flask and Redis.
- Pod recovery after deletion.
- Application scaling.
- Rolling updates and rollbacks.
- Application security configurations.

Test results and supporting evidence will be documented in the `tests/` and `docs/` directories.

## Project Scope

This project focuses on a **single-node local Kubernetes cluster** running through Minikube.

It is intended for educational and experimental purposes. It does not aim to provide a production-ready or multi-node high-availability infrastructure.

## Team Members

- **ATTOH Séverine**
- **DOSSOH Guillaume**
- **AYITOU Alfred**
- **MABIALA Lys**

**Supervisor:** Mr TETE Kodjovi

## Academic Context

This project is part of an academic study in software engineering, focusing on container orchestration, application availability, and security.

---

**Project Status:** In Development

**Environment:** Local Kubernetes Cluster – Minikube

**Repository:** GitHub
