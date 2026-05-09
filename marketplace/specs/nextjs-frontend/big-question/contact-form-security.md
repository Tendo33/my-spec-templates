# Contact Form Security

## Problem

A public contact or lead form accepts unsafe input, sends malformed emails, or
can be abused from arbitrary origins.

## Root Cause

The form is treated as a UI feature only, while the route handler is a public
server boundary.

## Solution

- Validate input with Zod or the target project's existing schema tool.
- Sanitize user-controlled text before HTML or email rendering.
- Use origin allowlists for browser-submitted forms.
- Add rate limiting or honeypot fields when abuse is realistic.
- Return finite error codes.
- Keep SMTP/API secrets server-only.

## Prevention Checklist

- [ ] Inputs are validated at the route handler.
- [ ] Email body escapes user-controlled values.
- [ ] Source paths are restricted to internal paths.
- [ ] Error codes are finite and documented.
- [ ] Secrets are not exposed through `NEXT_PUBLIC_*`.
