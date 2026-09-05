# Lauris Neimanis — Senior Platform & Cloud Infrastructure Engineer

**AWS Certified Solutions Architect – Professional · AWS · Terraform/Terragrunt · Kubernetes · ECS · GitOps · Linux · Observability**

I design, modernize, automate, and operate business-critical infrastructure across AWS, hybrid cloud, and on-premises environments.

My strongest value is **long-term infrastructure ownership**: architecture, infrastructure as code, platform engineering, reliability, observability, security, controlled change, and pragmatic modernization.

I bring **16+ years of hands-on infrastructure experience**, combining a strong Linux and networking foundation with modern AWS, containers, Kubernetes, infrastructure as code, and platform engineering.

---

## Target Roles

The strongest fit is a senior or lead role where infrastructure architecture, reliability, platform ownership, and pragmatic modernization matter:

* Senior / Lead Platform Engineer
* Senior Cloud Infrastructure Engineer
* Cloud / Infrastructure Architect
* Senior Site Reliability Engineer

---

## Certifications

* **AWS Certified Solutions Architect – Professional** — [verify on Credly](https://www.credly.com/badges/1faf5a74-6995-42b1-8965-4dabf1ab4cc3/public_url)
* AWS Certified Solutions Architect – Associate — [verify on Credly](https://www.credly.com/badges/d82e5b66-b13b-4a82-a258-4be92cd811f8)

---

## Production Infrastructure Experience

My production engineering experience spans long-lived AWS, hybrid-cloud, and on-premises environments where reliability, recovery, security, and maintainability matter.

Representative areas include:

* AWS infrastructure architecture and operations across networking, compute, containers, storage, databases, messaging, identity, and observability
* Terraform modules and Terragrunt-based multi-environment infrastructure composition
* ECS Fargate and ECS-on-EC2 application platforms
* Kubernetes platform engineering across EKS, AKS, Helm, GitOps, scheduling, and autoscaling
* Reusable web, worker, scheduled-task, and multi-container delivery patterns
* GitLab CI/CD, GitHub Actions, controlled releases, rollback, and environment-isolated workflows
* Ansible, Bash, Python, cloud-init, and Linux automation
* Production observability using Grafana, Prometheus, Mimir, Loki, Alloy, and CloudWatch
* Managed databases, caches, queues, shared storage, object storage, and supporting platform services
* Network segmentation, VPN connectivity, ingress/egress control, private service access, and security hardening
* Infrastructure controls for regulated and PCI DSS environments
* Production troubleshooting, root cause analysis, incident response, capacity planning, and preventive engineering
* Backup, restore, disaster recovery, migration, and recovery planning
* Staged modernization from legacy and containerized environments toward Kubernetes where operationally justified

My container-platform experience spans both **ECS and Kubernetes**, combining production operations with hands-on EKS and AKS platform engineering.

---

## What I Bring

* **Production ownership:** uptime, recovery, incidents, capacity, audits, and operational consequences are design inputs, not afterthoughts.
* **Platform thinking:** infrastructure, platform services, delivery workflows, and application workloads have clear ownership boundaries.
* **Architecture with operational context:** designs account for failure modes, maintainability, migration paths, and day-two operations.
* **Pragmatic modernization:** I prefer staged and reversible improvements over large rewrites that introduce unnecessary operational risk.
* **Infrastructure as Code discipline:** state, locking, module boundaries, dependency drift, validation, and reproducibility are treated as engineering concerns.
* **Reliability focus:** observability, backups, access control, recovery, and failure handling are built into infrastructure design.
* **Strong Linux and networking foundation:** I am comfortable working below cloud and orchestration abstractions when diagnosing production systems.

---

## Public Reference Work

The repositories below are public reference implementations.

They are intentionally scoped to demonstrate **architecture, platform ownership boundaries, delivery patterns, reliability practices, and operational reasoning** without exposing non-public production systems.

| Project                                                                               | What it demonstrates                                                     | Technologies                                   |
| ------------------------------------------------------------------------------------- | ------------------------------------------------------------------------ | ---------------------------------------------- |
| [AWS EKS Platform](https://github.com/LaurisNeimanis/aws-eks-platform)                | AWS infrastructure foundation for EKS                                    | Terraform, EKS, VPC, IAM, ACM                  |
| [AWS EKS GitOps](https://github.com/LaurisNeimanis/aws-eks-gitops)                    | Platform and workload delivery above the cluster boundary                | Argo CD, ApplicationSets, Helm, Kustomize      |
| [Karpenter Platform](https://github.com/LaurisNeimanis/gitops-karpenter-platform)     | Platform-owned capacity, scheduling, cost, and disruption model          | Karpenter, Spot/On-Demand, ARM64, GitOps       |
| [Autoscaling Platform](https://github.com/LaurisNeimanis/gitops-autoscaling-platform) | Governed workload scaling as platform policy                             | HPA, KEDA, Kyverno, Argo CD                    |
| [Observability Stack](https://github.com/LaurisNeimanis/gitops-observability-stack)   | GitOps-managed metrics, logs, dashboards, and alerting                   | Prometheus, Alertmanager, Grafana, Loki, Alloy |
| [Azure AKS Platform](https://github.com/LaurisNeimanis/azure-aks-platform)            | Azure infrastructure foundation using the same platform principles       | Terraform, AKS, VNet, Managed Identity         |
| [Infrastructure Automation](https://github.com/LaurisNeimanis/ccore-ai-infra)         | End-to-end AWS provisioning and server bootstrap reference stack         | Terraform, Ansible, cloud-init, Docker         |
| [Application Demo](https://github.com/LaurisNeimanis/ccore-ai-demo)                   | Application stack used to validate infrastructure and delivery workflows | FastAPI, Streamlit, Docker, GHCR               |

### Supporting Repositories

| Repository                                                                                        | Purpose                                                       | Technologies             |
| ------------------------------------------------------------------------------------------------- | ------------------------------------------------------------- | ------------------------ |
| [AWS Terraform Backend Bootstrap](https://github.com/LaurisNeimanis/aws-tf-backend-bootstrap)     | Shared S3 remote-state backend bootstrap with native locking  | Terraform, AWS S3        |
| [Azure Terraform Backend Bootstrap](https://github.com/LaurisNeimanis/azure-tf-backend-bootstrap) | Azure Blob remote-state backend bootstrap with native locking | Terraform, Azure Storage |

---

## Platform Architecture Model

```text
Terraform infrastructure
        ↓
Kubernetes cluster foundation
        ↓
Capacity and scheduling layer
        ↓
Autoscaling and policy layer
        ↓
GitOps reconciliation
        ↓
Platform services
        ↓
Application workloads
```

The model is intentionally layered:

* **Infrastructure** is provisioned through Terraform and cloud-native APIs.
* **Capacity and scheduling** are platform concerns rather than application concerns.
* **Autoscaling behavior** is governed through reusable and controlled policies.
* **GitOps reconciliation** provides reviewable and reproducible desired-state changes.
* **Platform services** are managed independently from application workloads.
* **Workloads** express runtime requirements without owning infrastructure implementation details.

The same principle applies to production engineering: **define clear contracts between layers so systems remain understandable, auditable, recoverable, and maintainable as they grow.**

---

## Selected Project Details

### AWS EKS Platform

**Terraform · AWS · EKS · IAM · Networking · ACM · Cloudflare**

A production-aligned AWS EKS infrastructure foundation focused on deterministic networking, controlled cluster access, and clear infrastructure/platform/workload boundaries.

Highlights:

* Explicit VPC, subnet, routing, NAT, and security topology
* EKS Managed Node Groups using Amazon Linux 2023
* IAM-native Kubernetes access through the EKS Access API
* EKS Pod Identity for workload identity
* ACM certificate automation with Cloudflare DNS validation
* Shared S3 Terraform backend with native locking
* Infrastructure-only scope with GitOps and workloads managed independently

Repository: https://github.com/LaurisNeimanis/aws-eks-platform

### AWS EKS GitOps

**Argo CD · GitOps · Kubernetes · Helm · Kustomize · ApplicationSets**

A production-aligned GitOps delivery layer for platform services and workloads above an existing EKS infrastructure boundary.

Highlights:

* Out-of-band Argo CD control plane
* App-of-Apps bootstrap pattern
* ApplicationSets for repeatable onboarding
* Helm and Kustomize-based delivery
* Clear separation between platform services and workloads
* Git as the source of truth for desired Kubernetes state

Repository: https://github.com/LaurisNeimanis/aws-eks-gitops

### Karpenter Platform

**Karpenter · Kubernetes · GitOps · AWS · Platform Engineering**

A platform-owned capacity and scheduling layer for EKS.

The platform owns node architecture, cost, capacity type, consolidation, and disruption while workloads express resource requirements without controlling infrastructure details.

Highlights:

* Explicit scheduling profiles for managed, On-Demand, and Spot capacity
* ARM64-first capacity strategy
* Separation between bootstrap/system capacity and workload capacity
* GitOps-managed NodePools and EC2NodeClasses
* Deterministic consolidation and disruption policies
* Documented platform and workload ownership boundaries

Repository: https://github.com/LaurisNeimanis/gitops-karpenter-platform

### Autoscaling Platform

**Kubernetes · HPA · KEDA · Kyverno · GitOps**

A governed autoscaling policy layer where workloads select approved scaling profiles while the platform owns limits, validation, and safety.

Highlights:

* Platform-owned HPA and KEDA profiles
* Event-driven scaling and scale-to-zero patterns
* Kyverno admission-time validation
* Namespace-level enablement controls
* Separation of autoscaling, capacity, and application concerns
* Argo CD-managed reconciliation

Repository: https://github.com/LaurisNeimanis/gitops-autoscaling-platform

### Observability Stack

**Prometheus · Alertmanager · Grafana · Loki · Alloy · Argo CD**

A GitOps-managed Kubernetes observability platform focused on metrics, logs, dashboards, alerting, and operational feedback loops.

Highlights:

* Prometheus Operator with controlled CRD lifecycle
* Alertmanager routing and noise reduction
* Loki with object storage
* Grafana dashboards and data sources
* Grafana Alloy for telemetry collection
* Argo CD-managed desired state

Repository: https://github.com/LaurisNeimanis/gitops-observability-stack

### Azure AKS Platform

**Terraform · Azure · AKS · Networking · Managed Identity**

A production-aware AKS infrastructure foundation built around the same ownership and lifecycle principles as the AWS EKS implementation.

Highlights:

* Explicit Resource Group, VNet, and AKS subnet boundaries
* AKS with a VMSS-backed system node pool
* Kubernetes RBAC
* Managed Identity
* Azure Blob Terraform backend with native locking
* CI-enforced formatting, linting, validation, and security checks
* Infrastructure-only scope with GitOps and workloads managed separately

Repository: https://github.com/LaurisNeimanis/azure-aks-platform

### Infrastructure Automation Stack

**Terraform · Ansible · AWS · cloud-init · Docker · CI/CD**

A production-inspired reference stack showing provisioning, bootstrap, configuration management, and application runtime automation in one repository.

Highlights:

* Modular Terraform with explicit environment separation
* cloud-init-based bootstrap
* Automatically generated Ansible inventory
* Idempotent Ansible roles and templates
* Docker-based application runtime
* CI validation for Terraform and Ansible

Repository: https://github.com/LaurisNeimanis/ccore-ai-infra

### Application Demo

**FastAPI · Streamlit · Docker · GHCR · CI/CD**

A small application stack used to validate container builds, artifact publishing, infrastructure automation, and application delivery workflows.

Highlights:

* Independent Dockerfiles for API and UI services
* GHCR-based multi-architecture image builds
* Pre-built images consumed by infrastructure automation
* Clear separation between UI, API, and data concerns

Repository: https://github.com/LaurisNeimanis/ccore-ai-demo

---

## Core Technical Areas

### Cloud Infrastructure

* **AWS:** networking, compute, ECS, EKS, IAM, load balancing, managed databases, storage, messaging, observability, security, and recovery architecture
* **Azure:** Virtual Networks, AKS, Managed Identity, Azure CNI, load balancing, and supporting infrastructure
* Hetzner Cloud and Scaleway
* Proxmox, VMware, Citrix XenServer, ZFS, storage, Linux networking, and virtualization

### Infrastructure as Code

* Terraform modules and reusable multi-environment infrastructure
* Terragrunt composition and dependency management
* Remote state, locking, imports, refactoring, and drift control
* Provider and dependency version discipline
* CI validation, linting, security scanning, and infrastructure validation
* Separation between bootstrap infrastructure and long-lived state

### Containers, Kubernetes & Platform Engineering

* Docker, ECS, Kubernetes, EKS, and AKS
* Helm, Argo CD, ApplicationSets, and Kustomize
* Platform/workload ownership boundaries
* Karpenter-based capacity management
* HPA, KEDA, and policy-driven autoscaling
* RBAC, workload identity, admission policies, and GitOps reconciliation

### Delivery & Automation

* GitLab CI/CD and GitHub Actions
* Review-driven delivery and controlled release workflows
* Ansible roles, inventories, templates, and idempotent automation
* cloud-init bootstrapping
* Bash and Python automation
* ECR, GHCR, and container image delivery workflows

### Reliability, Observability & Operations

* Metrics, logs, dashboards, alerting, and incident investigation
* Prometheus, Grafana, Mimir, Loki, Alloy, Alertmanager, and CloudWatch
* Root cause analysis and preventive engineering
* Backup, restore, disaster recovery, and recovery planning
* Capacity and performance troubleshooting
* Production database and storage operations

### Security & Networking

* VPC/VNet architecture, routing, NAT, load balancing, and DNS
* VPN and private connectivity
* Network segmentation and ingress/egress controls
* Least-privilege access and workload identity
* Hardened Linux baselines
* Regulated-environment and PCI DSS infrastructure controls

---

## Engineering Principles

* Prefer explicit and understandable systems over clever abstractions.
* Keep infrastructure, platform, delivery, and workload concerns separate.
* Design for predictable failure modes and practical recovery paths.
* Treat day-two operations as part of architecture.
* Use automation to reduce operational risk rather than hide complexity.
* Pin dependencies and validate drift where reproducibility matters.
* Treat observability as a decision-support system, not only monitoring.
* Prefer staged and reversible modernization.
* Optimize for systems that remain maintainable after the original builder leaves.

---

## Contact

* **LinkedIn:** https://www.linkedin.com/in/lauris-neimanis
* **Email:** [neimanis.lauris@gmail.com](mailto:neimanis.lauris@gmail.com)
* **Location:** Latvia
