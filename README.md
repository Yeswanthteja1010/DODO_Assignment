# ledger-api

Payments microservice for tokenising PANs and serving transaction metadata.
Deployed on Kubernetes in the `payments` namespace.

## Endpoints

| Method | Path            | Description                          |
|--------|-----------------|--------------------------------------|
| GET    | `/health`       | Liveness check                       |
| POST   | `/tokenize`     | `{"pan": "..."}` → opaque token      |
| GET    | `/transactions` | Recent transaction records           |
| POST   | `/import`       | Import a YAML configuration blob     |
| GET    | `/fetch?url=`   | Fetch a remote resource by URL       |



ledger-api does not require access to the Kubernetes API.
Therefore no Role or RoleBinding has been granted.
A dedicated ServiceAccount with zero permissions is used.

Original Dockerfile:
- Python 3.6 (EOL)
- Root user

Hardened Dockerfile:
- Python 3.12
- Dedicated non-root user (UID 10001)
- Least privilege execution

![alt text](image.png)

Replaced unsafe yaml.load() with yaml.safe_load() to prevent arbitrary object deserialization.

Security Findings in Original Application
Finding	                    Risk
Hardcoded Stripe API Key	Secret Exposure
Hardcoded DB Password	    Secret Exposure
yaml.load()	                Unsafe Deserialization
Python 3.6 Base Image	    End of Life
Vulnerable Dependencies	    Multiple CVEs
Root Container	            Privilege Escalation Risk


### Security Policy Enforcement

An intentionally insecure deployment was tested:

- Used nginx:latest
- Missing runAsNonRoot
- Missing seccompProfile
- Missing capabilities drop
- Missing allowPrivilegeEscalation=false

The deployment was rejected by:

1. Kubernetes Pod Security Standards (restricted)
2. Kyverno admission policies

Result:

Deployment creation denied before reaching the cluster.

