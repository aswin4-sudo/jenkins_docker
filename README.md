# 🚀 CI/CD Pipeline using Jenkins, SonarQube, Docker & AWS EC2

## 📌 Overview

This project demonstrates a complete CI/CD pipeline where a sample web application is:

- Pushed to GitHub
- Pulled and built by Jenkins
- Analyzed using SonarQube
- Deployed using Docker
- Hosted on AWS EC2

All configurations are done using Jenkins UI (no Jenkinsfile).

---

## 🧱 Architecture Flow

GitHub → Jenkins → SonarQube → Docker → AWS EC2 → End User

---

## ☁️ Infrastructure Used

- EC2 Instance 1 → Jenkins (CI Server)
- EC2 Instance 2 → SonarQube (Code Analysis)
- EC2 Instance 3 → Docker (Deployment)

---

## 📂 Project Files

- index.html (sample website)
- CSS & JS files
- Dockerfile

---

## ⚙️ Actual Implementation Flow

### Step 1: GitHub Setup

- Create repository
- Upload project files (including Dockerfile)

---

### Step 2: Jenkins Setup (EC2 - 1)

- Install Jenkins using official documentation
- Access Jenkins via browser (`http://<IP>:8080`)
- Complete initial setup (plugins + admin user)

---

### Step 3: Create Jenkins Job

- Create **Freestyle Project**
- Add GitHub repository in Source Code Management
- Save configuration

---

### Step 4: Enable Auto Trigger (Webhook)

- In Jenkins:
  - Enable **GitHub hook trigger for GITScm polling**

- In GitHub:
  - Add webhook:
  - 
👉 Now pipeline runs automatically on every push

---

### Step 5: SonarQube Setup (EC2 - 2)

- Install SonarQube using official documentation
- Access via browser (`http://<IP>:9000`)
- Login and generate **token**

---

### Step 6: Connect SonarQube with Jenkins

- In Jenkins → Manage Jenkins → Configure System:
  - Add SonarQube server (URL + token)

- In Jenkins job:
  - Add **Sonar Scanner build step**

👉 Now Jenkins sends code to SonarQube for analysis

---

### Step 7: First Pipeline Execution

When you push code:

1. Jenkins pulls code from GitHub  
2. SonarQube analysis starts  
3. Quality check runs  

👉 If SonarQube is not ready → build may fail  
👉 Once Sonar is running → build succeeds  

---

### Step 8: Docker Setup (EC2 - 3)

- Install Docker using official documentation
- Ensure Docker service is running

---

### Step 9: Add Deployment Step in Jenkins

In Jenkins job:

- Add **Execute Shell** build step:

Actions performed:
- Build Docker image from Dockerfile
- Stop old container (if exists)
- Run new container

👉 This deploys the application automatically

---

### Step 10: Final Pipeline Flow

Every GitHub push triggers:

1. Jenkins pulls latest code  
2. SonarQube analyzes code  
3. Jenkins builds Docker image  
4. Container is deployed  
5. Application becomes live  

---

## 🌐 Access Application


---

## ⚠️ Real Issues Faced

- SonarQube takes time to start → caused build failures
- Jenkins stopped when system overloaded
- Incorrect Sonar URL caused connection error
- Webhook misconfiguration prevented auto trigger

---




