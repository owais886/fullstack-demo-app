# Full-Stack Demo App

This repository contains a simple **full-stack application**:

- **Backend:** Java (Maven) application
- **Frontend:** Node.js application
- **Purpose:** Demonstrate CI/CD pipelines using Jenkins with Docker agents

---

## CI/CD & DevOps Demonstration

This project demonstrates **CI/CD concepts** using **Jenkins** with **Docker agents**:

- Maven-based backend builds
- Node.js frontend builds
- Jenkinsfile with separate Docker agents for backend and frontend
- Artifact stashing and integration between stages


---

## Pipeline Overview

The `Jenkinsfile` includes:

1. **Backend stage**
   - Runs inside Maven+JDK Docker container
   - Builds Java project
   - Archives the generated JAR

2. **Frontend stage**
   - Runs inside Node.js Docker container
   - Builds frontend application
   - Archives build artifacts

3. **Integration stage**
   - Combines backend and frontend artifacts
   - Displays final artifacts in Jenkins console

---

## Screenshots


![Pipeline Overview](https://github.com/owais886/fullstack-demo-app/blob/main/Screenshots/pipeline_overview.png)  
*Jenkins pipeline stage overview*

![Backend Build Success](https://github.com/owais886/fullstack-demo-app/blob/main/Screenshots/Backend_Build_Success.png)  
*Successful Maven backend build*

![Frontend Build Success](https://github.com/owais886/fullstack-demo-app/blob/main/Screenshots/Frontend_Build_Success.png)  
*Successful Node.js frontend build*

![Integration Stage Output](https://github.com/owais886/fullstack-demo-app/blob/main/Screenshots/Integration_Stage_Output.png)  
*Integration stage showing backend and frontend artifacts*

---

## How to run locally

### Backend (Java / Maven)
Make sure you have **Java JDK 11+** and **Maven** installed.

```bash
cd backend
mvn clean package
This will compile the backend and generate a JAR under target/.

### Frontend (Node.js)
Make sure you have Node.js 16+ and npm installed.

cd frontend
npm install
npm run build


This will create a build/ folder containing frontend artifacts.

Notes

After running both, you can manually combine backend JAR and frontend build folder if you want to test the full-stack locally.