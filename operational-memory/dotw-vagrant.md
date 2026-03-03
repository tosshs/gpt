# operational-memory/dotw-vagrant.md

## Hard Invariants

- Infrastructure provisioning is limited to VM creation + baseline OS prep.
- Must not contain platform lifecycle logic.
- Must not install Kubernetes, OpenShift, GitOps, or observability stacks.
- VirtualBox is the standard provider.
- Labs are self-contained and independently reproducible.
- Templates are the canonical reuse mechanism.
- Provisioning must remain minimal and deterministic.

## Responsibility Boundary

Owns:

- Vagrantfiles
- VM templates
- Baseline provisioning scripts
- /etc/hosts management

Does NOT own:

- Platform bootstrap
- GitOps deployment
- Cluster lifecycle
- Application deployment
