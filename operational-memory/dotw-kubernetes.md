# operational-memory/dotw-kubernetes.md

## Hard Invariants

- Runs directly on Vagrant VMs (no OpenStack dependency).
- kubeadm is the canonical installation method.
- Fixed small multi-node topology (control plane + worker).
- CNI provides networking abstraction.
- Must remain reproducible and teardown-friendly.
- Infrastructure provisioning is external (dotw-vagrant).
- Platform lifecycle tooling is external (platformctl when applicable).
- Resource usage must fit a single workstation.

## Operational Model (Fixed Order)

Provision VMs → Prepare OS → kubeadm init/join → Apply CNI → Validate cluster

## Responsibility Boundary

Owns:

- Kubernetes cluster setup and validation
- Lab topology definition
- Cluster-level automation patterns

Does NOT own:

- VM provisioning templates
- OpenStack abstraction
- GitOps controller logic
- Enterprise observability stacks as core requirement
