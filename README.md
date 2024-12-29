# CODETECH-Task1
## Kubernetes Deployment Example

This project demonstrates how to deploy and manage a containerized application using Kubernetes on a local Minikube cluster.

## Prerequisites
- Minikube installed
- kubectl installed
- Docker installed

## Steps
### Start a Minikube cluster:
   ```bash
   minikube start
   ```
### Build the Docker image:
   ```
   docker build -t my-app:1.0 .
   ```
### Apply Kubernetes manifests:
   ```
   kubectl apply -f deployment.yaml
   kubectl apply -f service.yaml
   ```
### Access the application:
   ```
   minikube service my-app-service --url
   ```
### Kubernetes Resources
Deployment: Ensures 2 replicas of the application are running.

Service: Exposes the application using a NodePort service.

### Scaling

Scale the application to 3 replicas:
```
kubectl scale deployment my-app --replicas=3
```
### Cleanup
Stop and delete resources:
```
kubectl delete -f deployment.yaml
kubectl delete -f service.yaml
minikube stop
```
