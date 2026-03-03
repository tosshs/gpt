# dotw-kubernetes

## Canonical Repository URL

<https://github.com/tosshs/dotw-kubernetes>

## Purpose

dotw-kubernetes is a Kubernetes multi-node training lab designed to run on a single workstation using Vagrant-provisioned virtual machines.

It provides an enterprise-realistic Kubernetes cluster environment for platform engineering practice, administration, troubleshooting, and automation.

## Scope and Boundaries

In Scope:

- Multi-node Kubernetes cluster running directly on Vagrant VMs
- kubeadm-based cluster installation model
- Cluster networking via CNI (e.g., Calico or equivalent)
- Core workload primitives (Deployments, StatefulSets, DaemonSets, Jobs, Services, Ingress)
- Lab-appropriate storage patterns (hostPath/local/NFS)
- Baseline observability (metrics and Kubernetes-native log inspection)
- Automation using kubectl, shell scripting, and Python Kubernetes client

Out of Scope:

- OpenStack-based infrastructure abstraction (owned by openshift-lab)
- Infrastructure provisioning logic beyond the shared Vagrant baseline
- Enterprise observability stacks (e.g., Elastic) as a core lab requirement
- Replacing GitOps or higher-level deployment controllers

Infrastructure provisioning is delegated to the Vagrant repository.

## Architecture Overview

The lab is intentionally direct and low-complexity relative to enterprise simulation labs:

Infrastructure Layer:

- Vagrant-managed VMs on VirtualBox
- Fixed 2-node topology:
  - 1 control plane node
  - 1 worker nodes
- Private network connectivity and SSH access

Platform Layer:

- Kubernetes installed via kubeadm
- Container runtime: containerd or CRI-O
- CNI-based pod networking

Automation Layer:

- Scriptable operations via kubectl
- Programmatic interaction via Python Kubernetes client

The lab remains independent from OpenStack-based lab environments.

## Repository Structure

The repository defines:

- Lab topology and node roles
- Configuration and conventions for repeatable cluster creation and teardown
- Validation expectations for cluster readiness and core functionality
- Automation entry points for inspection and health checks

Infrastructure templates and baseline provisioning are externalized to the Vagrant repository.

## Core Concepts

- Enterprise-realistic Kubernetes on a single host
- Deterministic, reproducible multi-node topology
- kubeadm as the canonical installation baseline
- CNI as the networking abstraction
- Automation-first operational practices

## Design Decisions

- Kubernetes runs directly on Vagrant VMs (no OpenStack dependency).
- Topology is fixed to a small, realistic multi-node cluster.
- kubeadm is used to reflect common enterprise baseline practices.
- Networking is implemented via a standard CNI plugin.
- Automation is a first-class goal (kubectl + Python client).

## Constraints

- Host environment: single Windows workstation using VirtualBox + Vagrant.
- No nested virtualization is required for this lab.
- Lab must remain independently reproducible and teardown-friendly.
- Platform lifecycle logic must not be embedded into infrastructure provisioning templates.
- Resource usage must remain compatible with a single-machine environment.

## Operational Model

- Provision lab VMs using Vagrant-managed definitions.
- Apply baseline OS preparation and host configuration via provisioning scripts.
- Install and initialize Kubernetes via kubeadm.
- Apply CNI networking and validate node/pod readiness.
- Validate core cluster functionality (workloads, networking, basic storage).
- Use automation for inspection, health validation, and repeatable workflows.

## Quality Bar

- Reproducible cluster bring-up with clear validation points
- Minimal hidden state and deterministic configuration
- Clear separation of infrastructure provisioning vs platform lifecycle concerns
- Automation-friendly interfaces and predictable outcomes

## Notes

dotw-kubernetes is intended to establish Kubernetes operational competency and provide a controlled environment for validating lifecycle tooling before extending patterns to higher-complexity labs.
