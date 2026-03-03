# dotw-openshift

## Canonical Repository URL

<https://github.com/tosshs/dotw-openshift>

## Purpose

openshift is an enterprise-style platform engineering lab designed to simulate a full infrastructure and platform stack within a controlled home lab environment.

It provides a realistic environment for practicing infrastructure automation, Kubernetes operations, GitOps workflows, CI/CD integration, and observability patterns.

## Scope and Boundaries

In Scope:

- OpenStack-based infrastructure simulation
- Kubernetes cluster deployment within OpenStack instances
- OpenShift-compatible platform patterns
- GitOps integration using ArgoCD
- CI/CD integration (e.g., GitLab CE or Jenkins)
- Observability stack deployment (Elastic Stack)
- Python-based automation for infrastructure and cluster lifecycle

Out of Scope:

- Physical infrastructure provisioning
- Workstation provisioning
- Replacing dedicated lifecycle tooling responsibilities
- Embedding infrastructure logic outside defined infrastructure repositories

Infrastructure provisioning is delegated to the Vagrant repository.

Platform lifecycle tooling is delegated to its respective controller repository.

## Architecture Overview

The lab is layered:

Infrastructure Layer:

- OpenStack multi-node cluster (controller and compute nodes)
- Provisioned on Vagrant-managed VirtualBox VMs

Platform Layer:

- Kubernetes cluster deployed inside OpenStack instances
- OpenShift-compatible configuration patterns

Delivery Layer:

- GitOps via ArgoCD
- CI/CD system integration

Observability Layer:

- Elastic Stack deployed within Kubernetes

Automation Layer:

- Python automation using:
  - openstacksdk
  - Kubernetes Python client
  - SSH and API integrations

Each layer remains logically separated and reproducible.

## Repository Structure

The repository organizes lab definitions and configuration required to:

- Provision OpenStack nodes via infrastructure tooling
- Configure OpenStack services
- Deploy Kubernetes inside tenant instances
- Integrate GitOps and CI/CD
- Deploy observability components
- Implement automation scripts

Detailed infrastructure templates are externalized to the Vagrant repository.

## Core Concepts

- Enterprise simulation on a single workstation
- Layered infrastructure → platform → delivery → observability model
- Deterministic, reproducible cluster lifecycle
- Infrastructure abstraction before platform deployment
- Programmatic control of infrastructure and cluster state

## Design Decisions

- OpenStack is used to simulate enterprise infrastructure abstraction.
- Kubernetes is deployed inside OpenStack instances rather than directly on VMs.
- GitOps is the authoritative deployment model.
- Observability is treated as a first-class platform concern.
- Automation is implemented in Python for programmatic lifecycle control.

## Constraints

- Must operate within single-workstation resource limits.
- Nested virtualization is required for OpenStack compute nodes.
- Labs must remain independently reproducible.
- Infrastructure logic must remain externalized to infrastructure repositories.
- Platform lifecycle logic must not be embedded in provisioning scripts.
- No hidden coupling with other lab repositories.

## Operational Model

The lab progresses through structured lifecycle stages:

1. Provision infrastructure nodes.
2. Deploy and validate OpenStack services.
3. Configure tenant resources.
4. Provision Kubernetes nodes as OpenStack instances.
5. Install and validate Kubernetes cluster.
6. Apply OpenShift-compatible platform patterns.
7. Integrate GitOps and CI/CD systems.
8. Deploy observability stack.
9. Implement Python-based automation workflows.

Each stage builds upon validated infrastructure and platform layers.

## Quality Bar

- Deterministic bring-up and teardown
- Clear separation of infrastructure and platform concerns
- Reproducible enterprise-style workflows
- Explicit automation interfaces
- Resource-aware configuration for single-host environments

## Notes

openshift-lab represents the highest-complexity lab within the DOTW ecosystem and is intended to model enterprise-grade infrastructure and platform engineering practices.
