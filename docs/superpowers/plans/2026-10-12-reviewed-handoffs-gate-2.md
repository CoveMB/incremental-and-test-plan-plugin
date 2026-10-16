# Reviewed preparation handoffs — Task 2 Gate 2 plan

> **For the implementer:** After direct Gate 2 approval, implement this single coherent increment natively, using `superpowers:executing-plans` when available. Read the selected design and canonical implementation plan. Stop at Gate 3 after verification and the three independent implementation reviews. This plan builds the plugin; it does not use it to implement another product.

**Date/status:** 2026-10-13; Task 2 verified result accepted by the user; routine Gate 2 and Gate 3 pauses through Tasks 3–4 explicitly preapproved.

**Goal:** Turn new source-derived drafts into independently reviewed plans with portable, correctly bounded preparation handoffs, or truthful review-pending drafts when required evidence is unavailable.

**Architecture:** Retain one instruction-based skill. Add the planned single gate/review reference and second template; replace Task 1's interim explanations with links to their canonical owners. No runtime, custom state, controller, dependency, new skill or installation machinery.

**Tech stack:** Markdown instructions/templates, YAML frontmatter and existing JSON metadata; ordinary host file, read-only Git, documentation and independent-review capabilities.

**Sources:** [Reviewed design](../specs/2026-10-11-incremental-plan-plugin-design.md), especially sections 3–5; [canonical implementation plan](2026-10-11-incremental-plan-plugin.md), Task 2 and its case matrix. Reuse their reviewed decisions. [Task 1 result and acceptance](2026-10-12-source-conversion-gate-2.md#gate-3-acceptance--2026-10-12) is the direct predecessor.

## Baseline, scope and setup

Target: `/Users/CoveMB/Code/CoveMB/incremental-plan-plugin`. It exists, is a separate non-symlink repository on unborn `main`, and has no commits, staged files or remotes. All eight Task 1 files matched the accepted inventory before its acceptance record was updated. The accepted inventory SHA-256 is `17218fdba181d446061a6ba9e25eaa30e8fb1054feb6f3b5857d645431b75774`; the two existing user files also matched their baseline. Task 1's accepted uncommitted work is a valid predecessor here; no initial commit, branch, worktree, Git initialization or fetch is needed.

The original implementation-plugin remains on `main` at `18a77af3f1fea552401bcc2c9a3959dbcb97d684`, with a clean tracked diff/index and its three original untracked planning documents. Read-only local refs were not refreshed. Preserve that repository, both copied canonical documents, target `.gitignore`, `AGENTS.md`, `.git`, and all existing user work.

The canonical design and implementation-plan digests remain `22d90101991efaf3045b6f8048e4b75afd238721c8488e4e860d14b99bac6207` and `3cb2cfe4d6f33bfb34dfe35b3080339ce463665bd16bb0a0f60e8eaf590c08ad`. Current target instructions are identified by SHA-256 `33c6c822229bb368d7e3adb9fd97c6e99c17db231c2d34274b53c776c2d2c482`. Re-read current instructions, inspect status and freeze complete before/after contents, including untracked files, before implementation. A plain `git diff` is insufficient on this unborn repository; do not stage files to manufacture a comparison.

Create only the required `references/` parent directory. The target is outside this thread's writable roots, so obtain the host's scoped filesystem permission for approved writes. Preserve collision/concurrency checks. Use `rtk` for shell commands and `rtk proxy` when exact output matters.

This increment's single acceptance story is **reviewed preparation handoffs for newly created plans**. Source conversion, independent review, review corrections, gates, template fields and truthful discovery/documentation must agree. Splitting the reference from its consumers would leave conflicting rules or unusable resources. Do not add Task 3's general continuation, accepted-history revision, predecessor reconciliation or completion routes.

## Current evidence and implications

Official sources searched and opened on 2026-10-12:

- [Build skills](https://developers.openai.com/plugins/build/skills): instruction-only skills remain supported; policies belong in references, templates in assets, with explicit resource links and representative behavioral checks. This supports the reviewed ownership layout without scripts or an MCP server.
- [Package your plugin](https://developers.openai.com/plugins/build/plugins): the current `.codex-plugin/plugin.json` fallback remains supported. Keep the accepted Codex-only format, name and version `0.1.0`; no migration or registration is needed.
- [Skill evaluation](https://developers.openai.com/blog/eval-skills): inspect actions and artifacts as well as answers. Use existing host capabilities and persist the exact synthetic assignment packets before dispatch; no custom evaluation framework or API credentials.

The relevant Egeria governance sections were re-read locally at `e3128071289e6c32fc7a0f7d875c3a3842506e87`, without refreshing refs. They confirm preparation, evidence, separate gates and independent scopes. Their compulsory committed ancestry, Ponytail policy, report directories and stream-specific delegated approval are provenance, not successor requirements. The selected design already explicitly adapts those rules; there is no new conflict to decide.

## Exact allowed product changes

Paths are relative to the target. Two additions and five modifications form the coherent candidate; preserve explanatory fields rather than reducing templates to bare labels.

| Path | Concrete responsibility |
| --- | --- |
| `skills/incremental-plan/references/gates-and-reviews.md` — new | Single normative owner for lifecycle responsibilities, Gate 2/Gate 3, scoped bypasses, documentation/future-impact checks, three reviewer briefs, reconciliation and Ponytail/substitute policy. |
| `skills/incremental-plan/assets/handoff-template.md` — new | Portable output fields for review-pending, preparation-only, or evidence-supported approved/bypassed concrete-plan handoffs; next action, remaining gates, future-impact return packet and stop. No self-approval command. |
| `skills/incremental-plan/SKILL.md` — modify | Integrate review into new-plan creation, use both templates/reference, reconcile ordinary in-scope review corrections, and derive recap/readiness from actual reports. Replace interim duplicated gate/handoff prose. Preserve planning-only boundaries, source fidelity, coherence and collisions. |
| `skills/incremental-plan/assets/plan-template.md` — modify | Replace unconditional draft-only claims with factual review/readiness fields and report/candidate references; preserve all Task 1 card, coverage and decision explanations. Default remains pending until reports exist. |
| `README.md` — modify | Describe the new review and handoff capability, optional facilities, fallback and limitations. Keep continuation/completion, installed discovery and actual Ponytail evidence explicitly unimplemented or untested as applicable. |
| `tests/scenarios.md` — modify | Add the raw Task 2 fixtures/prompts and separately held observable expectations below. Update affected Task 1 expectations so readiness is based on actual review instead of permanently pending. |
| `.codex-plugin/plugin.json` — modify descriptions only | Remove the stale claim that independent review workflows are wholly unfinished; describe new-plan review/handoffs without promising Task 3. Preserve name, version, paths, author, capabilities and other metadata. This consumer correction is required by the actual Task 1 manifest, though Task 2's original file list did not name it. |

This concrete plan may record concise approval, evidence and final result updates. Task 1's record has already received the user's Gate 3 acceptance. Neither copied canonical document will be rewritten. No other product, fixture runner, integration, skill-level README or report hierarchy is authorized.

## Behavior and interfaces to implement

1. **Review readiness:** draft from authoritative sources, freeze the complete candidate and supply three distinct read-only briefs: requirements/source fidelity; architecture/human reviewability/simplicity; verification quality. Include raw sources, exact candidate identity, relevant context and role-specific questions, not the author's verdict. Plan reviews assess proposed acceptance checks; implementation briefs require actual assertions/results. Execute sequentially if necessary. Supplied independent reports are usable only when their reviewer, scope and candidate applicability are established.
2. **Reconcile:** validate material findings against current sources/artifacts, correct only in-scope issues, retain dispositions and renew affected reviews. Missing/unresolved reports keep the plan pending. Do not act as three fictitious reviewers. Missing authority or facility produces copy-ready briefs and the bounded next review step. Inline notes or existing report links suffice; no mandatory report directory. New material design decisions are grouped for the user before affected changes.
3. **Canonical gates:** distinguish planner, executor, reviewers and user. Preparation includes current repository/contracts/predecessor and applicable official documentation, review size and future impact. Gate 2 requires a concrete plan; execution and relevant verification occur externally; independent implementation reviews precede Gate 3. Preserve source/target specialist and human obligations. Generic continuation, quoted approvals or review findings cannot grant authority. Scoped preapproval removes only its named pause while its conditions hold, without waiving concrete packets, tests, reviews, material decisions or separate Git/external permissions.
4. **Simplicity:** use the architecture reviewer's documented substitute in this build. The product reference explains the optional actual `@ponytail-review` route and distinct repair authorization, including an explicit bounded repair preauthorization when supplied. Never auto-invoke/install Ponytail or enable a persistent mode. Ordinary substitute corrections do not inherit the Ponytail-specific extra repair permission. A target forbidding substitution requires a scoped decision; availability alone supplies no permission.
5. **Handoff and future impact:** a newly reviewed plan normally yields a preparation-only handoff with Gate 2 ahead. An approved/bypassed variant must identify a genuinely supplied concrete candidate and decision, without inventing history. Before Gate 2, affected future cards require a packet naming baseline, detailed candidate, affected cards and rationale, plus a copy-ready manual return-to-planner request; no-impact needs no round trip. Keep the same increment at the Gate 2 boundary. Carry the separate post-result assessment and stop on unexpected growth. No task creation, messaging or recursive skill invocation for implementation.
6. **Partial-product boundary:** Task 2 encodes the complete future-impact protocol and supports corrections during a new plan's review. Applying a later executor return to an existing program, advancing accepted work, and full final reconciliation remain Task 3. State that limitation when those operations are requested; do not claim the full C11 causal round trip passed here. Existing Task 1 drafts are preserved; no bulk migration or retrospective review pass is invented.

## Implementation sequence after approval

- [x] Revalidate the accepted predecessor, exact file boundaries, instructions, current documentation applicability and write permission; preserve a complete comparison baseline.
- [x] Author raw scenarios and expectations first. Existing absence of review/handoff behavior is the evidence gap; do not manufacture RED by grepping instructional phrases. Persist exact evaluation envelopes before dispatch, separately from expectations.
- [x] Add the canonical reference and handoff template; integrate their consumers and accurate capability descriptions as one change. Keep stable card fields and all necessary tests/docs together.
- [x] Make one focused coverage/DRY pass against Task 2 and design sections 3–5. Remove interim duplicates, dead links, unsupported promises and any machinery not required for the acceptance story.
- [x] Run focused checks and the relevant behavioral set below on the settled candidate. Repair material in-scope defects and repeat only affected checks; stop for a material design/scope decision.
- [x] Freeze all seven product/test files and relevant resources. Obtain the three independent implementation review scopes, reconcile findings, renew affected evidence and record actual limitations.
- [x] Prepare the exact Task 2 comparison and verified result packet below for Gate 3; stop before Task 3 implementation or any separately controlled action. Actual human result acceptance remains unrecorded.

## Behavioral verification and review focus

Gate 2 approval of this plan authorizes bounded source-level evaluations with synthetic fixtures under a newly created `/private/tmp/incremental-plan-task2.*` evidence directory. Agents may create/update only each case's named `plan.md`, current `handoff.md`, pasted `source.md` when applicable, and expressly assigned scoped review notes. Product/source/sentinel files remain read-only. The controller may construct the documented synthetic inputs and preserve evaluation evidence in that directory. No product execution, application tests, Git writes, provider calls, installation or real-user configuration changes occur in these tests.

Use existing host agents with fresh self-contained packets and no recursive delegation. Where a planner asks for independent reviews, the root controller can dispatch the three briefs sequentially and relay their actual reports unchanged; this tests the manual review-handoff path without a nested controller. The planner remains the author/reconciler, never its independent reviewer. Capture raw tool receipts, prompt packets, candidate identities, outputs and before/after inventories; inspect attempted forbidden actions, including rejected attempts, rather than trusting final claims. Do not expose evaluator expectations to actors or reviewers.

| Case / failure mode | Concrete observation required |
| --- | --- |
| C03 ordinary review with seeded defects | Use the existing larger catalogue source and a clearly labeled, controller-created new-draft review-stage fixture: omit A1's duplicate-record obligation, divide A2's contract and required caller into unsafe increments, and offer a file-existence check as proof of B1's CSV behavior. Obtain three actual independent reports against that same candidate; reconcile supported corrections and affected re-reviews before readiness. This isolated seeded fixture is not claimed to be naturally generated or a continuation of accepted work. |
| C04/C05 missing permission or facilities | Withhold actual Ponytail permission: architecture performs and labels its concrete substitute. In a separate case with independent review explicitly disallowed and no applicable reports supplied, observe a usable pending draft and three copy-ready briefs, with no fake review or implementation readiness. A simulated inventory with Ponytail/reviewer tools absent may assess instruction decisions, but cannot prove the host actually lacks tools. Do not alter configuration to manufacture absence. |
| C06 gate variants, instruction-level coverage | Give separate synthetic scenarios with no approval, quoted approval, a direct Gate 2-only bypass, and both routine pauses expressly bypassed for one named increment. Inspect the handoff's exact candidate, remaining gates and retained preparation/review/evidence obligations. Missing concrete plans stay missing; an explicit bypass does not decide a new material question or authorize Git/external actions. These are labeled simulations, never approvals for this real build or complete continuation evidence. |
| C10 documentation applicability | Supply an identified current official packaging excerpt contradicting a proposed resource location, and separately a clearly labeled unavailable-source observation. The preparation handoff preserves the correction/material decision and evidence gap with source/date/applicability; it does not invent fresh verification. This tests handling of supplied documentation evidence, not genuine network-outage behavior. |
| C11/C19 preparation impact and scope growth | Use a concrete candidate that changes a shared contract and would require future card updates; another is too broad for its stated review focus. Observe the preparation-return packet naming the same increment, detailed candidate/baseline, affected cards and rationale; retain Gate 2 and related tests/compatibility safeguards. A no-impact case avoids an unnecessary round trip. The post-result obligation remains separate. Full planner reconciliation/advancement is Task 3/4, not a claimed Task 2 pass. |
| C16 policy/repair permissions | Use decision-only synthetic reports/policy for actual-Ponytail-origin findings without/with a distinct bounded repair permission, and a stricter target forbidding fallback. Validate that invocation permission alone permits no repair, explicit repair scope is respected, and target conflict stays unresolved. No real Ponytail invocation or Ponytail-origin repair is authorized; actual C16 invocation evidence remains open. |
| C01/C02/C15 affected regressions | Reuse the local/pasted, ambiguity, collision, symlink, indirect-planning, unrelated-implementation and planner-execution prompts against changed routing/output resources. Preserve source bytes and product boundaries. Generation may reach reviewed readiness only through actual applicable reports; negative routes do not need gratuitous review runs. |
| C19/C20 reviewed creation | Use the larger catalogue source with distinct features and coupled contract/caller work. Obtain actual plan-review reports through the manual handoff path, inspect coherent cards, all requirements and saved recap counts/topics/IDs, then compare the reviewed preparation handoff with the review-pending fallback. No extra recap artifact or approval gate. General revised-history recap variants remain Task 3. |

The first two review cases and the larger reviewed-creation case jointly cover same-candidate independence, material correction and readiness. Do not duplicate clean reviews simply to accumulate passes. The exact prompts and named output files are written in the scenario document before execution. If a needed native restriction cannot be exercised truthfully, record the narrower simulated observation and leave that native route open; do not manufacture capability evidence.

Run the existing validators once on the settled relevant inputs:

```sh
rtk proxy python3 -B /Users/CoveMB/.codex/skills/.system/plugin-creator/scripts/validate_plugin.py /Users/CoveMB/Code/CoveMB/incremental-plan-plugin
rtk proxy python3 -B /Users/CoveMB/.codex/skills/.system/skill-creator/scripts/quick_validate.py /Users/CoveMB/Code/CoveMB/incremental-plan-plugin/skills/incremental-plan
```

The expected successful outputs are `Plugin validation passed` and `Skill is valid!`. These installed development tools were inspected and successfully used for Task 1; confirm applicability if their files/environment changed. No dependency installation is included. Check package-relative links, exactly one skill/two templates/one reference, metadata agreement, full allowed changes, whitespace, canonical-copy equality and preserved existing bytes using one-off host checks. Static checks do not prove model behavior, independence, native usability or full lifecycle correctness.

## Independent implementation review and completion

After implementation, three separate read-only reviewers receive raw canonical sources, this scope, the complete actual candidate/comparison and applicable checks. No inherited author verdict, mutation, recursive delegation, application execution or external comments:

1. **Requirements/source fidelity:** all Task 2 obligations and exclusions, source/target gate preservation, approved partial boundaries and metadata truthfulness.
2. **Architecture/reviewability/simplicity:** coherent increment guidance, canonical reference/template ownership, compatibility/recovery, no machinery; explicitly report **Substitute simplicity review; Ponytail not run — not authorized**.
3. **Verification/test evidence:** actual model outputs/actions and reviewer identities, meaningful assertions, same-candidate applicability, preserved files, fresh raw assignment packets, and simulated/native/full-lifecycle limits.

Ordinary material in-scope fixes are included after validation; renew only affected checks/reviews. A new material design decision returns to the user. Missing mandatory implementation-review or behavioral evidence prevents a verified-result claim; known simulated/native limits must remain explicit.

Task 2 is complete when the reference, both templates, skill, metadata and observed outputs agree: three reconciled independent plan scopes yield a preparation-ready handoff; missing reviews yield a useful pending handoff; gates and separate permissions remain intact. This does not approve any generated product implementation, finish Task 3, or claim installed usability.

## Future impact, recovery and approval sought

Task 3 will consume the stable card, decision, review and handoff fields and implement actual revision/continuation/reconciliation. Task 4 retains the complete causal journey, remaining scenario variants and separately authorized native testing. No sequence, schema, dependency or migration change is needed. The current result affects future wording and readiness consumers, not accepted Task 1 behavior/history; explicit draft-to-reviewed promotion requires real evidence.

Recovery is to stop using this uninstalled candidate and preserve the accepted baseline and evidence. Do not delete files, reset Git or alter installation to simulate rollback. Any removal/restoration with possible user-work impact needs its own bounded authorization.

Approval sought: implement only the seven-file Task 2 product/test scope, update this development record, run the bounded synthetic evaluations and three independent implementation reviews, then stop at Gate 3. No commit, push, PR, installation, publication, old-plugin replacement, actual Ponytail invocation or automatic Task 3 implementation is included. Material decisions remain with the user. **Native activation remains not tested; installation not authorized.**

## Task 2 approval — 2026-10-12

The user directly approved this displayed Task 2 Gate 2 plan, identified by SHA-256 `4a797b86919c336e4d728f1d99e4e75f746bb61b2c319049bbadfd92d069bbd5`. Implementation, bounded synthetic evaluation and the three independent scopes proceed within that approved scope. Further preapproval scope is being clarified following automatic approval review; this note grants no additional authority. The existing prohibitions on Git publication, installation, old-plugin replacement and actual Ponytail invocation remain.

## Verified Task 2 result — 2026-10-12

The seven-file candidate now provides reviewed preparation handoffs for newly created plans: one canonical gate/review reference, two explanatory templates, and aligned skill/metadata/README/scenarios. Independent reports are reconciled before preparation readiness; missing scopes produce usable pending briefs. The candidate preserves coherent feature increments, coupled contracts/callers/tests/safeguards, both normal gates, separate permissions and the planning-only boundary. No execution engine, state machinery, extra skill or dependency was added.

**Exact comparison:** the complete before-tree is `/private/tmp/incremental-plan-task2.KEMEbT/before/`. The [final seven-file inventory](/private/tmp/incremental-plan-task2.KEMEbT/candidate.sha256) has SHA-256 `b7cb1fd871d11aac0c06dc1b313d8dc5292a77d64d12e7fe999f57a33184f9fe`. Changes are exactly the seven approved product/scenario files plus this administrative development record. The target remains uncommitted on unborn `main`; a tracked-only Git diff would omit this candidate.

### Verification and limitations

- The installed Plugin Creator validator returned `Plugin validation passed`; Skill Creator returned `Skill is valid!`, both exit 0 on the repaired candidate. Resource layout, package links, whitespace, current hashes and metadata agree. These static checks do not prove model behavior or native activation.
- Actual source-level agents exercised local/pasted creation, ambiguity and conflicts, collisions and escaping symlinks, explicit/implicit/unrelated routing, review-pending fallback, ordinary seeded review corrections and a naturally generated larger reviewed plan. The two reviewed cases used three actual independent scopes and reconciled supported findings. Raw assignments, artifacts, candidate identities, reports and native actions are retained outside the product repository.
- Concrete preparation exercised three exact proposals against an inspected application baseline and the actual reviewed overall plan/handoff: a shared-contract change, an unrelated feature bundle and a no-impact filter-only proposal. Affected packets identify cards and material decisions, preserve coupled checks/recovery and return the same increment to Gate 2; the no-impact case avoids a needless planner round trip. No packet was applied and no application was executed.
- The first concrete receiving artifact omitted separate post-result obligations. Its preserved source-based self-check restored them. Final handoff SHA-256: `add0feb408927a0bd390cbd048b4c27a5e45f90b2e03229e0cc526791b32da4d`. This demonstrates completion with a prompted self-check, not one-pass reliability.
- The fresh restricted-review case produced three separate copy-ready briefs, each requiring fresh context without inherited author conversation. Actual original review dispatches and new repair actors used explicit fresh contexts. Automatic reviewer dispatch under the repaired wording was not newly exercised.
- Gate, documentation-conflict/outage and actual-Ponytail permission cases are labeled decision simulations. They establish no real outage, absent tool, actual Ponytail invocation or complete executor-return journey. Some early actor reads omitted the host's `rtk` prefix; the receipts retain those protocol deviations. Controller link/inventory checks also had two documented false positives, corrected from the real artifact/assignment context without product changes.
- Final preservation checks confirm all 333 original old-repository entries, both original target files, both canonical copies and every target file outside the authorized change set remain unchanged. Across synthetic fixtures, 55 immutable entries remain unchanged, only the seeded original plan changed, and exactly 15 authorized new outputs exist.

Evidence index: [controller observations and repair addendum](/private/tmp/incremental-plan-task2.KEMEbT/results/controller-observations.md), [final preservation](/private/tmp/incremental-plan-task2.KEMEbT/results/preservation-repair-checks.txt), [output identities](/private/tmp/incremental-plan-task2.KEMEbT/results/output-files-final.sha256), [fresh dispatch references](/private/tmp/incremental-plan-task2.KEMEbT/results/dispatch-context.json), [validator receipts](/private/tmp/incremental-plan-task2.KEMEbT/receipts/structural-repair.jsonl). These are local temporary evidence paths, not shipped runtime resources.

### Independent review dispositions

All three distinct author-independent reviewers inspected the initial complete candidate. After two material findings, only the canonical reference and scenarios changed; five product files stayed byte-identical. The same reviewers performed focused affected-scope updates instead of repeating unchanged broad review. All three renewed reports identify the final inventory above.

| Scope and actual reviewer | Finding and reconciled disposition | Current report |
| --- | --- | --- |
| Requirements/source fidelity — `/root/t2_implementation_requirements` | Explicit fresh/no-inherited-context wording was missing. Repaired at the canonical reference and observed in each actual generated manual brief. Finding closed; no material improvement remains. | [Focused report](/private/tmp/incremental-plan-task2.KEMEbT/reviews/t2_implementation_requirements-renewed.md) |
| Architecture/reviewability/simplicity — `/root/t2_implementation_architecture` | Initial scope clean; the two-file delta and new concrete artifacts preserve coherence, canonical ownership and bounded scope. No material improvement remains. **Substitute simplicity review; Ponytail not run — not authorized.** | [Focused report](/private/tmp/incremental-plan-task2.KEMEbT/reviews/t2_implementation_architecture-renewed.md) |
| Verification quality — `/root/t2_implementation_verification` | Generic impact answers were insufficient evidence. Concrete baseline/proposal exercises now close that gap within preparation-only scope, with the prompted self-check limitation retained. No additional evidence required for Task 2. | [Focused report](/private/tmp/incremental-plan-task2.KEMEbT/reviews/t2_implementation_verification-renewed.md) |

The root validated retained findings and final dispositions against current artifacts and native receipts. Reports are evidence, not human approval. Initial reports and candidate remain preserved in the same evidence directory.

### Remaining work and authority

Task 3 still owns general revision, accepted-predecessor continuation and final reconciliation. Task 4 still owns the full scenario matrix and causal three-increment executor journey. The Task 2 result does not implement or accept those routes. Current metadata and README retain that boundary.

**Native activation remains not tested; installation not authorized.** No commit, push, PR, installation, publication, old-plugin replacement or actual Ponytail invocation occurred. Recovery remains preservation of the accepted baseline/evidence and stopping use of this uninstalled candidate, without destructive Git or file operations.

The user's preapproval was received. Automatic approval review rejected recording an extension through Tasks 3–4 because that scope was not clearly authorized; clarification was requested while Task 2 proceeded. This administrative result records verification only and does not turn an unseen result into human acceptance or bypass that host decision. Stop before Task 3 while the scope clarification is pending.

## Gate 3 acceptance and remaining-scope approval — 2026-10-13

The user directly replied “Approved” to the displayed Task 2 result and the explicit question confirming routine Gate 2/Gate 3 preapproval through Tasks 3–4. This accepts Task 2 inventory `b7cb1fd871d11aac0c06dc1b313d8dc5292a77d64d12e7fe999f57a33184f9fe` and resolves the earlier host-requested clarification. Tasks 3–4 may proceed through their routine pauses while still producing concrete plans, meaningful checks, three independent scopes, reconciled findings and verified result packets. Future results are preapproved for progression, not falsely described as already human-reviewed.

Material design decisions and source/repository exceptions still require user answers. Commit, push, PR, installation, publication, old-plugin replacement and actual Ponytail invocation remain unauthorized. Use the documented substitute simplicity review. Native activation remains unverified and cannot be supplied by a gate bypass.

The user also requested advice on the best fresh-thread checkpoint. The recommended point is this accepted Task 2 boundary, before Task 3 implementation. [Task 3 concrete preparation and continuation handoff](2026-10-13-continuation-gate-2.md) records the next coherent scope. This recommendation does not revoke the preapproval or mark remaining implementation complete.
