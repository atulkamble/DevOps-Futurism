# 🚀 Jenkins Server Setup on Azure VM (4GB RAM)

This document provides **step-by-step instructions** to install and configure **Jenkins on an Azure Linux VM**, along with required tools and a sample **Jenkins Declarative Pipeline**.

---

## 🖥️ Azure VM Prerequisites

| Component | Details                            |
| --------- | ---------------------------------- |
| VM Size   | 4 GB RAM (Recommended for Jenkins) |
| OS        | Ubuntu Server (20.04 / 22.04 LTS)  |
| Java      | JDK 21 (or 17 supported)           |
| Network   | NSG Port **8080** open (Inbound)   |
| User      | `atul`                             |

---

## 🔐 Connect to Azure VM using SSH

```bash
cd Downloads
chmod 400 jenkins.pem
ssh atul@135.235.138.29
```

---

## 🔄 Update System Packages

```bash
sudo apt update -y
```

---

## ☕ Install Java (JDK 21)

```bash
sudo apt install fontconfig openjdk-21-jre -y
java -version
```

> Jenkins supports **Java 17 & 21** (LTS versions)

---

## 🧰 Install Required Tools (Git, Docker, Maven)

```bash
sudo apt install git docker.io maven -y
```

### Enable & Start Docker

```bash
sudo systemctl start docker
sudo systemctl enable docker
```

### Verify Installations

```bash
git --version
docker --version
mvn --version
```

---

## 🔑 Add Jenkins Repository & GPG Key

```bash
sudo wget -O /etc/apt/keyrings/jenkins-keyring.asc \
  https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key
```

```bash
echo "deb [signed-by=/etc/apt/keyrings/jenkins-keyring.asc]" \
  https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null
```

```bash
sudo apt update
```

---

## ⚙️ Install Jenkins

```bash
sudo apt install jenkins -y
```

---

## ▶️ Start & Enable Jenkins Service

```bash
sudo systemctl start jenkins
sudo systemctl enable jenkins
sudo systemctl restart jenkins
```

### Check Jenkins Status

```bash
sudo systemctl status jenkins
```

---

## 🌐 Access Jenkins Web UI

Open browser:

```
http://<VM-PUBLIC-IP>:8080
```

### Get Initial Admin Password

```bash
sudo cat /var/lib/jenkins/secrets/initialAdminPassword
```

---

## 🧪 Sample Jenkins Declarative Pipeline

```groovy
pipeline {
    agent any

    stages {
        stage('dev') {
            steps {
                echo 'I am in dev stage'
                sh 'git --version'
            }
        }

        stage('staging') {
            steps {
                echo 'I am in staging stage'
                sh 'docker --version'
            }
        }

        stage('prod') {
            steps {
                echo 'I am in prod stage'
            }
        }
    }
}
```

---

## ✅ Best Practices

* Use **Java 17/21 only** for Jenkins
* Increase disk size (minimum **30 GB** recommended)
* Add Jenkins user to Docker group:

```bash
sudo usermod -aG docker jenkins
sudo systemctl restart jenkins
```

* Secure Jenkins using:

  * Credentials Manager
  * Role-Based Authorization
  * HTTPS (Azure Load Balancer / Nginx)

---

## 📌 Summary

✔ Azure VM Jenkins Setup
✔ Java + Git + Docker + Maven Installed
✔ Jenkins Running on Port 8080
✔ Pipeline Ready for Dev → Staging → Prod

---

**Built with ❤️ by Atul Kamble**


✅ **Jenkins Server on Azure VM – Document Created**

I’ve created a **clean, production-ready Jenkins setup document** in the canvas with:

* Azure VM prerequisites (4GB RAM, NSG 8080)
* SSH access steps
* Java 21 installation (Jenkins-compatible)
* Git, Docker, Maven setup
* Official Jenkins repo + installation
* Jenkins service management
* Web UI access & initial password
* **Declarative Jenkins Pipeline example**
* Best practices (Docker group, security tips)
* Professional formatting (Markdown-ready, GitHub-friendly)
