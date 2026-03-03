# operational-memory/dotw-ai.md

## Hard Invariants

- Context assembly must remain deterministic.
- Commands are explicit opt-in only. Never auto-load.
- `core.md` is the sole source of behavioral rules.
- `repo-definitions/` defines architectural truth only.
- `operational-memory/` stores curated operational signal only.
- Layers must not mix responsibilities.
- No implicit reasoning modes.

## Boundary

dotw-ai governs AI behavior and context policy only.
No tooling. No provisioning. No lifecycle logic.
