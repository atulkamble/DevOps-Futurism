## 🔰 Kubernetes CLI Basics (Common for All)

*(Applies to Minikube, EKS, AKS)*

### 🔹 Cluster & Context

```bash
kubectl version
kubectl cluster-info
kubectl config get-contexts
kubectl config current-context
kubectl config use-context <context-name>
```

---

## 📦 Namespace Management

```bash
kubectl get ns
kubectl create ns dev
kubectl delete ns dev
kubectl config set-context --current --namespace=dev
```

---

## 🚀 Pod Commands

```bash
kubectl get pods
kubectl get pods -o wide
kubectl describe pod <pod-name>
kubectl logs <pod-name>
kubectl logs -f <pod-name>
kubectl exec -it <pod-name> -- /bin/bash
kubectl delete pod <pod-name>
```

---

## 🧩 Deployment Commands

```bash
kubectl get deploy
kubectl create deployment nginx --image=nginx
kubectl apply -f deployment.yaml
kubectl describe deploy nginx
kubectl scale deploy nginx --replicas=5
kubectl rollout status deploy nginx
kubectl rollout undo deploy nginx
```

---

## 🔄 ReplicaSet

```bash
kubectl get rs
kubectl describe rs <rs-name>
```

---

## 🌐 Service Commands

```bash
kubectl get svc
kubectl expose deploy nginx --type=NodePort --port=80
kubectl describe svc nginx
```

Service types:

* ClusterIP
* NodePort
* LoadBalancer

---

## 📁 ConfigMaps & Secrets

```bash
kubectl create configmap app-config --from-literal=env=prod
kubectl get cm
kubectl describe cm app-config

kubectl create secret generic db-secret --from-literal=password=admin123
kubectl get secrets
kubectl describe secret db-secret
```

---

## 💾 Volumes & PVC

```bash
kubectl get pv
kubectl get pvc
kubectl describe pvc <pvc-name>
```

---

## ⚙️ Resource Management

```bash
kubectl top nodes
kubectl top pods
kubectl describe node <node-name>
```

---

## 🔐 RBAC & Security

```bash
kubectl get sa
kubectl get roles
kubectl get rolebindings
kubectl auth can-i create pods
```

---

## 🧪 Debugging & Troubleshooting

```bash
kubectl get events
kubectl describe pod <pod-name>
kubectl logs <pod-name> --previous
kubectl exec -it <pod-name> -- sh
```

---

## 📦 Helm (Advanced)

```bash
helm repo add bitnami https://charts.bitnami.com/bitnami
helm search repo nginx
helm install mynginx bitnami/nginx
helm list
helm uninstall mynginx
```

---

# 🟢 Minikube Commands

Entity: Minikube

```bash
minikube start
minikube start --driver=docker
minikube status
minikube stop
minikube delete
```

### Access Services

```bash
minikube service nginx
minikube ip
```

### Enable Addons

```bash
minikube addons list
minikube addons enable ingress
minikube addons enable metrics-server
```

---

# 🟡 Amazon EKS Commands

Entity: Amazon EKS

### Prerequisites

```bash
aws configure
```

### Cluster Management (eksctl)

```bash
eksctl create cluster --name eks-demo --region ap-south-1
eksctl get cluster
eksctl delete cluster --name eks-demo
```

### Update kubeconfig

```bash
aws eks update-kubeconfig --region ap-south-1 --name eks-demo
```

### Node Groups

```bash
eksctl create nodegroup --cluster eks-demo --name ng1
eksctl get nodegroup --cluster eks-demo
```

---

# 🔵 Azure AKS Commands

Entity: Azure AKS

### Login & Resource Group

```bash
az login
az group create --name aks-rg --location centralindia
```

### Create AKS Cluster

```bash
az aks create \
  --resource-group aks-rg \
  --name aks-demo \
  --node-count 2 \
  --enable-addons monitoring \
  --generate-ssh-keys
```

### Connect to AKS

```bash
az aks get-credentials --resource-group aks-rg --name aks-demo
```

### Scale AKS

```bash
az aks scale --resource-group aks-rg --name aks-demo --node-count 3
```

---

## 🚦 Advanced Kubernetes (Production)

```bash
kubectl autoscale deploy nginx --min=2 --max=10 --cpu-percent=70
kubectl get hpa
```

```bash
kubectl cordon <node>
kubectl drain <node> --ignore-daemonsets
kubectl uncordon <node>
```

```bash
kubectl apply -k ./overlays/prod   # Kustomize
```

---

## 🧠 Must-Remember for DevOps Interviews

✅ `kubectl apply` vs `create`
✅ Rolling updates & rollback
✅ Services vs Ingress
✅ HPA & Metrics Server
✅ EKS IAM / AKS RBAC integration
✅ Minikube for local testing

---
