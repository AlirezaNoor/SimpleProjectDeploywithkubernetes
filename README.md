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
Make sure to replace your-docker-username with your actual Docker Hub username.

### 3. Deploy to Kubernetes
To deploy both the Nginx and ASP.NET Core services to your Kubernetes cluster, use the following command:
```bash
kubectl apply -f deployment.yaml
```
This will deploy:

An ASP.NET Core application (aspnetcore-deployment)
An Nginx reverse proxy (nginx-deployment)
Services for both deployments
4. Access the Application
Once everything is deployed, you can check the status of the pods:

```bash
kubectl get pods
```
If all pods are running successfully, you can access the application through the Nginx service's external IP:
```bash
kubectl get services
```

Look for the external IP of the nginx-service and open it in your browser.

5. Troubleshooting
If you encounter a 504 Gateway Timeout error, make sure that the ASP.NET Core pod is running on the correct port (8080).

Check the logs for more information:
```bash
kubectl logs <pod-name>
```

## Ensure that the Docker image has been built and pushed correctly.

### Files Overview
Dockerfile
This file is used to build the Docker image for the ASP.NET Core application.

### nginx.conf
Configuration file for Nginx, used to forward requests to the ASP.NET Core service.

### deployment.yaml
Kubernetes deployment and service definitions for both Nginx and the ASP.NET Core app.

### .gitignore
Specifies the files and directories to be ignored by Git.

### Technologies Used
ASP.NET Core 7.0
Nginx
Docker
Kubernetes
Minikube (for local testing)
Contributing
Feel free to fork this repository and contribute by submitting pull requests. All contributions are welcome!

