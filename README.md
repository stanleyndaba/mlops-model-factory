#  Model Factory — End-to-End MLOps CI/CD Pipeline

**Production-grade MLOps pipeline** that automates the **training, testing, validation, deployment, and monitoring** of machine learning models — with CI/CD, rollback safety, and IaC-driven infrastructure.

---

##  Overview

Model Factory is a modular MLOps pipeline that enables:
- **Push-to-train** workflows
- **Validation gates**
- **Auto-deploy to staging/prod**
- **Live performance monitoring**
- **Rollback on failure**

> Built for high-frequency ML environments where models are deployed, updated, and evaluated continuously with complete reproducibility and safety.

---

##  Tech Stack

| Layer               | Tool / Framework             |
|---------------------|------------------------------|
| CI/CD Orchestration | Jenkins / GitHub Actions     |
| Experiment Tracking | MLflow                       |
| Deployment Platform | Kubernetes                   |
| Monitoring          | Prometheus + Grafana         |
| Infrastructure      | Terraform (IaC)              |
| Model Storage       | S3-compatible / MLflow Registry |

---

##  Key Features

-  **Git Push → Train → Validate → Deploy**
-  **Staging & Production Environments**
-  **Model Versioning + Metadata (MLflow)**
-  **Validation Gates (test coverage, accuracy threshold)**
-  **Rollback Support (if performance drops)**
-  **Prometheus Monitoring Dashboards**
-  **IaC Terraform Scripts for Cluster/Storage Setup**

---

##  Pipeline Diagram

```mermaid
graph TD
    A[Git Push] --> B[Jenkins Pipeline Trigger]
    B --> C[Model Training Script]
    C --> D[Model Validation Stage]
    D -->|Pass| E[Deploy to Staging]
    E --> F[Manual/Auto Promote to Production]
    F --> G[Prometheus Monitoring]
    D -->|Fail| H[Notify + Rollback to last stable]

