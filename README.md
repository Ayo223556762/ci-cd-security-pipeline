# 📦 Secure CI/CD Pipeline with Automated Security Scanning and Alerting

A full CI/CD pipeline that performs automated security scans on every code push, blocks risky changes, alerts on failures, and automatically builds and deploys container images to AWS ECR. This project demonstrates real DevSecOps, Security Engineering, and SOC automation skills using modern tooling.

---

## 📌 Key Features

### 🔁 Continuous Integration (CI)

Every push triggers:

- Repository checkout  
- Docker image build  
- Trivy vulnerability scanning  
- Gitleaks secret detection  
- Custom regex based secret detection  
- Structured CI logs  
- GitHub Issue creation on failures  
- Discord webhook alerts

---

### 🚀 Continuous Deployment (CD)

When all security checks pass:

- GitHub Actions authenticates securely to AWS  
- Builds a production ready Docker image  
- Pushes the image to AWS ECR  
- Produces a deploy ready artifact for ECS or other cloud targets

This completes the CI/CD workflow: detect, validate, build, and deliver.

---

## 🛠️ Tools and Technologies Used

- GitHub Actions (CI/CD automation)  
- Docker  
- AWS ECR (container registry)  
- Python Flask  
- Trivy (vulnerability scanning)  
- Gitleaks (secret detection)  
- Discord Webhooks (alert notifications)  
- Regex based detection patterns  
- YAML pipelines

---

## 📂 Project Structure

secure-ci-security-pipeline/
│
├── app/
│ ├── app.py
│ └── requirements.txt
│
├── Dockerfile
│
└── .github/workflows/
└── sec-pipeline.yml

---

## 🔎 How the Pipeline Works

### 1. Developer Pushes Code  
Triggers the `sec-pipeline.yml` GitHub Actions workflow.

### 2. Security Scanning

- Gitleaks checks for hardcoded secrets  
- Trivy scans the container for vulnerabilities  
- Custom regex detects AWS key patterns  

If any scan fails, deployment is blocked.

---

### 3. Incident Handling (Failure Case)

- ❌ Pipeline fails  
- ❗ GitHub Issue is automatically created  
- 🚨 Discord receives an alert  
- 🔍 Simulates real SOC / engineering response workflow  

---

### 4. Continuous Deployment (Success Case)

If security checks pass:

- GitHub Actions logs into AWS  
- Builds Docker image  
- Pushes `latest` tag to AWS ECR  
- Artifact becomes deploy ready for ECS Fargate

---

## 📸 Screenshots

- Successful CI/CD run  
- Failed CI run  
- Discord alert screenshot  
- Auto created GitHub Issue  
- Trivy scan results  
- Gitleaks scan results  
- VS Code project structure  
- AWS ECR image listing

---

## 💡 Why This Project Matters

This project showcases hands-on capability in:

- DevSecOps  
- Security automation  
- CI/CD pipeline design  
- Vulnerability management  
- Secret detection  
- Cloud-ready container delivery  
- SOC alerting workflows  

Recruiters and engineers can clearly see:

- Automated guardrails  
- Secure code validation  
- Failure alerting and incident flow  
- Practical cloud deployment integration

---

## ▶️ Run Locally

docker build -t secure-ci-app .
docker run -p 5000:5000 secure-ci-app
