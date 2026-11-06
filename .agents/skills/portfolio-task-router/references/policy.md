# Portable routing policy — 0.6 / bundle 1.0.2

Repository instructions, established scope and explicit user preferences govern the task. This policy does not replace project doctrine, OpenSpec approvals, existing tighter iteration limits, branch isolation or release/clinical gates. Keep unrelated work and Jev experiments separate. Roles are responsibilities; do not launch extra agents unless the user or applicable instructions authorize them. For a small task, no independent agent is mandated merely to satisfy a role; use a distinct reviewer when required and available, otherwise disclose the gap.

## Observation and promotion

Scheduled scouts observe within their existing scope, deduplicate findings and report or queue only at an authorized destination. A finding grants no repair, scheduling or publication authority. Existing explicitly authorized repair jobs retain their bounded scope; out-of-scope findings stay observations. Buffer routine patterns for days, cluster with human review and choose one approved root-cause experiment. Urgent security/data-loss concerns escalate via an authorized channel without automatic fix authority. Significant policy restrictions require human ratification. Record negative and valid-positive controls, false positives, cost and rollback.

## Architecture and execution lanes

Structural changes require an agreed before-implementation checkpoint; respect existing repo approval requirements. Prefer bounded seams and valid states over speculative rewrites. No Dune adoption or blanket comment removal. Staged expand → migrate → verify → contract retains required compatibility until deployment/caller constraints are proven. Web and portable checks require proven environment compatibility; Xcode native simulator/archive checks need macOS, device checks need hardware. Cloud availability and Linux success do not prove native behavior. Releases/deployments and clinical actions need human approval; InterEHR agent preparation is reviewed by a human acupuncturist before clinical execution.

## Operating contract


Use this contract for feature, bug, refactor and maintenance work. Roles are responsibilities, not a mandate to keep extra agents running.

| Role | Ownership and boundary |
| --- | --- |
| Portfolio coordinator | Non-coding: ranked allocation across projects, scope, acceptance, dependencies, status, budgets and evidence. Initially the parent can also perform project coordination. |
| Project coordinator, optional | Non-coding: briefs and queue for one project when workload exceeds the parent's ability to manage it. Do not create a permanent coordinator for every repo. |
| Builder | Sole code writer on its assigned branch/worktree; implements and repairs only approved scope, runs self-checks, submits exact-version evidence. |
| Independent reviewer | Read-only source/diff scrutiny against intent and acceptance; reports findings without quietly rewriting builder code. |
| Executable verifier | Runs normal repository commands and the actual acceptance scenario at the submitted identity in the appropriate lane, with isolated fixtures and declared runtime side effects. Does not patch source while verifying. |
| Integrator / coordination role | Owns stack topology and serialized integration. Mechanical integration requires existing authorization; conflicts or behavioral changes return to the assigned builder. Separately required merge/release approval still applies. |

For modest work one independent task can cover review and verification. Label **RERAN_CHECKS**, **INSPECTED_RECEIPTS_ONLY**, or a precise mixed scope; source review is not a runtime rerun. If only receipts were inspected, executable evidence must still come from an identified run, and any required independent rerun remains outstanding. Disclose actual model setup; multiple same-model tasks are not multi-model review.

**Review-return loop:** builder submits → coordinator checks packet completeness → independent review and executable acceptance verification → coordinator judges/deduplicates findings → grouped current acceptance blockers return to the original builder → bounded fixes and relevant reruns → new submission and revision-bound re-review. Record disagreements, dismissed findings and accepted limitations with reasons. Review is judgment, not automatic obedience to every suggestion.

A changed patch invalidates affected old green checks and verdicts. Refresh tracked/untracked identity, rerun relevant checks plus integration acceptance, and commission re-review at the resulting revision. A clean review at an old snapshot is historical only. The coordinator does not accept a worker's completion message as proof.

Current acceptance blockers are repair work within approved scope. Out-of-scope defects need separate promotion/authorization; unrelated smells and scout findings enter the observation buffer for periodic clustering. Do not fan out a repair task per sighting. Security/data-loss urgency retains the existing escalation exception. Repeated failures trigger diagnosis/design review at the existing harness/budget checkpoint, not identical retries indefinitely. Honor user stop, permissions, agreed spending/runtime limits and real environment blockers; BLOCKED cannot become VERIFIED by lowering acceptance.

Compact packets (collapse to a paragraph for small work; do not create another subsystem):

