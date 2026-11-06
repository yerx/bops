<!-- BEGIN:nextjs-agent-rules -->

# This is NOT the Next.js you know

This version has breaking changes — APIs, conventions, and file structure may all differ from your training data. Read the relevant guide in `node_modules/next/dist/docs/` (resolved from this file's directory; in monorepos the `next` package may not be visible from the repo root) before writing any code. Heed deprecation notices.

This block is written and re-added by `next dev` — verify at `node_modules/next/dist/server/lib/generate-agent-files.js`. Removing it from a diff only re-creates the uncommitted change; committing it with your work keeps the tree clean.

<!-- END:nextjs-agent-rules -->

## Development playbook

For development work in this fork, read [docs/development-playbook.md](docs/development-playbook.md) and [CONTRIBUTING.md](CONTRIBUTING.md). Keep work bounded: inspect the touched surface, implement the smallest accepted change, run focused checks and complete one review/fix cycle unless the user authorizes broader work. Preserve unrelated or dirty work.

<!-- PORTFOLIO-ROUTER:START -->
## Coding task routing

For choosing a coding workflow, use the repository-pinned `portfolio-task-router` at `.agents/skills/portfolio-task-router/SKILL.md`. Its bundled policy is advisory to these project instructions, existing tighter iteration limits and explicit user scope. It does not authorize extra agents, repairs outside scope, merge, release or deployment. Named source practices are not proof of installed skills. Keep task evidence in the PR or existing project documentation. Bundle identity: `references/provenance.json`; preserve its hashes and installation receipt when updating the bundle.
<!-- PORTFOLIO-ROUTER:END -->

## Fork and runtime boundaries

- This project's PR target is `yerx/bops:main`. Verify remote URLs; upstream `OrgoAI/bops` remains a separate repository.
- Read `cloud/README.md` and `db/README.md` before cloud or schema work. App checks use Node 22 in CI; cloud tests require Node 24 and disposable Postgres.
- Use synthetic fixtures and isolated state. Preserve workspace/computer ownership, member access and external-action approval boundaries.
- Review scripts before running setup, install, release or deployment commands. Inherited upstream publishing and signing settings are not fork release authorization.
