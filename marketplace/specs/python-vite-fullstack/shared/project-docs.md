# Project Docs

The preferred project-doc system is `.trellis/spec/`.

## Expected Layout

```text
.trellis/spec/
├── README.md
├── backend/
├── frontend/
├── shared/
├── guides/
└── big-question/
```

## Documentation Rules

- Layer specs describe what exists today and the rules for changing it.
- `shared/` stores repository-wide commands, paths, naming, dependencies, and
  verification facts.
- `guides/` stores reusable thinking and review checklists.
- Root files such as `AGENTS.md` and `CLAUDE.md` should link into
  `.trellis/spec/` instead of duplicating the full text.
- If behavior, structure, scripts, adapters, public APIs, or verification
  commands change, update the related docs in the same change.

## Tone

Prefer short operational docs over tutorial prose. Agents should be able to find
the right file, understand the boundary, and run the correct check quickly.
