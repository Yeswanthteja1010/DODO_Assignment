# Task 3 – Service Mesh & Zero Trust

## Objective

Implement Zero Trust networking using Istio.

## Implemented Controls

### Istio Service Mesh

Installed Istio sidecars for:

- ledger-api
- reporting

### mTLS

PeerAuthentication configured in STRICT mode.

Result:

- Plaintext traffic denied
- Mesh traffic encrypted

### Authorization

Default deny policy:

```yaml
AuthorizationPolicy:
  {}
```

Only reporting service account is allowed.

SPIFFE Identity:

```text
cluster.local/ns/payments/sa/reporting-sa
```

### Network Policy

Default deny networking enforced.

Explicit traffic allowed only where required.

## Validation

### Authorized Service

reporting → ledger-api

Result:

```json
{"status":"ok"}
```

### Unauthorized Service

attacker → ledger-api

Result:

```text
RBAC: access denied
```

## Certificate Management

Istiod acts as certificate authority.

Certificates are:

- Automatically issued
- Automatically rotated
- Bound to workload identity

Trust Root:

```text
cluster.local
```

## Defence in Depth

| Layer | Protection |
|---------|------------|
| NetworkPolicy | L3/L4 segmentation |
| Istio mTLS | Encryption & identity |
| AuthorizationPolicy | Workload authorization |

## Evidence

Outputs:

```text
outputs/
```

Screenshots:

```text
screenshots/
```