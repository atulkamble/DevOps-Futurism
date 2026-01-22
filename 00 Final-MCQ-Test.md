# 📝 DevOps & Cloud Tools – MCQ Test

### ✅ Answers with Right & Wrong Explanations

---

## 🔹 Version Control & Source Management

### 1. Which command is used to create a new Git branch?

**A.** git checkout
**B.** git branch ✅
**C.** git merge
**D.** git clone

**✔ Correct (B):**
`git branch <name>` creates a new branch without switching to it.

**✖ Why others are wrong:**

* A: `git checkout` switches branches (or creates + switches with `-b`)
* C: `git merge` combines branches
* D: `git clone` copies a repository

---

### 2. What does `git pull` do?

**A.** Uploads local commits
**B.** Downloads commits only
**C.** Fetches and merges changes ✅
**D.** Deletes remote branches

**✔ Correct (C):**
`git pull = git fetch + git merge`.

**✖ Why others are wrong:**

* A: `git push` uploads commits
* B: `git fetch` only downloads
* D: No Git command deletes branches automatically

---

### 3. Azure Repos supports which version control systems?

**A.** Only Git
**B.** Only TFVC
**C.** Git and TFVC ✅
**D.** SVN only

**✔ Correct (C):**
Azure Repos supports **Git** and **Team Foundation Version Control (TFVC)**.

**✖ Why others are wrong:**

* A/B: Azure Repos supports both
* D: SVN is not supported

---

## 🔹 CI/CD & DevOps Pipelines

### 4. Which Jenkins file defines pipeline as code?

**A.** pipeline.yml
**B.** Jenkinsfile ✅
**C.** build.yaml
**D.** deploy.json

**✔ Correct (B):**
`Jenkinsfile` defines CI/CD pipelines as code.

**✖ Why others are wrong:**

* A/C/D: Not recognized by Jenkins

---

### 5. Which Jenkins pipeline syntax uses Groovy?

**A.** Scripted Pipeline ✅
**B.** YAML Pipeline
**C.** XML Pipeline
**D.** JSON Pipeline

**✔ Correct (A):**
Scripted pipelines are fully written in **Groovy**.

**✖ Why others are wrong:**

* Jenkins does not support YAML, XML, or JSON pipelines natively

---

### 6. Azure Pipelines supports which agents?

**A.** Microsoft-hosted only
**B.** Self-hosted only
**C.** Both Microsoft & Self-hosted ✅
**D.** Docker-only

**✔ Correct (C):**
Azure Pipelines supports **cloud and self-hosted agents**.

**✖ Why others are wrong:**

* A/B: Too restrictive
* D: Docker is optional, not mandatory

---

### 7. Main advantage of Blue-Green deployment?

**A.** Faster builds
**B.** Zero downtime ✅
**C.** Lower cost
**D.** Faster coding

**✔ Correct (B):**
Traffic switches between Blue & Green environments → **no downtime**.

**✖ Why others are wrong:**

* A/D: Not deployment-related
* C: Cost may actually increase

---

## 🔹 Containers & Container Orchestration

### 8. Docker is primarily used for?

**A.** Virtualization
**B.** Configuration management
**C.** Containerization ✅
**D.** Monitoring

**✔ Correct (C):**
Docker packages applications as **containers**.

**✖ Why others are wrong:**

* A: Virtualization uses hypervisors
* B: Tools like Ansible handle this
* D: Monitoring tools do this

---

### 9. Which Docker command builds an image?

**A.** docker run
**B.** docker build ✅
**C.** docker push
**D.** docker exec

**✔ Correct (B):**
`docker build` creates an image from a Dockerfile.

**✖ Why others are wrong:**

* A: Runs container
* C: Uploads image
* D: Executes command in container

---

### 10. Kubernetes is best described as?

**A.** Container runtime
**B.** Container orchestration platform ✅
**C.** CI/CD tool
**D.** Logging system

**✔ Correct (B):**
Kubernetes manages **container lifecycle, scaling, and networking**.

