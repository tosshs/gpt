# commands/generate-repo-definitions.md

## Command

`generate-repo-definitions`

## Invocation

Primary Name:

- `generate-repo-definitions`

Aliases:

- generate repo definitions

## Purpose

- Generate a repository definition file at `repo-definitions/<repo>.md`.

## Preconditions

- Repository link, repository file tree, or sufficient repository context must be available.
- Never infer repository structure.
- Never hallucinate directories or capabilities.

## Inputs

- Required:
  - Repository name (or target repo identifier)
  - Repository context (link or file tree)
- Optional:
  - None

## Execution Rules

- Use exact section order.
- Keep sections concise and bullet-based where possible.
- Avoid implementation walkthroughs.
- Avoid excessive narrative.

### Required Section Order

1. Repository Name (H1)
2. Canonical Repository URL
3. Purpose
4. Scope and Boundaries
5. Architecture Overview
6. Repository Structure
7. Core Concepts
8. Design Decisions
9. Constraints
10. Operational Model
11. Quality Bar
12. Notes (optional)

### Guardrails

- Use neutral, declarative documentation tone.
- Do not include role-play language.
- Do not include assistant-directed imperatives.
- Do not include task procedures or response-formatting rules.
- Do not include chat history or brainstorming residue.

## Output Rules

- Return full `repo-definitions/<repo>.md` content.
- Do not include explanations unless explicitly requested.

## Validation Before Finalizing

- Section order is correct.
- No “You are…” or “You MUST…” language.
- Content reads as repository documentation.
- Constraints are phrased as repo invariants.
- No operational templates embedded.
