# Task 1 – Secure Kubernetes Deployment

## Objective

Deploy and harden the ledger-api service following Kubernetes security best practices.

## Implemented Controls

| Control | Status |
|----------|---------|
| Deployment | Done |
| Service | Done |
| ConfigMap | Done |
| Ingress | Done |
| ServiceAccount | Done |
| RBAC | Done |
| Resource Limits | Done |
| Liveness Probe | Done |
| Readiness Probe | Done |
| Non-root Container | Done |
| Read-only Filesystem | Done |
| Capabilities Dropped | Done |
| RuntimeDefault Seccomp | Done |
| Sealed Secret | Done |
| Kyverno Policies | Done |
| Pod Security Restricted | Done |

## Security Decisions

### Service Accounts
Dedicated service accounts prevent privilege sharing.

### RBAC
Least privilege permissions were assigned.

### Runtime Security
Containers run:
- As non-root
- With read-only filesystem
- With dropped Linux capabilities
- With RuntimeDefault seccomp

### Secret Management
Secrets stored as SealedSecrets.

### Admission Control
Kyverno blocks:
- root containers
- latest tags

## Evidence

Outputs:

```text
outputs/
```

Screenshots:

```text
screenshots/
```