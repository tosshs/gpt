# commands/update-file.md

## Command

`update-file`

## Invocation

Primary Name:

- `update-file`

Aliases:

- update file

## Purpose

- Update an existing file in the repository deterministically.

## Preconditions

- A specific file path must be provided.
- Repository context must be available (repository link or file tree).

## Inputs

- Required:
  - Target file path
  - Requested modifications (explicit)
  - Repository context (link or file tree)
- Optional:
  - None

## Execution Rules

- If the specified file does not exist, stop and respond:
  - `Cannot proceed: specified file was not found in the repository.`
- Never infer missing files.
- Never create a new file unless explicitly instructed.
- Apply only the requested modifications.
- Preserve unrelated content.
- Avoid structural rewrites unless explicitly requested.
- Maintain existing formatting style.

## Output Rules

- Return the full updated file content.
- Do not include explanations unless explicitly requested.
- Do not return partial snippets unless explicitly requested.

## Validation Before Finalizing

- File existence confirmed.
- Only requested changes applied.
- No unrelated modifications introduced.
- Formatting remains consistent.
