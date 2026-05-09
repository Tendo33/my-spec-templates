# Project Agent Entrypoint

This repository is Simon's Trellis spec marketplace.

## Read Order

1. Start with [README.md](README.md)
2. Read [marketplace/index.json](marketplace/index.json)
3. Read the template README under `marketplace/specs/<template-id>/README.md`
4. Verify marketplace structure before claiming completion

## Working Rules

- This repository stores Trellis spec templates, not application code templates.
- Template directories under `marketplace/specs/` must directly contain the files
  copied into a target project's `.trellis/spec/`.
- Do not wrap a template in an extra `spec/` directory.
- Do not add `.trellis/tasks/`, `.trellis/workspace/`, secrets, customer data, or
  platform-specific prompt folders inside a template.
- Keep template rules grounded in Simon's real repositories.
- Update `marketplace/index.json` whenever a template is added, renamed, moved,
  or intentionally replaced.

## Verification

```bash
node -e "JSON.parse(require('fs').readFileSync('marketplace/index.json','utf8')); console.log('index.json ok')"
```

Also confirm every `path` in `marketplace/index.json` exists and contains a
`README.md`.

## Release Gate

Before a release, verify the pushed remote registry, not only local files:

```bash
curl -fsSL https://raw.githubusercontent.com/Tendo33/my-spec-templates/main/marketplace/index.json >/tmp/my-spec-templates-index.json
trellis init --no-monorepo --registry gh:Tendo33/my-spec-templates/marketplace --template python-vite-fullstack -y
```

Run the same Trellis smoke test for every template ID in `marketplace/index.json`.
