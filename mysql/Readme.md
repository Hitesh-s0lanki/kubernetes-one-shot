## MySql Demo for Stateful

```

kubectl apply -f namespace.yml -f statefulset.yml -f service.yml

kubectl get pods -n mysql

kubectl exec -it mysql-statefulset-0 -n mysql --bash

```
