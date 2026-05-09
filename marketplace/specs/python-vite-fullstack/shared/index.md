# Shared Index

This spec assumes a repository shaped like `python-template`:

```text
src/<package_name>/      # Python package
tests/                   # Python tests
scripts/                 # Maintenance and release scripts
frontend/                # React + Vite starter
ai_docs/                 # Current facts, standards, and references
```

## Source of Truth

- If the project has `ai_docs/`, read it before editing.
- Start with `ai_docs/START_HERE.md`, then `ai_docs/INDEX.md`.
- Use `ai_docs/current/` for current behavior.
- Use `ai_docs/standards/` for default constraints.
- Use `ai_docs/reference/verification.md` for commands.

## Documentation Files

| File | Description | When to Read |
| --- | --- | --- |
| [code-quality.md](./code-quality.md) | Mandatory quality rules | Always |
| [dependencies.md](./dependencies.md) | Stack and dependency constraints | Adding or updating dependencies |
| [project-docs.md](./project-docs.md) | `ai_docs/` conventions | Changing docs or project structure |
| [verification.md](./verification.md) | Baseline verification commands | Before completion |

## Core Rules

- No untyped public Python APIs.
- No `Any` in new Python code unless the boundary is genuinely dynamic.
- No frontend `any` in new TypeScript code.
- No secrets in logs or Vite public environment variables.
- Generated frontend build artifacts stay out of git unless the target project
  explicitly stores static output.

## Working Rules

- Do not import Python modules through `src.<package_name>...`.
- Do not document future service, repository, database, or HTTP layers as
  already implemented.
- When adding a new public import surface, update package exports and tests.
- Keep frontend and backend contracts explicit. If the frontend calls a backend
  endpoint, document the request, response, and error shape.
- Do not commit generated frontend build artifacts unless the target project
  explicitly serves checked-in static files.
