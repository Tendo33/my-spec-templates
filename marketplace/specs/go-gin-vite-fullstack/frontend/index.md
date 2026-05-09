# Frontend Index

Read this before frontend work in a Go + Vite fullstack repository.

## Baseline

The frontend is a React + TypeScript + Vite + Tailwind CSS 4 app under
`frontend/`.

Common structure:

```text
frontend/src/
├── app/
├── lib/
├── styles/
├── test/
└── main.tsx
```

## Rules

- Read the project root `DESIGN.md` before any UI work.
- If no `DESIGN.md` exists and the task changes visual design, choose a suitable
  design-md starting point before coding.
- Use `pnpm --prefix frontend`.
- Keep TypeScript strict.
- Keep the starter small until real product flows exist.
- API helpers live in `frontend/src/lib` when they are shared.
- Prefer relative API paths or explicit Vite env configuration for backend base
  URLs.
- Do not couple React components to Go internals.

## Backend Integration

- Keep `/health` or equivalent smoke calls simple.
- If Vite dev server proxies backend routes, document the target port.
- If Go serves built frontend assets, keep API routes and static fallback
  behavior separate.

## Verification

```bash
pnpm --prefix frontend test --run
pnpm --prefix frontend build
```

## More Specific Guides

- `directory-structure.md`
- `design-md.md`
