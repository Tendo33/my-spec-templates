# Frontend Index

Read this before frontend work in a Python + Vite fullstack repository.

## Baseline

The frontend is a React + TypeScript + Vite app under `frontend/`.

Common structure:

```text
frontend/src/
├── app/
├── assets/
├── components/
├── features/
├── hooks/
├── lib/
├── styles/
└── test/
```

## Rules

- Read the project root `DESIGN.md` before any UI work.
- If no `DESIGN.md` exists and the task changes visual design, choose a suitable
  design-md starting point before coding.
- Use `pnpm`.
- Keep TypeScript strict.
- Do not use `any` by default.
- Use semantic design tokens instead of hard-coded color values.
- Prefer shadcn/ui-style primitives for reusable UI atoms.
- Add shared utilities to `frontend/src/lib` only after a second real use case
  appears.
- Keep the starter light until the project has real product flows.

## More Specific Guides

- `directory-structure.md`
- `design-md.md`
- `vite-static-mount.md`
- `components.md`
- `quality.md`
