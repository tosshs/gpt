# dotw-almalinux10wsl

## Canonical Repository URL

<https://github.com/tosshs/dotw-almalinux10wsl>

## Purpose

almalinux10wsl provides a clean AlmaLinux 10 environment inside WSL to serve as the Linux substrate for development and infrastructure tasks within the DOTW ecosystem.

It standardizes baseline packages and configuration to ensure reproducible tooling behavior across sessions.

## Scope and Boundaries

In Scope:

- Installing and maintaining AlmaLinux 10 in WSL
- Baseline package installation for development and infrastructure work
- Minimal, reproducible configuration for a reliable Linux substrate
- Integration considerations for Windows credential/key management (when defined)

Out of Scope:

- Windows workstation provisioning (owned by workstation-setup)
- Virtual machine lab provisioning (owned by vagrant and lab repositories)
- Platform installation (Kubernetes, OpenShift, GitOps)
- Repository-specific tool configuration beyond the WSL substrate

## Architecture Overview

The repository acts as a substrate layer:

- Provides a consistent AlmaLinux 10 WSL environment
- Prepares common dependencies used by other DOTW tooling
- Keeps configuration minimal and reproducible

## Repository Structure

The repository defines:

- Baseline environment configuration for AlmaLinux 10 on WSL
- Scripts for setup, update, verification, and (where supported) revert behavior
- Conventions for managing host integration (e.g., credentials/key storage) when required

## Core Concepts

- WSL-based Linux substrate
- Reproducible baseline configuration
- Minimal system drift through controlled updates
- Clear separation between substrate setup and higher-level tooling

## Design Decisions

- AlmaLinux 10 is used as the standard WSL Linux distribution.
- The repository focuses on baseline substrate preparation, not higher-level automation.
- Scripts (when implemented) should provide update and verification capability.

## Constraints

- Must run under WSL on Windows.
- Must remain minimal and reproducible.
- Avoid embedding unrelated workstation automation concerns.
- Any host credential/key integration must be explicit and non-destructive.

## Operational Model

- Install and configure AlmaLinux 10 within WSL.
- Apply baseline package and configuration changes.
- Provide verification to confirm expected substrate readiness.
- Support controlled updates to keep the environment consistent over time.

## Quality Bar

- Deterministic, repeatable environment state
- Minimal, maintainable configuration
- Clear separation of responsibilities
- Safe update behavior with verification

## Notes

This repository is the AlmaLinux WSL substrate layer used to support DOTW development and infrastructure workflows.
