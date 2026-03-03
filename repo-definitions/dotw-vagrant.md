# dotw-vagrant

## Canonical Repository URL

<https://github.com/tosshs/dotw-vagrant>

## Purpose

A centralized, version-controlled collection of reusable Vagrant environments for home lab solutions using the VirtualBox provider.

Primary goals:

- Consistent, reproducible VM environments
- Minimal setup effort via templates and standardized provisioning

## Scope and Boundaries

In Scope:

- Reusable Vagrant lab environments under `labs/`
- Vagrantfile templates and provisioning templates under `templates/`
- Baseline OS bootstrapping via provisioning scripts
- Host-entry management via `system-setting/hosts.entries`

Out of Scope:

- Platform installation and lifecycle management (e.g., Kubernetes, OpenShift, GitOps)
- Higher-level orchestration beyond Vagrant/VirtualBox VM creation and baseline provisioning
- Application deployment workflows

## Architecture Overview

The repository is template-driven:

- Labs are instances built from shared templates
- VM configuration is defined in per-lab `Vagrantfile`
- Provisioning scripts provide baseline OS preparation
- Lab-specific system settings are stored alongside each lab

VirtualBox is the standard provider target.

## Repository Structure

- `labs/<lab-name>/`
  - `Vagrantfile`
  - `system-setting/`
    - `<vagrant_box>.sh`
    - `hosts.entries`
  - `README.md`
- `templates/`
  - `vm/`
    - `Vagrantfile`
  - `provision/`
    - `<vagrant_box>.sh`

## Core Concepts

- Lab as a self-contained, reproducible VM environment
- Template reuse for consistent VM definitions
- Minimal, baseline provisioning
- Provider standardization on VirtualBox

## Design Decisions

- VirtualBox is the default provider for consistency across labs.
- Templates are the primary reuse mechanism; labs remain independent instances.
- Provisioning is script-based and parameterized per base box (`<vagrant_box>.sh`).
- Hostname and host mapping configuration is maintained as explicit lab data (`hosts.entries`).

## Constraints

Infrastructure provisioning is handled exclusively by Vagrant and is limited to:

- OS package updates
- Base system package installation
- `/etc/hosts` configuration
- Basic SSH and networking configuration

Provisioning must not include:

- Kubernetes installation
- OpenShift installation
- GitOps components
- Observability tooling
- Application deployments
- Any platform lifecycle logic

Additional constraints:

- Requires Vagrant 2.x and VirtualBox 6.x/7.x on the host.
- Labs must remain independent and reproducible.
- Lab directories must retain the standard `system-setting/` layout for portability.

## Operational Model

- A lab directory defines a VM environment via its `Vagrantfile` and `system-setting/`.
- VM provisioning applies baseline OS preparation and lab-specific host configuration.
- Templates provide canonical definitions for VM configuration and provisioning behavior.
- Platform-level lifecycle actions are delegated to dedicated repositories and tooling.

## Quality Bar

- Deterministic, repeatable lab bring-up and teardown behavior
- Minimal, maintainable provisioning scripts
- Strict separation between infrastructure provisioning and platform lifecycle concerns
- Consistent directory structure across labs

## Notes

This repository provides the infrastructure substrate for higher-level labs and controllers within the DOTW ecosystem.
