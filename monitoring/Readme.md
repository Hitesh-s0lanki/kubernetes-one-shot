## Install Kube Prometheus Stack

```
helm repo add prometheus-community https://prometheus-community.github.io/helm-charts

helm repo update

helm install kind-prometheus prometheus-community/kube-prometheus-stack --namespace monitoring --set prometheus.service.nodePort=30000 --set prometheus.service.type=NodePort --set grafana.service.nodePort=31000 --set grafana.service.type=NodePort --set alertmanager.service.nodePort=32000 --set alertmanager.service.type=NodePort --set prometheus-node-exporter.service.nodePort=32001 --set prometheus-node-exporter.service.type=NodePort

kubectl get svc -n monitoring
kubectl get ns
```

## Port Forwarding 

```
kubectl port-forward svc/kind-prometheus-kube-prome-prometheus -n monitoring 9090:9090 --address=0.0.0.0 &
kubectl port-forward svc/kind-prometheus-grafana -n monitoring 31000:80 --address=0.0.0.0 &

kubectl get secret -n monitoring svc/kind-prometheus-grafana -o jsonpath="{.data.password}" | base64 -d && echo
```