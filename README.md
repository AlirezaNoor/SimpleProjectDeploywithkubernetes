# SimpleProjectDeploywithkubernetes
# K8s ASP.NET Core with Nginx

This repository contains an example of deploying an ASP.NET Core application with Nginx as a reverse proxy in a Kubernetes environment.

## Project Overview

- **ASP.NET Core**: A .NET-based backend application.
- **Nginx**: Acting as a reverse proxy for the ASP.NET Core application.
- **Kubernetes**: Orchestrating the deployment and services for both the ASP.NET Core and Nginx containers.

### Architecture

- The **Nginx** server handles incoming requests and forwards them to the **ASP.NET Core** service.
- **Kubernetes** manages the pods and services, ensuring scalability and stability.

## Prerequisites

Before running the project, make sure you have the following installed:

- [Docker](https://www.docker.com/)
- [Kubernetes (Minikube or any Kubernetes cluster)](https://kubernetes.io/docs/setup/)
- [kubectl](https://kubernetes.io/docs/tasks/tools/)
- [.NET SDK 7.0](https://dotnet.microsoft.com/download/dotnet/7.0)

## Setup Instructions

### 1. Clone the repository

```bash
git clone https://github.com/your-username/k8s-aspnetcore-nginx.git
cd k8s-aspnetcore-nginx
```
### 2. Build and push the ASP.NET Core Docker image
First, you need to build the Docker image for the ASP.NET Core application and push it to a container registry (e.g., Docker Hub or a local registry).
```bash
docker build -t your-docker-username/aspnetcore-app:latest .
docker push your-docker-username/aspnetcore-app:latest
```
