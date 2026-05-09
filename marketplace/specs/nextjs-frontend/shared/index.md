# Shared Index

This spec assumes a frontend-first Next.js repository. Some projects may include
small route handlers for health checks, contact forms, or content workflows, but
the default assumption is still frontend and content work rather than a full
backend platform.

## Source of Truth

Read in this order when present:

1. `README.md`
2. Project docs under `docs/`
3. `AGENTS.md` or another repository entrypoint
4. `package.json` scripts
5. Existing route and component structure

## Documentation Files

| File | Description | When to Read |
| --- | --- | --- |
| [code-quality.md](./code-quality.md) | Mandatory quality rules | Always |
| [typescript.md](./typescript.md) | TypeScript and schema rules | Type-related decisions |
| [dependencies.md](./dependencies.md) | Stack and dependency constraints | Adding or updating dependencies |
| [verification.md](./verification.md) | Baseline verification commands | Before completion |

## Core Rules

- Default to Server Components.
- Add `"use client"` only for real browser-side behavior.
- No `any`, non-null assertions, or ignored TypeScript errors in new code.
- Public form inputs are validated and sanitized.
- Visible UI work requires browser inspection.

## Working Rules

- Do not add a database, Prisma, auth, or API layer unless the target project
  already has one or the user explicitly asks for it.
- Keep route, content, SEO, and i18n behavior grounded in existing project
  structure.
- Update docs when route maps, environment variables, deployment flow,
  content-maintenance flow, or verification commands change.
- Prefer typed static content and typed site configuration for content-driven
  projects.
- Treat browser smoke testing as required for visible UI or navigation changes.
