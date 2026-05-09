# Dependencies

Use this when adding or updating dependencies.

## Baseline

| Area | Tooling |
| --- | --- |
| Package manager | `pnpm` |
| Runtime | Node.js version from the target project |
| Framework | Next.js App Router |
| UI | React 19 |
| Language | TypeScript |
| Styling | Tailwind CSS 4 |
| UI primitives | Radix or shadcn-style primitives when useful |
| Validation | Zod for forms and route handlers when present |

## Rules

- Check `package.json` before adding a package.
- Prefer built-in Next.js, React, browser, or existing project helpers first.
- Avoid client-heavy libraries in Server Components.
- Use dynamic import or client isolation for heavy browser-only widgets.
- Do not add database, ORM, auth, or server-state libraries unless the target
  project already has that architecture or the user asks for it.
- Update docs when a dependency changes environment variables, deployment,
  build output, or content maintenance.

## Search Before Adding

```bash
rg "\"dependency-name\"" package.json
rg "from \"dependency-name\"|from 'dependency-name'" app components hooks lib data
```
