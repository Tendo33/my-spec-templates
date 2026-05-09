# Backend Directory Structure

Use this when adding Go backend files.

## Baseline Shape

```text
cmd/server/             # service entrypoint
internal/config/        # environment config and validation
internal/httpserver/    # Gin router, middleware, server assembly
internal/model/         # response structs
internal/observability/ # zap logger and request context helpers
internal/service/       # business services
```

## Placement Rules

| New thing | Default location |
| --- | --- |
| Startup wiring | `cmd/server/` |
| Env var parsing or validation | `internal/config/` |
| Gin routes or middleware | `internal/httpserver/` |
| HTTP response/request structs | `internal/model/` |
| Logger/context helpers | `internal/observability/` |
| Business flow | `internal/service/` |

## Conditional Directories

Add only when needed:

| Directory | Add when |
| --- | --- |
| `internal/repository/` | A real persistence layer exists |
| `internal/domain/` | Domain rules are complex enough to stand apart |
| `internal/auth/` | Authentication is a real feature |
| `internal/worker/` | Background jobs are a real runtime concern |

Prefer `internal/` until the project has a genuine external package consumer.
