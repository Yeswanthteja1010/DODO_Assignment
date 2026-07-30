# Security Gate Policy

## Hard Fail

The pipeline must fail when:

- Secrets detected by Gitleaks
- Critical vulnerabilities with fixes available
- High vulnerabilities exceeding organizational threshold
- Unsigned container images
- Failed Semgrep security findings classified as High/Critical

## Warning Only

The pipeline warns when:

- Medium vulnerabilities
- Informational Semgrep findings
- Deprecated dependencies

## CVEs Without Available Fix

If no vendor fix exists:

1. Document the CVE.
2. Apply compensating controls.
3. Track remediation.
4. Create an exception with expiry date.
5. Re-scan every release.
