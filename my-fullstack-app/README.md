# Full-Stack Demo App

This repository contains a simple **full-stack application**:

- **Backend:** Java (Maven) application
- **Frontend:** Node.js application
- **Purpose:** Demonstrate CI/CD pipelines using Jenkins with Docker agents

## CI/CD & DevOps Demonstration

This project demonstrates CI/CD concepts using **Jenkins** with **Docker agents**:

- Maven-based Java backend builds
- Node.js frontend builds
- Jenkinsfile with separate Docker agents for backend and frontend
- Ready for CI/CD demonstration to recruiters

## Pipeline

The `Jenkinsfile` includes:

1. **Backend stage:** Runs inside Maven+JDK Docker container, builds Java project, archives JAR
2. **Frontend stage:** Runs inside Node.js Docker container, builds frontend, archives build artifacts
3. **Integration stage:** Combines backend and frontend artifacts 

## How to run locally

- **Backend:**  
cd backend
mvn clean package

- **Frontend:**

cd frontend
npm install
npm run build
