# Verification

Use the target project's local `ai_docs/reference/verification.md` first. If it
does not exist, use this baseline.

## Backend

```bash
go test ./...
go build ./...
go run github.com/golangci/golangci-lint/v2/cmd/golangci-lint@v2.11.4 run
```

## Frontend

```bash
pnpm --prefix frontend test --run
pnpm --prefix frontend build
```

## Full Stack

```bash
go test ./...
go build ./...
go run github.com/golangci/golangci-lint/v2/cmd/golangci-lint@v2.11.4 run
pnpm --prefix frontend test --run
pnpm --prefix frontend build
```

## Container

```bash
docker build -t go-template:local .
```

Run the container check when `Dockerfile`, `.dockerignore`, build context, or
runtime startup behavior changes.
