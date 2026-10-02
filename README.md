# Automated CI/CD Pipeline with Jenkins, Docker & AWS

## 📌 Project Overview

This project demonstrates an automated CI/CD pipeline for deploying a containerized web application using GitHub, Jenkins, Docker, and AWS EC2.

A code change pushed to GitHub automatically triggers Jenkins through a GitHub webhook. Jenkins then builds the Docker image, tests the image, and deploys the application as a Docker container on an AWS EC2 instance.

## 🏗️ Architecture

GitHub → GitHub Webhook → Jenkins → Docker Build → Test → Deploy → AWS EC2

## 🛠️ Technologies Used

- Git & GitHub
- Jenkins
- Docker
- AWS EC2
- Nginx
- Linux / Ubuntu
- Jenkins Pipeline (Jenkinsfile)

## 🔄 CI/CD Pipeline

The Jenkins pipeline contains the following stages:

1. **Checkout** — Jenkins retrieves the latest code from the GitHub `main` branch.
2. **Build Docker Image** — Builds the application Docker image.
3. **Test** — Verifies that the Docker image was created successfully.
4. **Deploy** — Removes the previous container and starts the new container.
5. **GitHub Webhook** — Automatically triggers the pipeline whenever code is pushed to GitHub.

## 🐳 Docker

The application is packaged using Docker with an Nginx Alpine base image.

The container exposes port `80`.

## ☁️ AWS Deployment

The application is deployed on an AWS EC2 Ubuntu server.

Application URL:

http://56.155.41.191

## 🚀 How the Pipeline Works

```text
Developer
    |
    | git push
    v
GitHub Repository
    |
    | Webhook
    v
Jenkins
    |
    +--> Checkout
    |
    +--> Build Docker Image
    |
    +--> Test Docker Image
    |
    +--> Deploy Container
    |
    v
AWS EC2
    |
    v
Docker Container
    |
    v
Nginx Web Application
```

## 📂 Project Structure

```text
aws-jenkins-cicd/
├── app/
│   └── index.html
├── Dockerfile
├── Jenkinsfile
└── README.md
```

## ▶️ Run Locally

Clone the repository:

```bash
git clone https://github.com/meghanayarra1110/aws-jenkins-cicd.git
cd aws-jenkins-cicd
```

Build the Docker image:

```bash
docker build -t devops-cicd-app .
```

Run the container:

```bash
docker run -d --name devops-cicd-app -p 80:80 devops-cicd-app
```

Open:

```text
http://localhost
```

## ✅ CI/CD Verification

The pipeline was successfully tested with an automatic GitHub webhook trigger.

A GitHub push automatically created Jenkins build **#8**, which completed successfully.

## 🎯 Key DevOps Concepts Demonstrated

- Source control with Git and GitHub
- CI/CD automation with Jenkins
- Jenkins Pipeline as Code
- Docker image creation
- Docker container deployment
- GitHub webhook integration
- AWS EC2 deployment
- Automated application updates
