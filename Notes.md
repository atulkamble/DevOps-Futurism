# 📘 DevOps & Azure DevOps Notes

## 📖 Basic Definitions + 🔑 Points to Remember (Extended Theory Notes)

---

## 🔹 DevOps Fundamentals

### 📌 What is DevOps?

**Definition:**
DevOps is a set of practices that **combines Development and Operations** to deliver software **faster, reliably, and continuously**.

**🔑 Points to Remember**

* Focuses on **automation + collaboration**
* Reduces deployment failures
* Improves release frequency
* Not a tool → **culture + process + tools**

---

### 📌 CI (Continuous Integration)

**Definition:**
Frequent code integration into a shared repository with automated builds and tests.

**🔑 Points to Remember**

* Developers commit code frequently
* Automated build & test on every commit
* Detects issues early
* Tools: Jenkins, Azure Pipelines

---

### 📌 CD (Continuous Delivery / Deployment)

**Definition:**
Automated process to **deliver code to production or staging**.

**🔑 Points to Remember**

* Delivery → manual approval to prod
* Deployment → fully automated to prod
* Reduces human errors
* Uses pipelines

---

## 🔹 Version Control

### 📌 Version Control System (VCS)

**Definition:**
System that tracks changes in source code over time.

**🔑 Points to Remember**

* Enables collaboration
* Supports rollback
* Git is **distributed**
* Centralized VCS = SVN

---

## 🔹 CI/CD Tools

### 📌 Jenkins

**Definition:**
Open-source automation server for CI/CD pipelines.

**🔑 Points to Remember**

* Uses **Jenkinsfile**
* Master controls agents
* Pipeline written in Groovy
* Requires maintenance (self-hosted)

---

### 📌 Azure DevOps

**Definition:**
Microsoft’s cloud-based DevOps platform.

**🔑 Points to Remember**

* End-to-end DevOps solution
* Integrates well with Azure
* Supports GitHub & Bitbucket
* Enterprise-grade security

---

## 🔹 Containers

### 📌 Container

**Definition:**
Lightweight, portable unit that packages application + dependencies.

**🔑 Points to Remember**

* Shares host OS kernel
* Faster startup than VMs
* Immutable infrastructure concept
* Docker is most popular

---

### 📌 Container vs Virtual Machine

**Remember**

* VM → full OS
* Container → shared OS
* Containers are lighter & faster
* VMs offer stronger isolation

---

## 🔹 Kubernetes

### 📌 Kubernetes

**Definition:**
Open-source system for **automating deployment, scaling, and management** of containerized applications.

**🔑 Points to Remember**

* Declarative model
* Self-healing
* Auto-scaling
* Platform-independent

---

### 📌 Control Plane

**Definition:**
Manages the Kubernetes cluster.

**🔑 Points to Remember**

* Makes scheduling decisions
* Maintains cluster state
* API Server is entry point

---

### 📌 Node

**Definition:**
Worker machine that runs Pods.

**🔑 Points to Remember**

* Runs kubelet & container runtime
* Can be VM or physical
* Managed by control plane

---

## 🔹 Kubernetes Objects

### 📌 Deployment

**Definition:**
Manages replicas of Pods.

**🔑 Points to Remember**

* Supports rolling updates
* Ensures desired state
* Uses ReplicaSet internally

---

### 📌 Service

**Definition:**
Exposes Pods using a stable network endpoint.

**🔑 Points to Remember**

* Abstracts Pod IPs
* Enables load balancing
* Required for networking

---

## 🔹 Infrastructure as Code (IaC)

### 📌 Infrastructure as Code

**Definition:**
Managing infrastructure using code instead of manual configuration.

**🔑 Points to Remember**

* Version controlled
* Repeatable deployments
* Reduces configuration drift
* Tools: Terraform, ARM, Bicep

---

### 📌 Terraform State

**Definition:**
File that tracks real infrastructure.

**🔑 Points to Remember**

* Stored locally or remotely
* Critical for collaboration
* Must be secured
* Enables change tracking

---

## 🔹 Azure Core Services

### 📌 IaaS vs PaaS

**Remember**

* IaaS → VM, full control
* PaaS → Managed platform
* PaaS reduces operational overhead
* Web App = PaaS

---

### 📌 Load Balancer

**Definition:**
Distributes traffic across resources.

**🔑 Points to Remember**

* Improves availability
* Works with VMSS
* Azure LB is Layer 4

---

## 🔹 Configuration Management

### 📌 Configuration Management

**Definition:**
Ensuring systems remain in a desired state.

**🔑 Points to Remember**

* Prevents configuration drift
* Uses declarative approach
* Tools: Ansible, Puppet, Chef

---

### 📌 Ansible

**Definition:**
Agentless configuration management tool.

**🔑 Points to Remember**

* Push-based
* Uses YAML
* SSH-based
* Simple learning curve

---

## 🔹 Monitoring & Observability

### 📌 Monitoring

**Definition:**
Tracking system health and performance.

**🔑 Points to Remember**

* Metrics, logs, alerts
* Proactive issue detection
* Prometheus = metrics

---

### 📌 Observability

**Definition:**
Ability to understand system behavior from outputs.

**🔑 Points to Remember**

* Metrics + Logs + Traces
* More advanced than monitoring
* Essential for microservices

---

## 🔹 Prometheus Stack

### 📌 Prometheus

**Definition:**
Time-series monitoring system.

**🔑 Points to Remember**

* Pull-based
* Stores metrics
* Uses PromQL
* Kubernetes-native

---

### 📌 Grafana

**Definition:**
Visualization & dashboarding tool.

**🔑 Points to Remember**

* Works with many data sources
* Alerting supported
* No data storage

---

## 🔹 Code Quality

### 📌 Static Code Analysis

**Definition:**
Analyzing source code **without executing it**.

**🔑 Points to Remember**

* Detects bugs early
* Improves maintainability
* Used in CI pipelines

---

### 📌 SonarQube

**Definition:**
Static analysis tool for code quality & security.

**🔑 Points to Remember**

* Language-agnostic
* Integrates with CI/CD
* Measures technical debt
* Not a runtime tool

---

## 🎯 Final Memory Trick

If a tool:

* **Builds & tests** → CI
* **Deploys** → CD
* **Runs containers** → Docker
* **Manages containers** → Kubernetes
* **Creates infra** → Terraform / ARM / Bicep
* **Monitors** → Prometheus
* **Visualizes** → Grafana
* **Checks code** → SonarQube

---

## 👨‍💻 Author Details

**Atul Kamble**
Cloud & DevOps Trainer | Azure Solutions Architect

🔗 **LinkedIn:** [https://www.linkedin.com/in/atuljkamble/](https://www.linkedin.com/in/atuljkamble/)
💻 **GitHub:** [https://github.com/atulkamble](https://github.com/atulkamble)

📌 *These notes are designed for DevOps, Azure DevOps, and Cloud learners with a focus on conceptual clarity, exam readiness, and real-world understanding.*

