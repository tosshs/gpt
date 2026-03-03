# DOTW AI v0.1

## Purpose

DOTW AI defines the deterministic LLM context architecture for the DevOpsTheWay (DOTW, pronounced “dot-wuh”) multi-repository ecosystem.

It establishes structured context layering, explicit reasoning modes, and controlled context assembly to ensure predictable, scalable, and reproducible AI-assisted DevOps workflows.

This repository does not implement DevOps tooling or workstation automation.

---

## Architecture Overview

DOTW AI separates AI reasoning into explicit layers to ensure deterministic and controlled outputs.

The architecture is composed of:

- **core.md** — Global AI behavior rules and context loading policy  
- **project.md** — Cross-repository architecture and ecosystem overview  
- **repo-definitions/** — Static architectural definitions per repository  
- **operational-memory/** — Curated, high-signal operational knowledge  
- **commands/** — Explicit opt-in reasoning modes  
- **code-styles/** — Formatting and code output standards  

### Default Context Stack

1. `core.md`  
2. `project.md`  
3. User input  

Additional context layers must be explicitly requested and are never auto-loaded.

---

## Repository Structure

- `/core.md` — AI behavior rules and context loading policy  
- `/project.md` — DOTW ecosystem overview  
- `/repo-definitions/` — Static repository architecture definitions  
- `/operational-memory/` — Curated operational knowledge per repository  
- `/commands/` — Explicit reasoning commands  
- `/code-styles/` — Code and formatting standards  

---

## Usage

This repository is intended to be used with a wrapper layer (CLI, editor integration, or automation tooling) that assembles the required context before sending it to an LLM.

Commands must be explicitly invoked.

Repository definitions and operational memory files are conditionally included based on the active repository context.

The system enforces deterministic context loading and strict separation between behavior rules, architectural truth, and operational knowledge.

The repository can be operated through the "AskTheCode - GitCompanion" GPT by loading the repository context and interacting through structured prompts.

---

## Notes

- Commands are opt-in and scoped to a single interaction.  
- Repository definitions represent architectural truth.  
- Operational memory contains curated, high-signal information.  
- Context assembly must follow the loading rules defined in `core.md`.
