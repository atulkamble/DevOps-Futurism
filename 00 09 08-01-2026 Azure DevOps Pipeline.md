**complete, beginner-to-production friendly guide** to create an **Azure DevOps Organization**, **Project**, **GitHub Connector**, and a **working Azure Pipeline** using your repo:

👉 **GitHub Repo:** [https://github.com/atulkamble/mypipeline](https://github.com/atulkamble/mypipeline)

---

![Image](https://learn.microsoft.com/en-us/azure/devops/media/select-new-organization.png?view=azure-devops)

![Image](https://learn.microsoft.com/en-us/azure/devops/organizations/projects/media/create-project/select-new-project.png?view=azure-devops)

![Image](https://media2.dev.to/dynamic/image/width%3D800%2Cheight%3D%2Cfit%3Dscale-down%2Cgravity%3Dauto%2Cformat%3Dauto/https%3A%2F%2Fdev-to-uploads.s3.amazonaws.com%2Fuploads%2Farticles%2Fa277cmzao1324jrmfe54.png)

![Image](https://learn.microsoft.com/en-us/azure/devops/pipelines/library/media/ui-connection-setting.png?view=azure-devops)

# 🚀 Azure DevOps End-to-End Setup (Org → Project → GitHub → Pipeline)

---

## 1️⃣ Create Azure DevOps Organization

1. Open 👉 [https://dev.azure.com](https://dev.azure.com)
2. Sign in using **Microsoft account**
3. Click **New Organization**
4. Enter:

   * **Organization name**: `atul-org` (example)
   * **Region**: Closest (India / Asia)
5. Click **Continue**

✅ Your Azure DevOps Organization is ready

---

## 2️⃣ Create Azure DevOps Project

1. Inside the organization → **New Project**
2. Fill details:

| Setting           | Value                   |
| ----------------- | ----------------------- |
| Project Name      | `python-hello-pipeline` |
| Visibility        | Private                 |
| Version Control   | Git                     |
| Work Item Process | Agile                   |

3. Click **Create**

✅ Project created successfully

---

## 3️⃣ Connect GitHub Repository (Service Connection)

### Step A: Create GitHub Service Connection

1. Go to **Project Settings**
2. Click **Service connections**
3. Click **New service connection**
4. Select **GitHub**
5. Choose:

   * ✅ GitHub (OAuth)
6. Authorize GitHub access
7. Save the connection

---

### Step B: Select Your Repo

Repo used:

```
https://github.com/atulkamble/mypipeline
```

Azure DevOps now has permission to:

* Read repo
* Trigger pipelines
* Pull code securely

---

## 4️⃣ Create Azure Pipeline (YAML)

1. Go to **Pipelines → New Pipeline**
2. Choose **GitHub**
3. Select repo: `atulkamble/mypipeline`
4. Choose **Existing Azure Pipelines YAML**
5. Path:

```
azure-pipelines.yml
```

---

## 5️⃣ Azure Pipeline YAML (Validated)

### 📄 `azure-pipelines.yml`

```yaml
trigger:
  - main

pool:
  vmImage: 'ubuntu-latest'

variables:
  pythonVersion: '3.8'

stages:
- stage: Build
  displayName: "Python Build Stage"
  jobs:
  - job: BuildJob
    steps:
    - task: UsePythonVersion@0
      inputs:
        versionSpec: '$(pythonVersion)'
      displayName: "Use Python $(pythonVersion)"

    - script: |
        python --version
      displayName: "Verify Python Version"

    - script: |
        python helloworld.py
      displayName: "Run Hello World Script"

- stage: DockerBuild
  displayName: "Docker Build Stage"
  jobs:
  - job: DockerJob
    steps:
    - script: |
        docker --version
      displayName: "Verify Docker"

    - script: |
        docker build -t pythonhelloworld .
      displayName: "Build Docker Image"

    - script: |
        docker run pythonhelloworld
      displayName: "Run Docker Container"
```

---

## 6️⃣ Repository Structure (Expected)

```
mypipeline/
│── helloworld.py
│── Dockerfile
│── azure-pipelines.yml
```

### 🐍 `helloworld.py`

```python
print("Hello World from Azure Pipeline!")
```

### 🐳 `Dockerfile`

```dockerfile
FROM python:3.8-slim
WORKDIR /app
COPY helloworld.py .
CMD ["python", "helloworld.py"]
```

---

## 7️⃣ Pipeline Execution Flow

```text
GitHub Push (main)
   ↓
Azure Pipeline Trigger
   ↓
Python Installed
   ↓
helloworld.py Executed
   ↓
Docker Image Build
   ↓
Docker Container Run
```

---

## 8️⃣ Common Errors & Fixes

| Error                    | Fix                             |
| ------------------------ | ------------------------------- |
| Docker command not found | Use `ubuntu-latest` agent       |
| Pipeline not triggering  | Ensure branch = `main`          |
| Permission denied Docker | Hosted agent already configured |
| Repo not visible         | Recheck GitHub OAuth            |

---

## 9️⃣ Next Enhancements (Optional)

✅ Push image to **Azure Container Registry (ACR)**
✅ Add **Azure Key Vault secrets**
✅ Add **CI + CD stages**
✅ Deploy to **AKS / Azure VM**
✅ Add **Manual Approval Gates**

---

## 🎯 Result

✔ Azure DevOps Organization
✔ Project created
✔ GitHub connected securely
✔ Python + Docker pipeline running
✔ CI automation working

---
