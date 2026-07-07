# Contributing to .github

Thanks for your interest in improving `.github`! This project is
maintained by the Zerverless team and the open source community.

## Before You Start

- For anything non-trivial (new feature, breaking change), please open an
  issue first to discuss the approach before writing code.
- Check existing issues and PRs to avoid duplicate work.

## Development Setup

```bash
git clone https://github.com/zerverless/.github.git
cd .github
# No build step — this repo is Markdown only.
```

## Commit Convention

We use [Conventional Commits](https://www.conventionalcommits.org/):

```
feat: add ZerverlessQueueWorker construct
fix: correct IAM policy scope on ZerverlessTable
docs: clarify quick start in README
```

This keeps `CHANGELOG.md` generation predictable and makes history easy to
scan.

## Pull Requests

1. Fork the repo and create a branch from `main`: `feat/short-description`.
2. Make your change, with tests where applicable.
3. Run the full local check suite (see below) — there is no CI pipeline yet,
   so **your local run is the only signal we have before merge.**
4. Open a PR using the template; fill in every section.
5. At least one maintainer (see `CODEOWNERS`) must approve before merge.

## Local Check Suite

```bash
# No build step — this repo is Markdown only.
pnpm test
pnpm build
```

## Code of Conduct

This project follows our `CODE_OF_CONDUCT.md`. By participating, you agree
to abide by it.

## License

By contributing, you agree that your contributions will be licensed under
this repository's `LICENSE`.
