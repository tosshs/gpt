# DevOpsTheWay (DOTW)

## Purpose

DevOpsTheWay (DOTW) is a multi-repository DevOps ecosystem.

Its goal is to provide:

- A reproducible workstation baseline
- Structured platform labs
- Deterministic lifecycle tooling
- Clear architectural separation across repositories

---

## Architecture Overview

DOTW is composed of independent repositories.

- Each repository owns its architecture and `repo-definitions/<repo>.md`.
- Responsibilities must not overlap.
- Cross-repository relationships are defined explicitly and kept minimal.

---

## Development Environment

Primary workstation baseline:

- 12 CPU cores
- 32 GB RAM
- Windows 11
- Visual Studio Code
- PowerShell
- AlmaLinux 10 (WSL)
