
# Graduation Project: Patient Web Interface Deployment with CI/CD

This project demonstrates the full deployment pipeline for a Flask-based patient web interface, from development to production using:

- **GitHub Actions**
- **Docker**
- **Terraform (AWS EC2 + VPC)**
- **Kubernetes (Minikube)**

---

## 📦 Project Structure

```
final_pro/
├── k8s/                  # Kubernetes manifests
├── Patient-Web-interface/
│   └── project/          # Flask app source code
├── deploy.yml            # GitHub Actions workflow
├── main.tf               # Terraform file to provision infrastructure
├── patient-app.tar       # Docker image (not tracked)
├── screenshots/          # Project screenshots
└── README.md             # This file
```

---

## 🚀 Pipeline Overview

1. **GitHub Actions**:
   - On every push to main branch, a Docker image is built and pushed to DockerHub.

2. **Terraform**:
   - Provisions an AWS EC2 instance, VPC, and subnet.
   - SSH access is used to install Docker, Minikube, kubectl.

3. **Minikube + Kubernetes**:
   - Docker image is loaded into Minikube.
   - App is deployed using `Deployment` and `Service` YAML files.
   - Access is done via `kubectl port-forward`.

---

## 🧪 Screenshots

### ✅ GitHub Actions CI/CD

![CI/CD](screenshots/github-actions-success.png)

### ✅ Docker Image Build

![Docker Build](screenshots/docker-build.png)

### ✅ Terraform Provisioning EC2

![Terraform](screenshots/terraform-provision.png)

### ✅ Kubernetes Deployment

![K8s Deploy](screenshots/k8s-deploy.png)

### ✅ Flask App Running

![Flask App](screenshots/flask-app.png)

---

## 💡 Notes

- Make sure to run `eval $(minikube docker-env)` **before** building or loading Docker images.
- Use `kubectl port-forward` to access the app on localhost.
- You can use Git Large File Storage (LFS) if needed to handle large files like `patient-app.tar`.

---

## 🔗 Author

- GitHub: [Mousv99](https://github.com/Mousv99)


