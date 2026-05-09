# Dependencies

Use this when adding or updating dependencies.

## Baseline

| Area | Tooling |
| --- | --- |
| Go runtime | Go 1.26 |
| HTTP framework | Gin |
| Logging | zap |
| Go quality | Go test toolchain, `golangci-lint` |
| Frontend package manager | `pnpm` |
| Frontend runtime | React 19, TypeScript |
| Frontend build | Vite |
| Frontend testing | Vitest |
| Container | Docker when the target project uses the provided Dockerfile |

## Rules

- Check `go.mod` and `frontend/package.json` before adding a dependency.
- Prefer the Go standard library when it keeps the implementation clear.
- Add database, ORM, auth, Swagger, gRPC, queue, or OpenTelemetry dependencies
  only when the target project has a concrete feature requiring them.
- Keep frontend dependencies isolated under `frontend/`.
- Update Docker and CI docs when dependency changes affect build context or
  runtime startup.

## Search Before Adding

```bash
rg "module-name|package-name" go.mod go.sum internal cmd
rg "\"dependency-name\"" frontend/package.json
```
