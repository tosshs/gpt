# operational-memory/dotw-workstation-setup.md

## Hard Invariants

- Must remain idempotent and safe for repeated execution.
- Exit codes are authoritative: 0 = success, 1 = failure.
- Verification is mandatory and part of the workflow.
- Logging is always enabled and persisted.
- Logs are not tracked in git (directory only).
- setup.ps1 is the single orchestration entry point.
- Prefer simple PowerShell over added framework complexity.

## Execution Model (Fixed Order)

install → post-install → verify → log → exit code

## Boundary

Handles Windows 11 workstation baseline only.
No lab provisioning.
No Kubernetes/OpenShift lifecycle.
No CI/CD or GitOps deployment.
