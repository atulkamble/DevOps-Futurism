## 🌐 VM Scale Set (VMSS) with Load Balancer (LB)

![Image](https://learn.microsoft.com/en-us/azure/well-architected/service-guides/_images/virtual-machine-basic-deployment.svg)

![Image](https://kubernetes.io/images/docs/kubernetes-cluster-architecture.svg)

![Image](https://i.sstatic.net/tC5NmLgy.png)

### 🔹 VM Scale Set (VMSS)

* Azure service to **deploy & manage identical VMs**
* Supports **auto-scaling**
* Integrated with **Azure Load Balancer**
* Used as:

  * Backend pool for apps
  * **Node infrastructure for AKS**

### 🔹 Load Balancer (LB)

* Distributes incoming traffic across VMs / nodes
* Improves:

  * **Availability**
  * **Fault tolerance**
  * **Performance**

---

## ☸️ Kubernetes (K8s)

### 🔹 What is Kubernetes?

**Kubernetes** is an **open-source, production-grade container orchestration system**.

* Originally developed by Google
* Now maintained by **Cloud Native Computing Foundation (CNCF)**

### 🔹 Why Kubernetes?

Solves production problems like:

* Manual scaling
* Downtime
* Container crashes
* Load balancing
* Rolling updates

---

## 🔄 Kubernetes Container Lifecycle

Kubernetes manages the **entire lifecycle** of containers:

1. **Create**
2. **Maintain**
3. **Scale**
4. **Heal (restart if failed)**
5. **Terminate**

---

## 📄 Kubernetes Configuration

### 🔹 Templates

* Written in **YAML**
* Declarative approach

Common files:

* `deployment.yaml`
* `service.yaml`

Apply configuration:

```bash
kubectl apply -f deployment.yaml
kubectl apply -f service.yaml
```

---

## 🧱 Core Kubernetes Components

### 🔹 Pod

* **Smallest & basic deployment unit**
* Can contain **one or more containers**

### 🔹 Container

* Runs the application (Docker container)

### 🔹 Node

* A **VM or physical machine**
* Runs pods
* Managed by Kubernetes

📌 **Node = VM**

---

## ☁️ Managed Kubernetes Services

| Cloud Provider | Service                      |
| -------------- | ---------------------------- |
| AWS            | **Amazon EKS**               |
| Azure          | **Azure Kubernetes Service** |
| Google         | **Google Kubernetes Engine** |

---

## 🧪 Kubernetes Cluster Types

### 🔹 Single Node Cluster

* **Minikube**
* Used for:

  * Learning
  * Staging
  * Testing

### 🔹 Multi Node Cluster

* EKS / AKS / GKE
* Used for **production**

---

## 📊 Cluster Capacity Concepts

### 🔹 Cluster Size

* Small: 1–10 nodes
* Medium: ~50 nodes
* Large: 100+ nodes

### 🔹 High Availability (HA)

* Multiple nodes
* No single point of failure

### 🔹 SLA (Service Level Agreement)

* Guaranteed uptime by cloud provider

---

## 🔁 Scaling Concepts

| Term             | Meaning                |
| ---------------- | ---------------------- |
| Minimum Capacity | Least number of nodes  |
| Maximum Capacity | Upper scaling limit    |
| Desired Capacity | Expected running nodes |
| Running Capacity | Actual active nodes    |

### 🔹 Auto Scaling

* AWS: ASG (Auto Scaling Group)
* Azure: **VMSS**
* Kubernetes: HPA / Cluster Autoscaler

---

## 🧪 Minikube – Local Kubernetes

### 🔹 Supported OS

* Linux
* Windows
* macOS

⚙️ Uses **Hypervisor (VT-x / Hyper-V / VirtualBox)**

---

### 🔹 Minikube Commands

```bash
minikube status
minikube start
minikube stop
minikube delete
```

Dashboard:

```bash
minikube dashboard
```

Add-ons:

```bash
minikube addons list
minikube addons enable metrics-server
```

---

### 🔹 kubectl Basics (Minikube)

```bash
kubectl get nodes
kubectl get pods
kubectl get services
```

---

## 📦 Deploy App on Minikube

### 1️⃣ Apply Deployment

# deploymemnt.yaml
```
apiVersion: apps/v1
kind: Deployment
metadata:
  name: nginx-deployment
spec:
  replicas: 3
  selector:
    matchLabels:
      app: nginx
  template:
    metadata:
      labels:
        app: nginx
    spec:
      containers:
      - name: nginx
        image: nginx:latest
        ports:
        - containerPort: 80
```
```bash
kubectl apply -f deployment.yaml
```

### 2️⃣ Apply Service

# service.yaml
```
apiVersion: v1
kind: Service
metadata:
  name: nginx-service
spec:
  selector:
    app: nginx
  ports:
    - port: 80
      targetPort: 80
  type: ClusterIP

  type: LoadBalancer    

  ports:
    - port: 80
      targetPort: 80
```
```bash
kubectl apply -f service.yaml
```

### 3️⃣ Verify

```bash
kubectl get pods
kubectl get services
```

---

### 🔹 Access Service (NodePort / LB)

```bash
minikube tunnel   # keep running
```

```bash
kubectl service nginx-service
```

---

## ☁️ Azure Kubernetes Service (AKS)

---

### 🔹 Create Resource Group

```bash
az group create \
  --name aks-rg \
  --location eastus
```

---

### 🔹 Connect to AKS

```bash
az aks get-credentials \
  --resource-group aks-rg \
  --name aks-cluster

kubectl get nodes
```

---

## 📘 Azure AKS – Command Cheat Sheet

### 🔐 Login & Subscription

```bash
az login
az account list -o table
az account set --subscription "<SUBSCRIPTION_ID>"
```

---

### 📦 Create AKS Cluster

```bash
az aks create \
  --resource-group myRG \
  --name myAKS \
  --node-count 2 \
  --node-vm-size Standard_DS2_v2 \
  --enable-managed-identity \
  --generate-ssh-keys
```

---

### 🔗 Connect to AKS

```bash
az aks get-credentials \
  --resource-group myRG \
  --name myAKS

kubectl get nodes
```

---

### 🧩 Node Pool Management

```bash
az aks nodepool list \
  --resource-group myRG \
  --cluster-name myAKS
```

Add node pool:

```bash
az aks nodepool add \
  --resource-group myRG \
  --cluster-name myAKS \
  --name np2 \
  --node-count 2
```

Scale node pool:

```bash
az aks nodepool scale \
  --resource-group myRG \
  --cluster-name myAKS \
  --name nodepool1 \
  --node-count 3
```

---

### 📈 Scale AKS

```bash
az aks scale \
  --resource-group myRG \
  --name myAKS \
  --node-count 3
```

---

### 🚀 Deploy Sample App

```bash
kubectl create deployment nginx --image=nginx
kubectl expose deployment nginx --type=LoadBalancer --port=80
kubectl get svc
```

---

### 🛠 Debugging

```bash
kubectl logs pod-name
kubectl exec -it pod-name -- /bin/bash
kubectl describe pod pod-name
```

---

### 🔄 Upgrade AKS

```bash
az aks get-upgrades \
  --resource-group myRG \
  --name myAKS

az aks upgrade \
  --resource-group myRG \
  --name myAKS \
  --kubernetes-version 1.29.x
```

---

### 💰 Stop / Start (Cost Saving)

```bash
az aks stop --resource-group myRG --name myAKS
az aks start --resource-group myRG --name myAKS
```

---

### 🧹 Cleanup

```bash
az aks delete --resource-group myRG --name myAKS --yes
az group delete --name myRG --yes
```

---

## ✅ Summary (Interview-Ready)

* **VMSS + LB** = scalable infra
* **Kubernetes** = container orchestration
* **Pod** = smallest deployable unit
* **Minikube** = local single-node cluster
* **AKS/EKS/GKE** = production multi-node clusters
* **YAML + kubectl apply** = declarative deployments
