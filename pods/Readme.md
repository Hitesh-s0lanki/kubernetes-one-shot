# **Init Containers & Sidecar Containers in Kubernetes**

## **1. Init Containers** 🛠️

Init containers **run before the main application container** starts.
They are typically used to perform setup tasks, such as initializing configurations, waiting for dependencies, or preparing the environment.

### **Example**

```bash
kubectl apply -f init-container.yml
```

Check logs of both containers:

```bash
kubectl logs init-test -c init-container
kubectl logs init-test -c main-container
```

### **Use Cases**

* Database schema migration before app startup
* Pulling config files or secrets from external services
* Waiting for another service (e.g., DB, API) to be ready
* Setting up environment variables or certificates

---

## **2. Sidecar Containers** 🤝

Sidecar containers are **helper containers** that run **alongside the main container** in the same pod.
They extend the functionality of the main application without modifying it.

### **Example**

```bash
kubectl apply -f sidecar-container.yml
```

View logs:

```bash
kubectl logs sidecar-test -c sidecar-container
```

### **Use Cases**

* Log shipping: Forward app logs to tools like ELK or Splunk
* Monitoring: Collect metrics via Prometheus or Datadog agents
* Caching: Sidecar cache for reducing API/database load
* Proxying: Service mesh sidecars like Istio or Linkerd

---

## **3. Real-World Use Cases** 🌍

| **Scenario**           | **Init Container**                             | **Sidecar Container**                          |
| ---------------------- | ---------------------------------------------- | ---------------------------------------------- |
| **Database Setup**     | Run DB migrations before app starts            | N/A                                            |
| **Secrets Management** | Fetch secrets from HashiCorp Vault before boot | Rotate secrets periodically                    |
| **Logging**            | N/A                                            | Forward logs to Elasticsearch / Loki           |
| **Monitoring**         | N/A                                            | Collect metrics using Prometheus / Datadog     |
| **Service Mesh**       | N/A                                            | Inject Istio/Linkerd proxy for traffic control |
| **Caching**            | Pre-warm cache data before main app starts     | Maintain shared cache for main container       |
