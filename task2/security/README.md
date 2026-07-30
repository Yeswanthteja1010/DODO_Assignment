# Task 2 - Secure CI/CD Pipeline and GitOps

## Security Controls Implemented

### Dependency Scanning
- Trivy filesystem scan
- Detects vulnerable dependencies

### Container Image Scanning
- Trivy image scan
- HIGH and CRITICAL vulnerabilities reported

### Image Registry
- GitHub Container Registry (GHCR)

### GitOps
- ArgoCD Application manifest included
- Automated sync enabled
- Self-healing enabled

### Least Privilege
- Dedicated Kubernetes ServiceAccount