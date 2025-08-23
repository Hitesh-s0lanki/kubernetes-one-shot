## Probes (request)

- liveness probe
- readiness probe
- startup probe

## Check Probe

```
kubectl describe pod $NAME -n nginx
```

## Taint Command

```
kubectl taint node tws-cluster-worker2 prod=true:NoSchedule

kubectl taint node tws-cluster-worker2 prod=true:NoSchedule- # untaint
```
