# dotw-ai

## Canonical Repository URL

<https://github.com/tosshs/dotw-ai>

## Purpose

dotw-ai defines the deterministic context architecture for the DevOpsTheWay (DOTW) multi-repository ecosystem.

It standardizes how LLM context is structured and assembled by separating:

- Global behavior rules
- Cross-repository ecosystem overview
- Repository truth definitions
- Curated operational memory
- Explicit, opt-in command modes

This repository does not implement DevOps tooling, workstation automation, or lab infrastructure.

## Scope and Boundaries

In Scope:

- Global AI behavior rules and context loading policy (`core.md`)
- DOTW ecosystem overview and cross-repository framing (`project.md`)
- Repository definition documents (`repo-definitions/`)
- Curated high-signal memory files (`operational-memory/`)
- Explicit command documents loaded only on request (`commands/`)
- Documentation and code formatting standards (`code-styles/`)

Out of Scope:

- Implementations of DOTW tooling repositories (e.g., platform controllers, workstation setup)
- Infrastructure provisioning logic (e.g., Vagrant environments)
- Lab implementation content beyond definitions and memory
- Any auto-executed operational workflows

## Architecture Overview

The repository enforces a layered context model:

- `core.md` defines global behavioral rules and context loading policy.
- `project.md` provides cross-repository DOTW overview and minimal invariants.
- `repo-definitions/` contains declarative repository definitions (architectural truth).
- `operational-memory/` contains curated, high-signal operational context.
- `commands/` contains explicit, opt-in reasoning modes that must be requested.

Context assembly is deterministic: only explicitly defined layers are loaded.

## Repository Structure

- `core.md`
  - Global behavior rules
  - Context loading policy
  - Formatting discipline rules
- `project.md`
  - DOTW ecosystem overview
  - Cross-repository framing (kept minimal)
- `repo-definitions/`
  - `repo-definitions/<repo>.md` repository definition files
- `operational-memory/`
  - Curated memory files used as context inputs
- `commands/`
  - `commands/<command>.md` explicit command modes (opt-in)
- `code-styles/`
  - Documentation and code output style rules

## Core Concepts

- Deterministic context assembly
- Separation of behavioral rules from repository truth
- Separation of repository truth from operational memory
- Explicit command invocation (no implicit modes)
- Minimal, declarative documentation as source of truth

## Design Decisions

- Architectural truth lives in `repo-definitions/` as declarative definitions.
- Operational memory is separate and curated under `operational-memory/`.
- Commands are never auto-loaded and only apply when explicitly invoked.
- `core.md` is the single source for behavior and loading rules.
- `project.md` remains minimal and avoids duplicating repo definitions.

## Constraints

- Do not embed tool implementation logic in this repository.
- Do not mix behavioral rules into `repo-definitions/` definitions.
- Do not store brainstorming residue in `operational-memory/`.
- Commands must not be assumed or auto-loaded.
- Context loading must remain deterministic and explicit.
- Repository definitions must reflect actual repository reality.

## Operational Model

- A wrapper (CLI/editor integration) assembles context before sending it to an LLM.
- Default context is assembled from:
  - `core.md`
  - `project.md`

- Conditional context is loaded explicitly:
  - `repo-definitions/<repo>.md`
  - `operational-memory/<repo>.md`
  - `commands/<command>.md` (only when requested)

The repository provides the documentation artifacts required for deterministic assembly.

## Quality Bar

- Definitions match actual repository structure and responsibilities
- Minimal, declarative, non-narrative documentation
- Clear separation between rules, truth, memory, and commands
- No duplication across repositories
- Stable, deterministic context assembly behavior

## Notes

dotw-ai is the context-governance repository for DOTW. It provides the documentation layers that enable predictable LLM reasoning across the DOTW ecosystem.
