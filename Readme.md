# Kubernetes – One Shot 

An open-source container orchestration platform. It automates the deployment, scaling, and management of containerized applications.

> These are my notes from the “Kubernetes One Shot” session, organized by topic with reference images.

---

## Table of Contents
- [Kubernetes Architecture](#kubernetes-architecture)
- [Namespaces](#namespaces)
- [Workloads](#workloads)
- [Networking](#networking)
- [Storage](#storage)
- [Scaling & Scheduling](#scaling--scheduling)
- [Cluster Types](#cluster-types)
- [Cluster Administration](#cluster-administration)
- [Monitoring & Logging](#monitoring--logging)
- [Advanced Features](#advanced-features)
- [Security](#security)
- [Cloud-Native Kubernetes](#cloud-native-kubernetes)
- [Debugging & Troubleshooting](#debugging--troubleshooting)
- [Pods: Init vs Sidecar](#pods-init-vs-sidecar)

---

## Kubernetes Architecture
High-level components and how they interact: API Server, etcd, Controller Manager, Scheduler, Kubelet, Kube-Proxy, and worker nodes.

![Kubernetes Architecture](/images/kube-arch.png)

---

## Namespaces
Logical isolation within a cluster to group resources and apply policies/quotas.

![Kubernetes Namespaces](/images/namespace.png)

---

## Workloads
Primary controllers used to manage Pods at scale:

- **Deployment**
- **StatefulSet**
- **DaemonSet**
- **ReplicaSet**
- **Job**
- **CronJob**

> Example app (for practice/demo):

![Chat App (Workloads Example)](/images/chat-app.png)

---

## Networking
Connect and expose applications inside/outside the cluster:

- **Cluster Networking**
- **Services** (ClusterIP, NodePort, LoadBalancer)
- **Ingress** (HTTP/HTTPS routing)
- **Network Policies** (traffic rules between pods/namespaces)

> Ingress walkthrough (Notes app):

![Notes App via Ingress](/images/notes-app.png)

---

## Storage
Persistent data and configuration management:

- **PersistentVolumes (PV)**
- **PersistentVolumeClaims (PVC)**
- **StorageClasses**
- **ConfigMaps**
- **Secrets**

---

## Scaling & Scheduling
Ensure right capacity and placement:

- **HPA (Horizontal Pod Autoscaler)**
- **VPA (Vertical Pod Autoscaler)**
- **Node Affinity / Anti-Affinity**
- **Taints & Tolerations**
- **Resource Requests & Limits**
- **Liveness / Readiness / Startup Probes**
- **Resource Quotas**

![Scaling Overview](/images/scaling.png)

---

## Cluster Types
Ways to create/run Kubernetes clusters:

- **kubeadm**
- **Minikube**
- **kind** (Docker)
- **Managed Clouds:** **EKS** (AWS), **AKS** (Azure), **GKE** (Google)

---

## Cluster Administration
Operating the cluster safely and reliably:

- **RBAC (Role-Based Access Control)**
- **Cluster Upgrades**
- **CustomResourceDefinitions (CRDs)**

---

## Monitoring & Logging
Observe health, performance, and logs:

- **Metrics Server**
- **Centralized Logging**
- **Monitoring Stacks** (e.g., Prometheus + Grafana)

![K8s Monitoring Stack](/images/k8s-monitoring.png)
![Grafana Dashboards](/images/grafana.png)

---

## Advanced Features
Beyond the basics:

- **Helm** (package management)
- **Operators** (app-specific controllers)
- **Service Mesh** (traffic management, mTLS, observability)
- **Kubernetes API** (automation and integration)

---

## Security
Harden workloads and cluster:

- **Pod Security Standards (PSS)**
- **Image Scanning**
- **Network Policies**
- **Secrets Encryption**

---

## Cloud-Native Kubernetes
Running on cloud providers at scale:

- **Managed Services (EKS/AKS/GKE)**
- **Cluster Autoscaler**
- **Spot/Preemptible Nodes**

---

## Debugging & Troubleshooting
Quick checks when things go wrong:

- **kubectl** debugging commands
- **Pod/Container Logs**
- **Events**
- **Resource Usage Analysis**

---

## Pods: Init vs Sidecar
- **Init Containers:** run **before** the main container to perform setup tasks.
- **Sidecar Containers:** run **alongside** the main container to provide helper functions (e.g., log shippers, proxies).

