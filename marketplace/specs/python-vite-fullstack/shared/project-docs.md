# Project Docs

The preferred project-doc system is `ai_docs/`.

## Expected Layout

```text
ai_docs/
├── START_HERE.md
├── INDEX.md
├── current/
├── standards/
└── reference/
```

## Documentation Rules

- `current/` describes what exists today.
- `standards/` describes default working rules.
- `reference/` stores shared commands, paths, naming, and verification facts.
- Root files such as `AGENTS.md` and `CLAUDE.md` should link into `ai_docs/`
  instead of duplicating the full text.
- If behavior, structure, scripts, adapters, public APIs, or verification
  commands change, update the related docs in the same change.

## Tone

Prefer short operational docs over tutorial prose. Agents should be able to find
the right file, understand the boundary, and run the correct check quickly.
