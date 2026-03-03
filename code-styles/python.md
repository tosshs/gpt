# Python Code Style – AI Coding Definition (Best Practices Standard)

## 1. Foundational Standard

- Follow **PEP 8** style guidelines.
- Prioritize readability over cleverness.
- Write code for humans first, machines second.
- Maintain consistency across the entire project.

## 2. Formatting Rules

### Indentation

- Use 4 spaces per indentation level.
- Never mix tabs and spaces.

### Line Length

- Maximum 79 characters (88 if using Black formatter).
- Break long expressions using parentheses, not backslashes.

### Spacing

- Two blank lines between top-level functions/classes.
- One blank line between class methods.
- Surround top-level definitions with blank lines.

## 3. Naming Conventions

### Variables & Functions

- Use `snake_case`.
- Names must be descriptive and meaningful.
- Avoid unclear abbreviations.

Examples:

- `calculate_total_price`
- `user_profile_data`

### Classes

- Use `PascalCase`.

Examples:

- `UserProfile`
- `PaymentProcessor`

### Constants

- Use `UPPER_CASE`.

Examples:

- `MAX_RETRIES`
- `DEFAULT_TIMEOUT`

### Private/Internal Members

- Prefix with `_single_leading_underscore`.

## 4. Imports

- Place all imports at the top of the file.
- One import per line (grouped `from x import (...)` is OK).
- Order:
  1. Standard library
  2. Third-party packages
  3. Local application imports

Example:

- `import os`
- `import requests`
- `from myproject.utils import helper_function`

## 5. Function Design Principles

- One function = one responsibility.
- Keep functions short and focused.
- Avoid deep nesting (target max 2–3 levels).
- Use early returns to reduce indentation.
- Avoid side effects unless explicitly intended.
- Prefer pure functions when practical.

## 6. Type Hints (Required for Modern Code)

- Use type hints for all function parameters and return types.
- Use built-in generics when available (Python 3.9+): `list[str]`, `dict[str, int]`.

Example:

- `def calculate_area(radius: float) -> float: ...`

## 7. Docstrings (Mandatory for Public Interfaces)

- Use triple double quotes.
- Describe purpose, parameters, return values, and exceptions (if relevant).
- Keep the first line a short summary sentence.

Template:
"""
Short summary.

Args:
    param_name (type): Description.

Returns:
    type: Description.

Raises:
    SomeError: When/why it happens.
"""

## 8. Avoid Common Anti-Patterns

- No magic numbers: use named constants.
- No mutable default arguments: never use `[]` or `{}` as defaults.
- No deeply nested logic: refactor into helpers.
- No ambiguous names: avoid `tmp`, `data`, `stuff` unless scoped and obvious.

## 9. Pythonic Best Practices

- Use list/dict/set comprehensions when they improve clarity.
- Use `with` for resources (files, locks, connections).
- Use `enumerate()` instead of manual indexing.
- Prefer `dict.get()` over manual key checks when appropriate.
- Use f-strings for formatting (Python 3.6+).

## 10. Error Handling & Logging

- Catch the narrowest exception possible.
- Don’t silently swallow exceptions.
- Use `logging` (not `print`) for non-trivial applications.
- Include actionable context in error messages.

## 11. Tooling Requirements

Projects should use:

- `black` for formatting
- `ruff` (or `flake8`) for linting
- `isort` (optional if ruff/black config covers imports)
- `mypy` (or `pyright`) for static type checking

All code must pass formatter + linter checks before merge.

## 12. Structural Standards

- Separate business logic from I/O (CLI, HTTP, DB).
- Keep configuration separate; load secrets via environment variables.
- Organize code into modules with clear responsibilities.
- Write tests for critical logic.

## 13. Readability Rule (Non-Negotiable)

If code requires excessive explanation, rewrite it.

Clear > Clever  
Explicit > Implicit  
Simple > Complex  

## Compliance Requirement

All AI-generated Python code must:

- Follow these standards strictly
- Be auto-formatted
- Include type hints
- Include docstrings for public functions/classes
- Avoid listed anti-patterns
- Maintain consistent naming and import order

Failure to comply = reject and refactor.
