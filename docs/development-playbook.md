# Grokbot for Biz development playbook

Adapted from [Hxstory's development playbook](https://github.com/yerx/hxs-ios/blob/4e49c38dfbb814302f7eddc0426eb20352bb48b9/docs/development-playbook.md), pinned at `4e49c38dfbb814302f7eddc0426eb20352bb48b9`. Its source is `coding-productivity-playbook.md`, policy **0.6** (October 8, 2026), canonical source release `b1b5f598199bd65a66ae6405acf6be8ed0360e24` (unchanged at source revision `4a1b24c5803f85f54c685ffa31d8552d9349f0a1`). This adaptation retains the working loop, feature knowledge, evidence, journals and readiness guidance; project entrypoints below describe this Bops fork.

Read [AGENTS.md](../AGENTS.md), [CONTRIBUTING.md](../CONTRIBUTING.md), and the [task router](../.agents/skills/portfolio-task-router/SKILL.md) first. The unchanged portable router is bundle **1.0.2 / policy 0.6**, including its source pins and integrity receipt. Its cross-portfolio and clinical examples are reference context; they do not introduce Hxstory workflows or clinical requirements into Bops. Named source practices do not establish that those skills are installed.

## Working loop

1. Define one accepted outcome, scope, invariants and failure cases. Read repository and child guidance first. Select installed skills only when useful; the router's adoption catalog names methods, not proof that helpers are installed. Keep the repository's architecture and tighter task limits.
2. Verify repository identity and the current remote default branch. Record base/head SHA and any submitted tracked diff and relevant untracked file hashes. Use a fresh branch and isolated worktree from the verified remote base, with one writer. Never reset, stash, switch, clean or reuse another owner's dirty work. Give tests distinct ports, synthetic fixtures, databases/namespaces and artifact paths; clean only task-owned resources.
3. Map how to exercise the affected feature: entry screen/route, navigation, state, dependencies, fixture, permissions, expected result and failure/recovery cases. Link existing feature maps, specs and checks rather than inventing a parallel registry. Update the map when verified behavior changes.
4. Implement the smallest slice. For meaningful behavior changes, reproduce the bug or establish a baseline, then check valid behavior and negative cases at public seams. Documentation-only changes need factual, command/path and link checks; they do not establish application acceptance.
5. Run discovered repository commands in the correct environment. Portable/web checks prove only their tested scope. Apple SDK builds, simulator, archive/signing and physical-device checks have separate evidence. Record tool versions, fixture, actual command, exit/result and redacted artifacts at the submitted source identity.
6. Obtain independent read-only review against scope and acceptance at that identity. Distinguish **RERAN_CHECKS** from **INSPECTED_RECEIPTS_ONLY**. Return grouped findings to the original builder; fixes invalidate affected prior checks and review, so rerun and re-review. Stop at the tighter agreed limit or after two failed repair attempts and report the diagnosis.
7. Prepare a scoped PR/MR with exact source, evidence, risks, remaining gaps and rollback. Serialize integration and recheck the combined revision after integration. Keep merge, release, deployment and external-action authorization gates separate from engineering readiness.

## Evidence and durable handoff

Use **PASSED**, **FAILED**, **BLOCKED** and **NOT RUN** per scenario. A zero exit with skipped or absent tests does not prove acceptance. A screenshot, build, health response, preview or reviewer receipt each proves only its own scope. Never turn a missing check into a pass. Expected rejection in a negative fixture must be stated separately from an unexpected test failure.

Use existing journals/review notes and Git history for consequential decisions and corrections. Append concise evidence pointers; do not rewrite historical claims as current truth or commit private conversations, credentials, patient/customer records or internal assistant instructions. Record human time separately from elapsed time; unknown runtime/spend stays UNKNOWN. Unrelated observations enter the existing queue for review, not automatic repair or a new restriction. Promote a recurring lesson only after evidence, valid/negative controls and a bounded trial.

A compact task or handoff record can live in the established journal or PR/MR:

```text
Outcome / scope / owner / worktree / branch:
Base / head SHA / submitted dirty and untracked hashes:
Feature map / invariants / synthetic fixture / environment:
Actual commands / PASSED / FAILED / BLOCKED / NOT RUN:
Artifact links / reviewer / reviewed identity / review mode:
Findings / corrections / reruns / time and cost or UNKNOWN:
Remaining gaps / next owner / integration and release gate:
```

## Verify identity before release

Trace **app → repository → deployment → database → domain** before acting or claiming readiness. Record the application/bundle identity, canonical remote, branch and SHA, hosting account/project/environment and immutable build/deployment ID, database project/environment/schema or migration revision, and domain/alias/routing target. Discover uncertain links read-only and mark them UNKNOWN; a familiar name or working URL is insufficient. Keep identifiers and redacted evidence, never secret values.

For hosting, reconcile the produced artifact and runtime with the tested source: a healthy static frontend does not prove an API exists, and a successful preview does not prove the production alias serves that build. Inspect actual build/output/route configuration, immutable artifact or deployment metadata, API readiness and database compatibility. For native delivery, reconcile bundle ID, version/build number, archive/source/configuration and processed store build; simulator success does not prove a signed upload or device behavior.

Review CI configuration and external effects before publication. Documentation describes the workflow; it does not install enforcement or authorize automation. CI failures, billing/access limits and absent checks stay visible. After a separately authorized release, verify artifact processing, target/alias and critical behavior, with rollback appropriate to the change.

## Grokbot for Biz entrypoints and acceptance

This project is the user's fork [`yerx/bops`](https://github.com/yerx/bops), known locally as Grokbot for Biz. The integration target is the fork's `main`, not upstream [`OrgoAI/bops`](https://github.com/OrgoAI/bops). Inspect remote URLs and the current remote branch before creating a task branch. Upstream branding, hosted endpoints and release configuration remain inherited; they are not evidence of fork-owned infrastructure or publication authority.

| Identity link | Repository evidence and release check |
| --- | --- |
| App → repository | [package.json](../package.json) names Bops, Electron entrypoint `desktop/main.cjs` and app ID `ai.orgo.bops`. [README](../README.md#how-it-works) maps Electron, Next.js, cloud and computer runners. Verify the built app and exact source before claiming which fork is running. |
| Repository → runtime | Next.js lives in `app/` and `lib/server/`; [next.config.ts](../next.config.ts) produces a standalone server. [Bops Cloud](../cloud/README.md) is a separate Node 24+ service. [Cloud runner](cloud-runner.md) covers bot-computer execution; `edge/` is the self-hosted relay. A local page does not prove cloud, relay or runner behavior. |
| Runtime → data | [Database guide](../db/README.md) describes the `bops` Postgres schema and migrations under `db/migrations/`. Self-hosted state and hosted state differ; discover the active mode and database identity without exposing secrets. Cloud startup can apply migrations: starting it is not a read-only configuration check. |
| Runtime → distribution/domain | [package.json](../package.json) still points Electron publishing at `OrgoAI/bops`; [release script](../scripts/release.sh) checks the inherited app/signing identity and can notarize builds. README domains describe upstream services. Verify fork ownership, release destination, signing identity, runtime URLs and immutable artifacts before any separately authorized release. |

### Feature knowledge and acceptance

Use the [README](../README.md), [cloud guide](../cloud/README.md), [runner guide](cloud-runner.md), relevant source and existing `cloud/test/` cases as the starting map. No dedicated verification skill or feature registry is installed by this change. For substantial changes, put the touched journey's entrypoint, prerequisites, expected result, failure/recovery paths and evidence in the PR or a scoped note under `docs/`; promote maintained runbooks only when useful.

Match acceptance to the affected boundary:

- Chat, routines or saved state: create → save → reopen → restart, workspace isolation, offline/reconnect and failed-save recovery. Keep hosted and self-hosted cases explicit.
- Permissions and connected apps: allowed and denied roles, per-bot/per-workspace scope, approval rejection/cancellation and revoked access. Preserve the existing authorization rules; a model response is not proof that an external action succeeded.
- Cloud or runners: authenticated routing, cross-user/computer denial, provider failures and idempotent webhook/replay behavior with synthetic fixtures and fake providers. A local replay is not live-provider delivery.
- Electron or UI: verify the real app flow, keyboard/focus and accessibility where touched, and distinguish a browser check from packaged-app behavior. Never use another person's live state, Keychain or connected account as a fixture.

Bops creates or deletes Orgo computers only in its own workspace, as documented in CONTRIBUTING.md. Preserve that invariant. Use generic fictional data and isolated local providers; do not send messages, spend provider credit, provision computers or change access merely to validate documentation.

### Discovered commands and their limits

These commands come from checked-in manifests, CONTRIBUTING.md and [CI](../.github/workflows/ci.yml). Listing them does not claim they were run for this documentation change. Use prepared dependencies and task-owned output, ports and throwaway databases; do not run setup against someone else's checkout or start an authenticated app as a documentation check.

| Command from repository root | Scope / prerequisite |
| --- | --- |
| `npx next typegen` | Generate route types before typechecking, as CI does. Requires prepared Node dependencies; writes generated output. |
| `npx tsc --noEmit -p .` | App/server TypeScript check; does not prove a UI journey or provider integration. |
| `npx tsc -p cloud/tsconfig.json --noEmit` | Separate Bops Cloud TypeScript check. |
| `npm run lint` | Existing ESLint script. |
| `npm run build` | Next.js production build with standalone output; inspect runtime/artifact contents. Does not prove Electron packaging or signing. |
| `node --test --test-concurrency=1 "cloud/test/core-*.test.ts"` | CI core tests: Node 24+, dependencies, local fake providers and a throwaway Postgres configured through `BOPS_TEST_DATABASE_URL`. |
| `node --test --test-concurrency=1 "cloud/test/edge-*.test.ts" cloud/test/server.test.ts` | CI edge/router tests: Node 24+, a separate throwaway Postgres; run serially as CI does. |

The cloud-test job in CI provisions two disposable Postgres databases and the test role/schema using `db/provision.sql`. Follow that setup rather than pointing tests at an existing service database. The repository has no root `npm test` script; discover focused checks from source and CI instead of inventing one. CI uses Node 22 for app static checks and Node 24 for cloud tests.

Desktop acceptance needs macOS and the actual Electron app. `npm run app:build` writes `desktop/repo.json` and creates an unsigned local package; it does not prove a distributable release. `npm run app:install` replaces `/Applications/Bops.app`. `npm run app:release` executes the release script and may use signing/notarization services. These are operational actions with separate scope, not routine documentation checks.

### Evidence locations and publication effects

Keep scoped evidence and decisions in the PR, using the existing [PR template](../.github/PULL_REQUEST_TEMPLATE.md). Link durable procedures or reports from `docs/` when the change warrants them; `docs/releases/` contains existing upstream release notes, not an automatic journal for every task. Record independent review as outstanding when it has not occurred. Small documentation work can use one worker for edits and checks; no extra agents are authorized by this playbook.

The checked-in [CI workflow](../.github/workflows/ci.yml) runs on push and pull request, with read-only repository permissions. It typechecks, lints, scans Git history for secrets and runs cloud tests with fake providers and disposable databases. These checks do not establish live provider delivery, desktop acceptance, a release or production readiness. Inspect current workflow/integration configuration before publishing; report pending, failed, skipped or absent checks explicitly.

A branch push and draft PR to `yerx/bops` do not authorize upstream publication, merge, release, migrations or deployment. Inherited `OrgoAI` destinations and signing checks must be reconciled before any future release; this playbook does not change them. Roll back this documentation adoption by reverting its commit; no runtime or data migration is introduced.
