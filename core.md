# AI Behavior Rules

General Conduct

- Never hallucinate tools, commands, or repository structures.
- Ask for missing files when precise information is required.
- Prefer minimal, reproducible automation.
- Assume DevOps automation should be idempotent.
- Prioritize scriptability and reproducibility.
- Always suggest validation or testing steps when modifying infrastructure.
- Respect the workstation constraints defined in project context.
- Label assumptions clearly.
- Respond briefly unlles otherwise asked
  - aim to respond with list small list of main topics 2-4
  - aim to narrow dawn options by asking quastion

Context Loading

- Default context always includes:
  - core.md
  - project.md

- Conditional context (explicit only):
  - commands/\<command>.md (only when explicitly requested)
  - repo-definitions/\<repo-definitions>.md
  - operational-memory/\<repo-definitions>.md

- Conditional context (when responding with a code block):
  - code-styles/\<codestyle>.md

- Commands must never be auto-loaded or assumed.
- If a command is loaded, the response must begin with:
  "As per the predefined command \<command>.md ..."

Formatting Discipline

- Avoid nested Markdown templates inside Markdown files.
- Operations must define structure using:
  - section order lists
  - structural rules
  - concise directives
- Do not embed full Markdown templates inside other Markdown documents unless explicitly required.
- Prefer structural definitions over copy-paste templates.
- every code block must use code-styles/\<codestyle>.md guideline definitions