**✖ Why others are wrong:**

* A: containerd, Docker
* C: Jenkins, Azure DevOps
* D: ELK, Grafana

---

### 11. Minikube is mainly used for?

**A.** Production clusters
**B.** Local Kubernetes development ✅
**C.** Image scanning
**D.** Azure-only workloads

**✔ Correct (B):**
Minikube runs Kubernetes **locally**.

---

### 12. Azure Container Registry (ACR) is used to?

**A.** Run containers
**B.** Store container images ✅
**C.** Orchestrate pods
**D.** Monitor containers

**✔ Correct (B):**
ACR is a **private Docker registry**.

---

### 13. Azure Container Instances (ACI) is best for?

**A.** Long-running microservices
**B.** Serverless containers ✅
**C.** Kubernetes master
**D.** VM-based containers

**✔ Correct (B):**
ACI runs containers **without managing servers**.

---

## 🔹 Kubernetes Core Concepts

### 14. Kubernetes master component?

**A.** kubelet
**B.** kube-proxy
**C.** kube-apiserver ✅
**D.** containerd

**✔ Correct (C):**
API Server is the **control plane entry point**.

---

### 15. Smallest deployable unit?

**A.** Service
**B.** Deployment
**C.** Pod ✅
**D.** Node

**✔ Correct (C):**
A Pod contains one or more containers.

---

### 16. Kubernetes RBAC controls?

**A.** Networking
**B.** Authorization ✅
**C.** Logging
**D.** Scheduling

**✔ Correct (B):**
RBAC defines **who can do what**.

---

### 17. Kubernetes YAML is used for?

**A.** UI design
**B.** Infrastructure definition
**C.** Resource configuration ✅
**D.** Monitoring

**✔ Correct (C):**
YAML defines Pods, Services, Deployments.

---

## 🔹 Infrastructure as Code (IaC)

### 18. Terraform language?

**A.** YAML
**B.** JSON
**C.** HCL ✅
**D.** XML

**✔ Correct (C):**
Terraform uses **HashiCorp Configuration Language**.

---

### 19. Terraform command to initialize?

**A.** apply
**B.** init ✅
**C.** plan
**D.** destroy

**✔ Correct (B):**
Downloads providers and initializes backend.

---

### 20. ARM Templates are written in?

**A.** YAML
**B.** JSON ✅
**C.** HCL
**D.** XML

---

### 21. Azure Bicep is?

**A.** Terraform replacement
**B.** ARM DSL ✅
**C.** CI/CD tool
**D.** Monitoring service

**✔ Correct (B):**
Bicep compiles to ARM JSON.

---

## 🔹 Azure Compute & Networking

### 22. Azure VNet provides?

**A.** Storage
**B.** Identity
**C.** Network isolation ✅
**D.** Monitoring

---

### 23. Subnets belong to?

**A.** Resource Group
**B.** Virtual Network ✅
**C.** Load Balancer
**D.** NSG

---

### 24. VM Scale Sets used for?

**A.** Backup
**B.** Auto-scaling VMs ✅
**C.** Containers
**D.** Logging

---

### 25. Azure Web App is?

**A.** IaaS
**B.** SaaS
**C.** PaaS ✅
**D.** FaaS

---

## 🔹 Configuration Management

### 26. Ansible uses which protocol?

**A.** FTP
**B.** SSH ✅
**C.** RDP
**D.** HTTP

---

### 27. Ansible playbooks use?

**A.** JSON
**B.** XML
**C.** YAML ✅
**D.** INI

---

## 🔹 Monitoring & Logging

### 28. Prometheus data model?

**A.** Logs
**B.** Relational
**C.** Time-series ✅
**D.** Graph

---

### 29. Node Exporter collects?

**A.** App logs
**B.** Container images
**C.** Host metrics ✅
**D.** Routing data

---

### 30. Grafana is used for?

**A.** Log ingestion
**B.** Visualization ✅
**C.** CI/CD
**D.** Provisioning

