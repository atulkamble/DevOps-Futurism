# 📘 Linux, Networking & DevOps — Session Documentation

## 🗓️ Session Agenda

### 1️⃣ Linux Fundamentals

* Linux basics and command line usage
* Shell scripting basics
* File permissions and execution

### 2️⃣ Networking for DevOps

* IP addressing & CIDR
* Subnets & Virtual Networks
* Cloud networking concepts (VNet, Subnet)
* Practical networking using Azure CLI

### 3️⃣ DevOps Overview

* DevOps principles
* CI/CD basics
* Automation mindset

### 4️⃣ Package Managers

* **Linux**: `apt`, `yum`, `dnf`
* **Windows**:
  * Chocolatey
  * Scoop

### 5️⃣ Operating Systems & Tools

* Linux (Debian / RedHat based)
* Windows Server
* VS Code

  * Integrated Terminal
  * PowerShell

### 6️⃣ Version Control with Git

* Git installation & configuration
* Repository management
* Branching, merging & pull requests

---

## 🐧 Linux & Shell Scripting Basics

### Create a Shell Script

```bash
vi script.sh
```

### Make Script Executable

```bash
chmod +x script.sh
```

### Execute Script

```bash
./script.sh
```

---

## ☁️ Azure CLI Installation on Ubuntu

### Install Azure CLI

```bash
curl -sL https://aka.ms/InstallAzureCLIDeb | sudo bash
```

### Verify Installation

```bash
az --version
```

### Login to Azure

```bash
az login
```

---

## 🌐 Create Azure Virtual Network (VNet)

```bash
az network vnet create \
  --resource-group MyRG \
  --name demo-vnet \
  --address-prefix 10.0.0.0/16 \
  --subnet-name demo-subnet \
  --subnet-prefix 10.0.1.0/24
```

### 🔹 Explanation

* **Resource Group**: `MyRG`
* **VNet**: `demo-vnet`
* **VNet CIDR**: `10.0.0.0/16`
* **Subnet**: `demo-subnet`
* **Subnet CIDR**: `10.0.1.0/24`

---

## 🔧 Git Version Control

### Check Git Version

```bash
git --version
```

### Initialize Repository

```bash
git init
```

### Stage Files

```bash
git add a.txt
git add .
```

### Commit Changes

```bash
git commit -m "changes"
```

### Push to Main Branch

```bash
git push origin main
```

---

## 🌿 Git Branching

### Create Branch

```bash
git branch branch-name
git branch dev
```

### List Branches

```bash
git branch -a
```

### Switch to Dev Branch

```bash
git checkout dev
```

### Commit Changes in Dev Branch

```bash
git add a.txt
git commit -m "changes"
git push origin dev
```

---

## 🔀 Git Merge & Pull Request Flow

### Merge Dev Branch into Main

```bash
git checkout main
git merge dev
```

### 📌 Real-World Flow

1. Developer works on **dev branch**
2. Pushes code to remote
3. Creates **Pull Request (PR)**
4. Code review happens
5. PR is approved
6. Changes are merged into **main**

---

## 🧠 Key Takeaways

* Linux scripting enables automation
* Azure CLI allows Infrastructure as Code
* Git branching avoids production conflicts
* DevOps integrates **Linux + Networking + Git + Cloud**

---
