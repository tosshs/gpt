# commands/_command-template.md

## Command

`<command-name>`

## Invocation

Primary Name:

- `<command-name>`

Aliases:

- \<command name>

## Purpose

- \<One-sentence description of what the command does.>

## Preconditions

- <What must be available before execution (repo link, file tree, specific files, etc.).>
- <What must NOT be assumed (no inferred structure, no hallucinated files).>

## Inputs

- <Required inputs (e.g., repo name, file path).>
- <Optional inputs (e.g., constraints, style, limits).>

## Execution Rules

- \<Bullet rules that govern behavior.>
- \<Determinism and scope guardrails.>
- \<What to preserve vs. what can change.>

## Output Rules

- <Exactly what to return (full file, section only, etc.).>
- <What not to include (no explanations, no snippets unless requested, etc.).>
- <Output formatting constraints (if applicable).>

## Validation Before Finalizing

- \<Checklist of conditions that must be true before returning output.>
- \<No scope leakage.>
- \<No invented structures.>
