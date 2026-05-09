# Frontend Directory Structure

Use this when adding frontend files under `frontend/`.

## Baseline Shape

```text
frontend/src/
├── app/        # App entry and page-level composition
├── lib/        # API helpers and shared utilities
├── styles/     # Global styles
├── test/       # Test setup
└── main.tsx
```

## Placement Rules

| New thing | Default location |
| --- | --- |
| App shell or top-level page composition | `frontend/src/app/` |
| Shared API helper | `frontend/src/lib/` |
| Shared utility | `frontend/src/lib/` after 2+ real users |
| Global CSS | `frontend/src/styles/` |
| Test setup | `frontend/src/test/` |

Add `components/`, `features/`, or `hooks/` only when the frontend grows enough
to need them. Keep the starter small until product flows exist.
