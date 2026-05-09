# Verification

Use the target project's own `ai_docs/reference/verification.md` when it exists.
If no local verification reference exists yet, use this baseline.

## Backend

```bash
uv run ruff check src tests scripts
uv run ruff format --check src tests scripts
uv run mypy src
uv run pytest
```

## Frontend

```bash
pnpm --prefix frontend lint
pnpm --prefix frontend typecheck
pnpm --prefix frontend test
pnpm --prefix frontend build
```

## Full Stack

```bash
uv run ruff check src tests scripts
uv run ruff format --check src tests scripts
uv run mypy src
uv run pytest
pnpm --prefix frontend lint
pnpm --prefix frontend typecheck
pnpm --prefix frontend test
pnpm --prefix frontend build
```

## Rule

- Backend-only changes run backend checks.
- Frontend-only changes run frontend checks.
- Cross-boundary, scripts, or template-documentation changes run full stack.
- If docs changed, also run the project's docs/link check when one exists.
