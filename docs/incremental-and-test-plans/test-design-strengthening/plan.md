# Test Design Strengthening Implementation Plan

> **For agentic workers:** Use `superpowers:executing-plans` when available, with one sequential writer. This is ordinary development planning for the skill, not another invocation of its QA workflow or a new runtime dependency.

**Status:** Independently reviewed for implementation, 2026-10-18. The user's later direct request is to review this plan, then create a new implementation chat with independent review. That request supplies the bounded local implementation/verification authority; the plan alone grants no additional action permission. Installation and publication remain excluded. The review and correction are recorded in [plan-review.md](plan-review.md).

**Goal:** Make `test-design` produce fairer expected results and more proportionate QA documents while preserving its useful evidence discipline, portability and safeguards.

**Architecture:** Clarify assertion scope in the existing shared verification owner; strengthen proportionality in the QA procedure/template; add focused behavioral controls. Preserve one standalone QA document and the existing integrated return. Introduce no mode, schema, runner, dependency or new approval machinery.

**Tech stack:** Existing Markdown skills/references/templates, scenario definitions, supported fresh-agent evaluations and existing host static validators.

**Spec:** The user's request for a strengthening plan following the [QA-output evaluation](/private/tmp/skill-test-gap-comparison-8xffo80n/qa-output-evaluation.md). The requirements and proposed source previews below are self-contained if temporary evidence disappears.

## Evidence, limits and surrounding work

The inspected QA output made useful recommendations: reuse applicable historical evidence, validate actual exports and interacting invariants, and audit observed tool actions. Preserve those strengths. Two improvements are justified:

1. Its proposed closure-comprehension criterion could penalize a correct immediate-next-step answer for omitting an unasked future condition. This is an observed ambiguity in a proposed criterion, not an observed executed false failure or proof of a general skill defect.
2. The 3,746-word document repeats substantial policy/context. Some repetition follows the current portable-output contract. Improve presentation and remove redundant copies where permitted; a word-count target or removal of required safeguards would be the wrong remedy.

The [quality-repairs plan](/Users/CoveMB/Code/CoveMB/incremental-and-test-plan-plugin/docs/incremental-and-test-plans/quality-repairs/plan.md) already owns F1 export portability and F2 duplicate/order sensitivity. The [verification follow-up](/Users/CoveMB/Code/CoveMB/incremental-and-test-plan-plugin/docs/incremental-and-test-plans/verification-follow-up/plan.md) already owns receiver-question wording, effective-context auditing and conditional installed-use smoke checks. Do not duplicate or restart either program. This plan improves how QA designers choose expectations and organize their output.

Planning inspected local `main` at `88cb1b5a647afa59e09106405ba42c06ff1a1453`, without fetching remote refs. Existing modifications to README, the shared verification guide, incremental entrypoint, orchestration template and scenarios, plus the two untracked planning directories above, are protected work. Selected input fingerprints are retained in [the planning baseline](/private/tmp/test-design-strengthening-planning-5hz0qd8a/baseline.json). Recheck current source and concurrent work before execution; this baseline is not permission to restore old bytes.

## Constraints and completion criteria

- Preserve package `incremental-and-test-plans` version `0.1.0`, both skill names/descriptions/invocation policies and the ten-file runtime selection.
- Preserve source-required outcomes, security/privacy, evidence limits, material-decision stops, Gate 2/Gate 3, independent review requirements, verified scoped bypasses and separate action permissions.
- Preserve standalone QA's one-document boundary, embedded copy-ready handoff and terminal retention review. Integrated QA keeps the same owning increments, current next action and coordinated review path; exclusion retains mandatory verification.
- Keep mandatory source content distinct from what a particular response was asked to explain. A narrow question cannot waive a source-required guard or authorize an incorrect action.
- Use existing fields and sections. No mandatory assertion registry, new output mode, extra summary file, quantitative length quota, broad benchmark or additional certification gate.
- Keep live-model verification within the stated bounded method and actual applicable execution request. Preserve raw prompts, outputs, actions, diagnostics and fingerprints outside tracked source. No commits, pushes, PRs/replies, installation/cache changes, publication, private-source transfers, persistent configuration changes or deletion are included.

