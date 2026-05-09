# Third-Party Script Fallbacks

## Problem

A map, analytics widget, or external script fails to load and leaves a blank or
broken section.

## Root Cause

The UI assumes a third-party script will always load and does not preserve a
non-script fallback.

## Solution

- Keep primary content available without the third-party script.
- Show a clear failure or unavailable state.
- Preserve list/search/contact alternatives for maps.
- Keep public keys in public env vars and secrets server-only.
- Avoid blocking page rendering on analytics.

## Prevention Checklist

- [ ] Missing key state is handled.
- [ ] Script load failure state is handled.
- [ ] Non-script fallback still supports the user's main task.
- [ ] Browser smoke includes missing-key or failed-script behavior when touched.
