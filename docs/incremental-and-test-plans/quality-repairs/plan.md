# Skill Quality Repairs Implementation Plan

> **For agentic workers:** Use `superpowers:executing-plans` when available, with one sequential implementation writer. This development plan adds no runtime skill dependency. Fresh evaluation actors and one final reviewer have the separate read-only or disposable-workspace scopes below.

**Status:** Proposed, 2026-10-18. This request authorizes planning only. Sending the companion implementation prompt approves the previews and bounded implementation/evaluation scope described here.

**Goal:** Repair the two confirmed output gaps while preserving the plugin's coherent planning, authority, review and history contracts.

**Architecture:** Strengthen export instructions at the incremental recap/template boundary and refine the existing verification example to expose interacting invariants. Keep policy in its current canonical owners; verify actual generated artifacts and fresh receiving contexts rather than matching instructional wording.

**Tech stack:** Existing Markdown instruction package, native fresh-model evaluations in synthetic workspaces, and existing host Skill Creator validators. No runtime code or dependencies.

**Spec:** The user's request to address the two findings from the completed follow-up evaluations. The bounded findings, exact source previews and observable acceptance below are the implementation specification. This is ordinary repair planning, not invocation of `incremental-plan`.

## Evidence and baseline

The [evaluation report](/private/tmp/incremental-quality-evals-mv4fd1u2/report.md), [independent adjudication](/private/tmp/incremental-quality-evals-mv4fd1u2/independent-adjudication.md) and [ordering diagnostic](/private/tmp/incremental-quality-evals-mv4fd1u2/reused-index-ordering-diagnostic.json) record 12 completed fresh runs. Seven met their checked conditions; five shared one or both gaps. These are bounded observations, not an overall quality score.

- **F1:** Five recap-generation cases retained the correct immediate review/decision stop and substantial lifecycle guidance, but failed to export conditional owner continuity, resumption/identity reconciliation, prescribed chat naming and bounded-wait duties. Those duties are already in the orchestration template. No wholesale lifecycle loss or additional Git/PR/CI/provider defect was established for the evaluated fixtures.
- **F2:** The generated QA matrix, carried through exclusion/restoration, allowed a wrong consumer of a correct reused `dict[str, list[int]]` index to pass all 12 proposed query cases. Flattening matching title groups returns `[1, 3, 2]` for `1:Echo, 2:Other, 3:ECHO` instead of the required `[1, 2, 3]`, for both `""` and `"e"`. Counts, original objects and input nonmutation still pass. This is a generated-draft coverage gap; a canonical verification-policy defect or actual application failure was not established.

Inspected `main` at `88cb1b5a647afa59e09106405ba42c06ff1a1453`. All 13 source fingerprints still match the evaluation snapshot. Existing modifications to `README.md`, `skills/incremental-plan/assets/orchestration-prompt-template.md` and `tests/scenarios.md` are user-owned baseline work. Remote refs were not refreshed. Reinspect branch/status and preserve current complete contents/diffs before implementation; this recorded HEAD is not a license to overwrite intervening work.

Temporary evidence may disappear. If available, reuse its raw prompts, inputs and observations. If unavailable, retain the evidence limit and reconstruct synthetic inputs from the source scenarios; rerun only missing or changed baseline cases needed to establish the relevant failure. Do not describe unavailable evidence as inspected.

## Global constraints

- Preserve package `incremental-and-test-plans` version `0.1.0`, both skill identities/descriptions and invocation policies, and the ten-file runtime selection.
- Preserve coherent feature increments, default/coordinated QA, standalone QA's one-document boundary, explicit exclusion and source-required checks/certification.
- Preserve Gate 2/Gate 3, independent review scopes, semantic naming, verified scoped permissions, material-decision stops, accepted history and separate action boundaries.
- No execution engine, new state/registry, helper skill, runner, mandatory integration, dependency, hook, metadata expansion or automatic installation.
- Keep actual model-run traces, diagnostics and generated fixtures outside tracked source. Do not import local evaluation outputs into the runtime package.
- No commits, pushes, PRs/replies, installation, publication, production/provider operations, private-source transfer, cleanup or persistent configuration changes are included. An evaluation actor may write only its expressly selected synthetic planning documents.

## Files and ownership

