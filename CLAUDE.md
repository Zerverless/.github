# CLAUDE.md — .github

## What this repo is

The public face of the Zerverless GitHub organization, plus org-wide default
governance files. Category: **Core**, visibility: **public**.

## Do

- Keep `profile/README.md` accurate: product list, OSS list, links.
- Keep org-wide `CODE_OF_CONDUCT.md` / `SECURITY.md` / `CONTRIBUTING.md`
  generic enough to apply to any repo that doesn't override them.

## Never

- Add infrastructure, product logic, application code, billing, or
  deployment code here — this repo is documentation and governance only.
- Add secrets, internal URLs, or anything not meant for public eyes — this
  is the most publicly visible repo in the org.

## Related repos

Every repo in the ecosystem is *linked from* here, but this repo depends on
none of them.

## Ecosystem rules (apply org-wide, restated here for reference)

1. Platform (`zerverless-platform`) owns auth/users/orgs/entitlements/quotas/usage.
2. Products talk to Platform only via `zerverless-sdk`.
3. Shared AWS logic lives in `zerverless-engines`, never duplicated per product.
4. Private UI uses Cloudscape only via `zerverless-ui`.
5. `zdk` and `oz` must work with zero dependency on the private platform.
6. No GitHub Actions yet — everything is run and verified locally.
7. TypeScript + pnpm across the org.
