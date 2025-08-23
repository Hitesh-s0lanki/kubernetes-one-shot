## Cluster Admin

## RBAC

Service account

```
kubectl auth whoami
kubectl auth can-i get pods

kubectl auth can-i delete deployment -n apache
kubectl get serviceaccount -n apache

kubectl auth can-i get pods -n apache --as=apache-user

```