```text
SUBMISSION
Task / builder / branch or worktree / scope and non-goals:
Base and parent SHA / head SHA OR dirty snapshot:
Tracked diff hash / hashes of all relevant tracked and untracked submitted files:
Acceptance criteria / safety invariants:
Actual commands, environment, fixture, results including skips and NOT RUN:
Artifacts / known gaps / budget used or UNKNOWN:
Requested review and executable verification / next authorization gate:

RETURN FOR FIXES
Task / exact reviewed revision and source identities:
Grouped finding ID / severity / violated acceptance criterion:
File and location / expected versus actual behavior:
Reproduction or failing test / supporting evidence:
Coordinator judgment / approved repair scope / original builder:
Explicit resubmission acceptance / required reruns / remaining budget:

VERDICT
Exact revision / reviewer and verifier / RERAN_CHECKS or INSPECTED_RECEIPTS_ONLY:
Acceptance results / actionable findings / dismissed or deferred reasons:
Integration acceptance / limitations / VERIFIED, NEEDS_FIX or BLOCKED:
Required human authorization / next owner:
```


## Selective adoption catalog


Adoption here means a reviewed, adapted discipline; it does not establish that a named skill is installed or callable. The Matt source remains pinned in provenance.json. The updated pstack catalog review uses [snapshot d0ef80d](https://github.com/cursor/plugins/tree/d0ef80d86795816da932a153458c5dbe192d294e/pstack); prior pins remain historical references.

| Status | Practices and selection rule |
| --- | --- |
| Regular when relevant | Matt implementation/TDD and Standards/Spec review for meaningful changes; `why` for unclear existing decisions; sibling `deslop` for behavior-preserving current-diff cleanup. Small tasks may use direct work without skill ceremony. |
| Conditional | Matt planning/domain/spec/tickets/PR/retro/teach; pstack `how`, `architect`, `blast-radius`, verification creation/maintenance, `interrogate`, `reflect`, `swarm`. Choose by uncertainty, shared impact and actual capacity; architectural implementation retains its checkpoint. |
| Newly adopted adaptations | `correct` for repeated evidence-backed mistake classes: architecture/types/checks before more instructions, one approved experiment through the observation buffer. `benchmark-checklist` for performance claims: baseline, correct outputs/errors, real work, representative configuration, limiter, repeated alternating runs and end-to-end relevance; inconclusive evidence stays inconclusive. `typescript-best-practices` only for TypeScript paths: narrow runtime boundaries, infer validated types and model valid states using existing conventions. `show-me-your-work` for consequential decisions: concise append-only evidence pointers in the existing journal, correcting claims visibly; no mandatory second logging subsystem. |
| Not adopted wholesale | Sticky `poteto-mode`, `no-comments`, autonomous shipping/merge, blanket swarm, all 51 helpers/principles or all 23 nested playbooks as mandatory steps. Unlisted helpers remain references, not installed dependencies. Benny triage/fix/setup and cron are not configured. |

Matt and pstack both contain `tdd` and `teach`; our named adoption is Matt's source. `deslop` belongs to cursor-team-kit, while pstack `unslop` is prose cleanup. The mdsmithaustin port's code-review is not official pstack; our code-review remains Matt's. Preserve license/safety/explanatory comments when useful; no blanket comment deletion.

Explicit pstack principle mapping (adapted, not 24 additional mandatory invocations):

| Principles | Home and boundary |
| --- | --- |
| attack-the-premise; exhaust-the-design-space; foundational-thinking; redesign-from-first-principles | the structural/domain policy structural judgment: challenge assumptions, compare viable options; no speculative rewrite or Dune adoption. |
| boundary-discipline; model-the-domain; type-system-discipline | domain/glossary and feature acceptance: validated boundaries and valid states, stack-specific tools. |
| fix-root-causes; encode-lessons-in-structure; build-the-lever | observation promotion and session learning: prove recurring cause, reuse existing tooling, one approved measured intervention. |
| prove-it-works; test-behavior-not-implementation; explain-the-number | the operating/verification policy revision-bound executable behavior, negative controls and benchmark claims; no receipt-only rerun claim. |
| sequence-verifiable-units; outcome-oriented-execution; experience-first | the operating/task policy bounded slices with product acceptance; shipping and clinical gates stay human. |
| separate-before-serializing-shared-state; make-operations-idempotent | sole writers/serialized integration and isolated repeatable fixtures; inspect actual operation semantics. |
| migrate-callers-then-delete-legacy-apis | staged expand → migrate → verify → contract; preserve required compatibility until callers/deployment constraints are proven. No automatic one-wave deletion. |
| subtract-before-you-add; minimize-reader-load; guard-the-context-window; laziness-protocol | the structural/domain policy smallest useful workflow, concise handoffs and selective references; preserve necessary guards and evidence. |
| never-block-on-the-human | Continue reversible authorized work; pause dependent work for actual missing approval. It cannot override user stop, release or clinical gates. |
