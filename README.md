

# 🚀 Frontend DevOps CI/CD Project (GitHub → AWS → Kubernetes → ArgoCD)

This project demonstrates an **end-to-end DevOps and GitOps pipeline** for deploying a simple frontend application using modern cloud-native tools.

The application is automatically built, containerized, pushed to AWS ECR, and deployed to Kubernetes using ArgoCD.

---

## 📌 Project Overview

* Static frontend (Google-like search page)
* Automated CI using **GitHub Actions**
* Docker image stored in **AWS ECR**
* Deployed to **Kubernetes (EKS)**
* Managed using **ArgoCD (GitOps)**
* Exposed using **AWS LoadBalancer**

---

## 🏗️ Architecture Flow

```
Developer
  ↓
GitHub Repository
  ↓
GitHub Actions (CI)
  ↓
Docker Image
  ↓
AWS ECR
  ↓
ArgoCD (GitOps CD)
  ↓
Kubernetes Deployment
  ↓
LoadBalancer Service
  ↓
Browser Access
```


## 🧰 Tools & Technologies Used

* **GitHub** – Source code management
* **GitHub Actions** – CI/CD automation
* **Docker** – Containerization
* **AWS ECR** – Docker image registry
* **Kubernetes (EKS)** – Container orchestration
* **ArgoCD** – GitOps continuous delivery
* **Nginx** – Web server
* **HTML** – Frontend application

---

## ⚙️ CI/CD Workflow (GitHub Actions)

1. Developer pushes code to the `main` branch
2. GitHub Actions workflow triggers automatically
3. Docker image is built from the Dockerfile
4. Image is tagged and pushed to AWS ECR

> CI is fully automated — no manual intervention required.

---

## 🔁 GitOps Deployment with ArgoCD

* ArgoCD continuously monitors this GitHub repository
* Kubernetes manifests are stored in the `k8s/` directory
* Any change in GitHub is automatically applied to the cluster
* GitHub acts as the **single source of truth**

### Benefits of ArgoCD

* Automatic deployments
* Self-healing Kubernetes resources
* Easy rollback using Git history
* Production-grade GitOps workflow

---

## 🐳 Docker Configuration

### Dockerfile

```dockerfile
FROM nginx:alpine
COPY index.html /usr/share/nginx/html/index.html
EXPOSE 80
```

---

## ☸️ Kubernetes Deployment

* **Deployment** manages application pods
* **Service (LoadBalancer)** exposes the app publicly
* Kubernetes pulls the Docker image securely from AWS ECR

Access the application via:

```
http://<EXTERNAL-IP>
```

---

## 🔐 Security Practices

* AWS credentials stored securely in **GitHub Secrets**
* No hard-coded secrets in the repository
* Private ECR image access
* Git-based deployment using ArgoCD




