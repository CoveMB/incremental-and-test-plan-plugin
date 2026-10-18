# Orchestration Efficiency Implementation Plan

> **For agentic workers:** Use `superpowers:executing-plans` when available for native, sequential implementation of this bounded change. This development plan does not add a runtime skill dependency or authorize implementation by itself.

**Status:** Proposed, 2026-10-18. Planning requested; implementation, live evaluations and activation not approved by this document.

**Goal:** Reduce avoidable coordination turns and repeated context reading in generated orchestration prompts while preserving delivery quality, evidence and authority.

**Architecture:** Clarify the existing portable orchestration template and its documentation/scenarios. Reuse the existing gate and evidence policy; add no runtime component, state file, scheduler or integration.

**Tech stack:** Markdown instruction package; existing host Skill Creator validation and repository inspection.

**Spec:** The user's request in the originating chat to plan integration of the recommended token-use improvements: fewer status checks, less repeated reading, and reuse of applicable research/verification. The exact candidate wording and acceptance cases below make this plan self-contained. This is ordinary implementation planning, not invocation of the incremental-planning skill.

## Baseline and scope

Inspected local `main` at `08930fd2bb136582a50ed66a7bb6eb20b434c82c`; the worktree was clean before creating this plan. Remote refs were not fetched because this source-only proposal does not depend on remote freshness. Recheck the checkout and intervening edits before implementation; compare the eventual candidate against the preserved implementation baseline, not an assumed unchanged HEAD.

One coherent implementation batch owns these three existing files:

| File | Responsibility |
| --- | --- |
| `skills/incremental-plan/assets/orchestration-prompt-template.md` | Portable waiting, context-selection and evidence-reuse instructions. |
| `README.md` | Brief description of the new guidance and its evidence limit. |
| `tests/scenarios.md` | Decision-only C20 variants and separate evaluator expectations. |

The existing `skills/incremental-plan/references/gates-and-reviews.md` remains the unchanged authority for gate semantics, fresh-context independent reviews, evidence applicability, retention and execution discipline. Its lifecycle already allows reuse of unchanged applicable official-documentation evidence. The entrypoint already consumes the orchestration asset; no entrypoint, handoff template or standalone-QA change is needed.

## Global constraints

- Preserve package `incremental-and-test-plans` version `0.1.0`, both skill identities/descriptions, implicit selection, output routes and the ten-file runtime selection.
- Preserve requirements, exclusions, model selection/defaults, one writer, fresh increment chats, review scopes and simplicity/repair conditions, Gate 2/Gate 3, scoped permission provenance, native-stack proof and final reconciliation.
- Efficiency never supplies missing evidence, cancels a required read, overrides a host wait limit, or permits summarised authority to replace the actual user decision.
- Do not add fixed polling intervals, heartbeat backoff, a monitor, a controller, a ledger, a benchmark harness, hooks or dependencies. The separate existing-monitor proposal remains outside this change.
- Do not compress/delete historical evidence or migrate existing plans. Apply these instructions to newly generated prompts and requested revisions only; do not message or alter active orchestration chats.
- No model downgrade, review-count reduction, installation, publication, commits, pushes, PRs, private-source transfer or live-model runs are included in this planning request.

## Selected approach and alternatives

Use small changes to the portable prompt. Leaving it unchanged preserves ambiguity around repeated polling and the meaning of “latest” documentation on every increment. Moving the rules to another reference would add a required read without making the copied prompt self-contained. Adding adaptive monitoring would expand the product boundary and introduce scheduling/authority risks. None is preferable for this scope.

The intended benefit comes from avoided repeated work, not a shorter initial prompt. The prompt may grow modestly; any actual token benefit must be established separately.

## Exact prompt changes for approval

Keep all unmentioned text intact. If the baseline wording changes before implementation, reconcile these edits against the new source and surface material conflicts rather than overwrite them.

### 1. Make native waiting concrete

**Before:** The first implementation-chat paragraph requests “native chat creation, follow-up and waiting tools,” but defines no waiting/readback discipline.

**After:** Keep that paragraph and insert:

> While a child is running, prefer native waits with the latest returned continuation cursor when supported. Bound waits by host limits and the next required response or deadline; use compact status snapshots for immediate decisions. Read detailed history for a relevant completion, blocker, decision or inconsistency. A timeout or unchanged snapshot is not completion: continue useful authorized work or the required wait without repeatedly loading full history. Do not infer child progress from notification silence or assume a wait tool schedules future wakeups.

This changes the executor's requested behavior, not the planner's tool permissions. If required native tools are absent, the existing capability-blocker rule still applies; optional cursor absence alone is not tool absence.

