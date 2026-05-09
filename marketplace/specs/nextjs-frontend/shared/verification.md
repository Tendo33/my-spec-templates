# Verification

Use the target project's README, docs, or package scripts first. If no local
verification reference exists, use this baseline.

## Standard

```bash
pnpm lint
npx tsc --noEmit
pnpm build
```

## Optional When Present

```bash
pnpm test
pnpm check:i18n
```

## Browser Smoke

For UI or route changes, run the app locally and check the affected routes in a
browser. Include screenshots or notes for visual changes when the handoff needs
review.

## Rule

Do not claim a Next.js change is complete from code inspection alone. At minimum,
run lint, type check, and build unless the project documents a different gate.
