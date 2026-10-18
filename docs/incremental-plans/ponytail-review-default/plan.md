# Default Ponytail review when available

Execution steps superseded on 2026-10-17 by the [Superpowers writing-plans implementation plan](../../superpowers/plans/2026-10-17-ponytail-review-default.md). Preserve this document's policy requirements, unresolved choices and review history as supporting material; its increment sequence is no longer the implementation handoff.

Status: independently reviewed; one material finding corrected and rechecked. Draft pending two policy choices. Created: 2026-10-17; updated: 2026-10-17.

## Purpose and context

Change the planning workflow from exact-skill opt-in to a default `@ponytail-review` pass when available, unless explicitly excluded. Deliver this as one coherent increment, keeping the canonical policy, portable handoffs, documentation and behavioral scenarios consistent.

- Primary source: the user's direct request in this chat: “I would like to change that ponytail review if it is available unless explicitly excluded make a plan to make this change properly”. The preceding discussion concerned reviews per implemented increment.
- Current owner: [gates-and-reviews.md](../../../skills/incremental-plan/references/gates-and-reviews.md#simplicity-and-optional-ponytail), especially its exact-invocation, separate-repair and architecture-substitute rules. [Incremental planning](../../../skills/incremental-plan/SKILL.md), [standalone QA](../../../skills/qa-design/SKILL.md), their templates, [README](../../../README.md#package-and-validation) and [scenarios](../../../tests/scenarios.md) are consumers.
- Baseline: repository `/Users/CoveMB/Code/CoveMB/incremental-plan-plugin`, branch `main`, HEAD `68ad21a70b38c6cc77e5b549833074e6510ee687`, inspected 2026-10-17. Ten tracked files are modified; existing untracked references, QA sources and development records are preserved. This plan starts from that worktree, not a clean HEAD. The gate owner's inspected SHA-256 is `9f1764090ba6fe6a08512d101e3c1c43cd0d786e3526a2b737ffbc77dc695073`.
- QA: on; [qa-plan.md](qa-plan.md) owns detailed verification for this same candidate and increment. [handoff.md](handoff.md) carries the same pending next action.
- Authorization now: planning artifacts and bounded read-only inspection/review only. No product edits, actual Ponytail invocation, behavioral evaluation, global-instruction edit, Git writes, installation or publication are authorized by creating this plan.
- Preserve the three required independent review scopes, Gate 2/Gate 3, finding validation and distinct explicit authorization for Ponytail-origin fixes. Do not enable audit or implementation modes, add dependencies, a scheduler, runtime scripts, a state schema or a new approval gate.
- Evidence: reuse current source files and these planning documents. A small temporary baseline records current file digests and Git status for preservation checks; it is not shipped or durable acceptance evidence. No large capture is needed. No product behavior or installed activation has been tested for this change.

During the follow-up review, seven source/consumer files changed concurrently to add optional `material-code-review` recommendations and regular-review fallback. The current Ponytail subsection, user-instruction precedence and three-scope policy remain applicable. The author reread the affected guidance and preserved those concurrent edits; future I1 edits must use that updated worktree rather than the original source digest above. This review changes only the four planning/review documents in this directory.

Current official documentation was searched and read on 2026-10-17:

- [Build skills](https://learn.chatgpt.com/docs/build-skills) documents explicit and implicit selection, and `allow_implicit_invocation: false` suppressing implicit prompt-based invocation. This supports an instruction-level default, not a guarantee of host execution. Respect disabled/explicit-only host policy; do not change Ponytail metadata or host settings as a workaround.
- [AGENTS.md guidance](https://learn.chatgpt.com/docs/agent-configuration/agents-md) describes global/project instruction layering. The inspected global prohibition is a real policy conflict; this plan proposes a direct scoped amendment rather than treating a lower-priority skill as an override.
- [Plugin skill authoring](https://developers.openai.com/plugins/build/skills) recommends focused instructions, referenced policy/resources and no script when instructions and existing tools suffice. That supports retaining the existing gate owner and scenario method. It does not establish this change's behavioral acceptance.

## Material choices awaiting the user

1. **Stage:** implementation-result reviews only, or both plan and implementation reviews? Implementation only matches the preceding discussion and is the proposed scope until answered; this is not a recorded decision. If both are selected, Ponytail must assess the proposed plan as a proposal, without pretending that implementation exists, and be reconciled once across the coordinated plan/QA/handoff candidate.
2. **Global instructions:** include a narrow exception in `~/.codex/AGENTS.md`, or change only this plugin? The inspected global Ponytail section currently forbids automatic invocation and requires an exact skill request. A plugin-only change cannot override that rule. The recommended exception would apply only to `@ponytail-review` in the selected stages of this explicitly authorized workflow; audit, implementation modes and separate repair permission remain unchanged. Editing that file is a later separately authorized action, with host permission handling.

Do not implement either unresolved choice by assumption. Unrelated projects and explicit target restrictions are outside the requested amendment.

## Proposed policy

The shared gate reference remains the sole detailed owner. Adapt the first sentence below to the user's stage answer:

> At the selected review stage, use `@ponytail-review` by default when it is installed, enabled, exposed by the current host and usable for the bounded candidate under applicable instructions and permissions, unless the user has explicitly excluded it for that scope. A separate exact-skill mention is unnecessary. Identify the selected route, candidate and rerun conditions in the concrete plan and portable handoff. Availability never authorizes installation, permission changes, private-source transfer or other external actions.

| Condition | Required behavior |
| --- | --- |
| Available, applicable and not excluded | Perform one read-only Ponytail pass on the identified candidate at the selected stage; validate its findings and reconcile them with the three independent scopes. Do not use Ponytail's default “all dirty files or last commit” selection. |
| Direct user exclusion | Preserve its actual scope through plan, QA, handoff and continuation. Use the architecture-owned simplicity substitute; excluding Ponytail does not exclude simplicity or the other review scopes. A supplementary-QA exclusion alone does not exclude Ponytail. |
| Missing, disabled, not exposed, or unsuitable for this candidate | Record the actual reason and use the existing substitute. Do not install, enable or configure Ponytail to satisfy the default. Listing a skill alone does not prove a completed review. |
| Conflicting exact-opt-in or prohibitory instruction | Respect it. Record the restriction and substitute when permitted; obtain a scoped user amendment when the requested behavior cannot otherwise be met. Never infer a global waiver from the plugin default. |
| Invocation fails or is unusable | Preserve the failure, allow a bounded diagnostic using existing facilities, and substitute when permitted. Never report an attempted run as passed, retry unchanged failures repeatedly, or hide the reason. |
| Target requires actual Ponytail and forbids substitution | Missing or unusable Ponytail leaves that obligation pending; return the exact conflict for a user decision. |

Separate repair authorization stays intact, including applicable bounded repair preauthorization. Ordinary implementation approval, the default pass and a clean report grant no Ponytail-origin repair permission. Renew only affected checks/reviews after a material correction or changed candidate; reuse valid reports and never rerun unchanged work to reach a pass count.

For new workflows, preparation carries the default into the concrete plan; execution follows only after its applicable Gate 2 approval or scoped bypass. Old accepted results, explicit exclusions and specific opt-in-only decisions retain their historical scope. At a later authorized preparation/continuation, surface the changed policy and reconcile applicable authority before using it; do not silently reinterpret old preapproval or create retrospective missing-review failures. There is no bulk plan migration or history rewrite.

## Parts, coverage and increment

| Part | Ordered increment |
| --- | --- |
| Review default | I1 — Apply the available-by-default Ponytail policy consistently |

| Obligation | Owner / acceptance |
| --- | --- |
| Default when available; no exact user mention | I1; available/non-excluded behavior and portable handoffs |
| Direct exclusions and continuation | I1; scoped exclusions survive rereads and QA-mode changes |
| Availability, failure and strict-target recovery | I1; actual reason, substitute or precise pending obligation |
| Selected review stage and global-instruction boundary | I1; direct answers above, then only the agreed amendment |
| Findings remain unverified; fixes need distinct authority | I1; existing C16 repair cases remain governing |
| Candidate isolation, review independence and gates | Global obligation; exact incremental comparison, no unrelated dirty work, no scope substitution or fabricated approval |
| Verification and source/native evidence limits | I1; [QA design](qa-plan.md), actual future results kept separate |
| Existing work and accepted history | Global obligation; selective changes only, no bulk migration or changed historical receipts |

### I1 — Apply the available-by-default Ponytail policy consistently

- **Outcome:** the selected review stage chooses Ponytail without a separate exact-skill request when usable and not excluded; otherwise it truthfully selects the existing permitted substitute or leaves the strict obligation pending.
- **Prerequisites:** both material choices answered; current sources, host metadata and applicable target instructions reread; exact comparison prepared against the preserved worktree; Gate 2 retained.
- **Canonical edit:** update the Ponytail subsection and relevant lifecycle wording in `skills/incremental-plan/references/gates-and-reviews.md`. Keep default selection, exclusions, availability, failure, strict targets, candidate/rerun rules and separate repairs together.
- **Consumers:** update `skills/incremental-plan/SKILL.md` so its current “no implicit invocation” statement cannot negate the selected default; ensure `skills/qa-design/SKILL.md` carries the applicable executor policy through its portable handoff. Update `skills/incremental-plan/assets/plan-template.md`, `skills/incremental-plan/assets/handoff-template.md` and `skills/qa-design/assets/qa-plan-template.md` to carry default/excluded/substitute status, scope and reason in existing fields. Link to the canonical owner rather than copying the whole policy.
- **Documentation and checks:** update README's explicit-only statement and usage/exclusion guidance; extend the existing C16 scenario family and affected portable-handoff cases in `tests/scenarios.md`. Preserve historical result statements and explicit no-Ponytail fixture restrictions. Do not change package identity/version or add a mandatory integration merely because a default was changed.
- **Conditional global edit:** only if selected and authorized, make the smallest workflow-specific exception in the global Ponytail section. Preserve surrounding user edits and unrelated global defaults. No installed skill/cache or host configuration edit belongs to this increment.
- **QA ownership:** I1 owns every row in [qa-plan.md](qa-plan.md#verification-design), including the combined generated-handoff-to-executor selection journey. Keep the needed behavioral cases with the policy change.
- **Human review focus:** distinguish the default from authority to execute a stage or repair findings; verify exclusion precedence, exact candidate selection and freshness; prevent a fifth pass or duplicate plan/QA review set.
- **Safe intermediate / compatibility:** ship the canonical policy and all affected consumers together. No partial explicit-only/default contradiction. Existing accepted history stays factual; old active workflows receive scoped reconciliation at their next affected preparation rather than a forced migration. The change operates as an instruction policy, without deterministic scheduling or activation guarantees.
- **Acceptance:** selected-stage behavior and every branch above are represented consistently; a fresh executor receiving only the generated handoff can select the correct route; available review adds one pass to the three required scopes, while substitute simplicity remains inside architecture review. Actual results and remaining evidence gaps match the QA design. Static checks alone do not establish these model behaviors.
- **Verification:** after authorized implementation, run the README's two per-skill validators, parsed manifest/frontmatter/resource/link/privacy checks and whitespace checks on the settled candidate. Separately authorized synthetic evaluations exercise changed behavior; no text-matching test substitutes for those observations. Use one full relevant deterministic pass, repeating only for changed inputs or new evidence.
- **Recovery:** retain the before content and bounded increment diff, preserving all predecessor work. An authorized selective repair can restore the former policy and its consumers together; never reset, stash or overwrite the dirty tree. Reverting instructions cannot retract a disclosure, unwanted review expenditure or already-applied repair, so prevent those through the preserved action boundaries.
- **Gates and reviews:** Gate 2 approves the concrete scope after the decisions; Gate 3 receives actual checks, default/substitute/failure evidence, findings/dispositions and limitations. The product's three independent scopes and optional-integration evidence distinctions remain unchanged. No automatic bypass is granted here.
- **Future impact:** reassess actual global-rule correspondence and generated handoffs; installation and native invocation of changed sources remain a separate later scope. No successor feature or cleanup work is implied.

## Progress and review readiness

| Item | Factual state | Next action |
| --- | --- | --- |
| I1 implementation | Not started; no Gate 2 approval or bypass for this change | Answer material choices, then prepare the concrete edit scope |
| Static/source verification | Sources inspected; proposed checks have not run against an implementation | Execute only during authorized development |
| Behavioral / actual Ponytail / native activation | Not run for this change | Obtain applicable evaluation/invocation/installation authority separately |
| Independent planning review | [Current independent report](review.md#follow-up-independent-review--2026-10-17) identified one unsupported readiness blocker; corrected in plan/QA/handoff and independently rechecked as resolved | The two policy choices remain pending, with no additional report-count gate for this task |

For this repository planning task, the user's instruction to use at most one bounded final reviewer takes precedence over the skill's general three-report guidance. One independent report assesses source fidelity, architecture/simplicity and verification design without being counted as three reports. No additional report-count approval or review is required for this task. The plugin's future runtime review requirements remain unchanged; this task-specific instruction does not waive those requirements for other workflows.

The original fresh-context reviewer `/root/review_ponytail_default_plan` found no material improvements on the earlier draft. At the user's subsequent request, fresh-context reviewer `/root/independent_ponytail_plan_review` reviewed the coordinated candidate without the earlier report and identified the unsupported readiness blocker. The author validated it against the user's reviewer limit and the skill's explicit user-instruction precedence, then corrected the affected planning documents. The original report remains historical; its clean verdict does not establish that the later defect was absent. The same reviewer rechecked only affected sections and reported “Finding resolved. No material improvements recommended.” Post-correction document links/anchors and whitespace checks passed; all 35 nonplanning files matched the reread baseline containing the concurrent edits. Subsequent result/status notes are administrative. These document checks are not product/model/native verification.

Review subjects for this task are covered by the permitted independent report below. If later material answers or corrections change reviewed scope, renew only affected review using the raw request/answers, current instructions, exact coordinated candidate and relevant sources. Review remains read-only, without product execution, actual Ponytail, recursive delegation or external actions; a material finding needs a source locator, impact, smallest remedy and limitations.

- **Source fidelity:** verify default/exclusion scope and the actual stage/global answers; ensure repairs, accepted history and separate actions are preserved.
- **Architecture/simplicity:** verify one coherent policy increment, one canonical owner, portable consumers, precise candidate selection and adequate fallback without new machinery.
- **Verification:** verify discriminating expected outcomes for availability, exclusions, restrictions, failure, repairs and continuation; distinguish simulation, actual invocation and installed proof.

## Final scope reconciliation

Not performed. I1 must reconcile every coverage row with the actual changed candidate, verification and reports, direct material decisions and applicable Gate 3 result. The plan itself demonstrates no new invocation behavior. External installation/publication and a durable global change require their own actual authority and evidence.

### Evidence retention and cleanup review

**Planned**, after relevant verification/reviews, outside the feature-increment count. Keep these planning documents and applicable source/review references; hold temporary preservation/evaluation evidence while its consumers remain active. At closure identify actual owners and keep/hold/cleanup-candidate/unknown dispositions. No large capture, cleanup, deletion or compaction is currently proposed or performed.

Next action: resolve the two policy choices, then prepare I1's concrete scope for Gate 2. Current [handoff.md](handoff.md) is for decisions and preparation only, not implementation approval.