| File | Planned responsibility |
| --- | --- |
| [incremental-plan/SKILL.md](/Users/CoveMB/Code/CoveMB/incremental-and-test-plan-plugin/skills/incremental-plan/SKILL.md) | Require reading/rendering the applicable orchestration body and checking the actual exported result. |
| [orchestration-prompt-template.md](/Users/CoveMB/Code/CoveMB/incremental-and-test-plan-plugin/skills/incremental-plan/assets/orchestration-prompt-template.md) | Own the portability/export check; existing prompt-body rules remain canonical. |
| [verification-design.md](/Users/CoveMB/Code/CoveMB/incremental-and-test-plan-plugin/references/verification-design.md) | Refine the existing sensitivity example for interacting, source-required invariants. |
| [tests/scenarios.md](/Users/CoveMB/Code/CoveMB/incremental-and-test-plan-plugin/tests/scenarios.md) | Extend existing C20/Q/EX cases with raw requests and separate evaluator-only checks. |

The gate policy, handoff/QA/plan templates, standalone entrypoint and README need inspection for conflicts, but no changes are planned there. Existing general policy already covers their duties. If evidence shows a necessary additional owner change, surface its concrete scope and preview before applying it; do not broaden by habit.

## Selected approach and review focus

Use one coherent source change, then validate its settled candidate. Leaving everything unchanged would retain observed output gaps. A new orchestration artifact or shared framework would expand the output contract. Copying orchestration rules into all handoff templates would create competing policy owners. A mandatory mutation-testing system would overreact to one generated-fixture gap. None is justified.

Review particularly for: an immediate review stop erasing later conditional duties; same-title chats being mistaken for identities; silence being mistaken for completion; duplicate/order checks sharing a wrong assumption; and QA-mode changes or new examples weakening authority/history or imposing irrelevant index rules. The evaluations below exercise each condition.

