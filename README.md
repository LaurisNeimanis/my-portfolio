# Lauris Neimanis — Senior Infrastructure & Platform Engineer (Cloud & Kubernetes)

## AWS • Kubernetes • Terraform • GitOps • Platform Engineering • Networking • Reliability

I design and operate **production-grade cloud and platform systems** with a strong focus on **operability**, **clear ownership boundaries**, and **long-term sustainability**.

My work prioritizes:
- architectural clarity over clever abstractions
- automation over manual intervention
- systems that remain understandable as teams, environments, and workloads scale

I approach infrastructure and platforms as **long-lived internal products**, not one-off deliveries.

15+ years of hands-on experience owning infrastructure and platforms
across cloud, hybrid cloud, and on-prem environments,
including AWS, Hetzner Cloud, Scaleway,
and on-prem virtualization platforms such as Proxmox, VMware, and Citrix XenServer.

---

## 🧠 Architectural Approach

I regularly operate at a scope that spans multiple teams, environments, and long-lived platforms.

I design systems to survive **growth, failure, and team turnover**.

### Core principles
- Explicit, boring architectures over hidden complexity
- Early separation of concerns to avoid accidental coupling
- Predictable failure modes and recovery paths
- Opinionated defaults before optional flexibility
- Git as the single source of truth
- Infrastructure and platforms treated as internal products with contracts

### Non-goals
- Novelty for novelty’s sake
- Tight coupling between infrastructure and delivery layers
- Platforms that hide failure modes instead of exposing them

---

## 🔥 Core Capabilities

### Infrastructure Architecture
Designing infrastructure with explicit ownership, security as a baseline, and deterministic behavior.

- AWS VPC design, routing, subnetting, and security boundaries
- Hybrid and multi-cloud setups (AWS + Hetzner + Scaleway)
- Proxmox virtualization, ZFS storage, snapshot strategies
- API-driven infrastructure and platform integration patterns
- Trade-off driven architectural decision-making

---

### Infrastructure as Code
Building reproducible and auditable infrastructure foundations.

- Terraform modules and multi-environment stacks
- Remote state, locking, and drift control
- cloud-init based bootstrapping
- Clear separation between one-time bootstrap and long-lived state

---

### Configuration & Automation
Reducing operational load through deterministic automation.

- Ansible roles for Docker, networking, and platform services
- Zero-manual provisioning workflows
- Idempotent, modular automation patterns

---

### Container Platforms
Delivering immutable artifacts with clear promotion paths.

- Docker Engine and Compose stacks
- GHCR-based immutable images
- GitHub Actions CI pipelines
- GitOps-based CD via Argo CD

---

### Kubernetes
Operating Kubernetes clusters with a focus on reliability, controlled change, and operational clarity.

- Ingress controllers, service networking, RBAC
- Helm-based delivery
- Controlled access models and upgrades
- Explicit platform vs workload separation with enforced ownership boundaries

---

### Networking & Security
Designing secure-by-default network models.

- VPCs, routing, firewalls
- WireGuard-based private access
- Least-privilege access boundaries
- Hardened Linux baselines

---

### Reliability & Observability
Operating platforms with feedback loops and recovery paths.

- Metrics, logs, dashboards, and alerting
- Metrics-driven debugging
- Backup and restore strategies
- High-ownership incident handling

---

# ⭐ Featured Projects

## AWS EKS Platform Infrastructure Foundation
**Terraform · AWS · EKS · IAM · Networking · ACM · Cloudflare**

A production-aligned **AWS EKS infrastructure foundation** focused on clear ownership boundaries, deterministic networking, and API-only cluster access.

This repository defines the **authoritative infrastructure layer only** and intentionally excludes platform services and workloads.

**Highlights**
- Explicit VPC, subnet, routing, and NAT topology
- EKS with Managed Node Groups (Amazon Linux 2023)
- IAM-native Kubernetes authentication (EKS Access API)
- IRSA-based access model
- Automated ACM certificates with Cloudflare DNS validation
- Shared, pre-bootstrapped Terraform backend (S3 + DynamoDB)

Repo: https://github.com/LaurisNeimanis/aws-eks-platform

---

## GitOps Karpenter Platform — Capacity & Scheduling Layer
**Karpenter · Kubernetes · GitOps · AWS · Platform Engineering**

A production-aligned **capacity and scheduling platform** for EKS,  
formalizing **ownership boundaries between infrastructure, platform, and workloads**.

This repository defines a **platform-owned capacity and scheduling layer** where:
- the platform owns node architecture, cost, and disruption
- workloads express intent only (CPU / memory)

