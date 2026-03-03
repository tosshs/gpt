# operational-memory/dotw-almalinux10wsl.md

## Hard Invariants

- AlmaLinux 10 on WSL is the Linux substrate layer.
- Must remain minimal and reproducible.
- Must be safe for repeated updates.
- No lab provisioning logic.
- No platform installation logic.
- No workstation provisioning logic.
- Higher-level tooling configuration does not belong here.
- Host integration (credentials/keys) must be explicit and non-destructive.

## Operational Model (Fixed)

Install distro → Apply baseline packages → Verify readiness → Controlled updates

## Responsibility Boundary

Owns:

- WSL distro installation and maintenance
- Baseline Linux environment preparation

Does NOT own:

- VM labs
- Kubernetes/OpenShift lifecycle
- GitOps/CI/CD deployment
- Windows workstation provisioning
