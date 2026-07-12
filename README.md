# Lauris Neimanis — Senior DevOps & Platform Engineer

**AWS Certified Solutions Architect – Associate · Terraform/Terragrunt · AWS · ECS · Kubernetes · GitOps · Ansible · Linux · Observability**

I design, modernize, automate, and operate business-critical infrastructure across AWS, hybrid cloud, and on-premises environments.

My strongest value is long-term infrastructure ownership: taking systems from manual or inconsistent operations toward clear architecture, repeatable delivery, reliable observability, controlled change, and maintainable platform standards.

I have **16+ years of hands-on experience** across production infrastructure, B2B consulting, public-sector systems, and product-company environments.

---

## Target Roles

The strongest fit is a senior role where infrastructure reliability, platform ownership, and pragmatic modernization matter:

- Senior DevOps Engineer
- Senior Platform Engineer
- Infrastructure Architect
- Cloud Infrastructure Engineer
- SRE-oriented Infrastructure / Platform role

---

## Certification

- **AWS Certified Solutions Architect – Associate** — [verify on Credly](https://www.credly.com/badges/d82e5b66-b13b-4a82-a258-4be92cd811f8)

---

## Production Engineering Experience

My production engineering experience includes:

- AWS and hybrid infrastructure ownership across long-lived environments
- Terraform modules and Terragrunt environment composition
- ECS Fargate and ECS-on-EC2 application platforms
- Reusable web, worker, scheduled-task, and multi-container delivery patterns
- CI/CD, controlled releases, rollback, and environment-isolated review workflows
- Ansible, Bash, Python, and Linux automation
- Metrics, logs, dashboards, alerting, and operational feedback loops
- Managed databases, queues, cache, shared storage, object storage, and supporting platform services
- Regulated-environment infrastructure controls: segmentation, logging, hardening, recovery, and audit readiness
- Production troubleshooting, root cause analysis, incident response, backup, restore, and disaster recovery
- Staged modernization from standardized Docker/ECS delivery toward Kubernetes where it is operationally justified

My container-platform experience spans both **ECS and Kubernetes**, including production Kubernetes and Helm operations together with hands-on EKS and AKS platform engineering.

---

## What I Bring

- **Production ownership:** I understand uptime, recovery, incidents, audits, and operational consequences, not only build pipelines.
- **Platform thinking:** I separate infrastructure, platform services, delivery workflows, and workloads into clear ownership boundaries.
- **Pragmatic modernization:** I prefer staged, reversible improvements over large rewrites that create operational risk.
- **Infrastructure as Code discipline:** I care about state, locking, module boundaries, dependency drift, CI validation, and long-term maintainability.
- **Reliability focus:** I treat observability, backups, access control, and failure modes as design inputs, not afterthoughts.
- **Strong Linux and networking base:** I am comfortable below the abstraction layer when debugging production systems.

---

## Public Reference Work

The repositories below are public reference implementations. They are intentionally scoped to demonstrate architecture, ownership boundaries, delivery patterns, and operational reasoning without exposing non-public production systems.

| Project | What it demonstrates | Technologies |
|---|---|---|
| [AWS EKS Platform](https://github.com/LaurisNeimanis/aws-eks-platform) | AWS infrastructure foundation for EKS | Terraform, EKS, VPC, IAM, ACM |
| [AWS EKS GitOps](https://github.com/LaurisNeimanis/aws-eks-gitops) | Platform and workload delivery above the cluster boundary | Argo CD, ApplicationSets, Helm, Kustomize |
| [Karpenter Platform](https://github.com/LaurisNeimanis/gitops-karpenter-platform) | Platform-owned capacity, scheduling, cost, and disruption model | Karpenter, Spot/On-Demand, ARM64, GitOps |
| [Autoscaling Platform](https://github.com/LaurisNeimanis/gitops-autoscaling-platform) | Governed workload scaling as platform policy | HPA, KEDA, Kyverno, Argo CD |
| [Observability Stack](https://github.com/LaurisNeimanis/gitops-observability-stack) | GitOps-managed metrics, logs, dashboards, and alerting | Prometheus, Alertmanager, Grafana, Loki, Alloy |
| [Azure AKS Platform](https://github.com/LaurisNeimanis/azure-aks-platform) | Azure infrastructure foundation using the same platform principles | Terraform, AKS, VNet, Managed Identity |
| [Infrastructure Automation](https://github.com/LaurisNeimanis/ccore-ai-infra) | End-to-end AWS provisioning and server bootstrap reference stack | Terraform, Ansible, cloud-init, Docker |
| [Application Demo](https://github.com/LaurisNeimanis/ccore-ai-demo) | Small app used to validate delivery and infrastructure automation | FastAPI, Streamlit, Docker, GHCR |

Supporting repositories:

| Repository | Purpose | Technologies |
|---|---|---|
| [AWS Terraform Backend Bootstrap](https://github.com/LaurisNeimanis/aws-tf-backend-bootstrap) | Shared S3 remote-state backend bootstrap with native locking | Terraform, AWS S3 |
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

- **Infrastructure** is provisioned with Terraform and cloud-native APIs.
- **Capacity and scheduling** are owned by the platform, not individual applications.
- **Autoscaling behavior** is governed as policy through approved profiles.
- **GitOps reconciliation** provides controlled, reviewable desired-state changes.
- **Platform services** are managed independently from application workloads.
- **Workloads** express runtime intent without owning infrastructure details.

This is the same operating principle I use in production work: define clear contracts between layers so systems remain understandable, auditable, and maintainable as they grow.

---

## Selected Project Details

### AWS EKS Platform

**Terraform · AWS · EKS · IAM · Networking · ACM · Cloudflare**

A production-aligned AWS EKS infrastructure foundation focused on deterministic networking, controlled cluster access, and clear infrastructure/platform/workload boundaries.

Highlights:

- Explicit VPC, subnet, routing, NAT, and security topology
- EKS Managed Node Groups using Amazon Linux 2023
- IAM-native Kubernetes access through the EKS Access API
- EKS Pod Identity add-on for workload identity
- ACM certificate automation with Cloudflare DNS validation
- Shared S3 Terraform backend with native locking
- Infrastructure-only scope; GitOps and workloads are managed separately

Repository: <https://github.com/LaurisNeimanis/aws-eks-platform>

### AWS EKS GitOps

**Argo CD · GitOps · Kubernetes · Helm · Kustomize · ApplicationSets**

A production-aligned GitOps delivery layer for platform services and workloads above an existing EKS infrastructure boundary.

Highlights:

- Out-of-band Argo CD control plane
- App-of-Apps bootstrap pattern
- ApplicationSets for repeatable onboarding
- Helm and Kustomize-based delivery
- Clear separation between platform services and workloads
- Git as the source of truth for desired Kubernetes state

Repository: <https://github.com/LaurisNeimanis/aws-eks-gitops>

### Karpenter Platform

**Karpenter · Kubernetes · GitOps · AWS · Platform Engineering**

A platform-owned capacity and scheduling layer for EKS. The platform owns node architecture, cost, capacity type, consolidation, and disruption; workloads express resource requirements without controlling infrastructure details.

Highlights:

- Explicit scheduling profiles for managed, on-demand, and Spot capacity
- ARM64-first capacity strategy
- Separation between bootstrap/system capacity and workload capacity
- GitOps-managed NodePools and EC2NodeClasses
- Deterministic consolidation and disruption policies
- Documented platform and workload ownership boundaries

Repository: <https://github.com/LaurisNeimanis/gitops-karpenter-platform>

### Autoscaling Platform

**Kubernetes · HPA · KEDA · Kyverno · GitOps**

A governed autoscaling policy layer where workloads select approved scaling profiles while the platform owns limits, validation, and safety.

Highlights:

- Platform-owned HPA and KEDA profiles
- Event-driven scaling and scale-to-zero patterns
- Kyverno admission-time validation
- Namespace-level enablement controls
- Clear separation of autoscaling, capacity, and application concerns
- Argo CD-managed reconciliation

Repository: <https://github.com/LaurisNeimanis/gitops-autoscaling-platform>

### Observability Stack

**Prometheus · Alertmanager · Grafana · Loki · Alloy · Argo CD**

A GitOps-managed Kubernetes observability platform focused on metrics, logs, dashboards, alerting, and operational feedback loops.

Highlights:

- Prometheus Operator with controlled CRD lifecycle
- Alertmanager routing and noise reduction
- Loki with object storage
- Grafana dashboards and data sources
- Grafana Alloy for log collection
- Argo CD-managed desired state

Repository: <https://github.com/LaurisNeimanis/gitops-observability-stack>

### Azure AKS Platform

**Terraform · Azure · AKS · Networking · Managed Identity**

A production-aware AKS infrastructure foundation built around the same ownership and lifecycle principles as the AWS EKS implementation.

Highlights:

- Explicit Resource Group, VNet, and AKS subnet boundaries
- AKS with a VMSS-backed system node pool
- Kubernetes RBAC
- System-assigned managed identity
- Azure Blob Terraform backend with native locking
- CI-enforced formatting, linting, validation, and security checks
- Infrastructure-only scope with GitOps and workloads managed separately

Repository: <https://github.com/LaurisNeimanis/azure-aks-platform>

### Infrastructure Automation Stack

**Terraform · Ansible · AWS · cloud-init · Docker · CI/CD**

A production-inspired reference stack showing provisioning, bootstrap, configuration, and application runtime automation in one repository.

Highlights:

- Modular Terraform with explicit environment separation
- cloud-init-based bootstrap
- Automatically generated Ansible inventory
- Idempotent Ansible roles and templates
- Docker-based application runtime
- CI validation for Terraform and Ansible

Repository: <https://github.com/LaurisNeimanis/ccore-ai-infra>

### Application Demo

**FastAPI · Streamlit · Docker · GHCR · CI/CD**

A small backend/frontend demo used to validate container builds, GHCR publishing, and infrastructure deployment workflows.

Highlights:

- Independent Dockerfiles for API and UI services
- GHCR-based multi-architecture image builds
- Pre-built images pulled by infrastructure automation
- Clear separation between UI, API, and data concerns

Repository: <https://github.com/LaurisNeimanis/ccore-ai-demo>

---

## Core Technical Areas

### Infrastructure and Cloud

- AWS VPC, EC2, ECS, EKS, ECR, IAM, RDS/Aurora, ElastiCache/Redis, S3, EFS, SQS, SNS, CloudWatch, ACM, load balancing
- Azure Resource Groups, Virtual Networks, AKS, Managed Identity, Azure CNI, Azure Load Balancer
- Hetzner Cloud and Scaleway infrastructure
- Proxmox, VMware, Citrix XenServer, ZFS, storage, networking, and virtualization

### Infrastructure as Code

- Terraform modules and multi-environment stacks
- Terragrunt composition and dependency management
- Remote state, locking, imports, refactoring, drift control, and provider lock discipline
- CI validation for formatting, linting, security checks, and validation
- Separation between bootstrap infrastructure and long-lived state

### Delivery and Automation

- GitLab CI/CD, GitHub Actions, and review-driven release workflows
- Ansible roles, inventories, templates, and idempotent workflows
- cloud-init bootstrapping
- Bash and Python automation
- Docker, Docker Compose, ECR, GHCR, and image delivery workflows

### Kubernetes and Platform Engineering

- Kubernetes, Helm, EKS, AKS, Argo CD, ApplicationSets, and Kustomize
- Platform/workload ownership boundaries
- Karpenter capacity management
- HPA, KEDA, and policy-driven autoscaling
- RBAC, workload identity, admission policies, and GitOps reconciliation

### Reliability, Security, and Operations

- Metrics, logs, dashboards, alerting, and incident investigation
- Prometheus, Grafana, Loki, Alloy, CloudWatch, and related observability tooling
- Root cause analysis and preventive engineering
- Backup, restore, disaster recovery, and recovery planning
- Network segmentation, least-privilege access, hardened Linux baselines, and regulated-environment infrastructure controls

---

## Engineering Principles

- Prefer explicit, understandable systems over clever abstractions.
- Keep infrastructure, platform, delivery, and workload concerns separate.
- Design for predictable failure modes and practical recovery paths.
- Use automation to reduce operational risk, not to hide complexity.
- Pin dependencies and validate drift where reproducibility matters.
- Treat observability as a decision-support system, not only monitoring.
- Optimize for systems that remain maintainable after the original builder leaves.

---

## Contact

- **LinkedIn:** <https://www.linkedin.com/in/lauris-neimanis>
- **Email:** neimanis.lauris@gmail.com
- **Location:** Latvia
