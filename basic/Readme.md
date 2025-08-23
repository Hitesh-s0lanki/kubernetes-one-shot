## Basic using Nginx

Nginx (pronounced "Engine-X") is a high-performance web server that can also be used as a reverse proxy, load balancer, and API gateway.
It is lightweight, fast, and widely used for serving static content and handling high traffic.

Key Features

- Web Server → Serves HTML, CSS, JS, images, etc.
- Reverse Proxy → Forwards client requests to backend servers.
- Load Balancer → Distributes traffic across multiple servers.
- SSL Termination → Handles HTTPS easily.
- Caching → Improves performance.

## Namespaces

A namespace in Kubernetes is a logical partition that isolates and organizes cluster resources, allowing multiple environments or teams to coexist within the same cluster.

```
kubectl get ns --get all namespaces

kubectl apply -f namespace.yml

kubectl delete namespace

kubectl get pods -n <name>
```

## Pod

```
kubectl get pods -n <name>

kubectl delete -f pod.yml
```

## Deployment

```
kubectl apply -f deployment.yml

kubectl get pods -n nginx

kubectl scale deployment/nginx-deployment -n nginx --replicas=2
```

# Update all deployments' and rc's nginx container's image to 'nginx:1.9.1'

kubectl set image deployments,rc nginx=nginx:1.9.1 --all

## Replicastes

Without Rolling Updated Similar to Deployment

## Deamonsets

kubectl apply -f daemonsets.yml

Atleast One pod on each worker node

kubectl delete -f daemonsets.yml

### Check the worker node

kubectl get pods -n nginx -o wide

## Job

For Single task to run (can be in parallel)

```
kubectl get job -n nginx

kubectl get pods -n nginx

kubectl logs pod/demo-job-95kcn -n nginx
```

## Cron Job

Schedular Job

```

kubectl apply -f cron-job.yml

kubectl logs pod/demo-job-95kcn -n nginx

kubectl delete -f cron-job.yml
```

## persistentVolume && persistentVolumeClaim

Storage of the Data

kubectl apply -f persistentVolume.yml
kubectl apply -f persistentVolumeClaim.yml

### For Exposing the docker port

sudo -E kubectl port-forward service/nginx-service -n nginx 81:80 --address=0.0.0.0
