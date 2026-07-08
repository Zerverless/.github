# CLAUDE.md — .github

This file gives an AI agent full context before making any change in this
repository. Read it even if you've never seen any other Zerverless repo —
this file is written assuming that's the case.

## Ecosystem context: what is Zerverless?

Zerverless is an AI-native serverless ecosystem for AWS, built and
maintained by **a single person**. Its mission: help teams understand,
design, visualize, build, and improve serverless systems directly inside
their own AWS account — Zerverless is the control plane and the AI around a
customer's AWS account, never the thing running their code.

Three principles govern every technical decision across the whole
ecosystem, not just this repo:

1. Customer workloads always live in the customer's own AWS account.
2. Zerverless provides the control plane — visibility, analysis,
   generation, guidance — never the runtime.
3. Read-only AWS access and deploy/write AWS access are never treated as
   the same trust level.

The ecosystem is split into **13 repositories in 4 categories**, so that
each one stays scoped and understandable on its own even though a single
person maintains all of them:

| Category | Repos | Role |
|---|---|---|
| **Core** | `.github` (this repo), `zerverless-infra`, `zerverless-platform`, `zerverless-web`, `zerverless-app` | Foundation, control plane, customer-facing surfaces |
| **Products** | `zerverless-xero`, `zerverless-hero`, `zerverless-air` | What a customer actually pays for and uses |
| **Open Source** | `zdk`, `oz` | Public, independent of the private platform |
| **Shared Libraries** | `zerverless-sdk`, `zerverless-engines`, `zerverless-ui` | Private code shared across the 3 products so it isn't duplicated |

One-line description of every repo, so you never have to guess:

- **`zerverless-infra`** — global AWS foundation (DNS, certificate, WAF, security/observability baseline). Deploys first, before anything else.
- **`zerverless-platform`** — the control plane: auth, orgs, entitlements, quotas, usage, connected AWS accounts. Every product asks *this* repo for permission; no product decides access on its own.
- **`zerverless-web`** — public marketing site (zerverless.com).
- **`zerverless-app`** — private customer dashboard (app.zerverless.com).
- **`zerverless-xero`** — AI product: prompt → serverless architecture proposal.
- **`zerverless-hero`** — AI product: analyzes an existing serverless system, recommends fixes.
- **`zerverless-air`** — read-only visualization of a customer's serverless systems. Never writes to their AWS account.
- **`zdk`** — open source L3 CDK construct library. Must work standalone, zero dependency on anything private.
- **`oz`** — open source CLI for discovering/explaining any AWS account. Must work standalone, zero dependency on anything private.
- **`zerverless-sdk`** — the one typed client every private app uses to talk to `zerverless-platform`.
- **`zerverless-engines`** — the shared "AWS brain" (discovery, costs, logs, tracing, AI context, architecture generation), used by Xero/Hero/Air so it's written once.
- **`zerverless-ui`** — the shared Cloudscape component library every private dashboard/product renders through.

## What THIS repo (`.github`) is

Category: **Core**. Visibility: **public**. It is the org's public face and
the source of governance defaults.

Two responsibilities, and only two:

1. `profile/README.md` — rendered on `github.com/zerverless`. Explains what
   Zerverless is and links to every product and OSS project.
2. Org-wide governance defaults — `CODE_OF_CONDUCT.md`, `SECURITY.md`,
   `CONTRIBUTING.md`, and `ISSUE_TEMPLATE/` in this repo's root are used
   automatically by GitHub for any repo in the `zerverless` org that
   doesn't define its own version of that file. This is a platform feature
   of GitHub, not just a convention this project follows.

## Do

- Keep `profile/README.md` accurate whenever a repo is added, renamed, or
  its status changes (Defined → Planned → In Development → Active).
- Keep the org-wide governance files here generic enough that they make
  sense as a sane default for *any* repo in the org, public or private.

## Never

- Add infrastructure, product logic, application code, billing, or
  deployment code — this repo is documentation and governance only.
- Add secrets, internal URLs, staging/dev endpoints, or anything not meant
  for public eyes — this is the single most publicly visible repo in the
  organization; treat every change here as public from the moment it's
  committed.
- Assume the reader (human or agent) has seen any other Zerverless repo —
  this file and `profile/README.md` may be the only context they get.

## Related repos

This repo is *linked from* by every other repo's README, and its content
(`profile/README.md`) links back to all of them. It depends on none of
them technically — there's no build step, no package, nothing to install.

## Commands

None. This repository is Markdown only; there is no build, test, or deploy
step.
