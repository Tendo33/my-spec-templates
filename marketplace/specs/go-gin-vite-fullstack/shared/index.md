# Shared Index

This spec assumes a repository shaped like `go-template`:

```text
cmd/server/       # Go service entrypoint
internal/         # Config, HTTP server, models, observability, services
frontend/         # React + Vite starter
scripts/          # Template maintenance scripts
ai_docs/          # Current facts, standards, references
Makefile
Dockerfile
go.mod
```

## Source of Truth

- If `ai_docs/` exists, read it before editing.
- Use `ai_docs/current/` for what exists today.
- Use `ai_docs/standards/` for defaults.
- Use `ai_docs/reference/verification.md` for commands.

## Documentation Files

| File | Description | When to Read |
| --- | --- | --- |
| [code-quality.md](./code-quality.md) | Mandatory quality rules | Always |
| [dependencies.md](./dependencies.md) | Stack and dependency constraints | Adding or updating dependencies |
| [verification.md](./verification.md) | Baseline verification commands | Before completion |

## Core Rules

- No request-scoped loggers in globals or service structs.
- No secrets in logs.
- No new external framework dependency unless the current feature needs it.
- HTTP behavior must preserve request ID propagation.
- Fullstack changes run both Go and frontend verification.

## Working Rules

- Do not document missing database, auth, Swagger, gRPC, or repository layers as
  implemented.
- Keep environment configuration explicit.
- Preserve `X-Request-ID` propagation when touching HTTP middleware.
- Keep frontend and backend verification together for fullstack changes.
