# My Trellis Spec Templates

Personal Trellis spec marketplace for Simon's recurring project stacks.

This repository does not scaffold application code. It provides reusable
`.trellis/spec/` starting points that tell an agent how to work inside a real
project after the code template has already created the repository.

## Templates

| ID | Stack | Use when |
| --- | --- | --- |
| `python-vite-fullstack` | Python package/backend + React/Vite frontend | A Python project has a Vite frontend, usually built and mounted as backend-served static assets. |
| `nextjs-frontend` | Next.js App Router + TypeScript | The project is frontend-first, usually content, marketing, personal site, or product UI work. |
| `go-gin-vite-fullstack` | Go + Gin + zap + React/Vite | A Go service uses the `go-template` conventions and may include a Vite frontend. |
| `rust-tauri-desktop` | Rust + Tauri v2 + React/Vite | A desktop app follows CPA-Desktop-style Tauri IPC, app-data config, subprocess lifecycle, updater, and React shell conventions. |

## Install

Push this repository to GitHub before using it as a registry. Trellis 0.5.9
expects registry sources such as `gh:user/repo/path` and does not accept a local
filesystem path as `--registry`.

Interactive template chooser:

```bash
trellis init --registry gh:Tendo33/my-spec-templates/marketplace
```

Install one template:

```bash
trellis init --registry gh:Tendo33/my-spec-templates/marketplace --template python-vite-fullstack
trellis init --registry gh:Tendo33/my-spec-templates/marketplace --template nextjs-frontend
trellis init --registry gh:Tendo33/my-spec-templates/marketplace --template go-gin-vite-fullstack
trellis init --registry gh:Tendo33/my-spec-templates/marketplace --template rust-tauri-desktop
```

Append missing files to an existing project's `.trellis/spec/`:

```bash
trellis init --registry gh:Tendo33/my-spec-templates/marketplace --template python-vite-fullstack --append
```

## Repository Layout

```text
my-spec-templates/
└── marketplace/
    ├── index.json
    └── specs/
        ├── python-vite-fullstack/
        ├── nextjs-frontend/
        ├── go-gin-vite-fullstack/
        └── rust-tauri-desktop/
```

Each template directory directly contains the files that should land under a
target project's `.trellis/spec/`. Do not wrap template contents in another
`spec/` directory.

## Maintenance Rules

- Keep template rules grounded in real repositories.
- When a source template changes behavior, commands, structure, scripts, or
  public APIs, update the corresponding spec template.
- Do not put secrets, task state, `.trellis/tasks/`, `.trellis/workspace/`, or
  platform-specific prompt folders inside marketplace templates.
- Treat template IDs as public API. If a rewrite would surprise existing users,
  add a new ID instead of changing behavior in place.
- Frontend specs use `DESIGN.md` as the visual source of truth. When a target
  project does not have one, choose a suitable starting point from
  `VoltAgent/awesome-design-md` or `getdesign.md` before major UI work.

## Validation

```bash
node -e "JSON.parse(require('fs').readFileSync('marketplace/index.json','utf8')); console.log('index.json ok')"
find marketplace/specs -maxdepth 2 -name README.md -print
```

## Release Gate

Before tagging or announcing a release, run local validation, push `main`, then
verify the remote registry through Trellis:

```bash
curl -fsSL https://raw.githubusercontent.com/Tendo33/my-spec-templates/main/marketplace/index.json >/tmp/my-spec-templates-index.json

tmpdir=$(mktemp -d)
cd "$tmpdir"
trellis init --no-monorepo --registry gh:Tendo33/my-spec-templates/marketplace --template python-vite-fullstack -y
test -f .trellis/spec/README.md

tmpdir=$(mktemp -d)
cd "$tmpdir"
trellis init --no-monorepo --registry gh:Tendo33/my-spec-templates/marketplace --template nextjs-frontend -y
test -f .trellis/spec/README.md

tmpdir=$(mktemp -d)
cd "$tmpdir"
trellis init --no-monorepo --registry gh:Tendo33/my-spec-templates/marketplace --template go-gin-vite-fullstack -y
test -f .trellis/spec/README.md

tmpdir=$(mktemp -d)
cd "$tmpdir"
trellis init --no-monorepo --registry gh:Tendo33/my-spec-templates/marketplace --template rust-tauri-desktop -y
test -f .trellis/spec/README.md
```