It intentionally removes per-workload infrastructure coupling
and replaces it with **explicit, GitOps-managed scheduling profiles**.

**Highlights**
- Platform-owned capacity decisions (on-demand vs spot)
- Explicit scheduling profiles (`managed-on-demand`, `karpenter-on-demand`, `karpenter-spot`)
- ARM64-first capacity strategy driven by cost-efficiency and long-term sustainability,
enforced at the platform layer via architecture-aware NodePools
- Clear separation between bootstrap/system capacity and workload capacity
- GitOps-managed Karpenter configuration (NodePools, EC2NodeClasses)
- Deterministic consolidation and disruption policies
- Architecture-aligned documentation and diagrams

Repo: https://github.com/LaurisNeimanis/gitops-karpenter-platform

---

## AWS EKS GitOps Delivery Layer
**Argo CD · GitOps · Kubernetes · Helm · ApplicationSets**

A production-grade **GitOps delivery layer** managing everything **above the infrastructure boundary**.

Designed for safe change management, scalability across teams, and long-lived platform operation.

**Highlights**
- Out-of-band Argo CD control plane
- App-of-Apps bootstrap pattern
- ApplicationSets for scalable onboarding
- Clear separation between platform services and workloads
- Git as the single source of truth

Repo: https://github.com/LaurisNeimanis/aws-eks-gitops

---

## Kubernetes Observability Stack (GitOps)
**Prometheus · Alertmanager · Grafana · Loki · Alloy · GitOps**

A production-grade **observability platform** designed as a GitOps-managed internal product.

Focused exclusively on Kubernetes and platform reconciliation, with infrastructure treated as an external dependency.

**Highlights**
- Prometheus Operator with explicit CRD lifecycle management
- Alertmanager routing with noise suppression and separation of concerns
- Loki single-binary setup with object storage
- Grafana Alloy for unified log collection
- Fully GitOps-managed via Argo CD

Repo: https://github.com/LaurisNeimanis/gitops-observability-stack

---

## Infrastructure Automation Stack (ccore-ai-infra)
**Terraform · Ansible · AWS · cloud-init · Docker**

An end-to-end **infrastructure automation stack** demonstrating full lifecycle ownership from provisioning to application runtime.

**Highlights**
- Modular Terraform with clear environment separation
- cloud-init based bootstrapping
- Auto-generated Ansible inventory
- Idempotent Ansible roles
- Zero-manual provisioning workflow

Repo: https://github.com/LaurisNeimanis/ccore-ai-infra

---

## Application Architecture Demo (ccore-ai-demo)
**FastAPI · Streamlit · Docker · GHCR · CI/CD**

A backend–frontend demo showcasing immutable artifacts and clean service boundaries.

**Highlights**
- Independent Dockerfiles per service
- GHCR-based immutable image builds
- Zero build steps in production
- Clear separation between UI, API, and data layer

Repo: https://github.com/LaurisNeimanis/ccore-ai-demo

---

# 🌿 Kubernetes Platform & GitOps Flow

```
Terraform → AWS (VPC, EKS)
                     ↓
        Platform Capacity & Scheduling Layer (Karpenter)
                     ↓
            Argo CD (out-of-band GitOps control plane)
                     ↓
              ApplicationSets
                     ↓
        Platform Services (Ingress, DNS, Observability)
                     ↓
            Application Workloads
```

This flow demonstrates a clear separation between infrastructure provisioning,
out-of-band GitOps control, cluster-level platform management, and application delivery.

---

# 🌐 Cloud & Platform Experience

- **AWS:** VPC, EC2, S3, IAM, IGW, EKS, NLB, ACM
- **Hetzner Cloud:** networks, firewalls, IaC-driven provisioning
- **Scaleway:** compute, managed Kubernetes
- **On‑prem:** Proxmox, ZFS, virtualization
- **Networking:** routing, WireGuard-based private access, minimal attack surface

---

# 🧠 Current Focus Areas

- Scaling GitOps platforms across teams and environments (Argo CD, ApplicationSets)
- Defining platform standards and self-service boundaries without sacrificing operational control
- Terraform workflows for multi-environment and multi-team organizations
- Observability as a decision-support system, not just monitoring
- SRE-oriented automation focused on failure reduction, recovery, and operability

---

# 📌 Contact

**LinkedIn:** https://www.linkedin.com/in/lauris-neimanis  
**Email:** neimanis.laur@gmail.com  
**Location:** Latvia
