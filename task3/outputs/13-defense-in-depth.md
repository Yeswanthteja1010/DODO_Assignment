# Defense in Depth

## Istio mTLS

Provides:
- Encryption in transit
- Mutual authentication
- Service identity

## AuthorizationPolicy

Provides:
- Identity-based access control
- SPIFFE workload authorization

## NetworkPolicy

Provides:
- Kubernetes network segmentation
- L3/L4 traffic filtering

## Combined Protection

NetworkPolicy cannot validate workload identity.

AuthorizationPolicy cannot replace network segmentation.

Using both layers provides defense-in-depth and reduces attack surface.
