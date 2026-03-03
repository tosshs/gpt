# operational-memory/dotw-openshift.md

## Hard Invariants

- OpenStack is the infrastructure simulation layer (nested virt required).
- Kubernetes runs inside OpenStack instances (not directly on Vagrant VMs).
- GitOps is authoritative; ArgoCD is the GitOps controller.
- Platform lifecycle tooling is external (e.g., platformctl).
- Infrastructure provisioning is external (dotw-vagrant).
- Must remain reproducible within single-workstation resource limits.
- Layers must remain separated: infra → platform → delivery → observability.
- No hidden coupling with other labs.

## Lifecycle Stages (Fixed)

Provision infra → Validate OpenStack → Configure tenant → Provision K8s nodes →
Install/validate K8s → Apply OpenShift-compatible patterns → GitOps/CI-CD →
Observability → Automation workflows

## Responsibility Boundary

Owns:

- Lab layering + integration expectations
- Automation workflows for infra + cluster lifecycle (Python-based)

Does NOT own:

- Physical infrastructure provisioning
- Workstation provisioning
- Embedding infra logic outside infra repos
- Replacing dedicated lifecycle tooling responsibilities