### 2. Select context without weakening inspection

**Before:** The prompt requests a concise packet and existing artifacts, but does not distinguish initial/resumption inspection from repeated reading within an established context.

**After:** Insert immediately before the final “Keep orchestration lean” paragraph:

> On start or resumption, read the current brief, controlling requirements, applicable decisions and relevant evidence. Within an established context, retrieve relevant changes and missing proof; expand inspection when dependencies, uncertainty or conflicting records require it. Keep material updates and durable source references in existing artifacts instead of copying transcripts or full logs. Preserve history and required reads; summaries, hashes and status labels alone are not proof. Each independent reviewer still inspects the complete assigned candidate in a fresh context.

No automatic document compaction, new checkpoint or transcript archive is introduced. Completion/blocker details and failed-command diagnostics remain inspectable.

### 3. Carry existing evidence-reuse policy into research instructions

Replace the preparation paragraph's first sentence.

**Before:**

> For each increment, inspect the current checkout, contracts and predecessor and relevant latest official documentation; prepare the concrete increment plan, meaningful checks, recovery and future-impact assessment.

**After:**

> For each increment, inspect the current checkout, contracts and predecessor. Reuse official-documentation and tool-help evidence only while its source, version, operation and freshness remain applicable; refresh when uncertain, time-sensitive information matters or target policy requires it. Prepare the concrete increment plan, meaningful checks, recovery and future-impact assessment.

Replace the later native-stack documentation sentence to avoid an unconditional duplicate lookup.

**Before:**

> Consult current official native stacked-PR guidance and installed tool help before choosing commands.

**After:**

> Before choosing native stacked-PR commands, confirm that official guidance and installed tool-help evidence apply to the current version and operation, refreshing them under the same applicability rule.

Retain the existing “renew only affected checks/reviews” instructions. They already cover verification reuse; repeating them in another new paragraph would add no useful rule. Changed requirements, candidate inputs, dependencies, environment, authority or external state still reopen the affected evidence. Fresh reviewers establish coverage independently; another reviewer's conclusion is not their evidence.

### README addition

Append to the current orchestration-prompt description:

> The prompt requests bounded native waits, relevant context retrieval and reuse of still-applicable research and verification evidence, while preserving required reads and reviews. These instructions target avoidable repeated work; token savings and executor compliance remain unmeasured unless separately evaluated.

## Task 1: Integrate and verify the complete candidate

**Consumes:** This approved wording, the current source template, the existing gate/evidence policy and C20 scenario conventions.

**Produces:** One coherent three-file candidate and a concise verification return. No new runtime interfaces or artifacts.

- [ ] Recheck branch/status and the three target files plus their policy owner. Record the actual comparison and preserve all intervening user work. Confirm approval covers this concrete instruction change; do not infer execution permission from this draft.
- [ ] Apply the four prompt edits and README sentence above as one batch. Keep the source template self-contained and all unrelated text intact.
- [ ] Add `C20-orchestration-waiting`, `C20-orchestration-context` and `C20-orchestration-reuse` raw variants to the existing C20 table, with corresponding separate evaluator-only expectations. Use the synthetic catalogue fixture and decision-only format; do not create a new runner or assertions that merely match prose.
- [ ] Desk-check the five failure classes below and the existing C20 defaults, authority, readiness, unavailable-capability and negative/adjacent cases. Include QA-on and QA-excluded prompts. Inspect the proposed decisions, not whether a particular phrase is repeated.
- [ ] Run the existing relevant static checks once on the settled candidate, then inspect the whole diff against this plan. Repeat checks only after relevant changes or newly discovered gaps.
- [ ] Request at most one bounded fresh-context final reviewer for this repository change when applicable authorization permits it; inspect the same complete candidate for preservation, applicability and unnecessary complexity. No recursive delegation, live scenarios, external services or Ponytail invocation is included. Report unavailable independent review honestly. This development review does not change the generated workflow's three-report requirement.
- [ ] Return the diff, actual checks, review disposition, unmet obligations and source-only status. Further activation or Git publication requires its own authority.

## Review focus and acceptance cases

All new C20 inputs remain hypothetical and decision-only: actors draft the prompt/next action without dispatching chats, waiting on real work, executing tests or mutating external systems.

