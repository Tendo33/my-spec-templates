# Common Issues And Solutions

Documented pitfalls for frontend-first Next.js projects.

## Severity Levels

| Level | Description |
| --- | --- |
| Critical | Build fails, route crashes, or public form leaks unsafe behavior |
| Warning | Route, locale, SEO, or conversion flow is broken |
| Info | Degraded UX with a known fallback |

## Issue Index

| Issue | Category | Severity |
| --- | --- | --- |
| [Route Groups and Locale Drift](./route-groups-locale-drift.md) | Routing / I18n | Warning |
| [Contact Form Security](./contact-form-security.md) | Forms / API Routes | Critical |
| [Third-Party Script Fallbacks](./third-party-script-fallbacks.md) | Maps / External Scripts | Info |

## Quick Debugging Checklist

### Locale Page Shows Wrong Metadata

1. Check the route group layout for that locale.
2. Check canonical and alternates generation.
3. Check message/content parity across locales.

### Contact Form Fails Or Looks Abusable

1. Check Zod validation.
2. Check origin allowlist and rate limiting if public.
3. Check sanitized email rendering and finite error codes.

### Map Or External Widget Is Blank

1. Check public key env vars.
2. Check script load failure state.
3. Confirm list/content fallback still works.
