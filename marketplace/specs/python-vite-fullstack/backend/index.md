# Backend Index

Read this before backend work in a Python + Vite fullstack repository.

## Baseline

The Python side starts as a lightweight package/backend foundation. It commonly
contains:

- `config`: `Settings`, `get_settings()`, `reload_settings()`
- `observability`: logging setup and logger helpers
- `core`: runtime context helpers
- `contracts`: shared `Protocol` interfaces
- `models`: Pydantic base and project models
- `utils`: file, JSON, date, decorator, and common helpers

## Rules

- Keep handlers thin when an HTTP layer exists.
- Put business flow in service-level functions or classes only when the flow is
  real enough to justify the boundary.
- Do not add a repository layer before persistence exists.
- Use Pydantic v2 APIs.
- Use `pydantic-settings` for configuration.
- Read secrets only from environment variables or controlled configuration
  sources.
- Never log tokens, passwords, or sensitive personal data.
- Validate external input at the boundary.

## Import Surface

- Prefer stable package or submodule imports.
- Do not import from `src.<package_name>...`.
- Public models intended for users should be exported from the package's model
  namespace and covered by public API tests.

## More Specific Guides

- `python-package.md`
- `directory-structure.md`
- `type-safety.md`
- `config-logging.md`
- `http-api-when-added.md`
- `database-when-added.md`
- `testing.md`
