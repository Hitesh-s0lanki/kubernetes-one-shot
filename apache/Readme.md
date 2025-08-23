## Apache

Web Server -> use 80 port

```
curl http://apache-service.apache.svc.cluster.local

sudo -E kubectl port-forward service/apache-service -n apache 82:80 --address=0.0.0.0

kubectl scale deployment apache-deployment -n apache --replicas=3

## Create pod
kubectl run -it load-generator --image=busybox -n apache -- bin

## Delete the pod
kubectl delete pod load-generator -n apache

##
kubectl run -i --tty load-generator --image=busybox -n apache /bin/sh

## Hitting the url
while true; do wget -q -O- http://apache-service.apache.svc.cluster.local; done
```
