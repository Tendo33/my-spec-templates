# DESIGN.md Workflow

Use this before UI or visual-system work in a Next.js frontend project.

## Source Priority

1. Project root `DESIGN.md`
2. Existing brand, content-maintenance, or design docs
3. This spec's frontend rules
4. General taste or ad hoc inspiration

`DESIGN.md` is the visual source of truth. It tells the agent how the interface
should look and feel. It does not override accessibility, responsive behavior,
server/client component boundaries, or project-specific content requirements.

## When No DESIGN.md Exists

Before major UI work, choose a starting point from
`https://github.com/VoltAgent/awesome-design-md` or `https://getdesign.md`.

Choose based on project type:

- Marketing or company site: pick a reference with strong first-viewport brand,
  photography, and editorial rhythm.
- Product or SaaS UI: pick a restrained product reference with clear controls
  and dense but calm information hierarchy.
- Personal, portfolio, or memory site: pick a reference with stronger editorial
  personality and media treatment.

Example:

```bash
npx getdesign@latest add linear.app
```

## Implementation Rules

- Read `DESIGN.md` before editing UI files.
- Use it to guide typography, spacing, color roles, surface treatment,
  component states, and motion.
- Do not blindly copy a brand; adapt the visual language to the target project.
- Keep route metadata, content, SEO, and i18n requirements aligned with the
  visual implementation.
- Do not overwrite an existing `DESIGN.md` without explicit user approval.

## Handoff

For visible UI changes, mention which `DESIGN.md` was used and what browser
viewports/routes were checked.
