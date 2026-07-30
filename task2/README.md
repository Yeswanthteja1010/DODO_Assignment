# Task 2 – Secure CI/CD and GitOps

## Objective

Build a secure software delivery pipeline.

## CI/CD Pipeline

### Build Stage

- Source checkout
- Docker image build
- Push image to GHCR

### Security Stage

- Dependency Scanning
- Trivy Image Scanning

### GitOps Stage

- ArgoCD Application
- Declarative Kubernetes Deployment

## Security Gates

### Vulnerability Scanning

Trivy scans container images.

### Fail Policy

Pipeline fails when:

- Critical vulnerabilities exist
- High vulnerabilities exceed policy threshold

See:

```text
security/fail-policy.md
```

## GitOps

ArgoCD continuously reconciles cluster state against Git.

## Evidence

Workflow files:

```text
workflows/
```

Outputs:

```text
outputs/
```

Screenshots:

```text
screenshots/
```