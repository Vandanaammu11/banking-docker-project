# Banking Java Application — Docker & Kubernetes Project

A beginner-friendly DevOps project demonstrating how to containerize a banking web application using Docker and deploy it to Kubernetes with Minikube.

## What This Project Demonstrates

- Building Docker images using a Dockerfile
- Running containers locally
- Publishing Docker images to Docker Hub
- Deploying applications using Kubernetes
- Exposing applications using a NodePort Service
- Managing Pods using kubectl

## Technologies Used

- Docker
- Docker Hub
- Kubernetes
- Minikube
- kubectl
- Git and GitHub
- Visual Studio Code
- HTML

## Project Structure

```text
banking-docker-project/
├── index.html
├── Dockerfile
├── deployment.yaml
├── service.yaml
└── README.md
```

## Architecture

```text
VS Code
   ↓
GitHub
   ↓
Docker Build
   ↓
Docker Hub
   ↓
Kubernetes (Minikube)
   ↓
Deployment → Pods
   ↓
NodePort Service
   ↓
Banking Web Application
```

## Build the Docker Image

```bash
docker build -t banking-app:1.0 .
```

## Run the Application Locally

```bash
docker run -d --name banking-test -p 8080:80 banking-app:1.0
```

Open `http://localhost:8080` in your browser.

## Push the Image to Docker Hub

Replace `YOUR_DOCKERHUB_USERNAME` with your Docker Hub username.

```bash
docker login
docker tag banking-app:1.0 YOUR_DOCKERHUB_USERNAME/banking-app:1.0
docker push YOUR_DOCKERHUB_USERNAME/banking-app:1.0
```

Ensure the image name in `deployment.yaml` matches the image pushed to Docker Hub.

## Deploy to Kubernetes

```bash
minikube start
kubectl apply -f deployment.yaml
kubectl apply -f service.yaml
kubectl get deployments
kubectl get pods
kubectl get services
minikube service myapp-service
```

Make sure `myapp-service` matches the Service name in `service.yaml`.

## Future Enhancements

- GitHub Actions CI/CD
- Jenkins pipeline
- Amazon ECR integration
- Amazon EKS deployment
- Prometheus and Grafana monitoring

## Author

Vandana M.

DevOps Learning Project
