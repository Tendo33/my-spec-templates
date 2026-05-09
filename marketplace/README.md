# Trellis Marketplace

This directory is the registry source path for Trellis.

Use:

```bash
trellis init --registry gh:Tendo33/my-spec-templates/marketplace
```

Trellis reads `marketplace/index.json`, lists entries with `type: "spec"`, and
copies the chosen template directory into the target project's `.trellis/spec/`.

The `path` field in `index.json` is relative to the repository root, not to this
directory.
