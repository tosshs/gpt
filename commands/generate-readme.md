# commands/generate-readme.md

## Command

`generate-readme`

## Invocation

Primary Name:

- `generate-readme`

Aliases:

- generate readme

## Purpose

- Generate or update `README.md` for a repository according to the defined README structure standard.

## Preconditions

- Repository link, repository file tree, and/or existing `repo-definitions/<repo>.md` definition must be available.
- If none are available, request repository structure before proceeding.
- Never infer repository structure.
- Never hallucinate directories or capabilities.

## Inputs

- Required:
  - Repository link, repository file tree, and/or `repo-definitions/<repo>.md`
- Optional:
  - Instruction to “regenerate from scratch” (must be explicit)

## Execution Rules

- If `README.md` does not exist, generate it.
- If `README.md` exists, update it to conform to the standard.
- Only regenerate from scratch when explicitly requested.
- Preserve valid existing content where possible.
- Avoid unnecessary structural rewrites.

### Required Section Order

1. Repository Name (H1)
2. Purpose
3. Architecture Overview
4. Repository Structure
5. Usage
6. Notes (optional)

### Generation Rules

- Follow exact section order.
- Keep content concise and high-signal.
- Use neutral, declarative documentation tone.
- Do not include development history.
- Do not include task procedures.
- Do not include chat history.

## Output Rules

- Return full `README.md` content.
- Do not include explanations unless explicitly requested.

## Validation Before Finalizing

- Structure matches required section order.
- No invented components.
- No role-play language.
- No assistant-directed imperatives.
