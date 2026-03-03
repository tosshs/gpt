# operational-memory/dotw-platformctl.md

## Hard Invariants

- All lifecycle operations must be deterministic and idempotent.
- Infrastructure provisioning is external (Vagrant-owned).
- ArgoCD is the deployment engine; platformctl orchestrates lifecycle only.
- No external IO outside adapters/.
- No concurrency logic outside execution/.
- Platform-specific logic must remain isolated in platforms/.
- Configuration must validate against schema before execution.
- No hidden global state.

## Lifecycle Model (Fixed)

Provision (external) → Bootstrap → Deploy (GitOps) → Operate

## Responsibility Boundary

Owns:

- Platform bootstrap
- Health validation
- Structured status reporting
- Lifecycle orchestration

Does NOT own:

- VM provisioning
- Direct networking implementation
- Replacing GitOps controller logic
