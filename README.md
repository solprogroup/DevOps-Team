# Bejite DevOps

This repository contains the **DevOps workflows, automation, and infrastructure code** for the [Bejite Project].

## 🚀 Purpose
The goal of this repository is to centralize and manage:
- **CI/CD Pipelines** (build, test, deploy)
- **Infrastructure as Code (IaC)**
- **Monitoring and Deployment Configurations**

This ensures developers can focus on building features, while DevOps handles automation and reliability.

---

## ⚙️ Current Workflows

### Frontend CI Pipeline
- Location: `.github/workflows/frontend-ci.yml`
- Trigger: Runs on every push or pull request to `main`
- Steps:
  1. **Checkout Frontend Repo** → pulls code from [`Ochaworldwide/Bejite`] 
  2. **Install Dependencies** → `npm install`  
  3. **Build Project** → `npm run build`  
  4. *(Optional)* Run tests (`npm test`) if/when added  

The build output can later be uploaded as an artifact or deployed to hosting.

---

## 🏗️ Infrastructure (Planned)

The following will be introduced incrementally:
- **Dockerization** of frontend and backend services
- **Terraform** for infrastructure provisioning (e.g., AWS EC2, S3, networking)
- **Ansible** or **Kubernetes** for configuration management and orchestration
- **NGINX** as a reverse proxy and load balancer
- **Continuous Deployment** to staging and production environments

---

## 📌 Roadmap
- [x] Set up CI pipeline for frontend  
- [ ] Add linting & test stages  
- [ ] Dockerize frontend app  
- [ ] Provision cloud infrastructure with Terraform  
- [ ] Deploy to staging environment  
- [ ] Add monitoring & logging  

---

## 🔑 Notes
- The **frontend codebase** lives in a separate repository: [`Ochaworldwide/Bejite`](https://github.com/Ochaworldwide/Bejite).  
- This DevOps repo pulls the frontend repo during CI runs for build & test.  
- Secrets (if needed later) should be stored in **GitHub Actions Secrets**, not hardcoded.

---

## 👨‍💻 Maintainers
- DevOps Engineers:
- Bejite Development Team

## Run locally:
- docker compose -f docker-compose.local.yml up --build
- CI/CD runs automatically with docker-compose.ci.yml