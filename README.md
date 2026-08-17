# 🚀 Production-Grade DevOps Platform on AWS EKS

An end-to-end DevOps and GitOps project demonstrating infrastructure provisioning, CI/CD, containerization, Kubernetes deployment, AWS Load Balancing, GitOps automation, and security scanning using modern DevOps tools.

The project deploys a microservices-based application on **Amazon EKS**, with infrastructure provisioned using **Terraform**, CI automation using **GitHub Actions**, container images stored in **Docker Hub**, and continuous deployment managed through **Argo CD**.

---

## 📌 Project Overview

This project demonstrates a complete DevOps workflow:

Developer Code
      ↓
GitHub
      ↓
Pull Request
      ↓
GitHub Actions CI
      ↓
Build + Unit Test + Code Quality
      ↓
Docker Build
      ↓
Trivy Security Scan
      ↓
Docker Hub
      ↓
Update Kubernetes Manifest
      ↓
Argo CD
      ↓
Amazon EKS
      ↓
AWS Application Load Balancer
      ↓
Application

---

## 🏗️ Architecture

The platform consists of:

- AWS VPC
- Public and Private Subnets
- Internet Gateway
- NAT Gateways
- Amazon EKS
- Managed Worker Nodes
- AWS IAM
- AWS Load Balancer Controller
- Application Load Balancer
- Route 53
- Kubernetes
- Docker
- GitHub Actions
- Argo CD
- Trivy
- SonarQube
- Prometheus & Grafana

---

## 🛠️ Technology Stack

| Technology | Purpose |
|---|---|
| AWS | Cloud platform |
| Terraform | Infrastructure as Code |
| Amazon EKS | Managed Kubernetes cluster |
| Kubernetes | Container orchestration |
| Docker | Application containerization |
| Docker Hub | Container image registry |
| GitHub | Source code management |
| GitHub Actions | CI automation |
| Argo CD | GitOps continuous deployment |
| AWS ALB Controller | Kubernetes ingress/load balancing |
| Route 53 | DNS management |
| Trivy | Container vulnerability scanning |
| SonarQube | Source code quality analysis |
| Prometheus | Metrics collection |
| Grafana | Monitoring dashboards |

---

# ☁️ AWS Infrastructure

AWS infrastructure is provisioned using Terraform.

The Terraform configuration creates:

- Custom VPC
- Public subnets
- Private subnets
- Internet Gateway
- NAT Gateways
- Route Tables
- IAM roles
- Amazon EKS cluster
- EKS Managed Node Group

The Kubernetes worker nodes are deployed in **private subnets**, while public subnets are available for internet-facing AWS load balancers.

---

## Terraform Remote State

Terraform state is stored remotely using an **Amazon S3 backend**.

S3 versioning and server-side encryption are enabled to improve state protection and recovery.

This allows Terraform infrastructure state to be managed centrally rather than storing `terraform.tfstate` locally.

---

# ☸️ Amazon EKS

The application runs on an Amazon EKS cluster.

Cluster:

```text
my-eks-cluster
