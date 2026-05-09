# Quality

## Baseline Commands

Prefer the target project's scripts. If no local docs exist, start with:

```bash
pnpm lint
npx tsc --noEmit
pnpm build
```

If the project has tests:

```bash
pnpm test
```

If the project has i18n parity checks:

```bash
pnpm check:i18n
```

## Manual Checks

Use browser smoke tests for:

- Alignment with the project root `DESIGN.md`
- Primary routes
- Navigation
- Locale switching
- Contact or conversion forms
- Search, filtering, and pagination
- Map or third-party script fallbacks
- Production build preview when deployment behavior matters

## Release Risk

Call out missing automated tests honestly. Passing lint, type check, and build is
not the same as validating a user flow.
