# Verification

Use the target project's local docs first. If no local verification file exists,
use this baseline.

## Frontend

```bash
npm run lint
npm run format:check
npm run typecheck
npm run test:run
node scripts/check-i18n.mjs
npm run build
```

## Rust Native Layer

```bash
cd src-tauri
cargo fmt --check
cargo test
cargo clippy --all-targets --all-features -- -D warnings
```

If the project does not yet enforce clippy in CI, run `cargo test` and
`cargo fmt --check`, then call out that clippy is not an enforced local gate.

## Full Desktop Build

```bash
npm run tauri build
```

Run the full desktop build when changing:

- `src-tauri/tauri.conf.json`
- `src-tauri/capabilities/`
- updater, signing, bundle, icons, or platform-specific code
- frontend build configuration consumed by Tauri

## Focused Checks

```bash
npx vitest run src/components/__tests__/statusbar.helpers.test.ts
cd src-tauri && cargo test app_config
cd src-tauri && cargo test cpa_lifecycle
```

Use focused checks while iterating, but run the broader gate before handoff when
the change crosses Rust/frontend boundaries.
