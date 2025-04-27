## This project deploys a simple "Hello World" website using NGINX on a local Kubernetes cluster created with Kind.

## Tools I have used
- Docker
- Kind
- kubectl
- VS Code

## Created a Kind cluster

kind create cluster --name hello-world-cluster
kubectl get nodes

## Built and loaded the Docker image

docker build -t hello-world-nginx docker/
kind load docker-image hello-world-nginx

## Deployed the app on Kubernetes

kubectl apply -f k8s/
kubectl get pods
kubectl get svc

kubectl port-forward service/hello-world-service 8080:80
 http://localhost:8080