| Input or failure class | Variant and observable acceptance |
| --- | --- |
| Running child returns the same compact state/cursor, then a relevant completion; an approaching deadline constrains waiting. | `waiting`: request a supported bounded native wait and reuse the newest cursor, avoid full-history reloads, and inspect completion evidence before progression. No fixed sleep or heartbeat is invented. |
| Cursor is unavailable/invalid, status is unknown or a wait times out. | `waiting`: obtain the smallest necessary current state, report concrete tool failure when relevant, and preserve pending work. Optional cursor absence is not permission to drop the child; timeout/silence is not success or failure proof. |
| Large retained history, an interruption, a missing source reference, conflicting summaries or a narrowed user decision. | `context`: re-establish controlling records on resumption, retrieve missing/contradictory source material, preserve history and apply the actual authority change. No summary-only approval or completion claim. |
| Documentation, tool version, operation and verification inputs are unchanged with usable evidence. | `reuse`: retain applicable research/check results and required report coverage without unnecessary reruns or repeated lookups; retain exact evidence references and their limitations. |
| Tool/dependency/environment/contract changes, or time-sensitive security/provider information needs current verification. | `reuse`: refresh affected research/checks/reviews before dependent work. Preserve unaffected proof, but never substitute a previous result for the new candidate. |

Existing route expectations remain: explicit prompt exclusion, standalone QA, prose edits, execution-only requests and completed implementation receive no new implementation-start prompt. Generated text alone never performs orchestration. Preserve raw-input/evaluator separation and label all desk-checks as static reasoning, not observed agent behavior.

## Validation and evidence limits

Use the [repository validation procedure](../../../README.md#package-and-validation). The existing helper was located in the current host inventory; re-resolve it if the environment differs. These are future implementation commands, not results of this planning turn:

```sh
rtk proxy python3 -B "$HOME/.codex/skills/.system/skill-creator/scripts/quick_validate.py" skills/incremental-plan
rtk proxy python3 -B "$HOME/.codex/skills/.system/skill-creator/scripts/quick_validate.py" skills/test-design
rtk proxy git --no-optional-locks -c diff.autoRefreshIndex=false diff --check
```

Also inspect parsed manifest/frontmatter identity, runtime resource containment, current shipped links/anchors and delivered-file privacy as required by the README. Confirm both skill descriptions and their lengths are unchanged, the catalogue still contains two skills, and the runtime selection still contains ten files. The development plan and evaluation definitions must not enter that runtime selection. Do not install missing validator dependencies automatically or describe an unavailable whole-package validator as passed.

Compare before/after prompt word/byte sizes and total mandatory reading, without treating either as measured tokens or applying an arbitrary shrink target. Preserve tool failures and relevant diagnostics. Static success establishes package structure and documented contract coverage only; it does not establish executor behavior, native activation, responsiveness or token savings.

Optional later evidence, only under separate explicit live-model authorization: use the same safe synthetic cases and available model/settings to compare old/new prompts, completed scope, input/cached-input/output usage, status/history calls, missed evidence and rework. Use available telemetry without adding instrumentation infrastructure; record missing usage data as unknown. Decision-only prompt evaluations cannot prove real waiting behavior or end-to-end savings. Observe those separately during ordinary authorized execution. Do not trigger project work solely to manufacture an efficiency result.

## Recovery, approval and completion

Recovery is a reviewed inverse patch limited to this candidate's hunks, preserving intervening work; no reset, stash, cache edit or deletion. Source changes do not alter active chats or installed copies. Any later installation must use supported native tooling and verify the actual delivered selection under separate approval.

Approval of implementation would cover this bounded source change and its deterministic checks, subject to applicable review authority. It would not activate heartbeat backoff or authorize live-model evaluations, installation, publication or unrelated policy changes. No new material design decision is currently unresolved; conflicts discovered against changed sources return for a scoped decision.

Completion means the three-file candidate matches this plan, preservation and static checks are reported, applicable review is reconciled, and any untested behavior is explicit. The outcome may honestly be “source guidance updated; token savings unmeasured.”

## Sources and planning check

- Local canonical owners inspected: orchestration template, README, C20 scenarios and gate/evidence policy. Existing evidence-reuse and fresh-review rules supplied the preservation baseline.
- [Official usage guidance](https://learn.chatgpt.com/docs/pricing#frequently-asked-questions), checked 2026-10-18: prompts, history and tool results contribute to usage; context, reasoning, tools, retrieval and caching prevent prompt length alone from predicting savings.
- [OpenAI workflow guidance](https://developers.openai.com/cookbook/examples/codex/iterating-development-workflows-with-codex), checked 2026-10-18: retain material decisions and source references, and avoid duplicating routine output or full source artifacts. This plan adopts that principle, not the article's example harness or file layout.
- Current native wait/read tool contracts support bounded waits, cursors and compact status retrieval; capabilities must still be checked on the executor's actual host.

Author self-review: the three recommended improvements have concrete edits and acceptance cases; authority, review and package boundaries remain owned by existing sources. No independent review or live evaluation was performed during planning. Implementation checkboxes remain pending.
