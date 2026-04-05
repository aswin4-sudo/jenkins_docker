 # 🚀 CI/CD Pipeline using Jenkins, SonarQube, Docker & AWS

## 📌 Overview

This project demonstrates a complete CI/CD pipeline for a sample web application using:

- GitHub for source code management
- Jenkins for continuous integration
- SonarQube for code quality analysis
- Docker for containerization
- AWS EC2 for deployment

The pipeline is automatically triggered using GitHub webhooks.

---

## 🧱 Architecture

GitHub → Jenkins → SonarQube → Docker → AWS EC2 → End User

---

## ☁️ Infrastructure

Three AWS EC2 instances are used:

- Jenkins Server
- SonarQube Server
- Docker Deployment Server

---

## 📂 Repository Contents

- HTML, CSS, JavaScript files (sample website)
- Dockerfile for containerization

---

## ⚙️ Setup Process

### 1. GitHub

- Create a repository
- Push the application code

---

### 2. Jenkins Setup (CI Server)

- Install Jenkins by following the official documentation:  
  https://www.jenkins.io/doc/book/installing/

- Access Jenkins via browser:  
  `http://<JENKINS_PUBLIC_IP>:8080`

- Complete initial setup:
  - Install suggested plugins
  - Create admin user

- Create a Freestyle Project
- Configure GitHub repository
- Enable build trigger using GitHub webhook

---

### 3. GitHub Webhook Configuration

- Go to repository → Settings → Webhooks
- Add webhook URL:
- 
- This enables automatic pipeline execution on every code push

---

### 4. SonarQube Setup (Code Analysis)

- Install SonarQube using official documentation:  
  https://docs.sonarqube.org/latest/setup/install-server/

- Access SonarQube via browser:  
  `http://<SONAR_PUBLIC_IP>:9000`

- Generate authentication token

- In Jenkins:
  - Configure SonarQube server
  - Add SonarScanner in build steps

---

### 5. Docker Setup (Deployment)

- Install Docker using official documentation:  
  https://docs.docker.com/engine/install/

- Use Dockerfile from repository to build image

- Configure Jenkins job to:
  - Build Docker image
  - Run container
  - Deploy application

---

## 🔄 Pipeline Flow

1. Developer pushes code to GitHub  
2. GitHub webhook triggers Jenkins  
3. Jenkins pulls latest code  
4. SonarQube analyzes code quality  
5. Jenkins builds Docker image  
6. Application is deployed using Docker  
7. End user accesses application  

---

## 🌐 Access Application