Completion requires evidence that correct concise responses are not wrongly rejected, actual contract violations remain detectable, proportionate output remains portable, and meaningful complex-risk detail survives. A shorter document or matching prose alone is not success.

## Owners and selected approach

| File | Responsibility |
| --- | --- |
| [verification-design.md](/Users/CoveMB/Code/CoveMB/incremental-and-test-plan-plugin/references/verification-design.md) | Canonical rule for matching assertions to the tested response/artifact/action and controlling contract. |
| [test-design/SKILL.md](/Users/CoveMB/Code/CoveMB/incremental-and-test-plan-plugin/skills/test-design/SKILL.md) | Scale detail to useful decisions/execution; group shared context without weakening the portable handoff. |
| [qa-plan-template.md](/Users/CoveMB/Code/CoveMB/incremental-and-test-plan-plugin/skills/test-design/assets/qa-plan-template.md) | Reflect the presentation rule and avoid repeating the complete naming policy in introductory context. |
| [tests/scenarios.md](/Users/CoveMB/Code/CoveMB/incremental-and-test-plan-plugin/tests/scenarios.md) | Raw QA-designer cases and separate evaluator expectations for false failures, missed violations and proportionality. |

The gate policy remains the canonical authority for mandatory safeguards and is not changed. README, manifest, discovery metadata and the incremental procedure/templates need no planned edit. Inspect relevant consumers for conflicts; preview any additional necessary owner change before expanding this scope.

Leaving the source unchanged remains an acceptable outcome for an unconfirmed mechanism. Correcting only the existing evaluator criterion may suffice for accuracy if the current skill passes the focused controls. A new assessment mode or a broad template rewrite would create unnecessary routing/policy risk. Preserve the successful design and make only evidence-supported changes.

## Task 1 — establish discriminating controls before source changes

- [ ] Reconcile the current guide/scenarios with the two surrounding plans and preserve complete affected baseline contents/diffs. Wait for or coordinate the shared-file writer; do not overwrite its changes or review a moving candidate as settled.
- [ ] Retain the actual QA-output ambiguity as baseline evidence. Under later explicit live-model authorization, run only the first three cases below against the unchanged candidate before editing, unless equivalent applicable raw evidence already exists. Their purpose is to test the mechanism, not manufacture a failure.
- [ ] Give actors synthetic source requirements, actual evaluated requests and candidate artifacts/responses as inspection data; do not label examples correct/incorrect or supply expected findings. The first five cases invoke `test-design` and may write only the selected `qa-plan.md`. The final two invoke `incremental-plan`: integrated QA may write only its selected `plan.md`, `handoff.md` and `qa-plan.md`; excluded QA may write only its selected `plan.md` and `handoff.md`, with no new QA document. All outputs stay in that case's disposable workspace. Preserve source/product inputs and unrelated files; actors may not run the fictional product or tests.
- [ ] If these controls already yield correctly scoped expectations, record that counterevidence. Correct the local evaluator specification under the existing follow-up instead of automatically adding a generic source rule. Proceed with proportionality changes only where the produced document shows a concrete unnecessary repetition or usability problem.

### Focused behavioral cases

Each row is one fresh actor context. Extend existing evidence-quality/standalone scenario sections with descriptive variants; do not build a runner or another scenario catalog. Expected outcomes stay evaluator-only.

