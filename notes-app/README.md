# Simple Notes App

This is a simple notes app built with React and Django.

## Requirements

1. Python 3.9
2. Node.js
3. React

## Installation

1. Clone the repository

```
git clone https://github.com/LondheShubham153/django-notes-app.git
git checkout dev
```

2. Build the app

```
docker build -t notes-app .
```

3. Run the app

```
docker run -d -p 8000:8000 notes-app:latest
docker image tag notes-app:latest hiteshs0lankistriq/notes-app
docker push hiteshs0lankistriq/notes-app:latest
```

## kubernetes command

```
kubectl apply -f namespace.yml \
kubectl apply -f deployment.yml \
kubectl apply -f service.yml

kubectl port-forward service/notes-app-service -n nginx 8000:8000 --address=0.0.0.0

kubectl logs pod/notes-app-deployment-68d5f9b644-jzff9 -n nginx
```

## ingress Config

kubectl apply -f https://kind.sigs.k8s.io/examples/ingress/deploy-ingress-nginx.yaml

kubectl get pods -n ingress-nginx
kubectl get svc -n ingress-nginx

kubectl get all -n nginx

kubectl port-forward service/ingress-nginx-controller -n ingress-nginx 81:80 --address=0.0.0.0
kubectl port-forward svc/ingress-nginx-controller -n ingress-nginx 81:80 --address=0.0.0.0

## Nginx

Install Nginx reverse proxy to make this application available

`sudo apt-get update`
`sudo apt install nginx`
