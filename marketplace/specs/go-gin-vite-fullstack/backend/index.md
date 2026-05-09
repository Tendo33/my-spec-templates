# Backend Index

Read this before Go backend work.

## Baseline Modules

```text
cmd/server/             # service entrypoint
internal/config/        # environment config and validation
internal/httpserver/    # Gin router, middleware, server assembly
internal/model/         # response structs
internal/observability/ # zap logger and request context helpers
internal/service/       # business services
```

## Rules

- Use environment variables for configuration.
- Validate critical config before service startup.
- Keep handlers thin.
- Put real business flow in `internal/service`.
- Keep request-scoped logger access through `observability.FromContext(...)`.
- Do not store request loggers in global variables or service structs.
- Add repository or domain packages only when a real persistence or domain
  boundary exists.

## More Specific Guides

- `directory-structure.md`
- `configuration.md`
- `http-and-context.md`
- `error-handling.md`
- `security.md`
- `testing.md`
