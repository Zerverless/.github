<div align="center">

# Zerverless

**AI-native serverless ecosystem for AWS.**

</div>

---

## What is Zerverless?

Zerverless helps teams **understand, design, visualize, build, and improve**
serverless systems — directly inside their own AWS account. It's not a
platform that runs your code for you; it's the control plane, the AI, and
the tooling around your own AWS account.

Three principles drive every technical decision in this organization:

1. **Customer workloads always live in the customer's own AWS account.**
   Zerverless never runs your code — it reads, analyzes, generates, and
   guides.
2. **Zerverless provides the control plane** — visibility, analysis,
   generation, guidance — never the runtime itself.
3. **Read-only access and deploy/write access are never the same trust
   level.** A product that only *looks* at your AWS account (like Air) is
   architecturally distinct from one that could *change* it.

Zerverless is currently built and maintained by a single person. The
project is organized as **13 repositories across 4 categories** so that
each piece stays independently understandable, even though one person
touches all of them.

## The 13 repositories, by category

### Core — foundation, control plane, and customer-facing surfaces

| Repo | What it is |
|---|---|
| **[.github](https://github.com/zerverless/.github)** | This repo. Public org profile + governance defaults shared across the org. |
| **[zerverless-infra](https://github.com/zerverless/zerverless-infra)** | Global AWS foundation: DNS, wildcard certificate, WAF, security & observability baseline. Deploys first, before anything else. |
| **zerverless-platform** | The control plane: Cognito auth, users, organizations, entitlements, quotas, usage tracking, connected AWS accounts. Every product asks *this* repo whether a user is allowed to do something — no product decides that on its own. |
| **zerverless-web** | The public marketing site at zerverless.com — landing page, pricing, blog, docs. |
| **zerverless-app** | The private customer dashboard at app.zerverless.com — organization settings, billing, usage, links into the products. |

### Products — what a customer actually pays for and uses

| Repo | What it is |
|---|---|
| **zerverless-xero** | AI product. Turns a prompt into a serverless architecture proposal, explanation, migration plan, and a CDK/ZDK code skeleton. |
| **zerverless-hero** | AI product. Analyzes an *existing* serverless system — cost, security, performance, logs — and recommends fixes. |
| **zerverless-air** | Read-only visualization of the serverless systems already running in a customer's AWS account. Never writes to it. |

### Open Source — public, and deliberately independent of everything private

| Repo | What it is |
|---|---|
| **[zdk](https://github.com/zerverless/zdk)** | Zerverless Development Kit. An opinionated, secure-by-default L3 construct library on top of AWS CDK. Usable by anyone, with zero relationship to Zerverless the company. |
| **[oz](https://github.com/zerverless/oz)** | Open Zerverless. A CLI for discovering, tracing, and explaining what's running in *any* AWS account — again, usable standalone. |

### Shared Libraries — private code shared across the products, so it isn't duplicated three times

| Repo | What it is |
|---|---|
| **zerverless-sdk** | The one typed client every private app uses to talk to `zerverless-platform` — auth, entitlements, quotas, usage. |
| **zerverless-engines** | The shared "AWS brain": discovery, costs, logs, tracing, AI context building, architecture generation. Used by Xero, Hero, and Air so none of them reimplement it. |
| **zerverless-ui** | The shared Cloudscape component library every private dashboard/product renders through. |

## What this specific repo (`.github`) does

This repository controls two things for `github.com/zerverless`:

1. **The public organization profile** — [`profile/README.md`](profile/README.md)
   is what renders on the org's GitHub landing page.
2. **Org-wide governance defaults** — the `CODE_OF_CONDUCT.md`, `SECURITY.md`,
   `CONTRIBUTING.md`, and issue templates in this repo's root apply
   automatically to any repository in the `zerverless` org that doesn't
   define its own. This is a real GitHub feature, not just a convention.

## Not responsibilities

This repo has no infrastructure, no product logic, no application code, no
billing, and no deployment code. If you're looking for any of that, find
the right repo in the table above.

## Status

Defined.
