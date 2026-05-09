# Next.js Frontend Spec

Use this spec for frontend-first TypeScript projects built with Next.js App
Router. It fits content sites, marketing sites, personal sites, and product UI
frontends. It should not assume a database, Prisma, or backend API unless the
target project already has one.

## Structure

### [Frontend](./frontend/index.md)

Next.js App Router frontend patterns:

- [Directory Structure](./frontend/directory-structure.md)
- [DESIGN.md Workflow](./frontend/design-md.md)
- [App Router](./frontend/app-router.md)
- [Components and Styling](./frontend/components-and-styling.md)
- [Data and I18n](./frontend/data-and-i18n.md)
- [Quality](./frontend/quality.md)

### [Shared](./shared/index.md)

Cross-cutting project rules:

- [Code Quality](./shared/code-quality.md)
- [Dependencies](./shared/dependencies.md)
- [TypeScript](./shared/typescript.md)
- [Verification](./shared/verification.md)

### [Guides](./guides/index.md)

Thinking and handoff guides:

- [Task Flow](./guides/task-flow.md)
- [Pre-Implementation Checklist](./guides/pre-implementation-checklist.md)
- [Cross-Layer Thinking Guide](./guides/cross-layer-thinking-guide.md)
- [Review Checklist](./guides/review-checklist.md)

### [Common Issues / Pitfalls](./big-question/index.md)

Stack-specific debugging notes:

- [Route Groups and Locale Drift](./big-question/route-groups-locale-drift.md)
- [Contact Form Security](./big-question/contact-form-security.md)
- [Third-Party Script Fallbacks](./big-question/third-party-script-fallbacks.md)

## Read Order

1. `shared/index.md`
2. `frontend/index.md`
3. `frontend/app-router.md`
4. `frontend/components-and-styling.md`
5. `frontend/data-and-i18n.md` when content, locale, or routing data changes
6. `guides/pre-implementation-checklist.md` before non-trivial changes
7. `shared/verification.md`
8. `guides/review-checklist.md`

## Baseline Stack

- Next.js 16 App Router
- React 19
- TypeScript
- Tailwind CSS 4
- Radix or shadcn-style primitives when useful
- Zod for boundary validation when forms or API routes exist
- `pnpm`

## Project Bias

- Prefer server components by default.
- Use client components only for browser state, effects, event handlers, or
  client-only APIs.
- Keep content and route data typed.
- Treat image, metadata, SEO, and accessibility as part of the feature, not
  late polish.