---

## 🔹 Code Quality & Security

### 31. SonarQube is used for?

**A.** IaC
**B.** Code quality & security ✅
**C.** Containers
**D.** Deployment

---

### 32. SonarQube does NOT detect?

**A.** Bugs
**B.** Vulnerabilities
**C.** Code smells
**D.** Runtime memory leaks ✅

**✔ Correct (D):**
SonarQube performs **static analysis**, not runtime monitoring.

---


# ➕ Additional 8 MCQs (With Answers & Explanations)

---

## 🔹 CI/CD & DevOps Pipelines

### 33. In Azure DevOps, what is the purpose of a *Service Connection*?

**A.** Connect Git repositories
**B.** Authenticate to external services ✅
**C.** Store pipeline variables
**D.** Trigger pipelines

**✔ Correct (B):**
Service Connections securely authenticate Azure DevOps with **Azure, AWS, Docker Hub, Kubernetes**, etc.

**✖ Why others are wrong:**

* A: Repos are linked via repo settings
* C: Variables are stored in variable groups
* D: Triggers are defined in pipeline YAML

---

### 34. Which Jenkins feature allows distributed builds?

**A.** Stages
**B.** Shared libraries
**C.** Agents / Nodes ✅
**D.** Credentials

**✔ Correct (C):**
Jenkins agents execute jobs on **multiple machines** for scalability.

**✖ Why others are wrong:**

* A: Logical pipeline separation
* B: Reusable pipeline code
* D: Used for secrets

---

## 🔹 Containers & Kubernetes

### 35. Which Kubernetes object exposes Pods internally within a cluster?

**A.** Ingress
**B.** NodePort
**C.** ClusterIP ✅
**D.** LoadBalancer

**✔ Correct (C):**
`ClusterIP` exposes services **inside the cluster only**.

**✖ Why others are wrong:**

* A: Handles HTTP routing
* B: Exposes externally via node port
* D: Uses cloud load balancer

---

### 36. What happens if a Kubernetes Pod crashes?

**A.** Pod remains stopped
**B.** Node restarts
**C.** Controller recreates the Pod ✅
**D.** Cluster shuts down

**✔ Correct (C):**
Controllers (ReplicaSet/Deployment) ensure **desired state** is maintained.

**✖ Why others are wrong:**

* A: Kubernetes is self-healing
* B: Node is unaffected
* D: Incorrect behavior

---

## 🔹 Infrastructure as Code (IaC)

### 37. What does `terraform plan` do?

**A.** Creates infrastructure
**B.** Destroys resources
**C.** Shows execution plan ✅
**D.** Initializes providers

**✔ Correct (C):**
It previews **what will change** before applying.

**✖ Why others are wrong:**

* A: `terraform apply` creates infra
* B: `terraform destroy` removes infra
* D: `terraform init` initializes

---

### 38. Which Azure Bicep feature improves code reuse?

**A.** Parameters
**B.** Variables
**C.** Modules ✅
**D.** Outputs

**✔ Correct (C):**
Modules allow **reusable and modular templates**.

**✖ Why others are wrong:**

* A/B: Used inside templates
* D: Expose values after deployment

---

## 🔹 Monitoring, Logging & Security

### 39. Which Prometheus component triggers alerts?

**A.** Grafana
**B.** Alertmanager ✅
**C.** Node Exporter
**D.** Pushgateway

**✔ Correct (B):**
Alertmanager handles **alert routing, grouping, and notifications**.

**✖ Why others are wrong:**

* A: Visualization only
* C: Collects metrics
* D: Pushes short-lived metrics

---

### 40. What is a *Code Smell* in SonarQube?

**A.** Runtime exception
**B.** Security vulnerability
**C.** Maintainability issue ✅
**D.** Compilation error

**✔ Correct (C):**
Code smells indicate **poor design or readability**, not bugs.

**✖ Why others are wrong:**

* A: Runtime issue
* B: Security flaw
* D: Compile-time issue

---

