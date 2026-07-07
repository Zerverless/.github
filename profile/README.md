<div align="center">

# Zerverless

**AI-native serverless ecosystem for AWS.**

Understand, design, visualize, build, and improve serverless systems —
directly inside your own AWS account.

[Website](https://zerverless.com) · [Docs](https://zerverless.com/docs) · [ZDK](https://github.com/zerverless/zdk) · [OZ](https://github.com/zerverless/oz)

</div>

---

## Products

| Product | What it does |
|---|---|
| **[Xero](https://zerverless.com/xero)** | Turns prompts into serverless architecture proposals, explanations, migration plans, and CDK/ZDK skeletons. |
| **[Hero](https://zerverless.com/hero)** | Analyzes existing serverless systems for cost, security, performance, and logs, then recommends fixes. |
| **[Air](https://zerverless.com/air)** | Read-only visualization of serverless systems already running in your AWS account. |

## Open Source

| Project | What it is |
|---|---|
| **[zdk](https://github.com/zerverless/zdk)** | L3 AWS CDK construct library — opinionated, high-level serverless building blocks. |
| **[oz](https://github.com/zerverless/oz)** | CLI for discovering, tracing, and explaining serverless AWS accounts. |

## Principles

1. Customer workloads live in the customer's own AWS account — Zerverless never runs your code for you.
2. We provide the control plane, visibility, analysis, generation, and guidance.
3. Read-only access and deploy/write access are never treated as the same trust level.
4. Open source projects (`zdk`, `oz`) work standalone — no dependency on the private Zerverless platform.

## Org-wide Defaults

Files in this repository's root apply as GitHub org-wide defaults for any
repository under `zerverless/` that does not define its own:
`CODE_OF_CONDUCT.md`, `SECURITY.md`, `CONTRIBUTING.md`, issue templates. See
each individual repository for overrides specific to that project.

---

<sub>© Zerverless LLC. See individual repositories for license terms — open
source projects (`zdk`, `oz`) are permissively licensed; product and platform
repositories are proprietary.</sub>
