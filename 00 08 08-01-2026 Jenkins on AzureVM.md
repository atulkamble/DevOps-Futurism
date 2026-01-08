# 🚀 Jenkins Server Setup on Azure VM (4GB RAM)

This document provides **step-by-step instructions** to install and configure **Jenkins on an Azure Linux VM**, along with required tools, a sample **Jenkins Declarative Pipeline**, and common **troubleshooting steps**.

---

## 🖥️ Azure VM Prerequisites

| Component | Details                             |
| --------- | ----------------------------------- |
| VM Size   | 4 GB RAM (Recommended for Jenkins)  |
| OS        | Ubuntu Server 20.04 / 22.04 LTS     |
| Java      | JDK 21 (JDK 17 also supported)      |
| Network   | NSG – Inbound Port **8080** allowed |
| User      | `atul`                              |
| Disk      | Minimum **30 GB** recommended       |

---

## 🔐 Connect to Azure VM using SSH

```bash
cd Downloads
chmod 400 jenkins.pem
ssh atul@<VM-PUBLIC-IP>
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

> ✅ Jenkins officially supports **Java 17 and Java 21 (LTS)**

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

Open your browser:

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

* Use **Java 17 or Java 21 only**
* Allocate **4 GB RAM minimum** for stable Jenkins
* Increase OS disk to **30–50 GB**
* Add Jenkins user to Docker group:

```bash
sudo usermod -aG docker jenkins
sudo systemctl restart jenkins
```

* Secure Jenkins using:

  * Credentials Manager
  * Role-Based Authorization Strategy
  * HTTPS (Nginx Reverse Proxy / Azure Load Balancer)

---

## 🛠️ Troubleshooting

### ❌ Docker Permission Denied (Jenkins / User)

```bash
sudo usermod -aG docker $USER
newgrp docker
```

For Jenkins:

```bash
sudo usermod -aG docker jenkins
sudo systemctl restart jenkins
```

---

### 🐳 Docker Buildx Issues

Build multi-arch image:

```bash
docker buildx build --platform linux/amd64 \
  -t docker.io/atuljkamble/pythonhelloworld:latest .
```

Install buildx if missing:

```bash
sudo apt install docker-buildx -y
```

Verify Docker:

```bash
docker ps
docker buildx version
```

---

### ❌ Jenkins Not Opening on Port 8080

Check:

* Azure NSG → Inbound rule for **8080**
* Jenkins service status

```bash
sudo systemctl status jenkins
```

---

## 📌 Summary

✔ Jenkins installed on Azure VM
✔ Java, Git, Docker, Maven configured
✔ Jenkins accessible on port **8080**
✔ Declarative pipeline ready (Dev → Staging → Prod)
✔ Common Docker & Jenkins issues covered

---

**Built with ❤️ by Atul Kamble**