The narrow scope and behavioral checks follow current official OpenAI guidance to [keep skills focused and disclose conditional detail progressively](https://developers.openai.com/blog/rethinking-skills-and-prompts-for-gpt-6-astra), and to [define must-pass outcomes and inspect captured traces/artifacts](https://developers.openai.com/blog/eval-skills). These sources support the method; repository evidence determines the repairs.

## Task 1 — repair conditional orchestration export

**Consumes:** Saved plan/handoff/QA, reconciled authority and the existing orchestration prompt body. **Produces:** The same eligible fenced recap prompt, with current first action and recoverable conditional orchestration instructions; no additional output file.

- [ ] Before source edits, capture the implementation baseline, including staged/unstaged/untracked content and complete contents/diffs of the three existing modified files, outside tracked source. Associate F1's observed failures with that source. Reuse applicable existing runs; do not repeat them merely to obtain another red result. Re-read before affected writes and preserve concurrent work; do not stash/reset/amend or overwrite it.
- [ ] Apply the following two exact replacements, leaving unmentioned text intact. If intervening changes alter their meaning, reconcile first and stop only for a material conflict.

In `skills/incremental-plan/SKILL.md`, replace this sentence in **Return a concise recap**:

**Before**

> Derive its references and first action from the saved artifacts and reconciled authority.

**After**

> Derive its references and first action from the saved artifacts and reconciled authority. Read the template and render its applicable prompt body; a review/decision first action does not remove conditional later orchestration duties. Check the actual fenced prompt and selected target artifacts against the template's portability requirements before returning it.

In the orchestration template's **Compose from current artifacts**, replace its final bullet:

**Before**

> Render one fenced prompt under **Implementation orchestration prompt**. Replace bracketed fields and remove inapplicable optional clauses; leave no unresolved placeholders or installed-plugin links. The selected target artifacts and plain instructions must suffice for a fresh orchestrator.

**After**

> Render one fenced prompt under **Implementation orchestration prompt**. Replace bracketed fields and remove inapplicable optional clauses; leave no unresolved placeholders or installed-plugin links. Preserve applicable conditional duties from the prompt body even when the first action is review or a decision. Before returning, compare the actual fenced prompt and selected target artifacts with that body: one orchestrator and sequential writers; persistent increment owners; actual owner/reviewer references and resumption/replacement guards; prescribed chat naming; and bounded waiting/continuation semantics must remain recoverable without this plugin. Put each applicable duty in the prompt or as self-contained instructions in the selected target artifacts; a generic instruction to follow the handoff, a title alone or a package link is insufficient. Keep current stops and separate permissions; export no invented dispatch identities or authority.

- [ ] Desk-check applicability: pending reviews retain later conditional guidance; actual execution still requires applicable authority; unavailable naming operations remain limitations; explicit omission, completed scope and standalone/implementation-only routes retain existing behavior.

**Acceptance:** Actual generated text plus referenced target artifacts carries F1's missing semantics without plugin access. There is one fenced prompt, no extra saved recap, no invented owner IDs, and no widened permissions. A list of keywords alone is not a pass.

## Task 2 — strengthen discriminating verification design

**Consumes:** Source-required behavior and existing independent-expectation/sensitivity policy. **Produces:** Proportionate combined-invariant examples in generated QA or QA-excluded verification fields. No new gate, runtime test engine or mandatory technique.

- [ ] Preserve F2's baseline distinction: the canonical policy is already adequate in principle; the observed generated example was insensitive to a plausible wrong consumer.
- [ ] In **Independent expectations and test sensitivity**, replace only the first paragraph:

**Before**

> Ground important expected results in approved requirements, trusted examples or a justified reference independent of the implementation under test. Name the basis and the material wrong behavior a check should detect. For example, when separate records with equal titles must survive a search, asserting their ordered IDs distinguishes preservation from a deduplicating implementation; checking only distinct titles does not.

**After**

> Ground important expected results in approved requirements, trusted examples or a justified reference independent of the implementation under test. Name the basis and the material wrong behavior a check should detect. When requirements interact, choose a small discriminating example for their combination; isolated examples can share a blind spot. For example, if search must preserve duplicate records and global input order, interleave equal titles with a different matching title and assert literal ordered IDs and any source-required original-object identity. Where empty-query behavior and index reuse are also required, check both empty and nonempty queries matching those groups against the same reused index. Counts or contiguous duplicates alone cannot distinguish correct order from grouping by title.

- [ ] Extend the existing scenario sections, without duplicating their general evaluation method. C20 generation expectations must inspect the actual export, not just explicit orchestration-decision answers. Add raw fresh-receiver packets using actual generated prompts/artifacts. Extend the Q sensitivity cases with the interleaved-order evaluator diagnostic and a held-out non-indexed event-filtering example. Keep fixture expectations and wrong-consumer diagnostics evaluator-only.
- [ ] Keep exact `Echo/Other/ECHO` values in evaluator material, not as a universally required runtime fixture. Accept semantically equivalent discriminating examples. Require index/identity checks only where their selected source requires them.

**Acceptance:** The emitted cases reject both deduplication and group-flattening order loss while retaining meaningful empty/nonempty, identity, input-preservation and required reuse checks. Exclusion carries this work in the selected plan/handoff; restoration retains it and human notes. Standalone QA benefits without adding incremental outputs. The held-out non-indexed case does not gain an invented index requirement.

## Task 3 — verify the settled candidate and reconcile findings

- [ ] Compare the coherent repair diff against the baseline preserved before Task 1 rather than treating the whole dirty checkout as this change. Confirm that the three existing modified files and any concurrent work have been preserved.
- [ ] Run the README's existing static checks once on the coherent source batch. Resolve current validator availability before running; the inspected helper is `/Users/CoveMB/.codex/skills/.system/skill-creator/scripts/quick_validate.py`:

```sh
rtk proxy python3 -B /Users/CoveMB/.codex/skills/.system/skill-creator/scripts/quick_validate.py /Users/CoveMB/Code/CoveMB/incremental-and-test-plan-plugin/skills/incremental-plan
rtk proxy python3 -B /Users/CoveMB/.codex/skills/.system/skill-creator/scripts/quick_validate.py /Users/CoveMB/Code/CoveMB/incremental-and-test-plan-plugin/skills/test-design
rtk proxy git diff --check
```

Also inspect parsed manifest/frontmatter identity, resource containment and shipped links/anchors, unchanged skill counts/descriptions/invocation policies, and actual ten-file runtime inventory/privacy/dependencies as the README requires. Use temporary inspection only, not a permanent runner or regex test of prose. Missing validator dependencies are a limitation, not permission to install them. Successful static checks prove structure only.

- [ ] Run the following **12 fresh-model cases** once on the settled candidate. This live batch is authorized only when the companion prompt is sent. Use configured model defaults; actors receive raw inputs and minimum source resources, never this plan, findings, intended answers or evaluator sections. Preserve exact prompts/source hashes, native process exits, raw JSONL/stderr, responses, actions and before/after files outside tracked source. Use disposable synthetic workspaces; keep plugins/memory/history/delegation out of actor context as supported, record actual isolation limitations, and avoid experimental bypasses. Actor evaluation permissions do not include product execution, application tests, Git writes or external actions.

| Case | Actor input/action | Evaluator-only must-pass observations |
| --- | --- | --- |
| R01 | Original small conversion, default QA, pending reviews. | Coherent single feature and current stop; complete conditional F1 export recoverable from actual outputs. |
| R02 | Same small conversion with supplementary QA excluded. | No QA doc; mandatory checks/gates preserved; same F1 portability. |
| R03 | Standalone QA for the indexed-catalogue source/contract. | Only QA document; discriminating combined order/duplicate examples, required reuse/identity and portable embedded handoff. |
| R04 | Original larger indexed-catalogue source with required local certification. | F1/F2 fixed; ordinary checks with feature owners; certification after actual prerequisite and before adoption; no approval or human pass invented. |
| R05 | Exclude supplementary QA using actual R04 outputs plus three distinct human annotations. | Historical QA body/notes preserved, mode notice allowed; mandatory discriminating checks retained in plan/handoff; F1 export survives. |
| R06 | Restore QA using actual R05 outputs. | Same selected artifacts/IDs; notes and mode history retained; F1/F2 remain fixed. |
| R07 | Fresh read-only receiver of actual R01 prompt and referenced target inputs, no plugin. Supply hypothetical same-title unrelated chat, unknown original owner, outstanding reviewer and timed-out cursor. | Recovers owner/reviewer reconciliation, no duplicate writer/replacement on unknown state, exact naming semantics, bounded waits and current review/authority stop. No dispatch/wait/title mutation. |
| R08 | Same receiver task using actual R02 excluded outputs. | Same F1 recovery; excluded QA does not erase meaningful verification or create a missing-QA blocker. |
| R09 | Fresh read-only receiver of actual R03 embedded handoff, no plugin. | Understands concrete preparation/check/review boundaries and F2 expectations; no incremental orchestration output or execution. |
| R10 | Standalone QA for held-out non-indexed event filtering: original event identities, arrival order and repeated type labels must survive filtering, with local source-owned examples/docs. | Combines duplicate/order invariants in discriminating examples; literal source-derived expectations; no invented index or certification requirement. |
| R11 | Read-only contract/authority decision packet using actual R04 outputs and the original 07/12 raw hypothetical controls. | Rejects incompatible producer/consumer shape, quoted approval and missing proof; honors a scoped bypass only with supplied prerequisites; later revocation affects only its scope; existing gates/reviews remain. |
| R12 | Read-only C20 negative/adjacent packet: explicit prompt omission, implementation scope complete with closure pending, standalone QA, and implementation-only request. | Correct route/output decisions, no new start prompt on excluded routes, closure still visible and no action performed. This is decision evidence, not automatic-routing proof. |

For R07/R08, hypothetical native facts are inspection data; no real chat lookup/dispatch is needed. Readers must not receive source-policy text that the generator failed to export. Score recoverable semantics from their actual decisions, not agreement with a hint. R09 must have access only to its generated QA handoff and actual references.

Use a disposable controller-only diagnostic to compare generated verification examples against the plausible wrong reused-index consumer. Do not run the fixture application. The known counterexample is `[1:Echo, 2:Other, 3:ECHO]`, with index `echo:[0,2], other:[1]`; both `""` and `"e"` must yield `[1,2,3]`. Check the actual generated matrix's sensitivity, not merely the presence of this example in the instructions. Exact values may differ if the same wrong behavior is exposed.

- [ ] Reconcile each actual result. Reuse still-applicable original passing authority/history evidence as historical baseline, not a fresh pass. Fix material in-scope failures; rerun only cases/checks affected by changed inputs or incomplete evidence. No repeated unchanged trials, broad benchmark, reliability percentage or installed/native-orchestration claim.
- [ ] Once the coherent candidate and evidence are settled, obtain **one fresh, read-only independent final reviewer**, with no inherited author history, no recursive delegation and no external transport. Give raw sources, the exact repair baseline/candidate, generated artifacts and raw evaluation records. Ask it to challenge F1 completeness, F2 sensitivity/overfitting, source-consumer coherence, scope and dirty-work preservation. Validate findings; if it finds a material defect, make one coherent authorized repair and renew affected verification/review only. Unavailable independence remains explicit, never relabeled self-review.

## Completion and handoff

Complete only when the three source previews and necessary scenario updates are implemented, every applicable must-pass above is met, relevant static checks have actual outcomes, and the final independent review has been reconciled. Disclose concrete blockers; a blocked required case is not a completed repair. Preserve all existing local work and compare the final repair against this scope; remove newly introduced unnecessary instructions or duplication.

Return a concise summary of changed files, F1/F2 before/after behavior, actual check/evaluation outcomes and evidence paths, independent review/dispositions, preserved pre-existing changes and material limits. Keep static structure, source/model behavior and installed/native orchestration separate. No installation or publication is needed to finish this local repair.

The [copy-ready implementation prompt](/Users/CoveMB/Code/CoveMB/incremental-and-test-plan-plugin/docs/incremental-and-test-plans/quality-repairs/implementation-prompt.md) provides the scoped approval for a new chat. This chat creates neither that chat nor the implementation.
