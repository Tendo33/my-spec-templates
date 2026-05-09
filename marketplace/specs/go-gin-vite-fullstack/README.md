# Go + Gin + Vite Fullstack Spec

Use this spec for repositories based on Simon's Go template: a Gin service with
zap logging, request context propagation, explicit configuration, and an
optional React + Vite frontend.

## Structure

### [Backend](./backend/index.md)

Go + Gin service patterns:

- [Directory Structure](./backend/directory-structure.md)
- [Configuration](./backend/configuration.md)
- [HTTP and Context](./backend/http-and-context.md)
- [Error Handling](./backend/error-handling.md)
- [Security](./backend/security.md)
- [Testing](./backend/testing.md)

### [Frontend](./frontend/index.md)

React + Vite frontend patterns:

- [Directory Structure](./frontend/directory-structure.md)
- [DESIGN.md Workflow](./frontend/design-md.md)

### [Shared](./shared/index.md)

Cross-cutting project rules:

- [Code Quality](./shared/code-quality.md)
- [Dependencies](./shared/dependencies.md)
- [Verification](./shared/verification.md)

### [Guides](./guides/index.md)

Thinking and handoff guides:

- [Task Flow](./guides/task-flow.md)
- [Pre-Implementation Checklist](./guides/pre-implementation-checklist.md)
- [Cross-Layer Thinking Guide](./guides/cross-layer-thinking-guide.md)
- [Review Checklist](./guides/review-checklist.md)

### [Common Issues / Pitfalls](./big-question/index.md)

Stack-specific debugging notes:

- [Request ID Propagation](./big-question/request-id-propagation.md)
- [Docker Build Context](./big-question/docker-build-context.md)
- [Vite Proxy and Static Serving](./big-question/vite-proxy-and-static-serving.md)

## Read Order

1. `shared/index.md`
2. `backend/index.md` before Go service work
3. `frontend/index.md` before Vite frontend work
4. `guides/pre-implementation-checklist.md` before non-trivial changes
5. `shared/verification.md`
6. `guides/review-checklist.md`

## Baseline Stack

- Go 1.26
- Gin
- zap
- `golangci-lint`
- Go test toolchain
- React 19
- TypeScript
- Vite
- Vitest
- `pnpm`
- Docker when the target project uses the provided Dockerfile

## Project Bias

- Keep Go code inside `internal/` unless external reuse is a real requirement.
- Keep handlers thin and services direct.
- Pass request-scoped loggers through `context.Context`.
- Add databases, ORMs, Swagger, gRPC, queues, or OTel SDKs only when the real
  project needs them.