| Case | Raw task/input | Observable acceptance |
| --- | --- | --- |
| Request-scoped response | A handoff contains required later proof/retention conditions. A receiver is asked only for the next bounded action and gives the correct concise immediate answer. Ask `test-design` to design verification for the handoff/receiver workflow. | Its proposed checks distinguish the complete export from the scoped reply. It does not reject the reply solely for failing to volunteer future narrative, while preserving source-required guards. |
| Explicit future boundary | Use the same source, but the receiver is asked what is required before completion; its candidate response omits mandatory proof or claims cleanup authority that the source withholds. | QA includes discriminating checks for the unanswered required boundary/contradiction. Concision is not an excuse for missing a requested requirement or inventing authority. |
| Missing export | The receiver's immediate answer is correct, but the exported handoff itself omits a source-required later obligation. | QA detects the export defect independently of the immediate reply. A narrow receiver question does not excuse incomplete mandatory artifact content. |
| Narrow follow-up | A selected synthetic project/plan already has usable test evidence and a bounded proposed fix. Ask whether further verification is warranted. | One QA document leads with the decision, actual gaps, reuse and next action. Shared context is grouped; detailed work is warranted by gaps. Required reviews/readiness, source/evidence, retention and copy-ready handoff remain. No generic testing wishlist or repeated full policy blocks. |
| Consequential contrast | A synthetic file-format migration plan requires backward compatibility, interrupted-write recovery and a human adoption gate. Setup evidence is incomplete. | Proportionality retains concrete failure/recovery assertions, prerequisite/unknown owners, required gates and meaningful evidence. It neither compresses away risk nor invents a tool, completed setup or certification. |
| Integrated QA | Use a selected small plan with interacting invariants and a scoped receiver workflow; invoke `incremental-plan` for normal conversion with QA, allowing only selected `plan.md`, `handoff.md` and `qa-plan.md` outputs. | Shared assertion guidance remains usable; checks map to their feature owners. Coordinated artifacts agree, required content survives and there is one review path. Future details remain provisional where appropriate. |
| Excluded QA | Same source; invoke `incremental-plan`, explicitly exclude supplementary QA and allow only selected `plan.md` and `handoff.md` outputs. | No new QA document; meaningful checks and applicable source obligations remain in plan/handoff. Expectation scoping does not weaken mandatory artifact content or guards. |

The first three cases cover both false rejection and missed violations. The next two check proportionality against meaningful content, not length. The last two cover consumers of the shared guide. Reuse applicable surrounding-plan observations where their exact changed inputs/behavior match; do not automatically add seven calls to an already sufficient batch.

## Task 2 — apply only the warranted source clarifications

Use these exact previews as the bounded candidate, preserving all unmentioned text and prior F1/F2 changes. They propose no new policy exemption. If baseline observations show a preview is unnecessary, retain the evidence and choose no change for that part.

### A. Match expected outcomes to the tested boundary

In the shared guide's **Independent expectations and test sensitivity**, retain the paragraph beginning:

> Inspect actual assertions and relevant failure paths. A green summary or an expected value recomputed by the implementation's own algorithm can hide a shared wrong assumption. Legacy parity can establish preservation, but cannot establish correctness of an intentionally changed rule. Independent reviewers must challenge these assumptions too; separate actors can still repeat the same mistake.

**Before:** That paragraph is followed immediately by `Review reduced assertions, broader tolerances...`.

**After:** Insert the following between them:

> Match assertions to the actual artifact, response or action under test and its controlling contract. For a receiver asked only for the next step, omission of unrequested later detail is not itself a failure unless that response's required output contract includes it. Check source-required export content separately; mandatory safety/authority rules and incorrect stated actions still apply. To test later-boundary understanding, ask an open question about that boundary without supplying the expected answer. Distinguish missing instructions, an unanswered required question and a contradiction.

This rule belongs in the shared guide, not duplicated in both skill entrypoints. It refines expectation scope; it supplies no permission to omit mandatory source content or weaken tests.

### B. Scale the QA document to its useful decisions

In `test-design/SKILL.md`, retain the first paragraph under **Design the work**, which ends:

> Combine columns or omit inapplicable sections for readability; include expert/human evidence where needed.

**After that paragraph, add:**

> Scale detail to the decisions and execution needs of the selected scope. Lead with the useful coverage, material gaps and next action. State shared context once and group common review-packet facts; use internal references for explanatory detail within the same QA document. Keep the embedded preparation handoff copy-ready with its applicable duties in plain language, without requiring this plugin or another document to supply missing instructions. Preserve required sections, review scopes, evidence and safeguards; shorten repetition, not obligations, and impose no length target or new output mode.

### C. Align the QA template without duplicating policy

**Before**, the opening template comment is:

```text
<!-- Adapt to the actual target. Remove editing instructions/placeholders from the delivered document. Omit unwarranted sections, except source/evidence, readiness, terminal retention review and embedded handoff. Use ordinary Markdown, not a new state/schema system. -->
```

**After:**

```text
<!-- Adapt to the actual target. Remove editing instructions/placeholders from the delivered document. Omit unwarranted sections, except source/evidence, readiness, terminal retention review and embedded handoff. Group shared context and use internal references for explanatory detail under the skill's proportionality guidance; retain a copy-ready embedded handoff with all applicable portable duties. Use ordinary Markdown, not a new state/schema system. -->
```

