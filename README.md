# AuctionHub — Kubernetes Deployment & Operations

## Project Overview

AuctionHub is a hands-on DevOps portfolio project demonstrating how to containerise, deploy and manage an auction-platform demonstration application using Docker and Kubernetes.

The application is packaged into a custom Docker image (`adiotayo/auctionhub:v1`) and published to Docker Hub. It has been deployed successfully to a local Kubernetes cluster using two application replicas.

The project demonstrates Kubernetes Deployments, Services, Ingress routing through Traefik, ConfigMaps, resource requests and limits, container networking, rolling updates and operational troubleshooting.

The project will be extended with Helm, cloud deployment, infrastructure automation, CI/CD and monitoring as these topics are covered in the DevOps learning roadmap.

**Project Status:** In development.

## Project Objectives

- Build and containerise an AuctionHub demonstration application.
- Deploy and manage application workloads using Kubernetes.
- Configure Kubernetes Services and Ingress for application networking.
- Implement health checks and resource management.
- Manage application configuration and sensitive information securely.
- Configure persistent storage.
- Apply Kubernetes Role-Based Access Control (RBAC).
- Demonstrate troubleshooting and operational verification.

## Technologies

- Docker
- Kubernetes
- kubectl
- YAML
- Nginx
- Git and GitHub

## Repository Structure

```text
auctionhub-kubernetes/
├── app/
├── architecture/
├── docs/
├── kubernetes/
├── README.md
└── .gitignore
```

## Implementation Progress

- [x] Create project directories
- [x] Create initial README and .gitignore files
- [x] Build and containerise the application
- [x] Create Kubernetes Deployments and Services
- [x] Configure Ingress and networking
- [ ] Implement ConfigMaps, Secrets and persistent storage
- [ ] Configure health probes and resource limits
- [ ] Implement ServiceAccounts and RBAC
- [ ] Perform troubleshooting and operational testing
- [ ] Complete architecture and deployment documentation

## Deployment Instructions

### Prerequisites

- Docker installed and running
- A working Kubernetes cluster
- `kubectl` installed and configured
- Access to Docker Hub to pull the public AuctionHub image

### Deployment Steps

From the `auctionhub-kubernetes` project directory, run:

```bash
kubectl apply -f kubernetes/configmap.yaml
```

```bash
kubectl apply -f kubernetes/deployment.yaml
```

```bash
kubectl apply -f kubernetes/service.yaml
```

```bash
kubectl apply -f kubernetes/ingress.yaml
```

### Verify the Deployment

```bash
kubectl get deployments
```

```bash
kubectl get pods
```

```bash
kubectl get services
```

```bash
kubectl get ingress
```

### Test the Application Locally

```bash
kubectl port-forward service/auctionhub-service 8086:80
```

Open `http://localhost:8086` in your browser to access the AuctionHub demonstration website.

### Application Image

The application uses the public Docker Hub image `adiotayo/auctionhub:v1`.

### Notes

The Ingress configuration uses the Traefik Ingress Controller, which must be installed and configured in the Kubernetes cluster for Ingress routing to work. The port-forward command provides a separate local testing method.