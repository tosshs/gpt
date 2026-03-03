# dotw-workstation-setup

## Canonical Repository URL

<https://github.com/tosshs/dotw-workstation-setup>

## Purpose

workstation-setup provisions and verifies a Windows 11 DevOps workstation baseline.

It provides a deterministic, idempotent setup flow that can be run repeatedly to reach the same workstation state, with full logging and verification.

## Scope and Boundaries

In Scope:

- Installing required DevOps tooling on Windows 11
- Post-install configuration needed for a functional baseline
- Built-in verification (PASS/FAIL) and correct exit codes
- Deterministic logging (timestamped logs + latest pointer)
- WSL enablement and AlmaLinux-10 distro installation (idempotent)

Out of Scope:

- Lab provisioning (Vagrant labs, VirtualBox VMs)
- Platform installation (Kubernetes, OpenShift)
- CI/CD or GitOps system deployment
- Repository-specific tool configuration beyond workstation baseline

## Architecture Overview

The system is implemented as a small, explicit PowerShell pipeline:

- `setup.ps1` is the orchestration entry point
- Installation and configuration are split into focused scripts
- Verification is a first-class stage
- Logging is always enabled and persisted
- Exit codes are authoritative (0 success, 1 failure)

The design favors minimal moving parts over frameworks.

## Repository Structure

- `setup.ps1`
  - Main entry point orchestrating install → post-install → verify → log
- `scripts/`
  - `install-packages.ps1` — installs packages via winget
  - `post-install.ps1` — post-install fixes and baseline configuration
  - `setup-check.ps1` — existence-only verification (PASS/FAIL)
- `packages/`
  - `packages-winget.json` — winget install profiles
- `logs/`
  - `.gitkeep` — ensures logs directory exists while logs remain git-ignored
- `.gitignore`
- `README.md`

## Core Concepts

- Idempotent execution (safe re-runs)
- Deterministic outcomes
- Fully logged operations
- Verification as part of the workflow
- Correct exit-code semantics for automation
- Standalone execution from ZIP extraction or git clone

## Design Decisions

- PowerShell is the implementation language for Windows-native determinism.
- `setup.ps1` is the single orchestrator to keep the workflow explicit.
- Winget profiles (`packages-winget.json`) define tool installation declaratively.
- Verification is existence-based to keep checks fast and deterministic.
- Logs are never tracked in git; only directory presence is retained.

## Constraints

- Must not redesign or replace the existing working architecture unnecessarily.
- Must preserve idempotency and deterministic behavior.
- Must preserve logging behavior and log file conventions.
- Must preserve correct exit codes (0 success, 1 failure).
- Prefer simple PowerShell over introducing complexity or new frameworks.
- Assume Windows 11 clean-machine setup use case.

## Operational Model

1. `setup.ps1` starts transcript logging.
2. Installs packages via `scripts/install-packages.ps1` using winget profiles.
3. Applies post-install fixes via `scripts/post-install.ps1`.
4. Verifies baseline tooling via `scripts/setup-check.ps1` and prints PASS/FAIL with green/red indicator.
5. Saves logs (`logs/setup-YYYYMMDD-HHMMSS.log` and `logs/latest.log`).
6. Returns exit code based on verification outcome.

## Quality Bar

- Safe to run multiple times without breaking the system
- Predictable and reproducible workstation state
- Clear script boundaries and minimal implicit behavior
- Actionable verification output and reliable exit codes
- Comprehensive logging for troubleshooting

## Notes

The workstation baseline includes common DevOps tooling (e.g., Git, PowerShell 7, VS Code, Python, NodeJS, Docker Desktop, WSL, VirtualBox, Vagrant, Terraform, AWS CLI, Java), with additional post-install configuration to ensure usability.
