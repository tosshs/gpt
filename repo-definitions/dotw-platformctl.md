# dotw-platformctl

## Canonical Repository URL

<https://github.com/tosshs/dotw-platformctl>

## Purpose

platformctl is a deterministic, enterprise-style platform lifecycle controller for lab environments provisioned via Vagrant.

It bootstraps, validates, and operates Kubernetes and OpenShift platforms after infrastructure provisioning.

---

## Scope and Boundaries

In Scope:

- Platform bootstrap (Kubernetes, OpenShift)
- Installation and validation of platform components
- GitOps controller bootstrap (ArgoCD)
- Deployment orchestration via GitOps
- Platform status inspection
- Platform health validation (including concurrent checks)

Out of Scope:

- Infrastructure provisioning
- VM lifecycle management
- Replacing ArgoCD deployment logic
- Direct networking implementation

Infrastructure provisioning is handled externally by Vagrant.

---

## Architecture Overview

platformctl follows a layered, deterministic architecture:

- Domain core separated from IO
- Strict module boundaries
- Execution engine controlling lifecycle flow
- Platform-specific logic isolated
- External integrations abstracted via adapters

Lifecycle model:

1. Provision (Vagrant)
2. Bootstrap (platformctl)
3. Deploy (ArgoCD)
4. Operate (platformctl health & status)

Bootstrap and deploy operations are idempotent.

---

## Repository Structure

platformctl/

- src/platformctl/
  - core/
  - workspace/
  - actions/
  - execution/
  - platforms/
  - components/
  - adapters/
  - util/
- schemas/
  - lab.schema.json

Each module has strictly defined responsibility boundaries.

---

## Core Concepts

- Deterministic lifecycle control
- Idempotent bootstrap and deployment
- Structured execution steps
- Explicit separation of concerns
- Platform abstraction
- GitOps-driven deployment model
- Component-based platform extensions

---

## Design Decisions

- Infrastructure is external to the controller.
- ArgoCD is the deployment engine.
- platformctl is the lifecycle orchestrator.
- All external IO is isolated to adapters/.
- Concurrency and retries are handled by execution/.
- Platform-specific logic resides only in platforms/.
- Component lifecycle management is isolated in components/.
- Configuration is schema-validated.

---

## Constraints

- All operations must be deterministic.
- All lifecycle steps must be idempotent.
- No hidden global state.
- No ad-hoc scripting outside defined modules.
- No external IO outside adapters/.
- No concurrency logic outside execution/.
- Lab configuration must validate against schema.
- Platform logic must not leak across layers.

---

## Operational Model

- Discover lab configuration.
- Validate configuration against schema.
- Execute lifecycle steps via execution engine.
- Bootstrap platform runtime.
- Bootstrap and validate networking provider.
- Bootstrap and validate ArgoCD.
- Trigger and validate GitOps sync.
- Provide structured status and health reports.

Execution results are structured and composable.

---

## Quality Bar

- Modular and testable design.
- Strict boundary enforcement.
- Clear execution result modeling.
- Explicit error handling.
- Minimal implicit behavior.
- Enterprise-style architectural discipline.

---

## Notes

Designed for lab environments supporting Kubernetes and OpenShift training scenarios within the DevOpsTheWay (DOTW) ecosystem.
