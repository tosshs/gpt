# commands/generate-next-steps.md

## Command

`generate-next-steps`

## Invocation

Primary Name:

- `generate-next-steps`

Aliases:

- generate next steps

## Purpose

- Generate a forward-looking `Next Steps` section for a repository.

## Preconditions

- Repository context must be available (repository link, file tree, and/or `repo-definitions/<repo>.md`).

## Inputs

- Required:
  - Repository context (link, file tree, and/or `repo-definitions/<repo>.md`)
- Optional:
  - None

## Execution Rules

- Include only forward-looking items.
- Do not include completed work.
- Do not include historical phases.
- Keep items actionable and specific.
- Keep list short (3–7 items).
- Focus only on this repository’s scope.

## Output Rules

- Return only the `Next Steps` section content.
- Do not include explanations unless explicitly requested.

## Validation Before Finalizing

- No completed items included.
- No cross-repository scope leakage.
- Items are concrete and actionable.
