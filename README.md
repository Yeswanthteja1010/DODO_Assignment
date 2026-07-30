# Dodo Payments Security & Platform Engineering Assessment

Author: Yeswanth Teja Karanam

This repository contains my solution for the Dodo Payments DevOps / Platform Security assessment.

## Assessment Overview

### Task 1 – Secure Kubernetes Deployment
Implemented a production-grade deployment of ledger-api with:

- Kubernetes Deployment & Services
- ConfigMaps
- Ingress
- Service Accounts
- RBAC
- Liveness & Readiness Probes
- Resource Requests & Limits
- Non-root Containers
- Read-only Filesystem
- Dropped Linux Capabilities
- RuntimeDefault Seccomp Profile
- Sealed Secrets
- Kyverno Admission Policies
- Pod Security Restricted Enforcement

See [Task 1](./task1)

---

### Task 2 – Secure CI/CD & GitOps

Implemented:

- GitHub Actions CI Pipeline
- Container Build & Push to GHCR
- Security Scanning Pipeline
- Trivy Vulnerability Scanning
- GitOps Deployment using ArgoCD
- Security Gate Documentation
- Fail Policy Documentation

See [Task 2](./task2)

---

### Task 3 – Service Mesh & Zero Trust

Implemented:

- Istio Service Mesh
- STRICT mTLS
- SPIFFE Identity-based Authorization
- Default-Deny Authorization Policy
- NetworkPolicy Segmentation
- Authorized Service Access
- Unauthorized Service Blocking
- Workload Certificate Validation

See [Task 3](./task3)

---

### Task 4 – Reconnaissance & Penetration Testing

To be completed.
See [Task 4](./task4)

---

## Repository Structure

```text
task1/
task2/
task3/
task4/
```

## Evidence

Screenshots and command outputs are stored inside each task folder under:

```text
screenshots/
outputs/
```