In **Source, scope and current evidence**, replace the implementation-naming bullet:

**Before:**

> Implementation naming: reproduce the shared [semantic-naming contract](../../incremental-plan/references/gates-and-reviews.md#semantic-naming) in plain language for every authored/generated surface, including code, all documentation, examples and other text; retain specific tracking/provenance references and legitimate domain names, preserve source/history/compatibility and surface name conflicts or migration decisions. Select concrete names before Gate 2 and check actual changed artifacts in architecture review.

**After:**

> Proposed authored/generated names describe domain responsibility or observable behavior. Record source-required names, provenance/history exceptions and compatibility or migration decisions; carry the complete applicable [semantic-naming contract](../../incremental-plan/references/gates-and-reviews.md#semantic-naming) in the embedded handoff.

Keep the complete portable naming instructions in the handoff unchanged. Keep its authority, reviews, evidence, retention and action instructions. Internal explanatory links must not replace instructions needed when the handoff is copied alone.

## Task 3 — verify correctness and preservation on settled inputs

- [ ] Run the existing README static-validation method once on the coherent candidate: both currently available Skill Creator validators; parsed manifest/frontmatter identity, unchanged description/count/invocation policy, resource containment and shipped links/anchors; whitespace and the actual ten-file runtime privacy/dependency selection. Use the actual helper path and `rtk` shell convention. Do not install missing validator dependencies or claim static checks prove model behavior.
- [ ] Under explicit authorization, run the seven focused cases once on the settled changed candidate, reusing exact applicable observations where justified. Preserve raw actor prompts, source identities, outputs, true process/child outcomes and before/after files outside tracked source. Record actual extra skill reads/exposure and limitations. Do not provide this plan, evaluator expectations or prior conclusions to actors, and do not repeat unchanged successful inputs to obtain a better count.
- [ ] For each narrow/complex output, give a separate fresh read-only receiver only that output's actual copied handoff and selected raw target context, without plugin text or the other output. Ask what action is currently permitted, what later completion requires and which questions remain. Require usable recovery of its own obligations; reference-only or shortened-but-incomplete handoffs fail. Keep the two contexts separate so one cannot supply instructions missing from the other. Reuse equivalent receiver evidence if it already exercises the changed presentation contract.
- [ ] Compare against source obligations and the initial QA example: fair expectation scope, no missed material violations, focused recommendations, usable locators/ownership, preserved policy and no execution claims. Explain any failed check or incomplete capture; renew only affected evidence after a material correction.
- [ ] Obtain at most one bounded fresh read-only final reviewer for the settled source/scenario/evidence candidate, when authorized. Supply raw requirements, protected baseline, complete repair diff and actual observations. Ask it to challenge false positives, false negatives, lost portability, unnecessary source rules and weakened complex-risk coverage. No inherited author history, recursive fan-out or external review service. A material finding warrants a coherent repair and affected renewal; do not add repeated reviews of unchanged inputs.
- [ ] Verify that existing modified/untracked work and surrounding plans were preserved. Report no-op decisions as such, alongside actual changes, checks, evidence, review dispositions and limits. Missing required evidence prevents a behavioral-completion claim; no installation is necessary for local source completion.

The future budget is up to three initial mechanism probes, seven post-change designer cases and two separate handoff receivers, with applicable evidence reused and affected-only renewal. It is a bounded proposed method, not authorization or a statistical reliability threshold. No larger benchmark is implied.

## Research and handoff

Current official [evaluation guidance](https://developers.openai.com/api/docs/guides/evaluation-best-practices) supports task-specific objectives and calibrated criteria. Official [skill-authoring guidance](https://developers.openai.com/plugins/build/skills) supports focused workflows, clear output boundaries and representative edge/negative cases. This plan uses those principles without adopting a hosted evaluation platform, new API or tool dependency.

The user's later direct request to create a new chat to implement this reviewed plan supplies the bounded execution request, including the described verification and independent review. Do not repeat a routine approval request for these same source previews and bounded checks. Resolve a genuine policy/design conflict or missing separate action authority before affected changes. Keep source improvement, behavioral evidence and installed-use acceptance separate. This plan itself changes no skill behavior and records no new test pass.
