# Evidence-based continuation — Tasks 3–4 result and fresh-thread boundary

Date: 2026-10-13. Current status: Tasks 1–4 are implemented; authorized source-level verification, independent reviews, local installation and native CLI acceptance are complete. The user approved native work and routine progression. See [native acceptance and plan completion](#native-acceptance-and-plan-completion--2026-10-13) for the current result, durable local evidence and limits. Earlier preparation, unapproved-installation statements and fresh-thread instructions below are historical. Material decisions and separate Git/publication permissions remain required.

## Purpose and evidence to carry forward

Build the existing plugin, not a product through it. This increment adds one coherent capability: reopen a persisted incremental plan in a fresh task, reconcile current evidence and history, and write the correct next handoff or final scope reconciliation. Source identity, accepted predecessors, revisions, consistent handoffs and complete requirement ownership must work together; separating them would make continuation unsafe.

Target: `/Users/CoveMB/Code/CoveMB/incremental-plan-plugin`. Legacy repository: `/Users/CoveMB/Code/CoveMB/implementation-plugin`, preserved read-only. Open the fresh development thread in the target repository so its guidance and filesystem scope match the work. Do not create another repository, worktree or branch.

Read the target `AGENTS.md`, applicable parent/session instructions, `/Users/CoveMB/.codex/RTK.md`, the [reviewed design](../specs/2026-10-11-incremental-plan-plugin-design.md), especially sections 3–6, the [canonical implementation plan](2026-10-11-incremental-plan-plugin.md), Tasks 3–4 and its matrix, and [Task 2's accepted result and approval](2026-10-12-reviewed-handoffs-gate-2.md#gate-3-acceptance-and-remaining-scope-approval--2026-10-13). Reuse settled decisions; no new brainstorming, architecture, setup gate or approval ceremony is needed.

Both repositories and the complete Task 2 candidate were inspected on 2026-10-13. Target exists, is not a symlink, has no commits/remotes/staged files and is on unborn `main`. Legacy `main` remains at `18a77af3f1fea552401bcc2c9a3959dbcb97d684`, with no tracked/index changes and its same three untracked planning documents. No refs were refreshed. Recheck these facts before changing files; preserve divergence rather than overwriting it.

Task 2 inventory: `/private/tmp/incremental-plan-task2.KEMEbT/candidate.sha256`, SHA-256 `b7cb1fd871d11aac0c06dc1b313d8dc5292a77d64d12e7fe999f57a33184f9fe`. All seven hashes still match. Its exact before-tree, raw packets, actual synthetic outputs, native receipts and all three initial/focused independent reports remain in that evidence directory. Preserve those inputs; do not regenerate them or repeat passing checks on unchanged behavior merely to obtain a fresh timestamp. They are local temporary paths: if unavailable, state the specific missing evidence rather than reconstructing a pass.

Original target `AGENTS.md`: `33c6c822229bb368d7e3adb9fd97c6e99c17db231c2d34274b53c776c2d2c482`; `.gitignore`: `0ab55b4cc11c8f7b761159ebd61bbe558a06f4dda33d8777f2f4a02dd5a28633`. Preserve both. Canonical copied design/plan remain unchanged at `22d90101991efaf3045b6f8048e4b75afd238721c8488e4e860d14b99bac6207` / `3cb2cfe4d6f33bfb34dfe35b3080339ce463665bd16bb0a0f60e8eaf590c08ad`.

## Current documentation and architecture

Current official sources were rechecked 2026-10-13 after local instruction/tool inspection:

- [Build skills](https://developers.openai.com/plugins/build/skills): keep narrow discovery, procedure in the entry point, policy in references and output resources in assets. Existing tools/instructions remain adequate; no script is justified by this task.
- [Package your plugin](https://developers.openai.com/plugins/build/plugins): the existing `.codex-plugin/plugin.json` compatibility format remains supported. Preserve the Codex-only layout and version `0.1.0`; do not migrate or add optional integrations.
- [Skill evaluation](https://developers.openai.com/blog/eval-skills): inspect actual actions and artifacts. Use existing native agents and saved raw assignments rather than adding an evaluation framework.

No current conflicting requirement changes the reviewed architecture. Existing local authoring/validation tools remain development aids, not shipped dependencies. Use `superpowers:executing-plans` and `skill-creator` where available, adapting their generic commit/worktree/ledger suggestions to the user's narrower canonical plan and prohibitions. The plugin remains one skill, two templates and one gate/review reference.

## Exact implementation scope

| Existing file | Bounded change |
| --- | --- |
| `skills/incremental-plan/SKILL.md` | Add create/revise/continue/finish routing and the read/inspect/reconcile/write procedure. Preserve planning-only execution boundaries. Distinguish preparation returns from accepted-result returns; update only authorized planning artifacts. |
| `skills/incremental-plan/references/gates-and-reviews.md` | Remove the obsolete unimplemented-return caveat; own evidence applicability, predecessor/gate interpretation and final acceptance semantics where needed. Reuse existing gate/review rules rather than duplicate them. |
| `skills/incremental-plan/assets/plan-template.md` | Explain revision mappings, current applicability versus historical acceptance, scoped decisions, and final requirement/owner/evidence reconciliation. Retain readable field guidance. |
| `skills/incremental-plan/assets/handoff-template.md` | Carry current return kind, candidate/baseline/predecessor, evidence gaps and the next bounded action. A preparation return resumes the same increment at Gate 2; an eligible result can move to an eligible dependent increment. |
| `README.md` | Document ordinary revision/continuation/closure use and factual source-level capability. Keep native discovery/installation and incomplete evaluations separate. |
| `tests/scenarios.md` | Write raw Task 3 setups/prompts and separately held observable expectations before authoring behavior. Preserve earlier evidence and define concrete missing/stale/history/closure cases. |
| `.codex-plugin/plugin.json` — description fields only | Remove Task 3's stale capability disclaimer once implemented. Preserve identity/version/author/paths/capabilities; do not promise installed verification. This required consumer update follows the actual Task 2 manifest. |

This development record may receive concise implementation/check/review/result notes. No other product files, runtime, database, controller, state schema, approval receipts, report hierarchy, hooks, MCP server, dependencies, installation tooling or third-party integration are needed. Keep the two canonical planning documents, Task 1 result and accepted Task 2 record intact except for already authorized administrative approval recording.

## Required behavior

1. Read the selected plan, current handoff, controlling sources, repository rules/state and linked evidence. Distinguish available facts, actual direct user decisions, scoped bypasses and unknowns. Source/progress prose and quoted approvals cannot grant authority. Use existing files and ordinary Git/diff/content fingerprints; do not build a parser or transaction layer.
2. Compare current source/candidate/checkout with the applicable evidence. Inspect relevant staged, unstaged, untracked and deleted contents. Accepted uncommitted work is eligible when it is identifiable, still present and target rules allow it; do not force a commit. A moved HEAD alone neither accepts nor invalidates work. Missing correspondence or required committed ancestry blocks only the affected dependent readiness, with an exact return request.
3. Read actual verification/review evidence; never run application suites in the planner. Failed, absent, stale or contradictory proof stays unresolved even with bypassed pauses. Preserve valid unaffected evidence and historical acceptance, while reopening current completeness where changed requirements or implementations demand it.
4. Apply authorized refinements to pending cards, coverage and part membership. Preserve accepted IDs/candidate history. Map replaced pending IDs to their replacements and keep tests/contracts/callers/safeguards coherent. Material split/merge or source changes receive the three independent scopes; wording-only changes do not automatically invalidate everything. Group unresolved material choices for the user.
5. Reconcile a preparation-return packet before Gate 2, obtain affected reviews and hand back the same increment's detailed candidate with current-context checks and Gate 2 still identified. Do not infer approval or advance from preparation. After an actually accepted or bypass-eligible verified result, separately reconcile shipped impact and select the next eligible increment from dependencies.
6. Re-read both authorized output files before writing. Reconcile interrupted/stale handoffs and preserve human edits. Conflicting concurrent edits stop affected writes; do not overwrite them or fabricate lost decisions. Use ordinary inspectable edits, not custom recovery machinery.
7. Reconcile every original and amended obligation with its owning increment's evidence at closure. Distinguish historically accepted work, achieved selected scope, approved deferrals and separate certification/release obligations. Bare status labels, the last increment's acceptance and unapproved deferrals cannot prove full completion. Keep the response recap derived from the saved cards and current gates.

## Verification plan and local setup

Create one disposable `/private/tmp/incremental-plan-task3.*` workspace with immutable raw fixtures, exact plaintext packets and before/after inventories. Preserve previous Task 2 artifacts. Actors receive only the raw request, relevant sources/candidate and explicit allowed paths/actions; evaluator expectations remain separate. Start independent actors/reviewers with explicit fresh context and no recursive fan-out. Capture real actions, attempted forbidden actions, outputs and candidate identities; final claims alone are insufficient.

Use one genuine causal continuation path, preserving generated files between stages, plus small isolated evidence-boundary variants. A separate bounded executor may implement trivial synthetic fixture code and meaningful tests; the planner may update only its named plan/handoff/review notes. Label controller-supplied approvals as test simulations. Never report seeded review/history fixtures as naturally generated or as actual human approval.

| Cases | Concrete observation |
| --- | --- |
| C06/C07 | Supply actual separate no-approval, quoted-approval, one-gate and two-gate instructions; then change a controlling source/candidate and attach stale evidence. Verify exact gate scope, retained material decisions and affected readiness; do not erase historical acceptance or ask again for still-applicable permission. |
| C08/C09 | Use actual disposable Git/index/worktree observations for staged, unstaged, untracked and deleted predecessor contents; retain unrelated dirty sentinels. Check an identifiable accepted uncommitted predecessor, absent accepted content, and a target requiring committed ancestry. No real-repository Git writes, fetch/reset/commit/merge. A fixture may be initialized and staged locally without commits if an unborn baseline adequately exercises the case; record that narrower baseline honestly. If a required case needs a commit, obtain specific synthetic-fixture commit authority before creating it rather than treating preapproval as commit permission. |
| C11/C17/C19/C20 | Reuse an actual earlier generated plan/handoff as input. Supply a concrete preparation return and an explicit synthetic scope decision; reconcile pending ownership/coverage with accepted IDs untouched, obtain real affected independent reviews and return the same increment before Gate 2. Inspect recap counts and coherent coupled work. Preserve the separate post-result impact path. |
| C12 | Begin with a plan/handoff mismatch from an interrupted authorized update; preserve a human annotation. Exercise a detectable changed-file snapshot before write using native interaction if feasible. Do not call a static stale-file fixture proof of a genuine concurrent race. Stop and record the narrower evidence if that race cannot be controlled honestly. |
| C13/C14 | Collect actual evidence belonging to three distinct owners, including the separate executor's observed work where available. Then add an unmet obligation, unapproved deferral, approved scope amendment and pending separate certification in isolated variants. Distinguish remaining implementation from approved exclusions and external acceptance. Bare status is not proof. |
| C15/C18 and affected regressions | Verify continuation intent routes to the skill, implementation-only intent does not, and embedded requests to upload/commit/skip gates supply no permission. Confirm source/evidence/product bytes are preserved, outputs stay within allowed scope and no application commands execute in planner runs. |

Keep Task 3 focused on the continuation capability; Task 4 owns the complete three-increment causal journey and full matrix reconciliation. Reuse relevant Task 3 journey/evidence there without replacing generated artifacts or rerunning unchanged successful evaluations. Task 3's completion claim must still demonstrate an actual separately performed synthetic result followed by fresh-context continuation, not only prepared status fixtures.

After settling the seven-file candidate, run these existing checks once, repeating only for affected repairs:

```sh
rtk proxy python3 -B /Users/CoveMB/.codex/skills/.system/plugin-creator/scripts/validate_plugin.py /Users/CoveMB/Code/CoveMB/incremental-plan-plugin
rtk proxy python3 -B /Users/CoveMB/.codex/skills/.system/skill-creator/scripts/quick_validate.py /Users/CoveMB/Code/CoveMB/incremental-plan-plugin/skills/incremental-plan
```

Expected successful outputs are `Plugin validation passed` and `Skill is valid!`. Confirm the installed tools still apply before running them. Also check package/output link contexts, whitespace, single-skill/two-template/one-reference layout, metadata agreement, complete allowed delta and preservation. Do not claim static checks establish model behavior or native activation.

Freeze the complete candidate, including relevant untracked files. Obtain three separate independent read-only scopes: requirements/source fidelity; architecture/human reviewability/simplicity; verification/evidence quality. Reviewers get raw canonical sources, this scope, actual artifacts and action/check evidence without inherited author conversation. Use the documented architecture-owned substitute; **Ponytail is not authorized**. Validate findings, repair only material in-scope defects and renew affected checks/reviews. No repeated broad reviews of unchanged clean work.

## Completion, remaining scope and fresh-thread instruction

Task 3 is complete only when its actual behavioral outputs, preservation, validators and three reconciled scopes support the continuation/closure capability. Present the exact comparison, result evidence, limitations and future impact. The user has preapproved the routine Gate 3 pause; record eligibility under that permission rather than claim the unseen result was human-reviewed. A new material design question still stops its affected work.

Then prepare the concrete Task 4 scope and carry out the canonical full matrix and three-increment executor journey, retaining coherent increments and required reviews. Native activation remains separately unapproved; report that limit, do not install or invent a native invocation. Finish all authorized source-level work without reopening settled choices or routine gate permissions.

Recovery: preserve the accepted Task 2 candidate and all evidence, stop before using an unsupported result, and make only bounded authorized repairs. Do not delete/reset/stash existing work, replace the old plugin or alter installation.

Original instruction used for this development run (historical):

> Continue building `/Users/CoveMB/Code/CoveMB/incremental-plan-plugin` from this Task 3 concrete plan. Read its linked canonical sources, target instructions and accepted Task 2 record. The user explicitly approved routine Gate 2 and Gate 3 progression through Tasks 3–4; preserve all concrete preparation, behavioral verification, independent reviews and material-decision questions. Implement Task 3, verify/review its coherent result, then complete Task 4's authorized source-level validation and full synthetic journey. Use the documented simplicity substitute. Do not commit, push, create a PR, install, publish, replace the old plugin or invoke Ponytail. Keep native activation unverified unless separately authorized and actually observed. Recheck the current checkout and candidate before edits; preserve all user work. Tell the user when another fresh-thread boundary would help. This file is a handoff for building the skill, not a request to use the skill to implement a product.


## Development observations — 2026-10-13

The user's current continuation request confirms work in this repository under the recorded Tasks 3–4 preapproval. Initial checks matched the recorded target/legacy state, all seven Task 2 candidate hashes and preserved guidance/design/plan identities. No refs were refreshed.

Task 3 raw fixtures and evaluator-only expectations were saved before behavioral instructions. The seven-file implementation now adds revision/continuation/closure routing, evidence/predecessor applicability, pending-ID mappings, final owner/evidence reconciliation and matching documentation/metadata. Package identity/version and the one-skill/two-template/one-reference layout are unchanged. No runtime or new product file was introduced.

Evidence directory: `/private/tmp/incremental-plan-task3.7b_cor9m`. `before/` and `before.json` preserve the exact comparison; `candidate-initial.sha256` identifies the seven-file candidate; `packets/` holds plaintext actor assignments; `observations/` holds checks and native action evidence; `fixtures/journey/` preserves the actual Task 2 generated plan and subsequent executor/planner artifacts. The old Task 2 directory remains unchanged.

Both existing bundled validators passed; link contexts, whitespace, package counts and the exact allowed delta passed. These are structural checks only. At that initial checkpoint the synthetic journey and evidence-boundary variants were still in progress; the final result below supersedes that pending status. Controller-supplied decisions are labeled test simulations; native activation and actual Ponytail remain unapproved/unverified.

The first product-write escalation was rejected by automatic approval review as a material design change. A read-only comparison demonstrated the exact file/behavior scope already explicitly requested by the user and recorded above; the same bounded write was then approved. No rejected write occurred and no workaround was used.

## Final source-level result and remaining acceptance — 2026-10-13

The continuation capability, authorized three-increment synthetic journey and matrix reconciliation are complete. All three independent source scopes are reconciled with no material improvements recommended. The final verification report supports this bounded result; its SHA-256 is `964324380127900cf06c032b4f22cddb4fa35c8bebd24924828650ca2e2e0de1`. Concrete preparation, applicable checks, reviews and reconciliation satisfy the recorded routine Gate 2/Gate 3 preapproval. This is bypass eligibility, not human review of an unseen result. Native installed-product acceptance remains open and separately unapproved.

Exact seven-file source candidate: [candidate.sha256](/private/tmp/incremental-plan-task3.7b_cor9m/candidate.sha256), SHA-256 `08c97e235d539bbf9b6b6c0159bcf96b5660e4f0d3285012cccbe81171842386`. Compare with `before/` and `before.json` in the same evidence directory. Only the seven authorized product/test files and this development record changed; no product file was added. Identity/version, one skill/two templates/one reference, canonical design/plan, repository guidance and legacy work are preserved. The final [preservation record](/private/tmp/incremental-plan-task3.7b_cor9m/observations/final-preservation.json) identifies the exact current tree and real-repository state.

The settled candidate passed both bundled validators, package links/layout, description-only metadata constraints and whitespace checks. [Exact check receipt](/private/tmp/incremental-plan-task3.7b_cor9m/observations/settled-structural-checks.json) binds their zero exits to this candidate. Successful unchanged checks were reused; static validation is not behavioral or native proof.

### Observed behavior and independent reviews

The [matrix](/private/tmp/incremental-plan-task3.7b_cor9m/observations/task4-matrix-working.md) reconciles C01–C20 with exact reuse and limits; the [evidence index](/private/tmp/incremental-plan-task3.7b_cor9m/observations/verification-evidence-index.md) locates raw packets, artifacts, inventories, native actions and actual reports. It is not an assertion that every native or unavailable-host route passed.

- Actual preparation returned to a fresh planner, changed pending ownership through an explicit simulated decision, received three affected reviews and resumed the same I1 before Gate 2.
- Separate executors produced I1 inspection, I2a reusable queries and I2b default integration. Each delivered its coupled tests/usage and received three actual implementation reviews. I1 passed 10 unit methods/34 doctest examples; I2a passed 15/63 plus eight consumer smoke assertions; I2b passed 20/85 plus 21 independent-original/literal parity cases across eight snapshots. These are synthetic Python behavior checks, not plugin unit tests or production certification; doctest counts include setup examples.
- A controller-delivered consumer arrived after I2a preparation/initial implementation. The executor identified its real downstream effect; a fresh planner and three affected reviews assigned consumer coverage to I2b, whose actual integration then verified it. This is distinct from the earlier preparation revision.
- Actual fresh continuation inspected accepted uncommitted contents, preserved history, and distinguished no/quoted/one/both gate authority. Stale source/candidate, missing predecessor and required committed ancestry held affected readiness. A pending-card merge received all three scopes without executing that alternate increment. Interrupted handoff recovery preserved human content; a controlled inter-turn edit stopped conflicting writes.
- Final closure reconciled all three owning results and reviews. Four isolated variants retained mandatory unmet R4 and rejected an unapproved deferral; closed an explicitly amended delivery with unachieved R4 assigned to future F1; and distinguished completed local implementation from pending external L1 certification/release. All affected documentary scopes were independently reviewed. Final closure changed only ten planning outputs and preserved all 222 other fixture files, including 105 Git files.

All synthetic gate/design decisions are labeled controller simulations. They demonstrate bounded workflow behavior, not actual human acceptance. Planners inspected evidence without executing application suites; executors remained confined to disposable fixtures.

| Independent final source scope | Actual report and current disposition |
| --- | --- |
| Requirements/source fidelity | [product-requirements.md](/private/tmp/incremental-plan-task3.7b_cor9m/reviews/product-requirements.md): no material improvements; focused renewal covers current scenario and Git-preservation repair. |
| Architecture/human reviewability/simplicity | [product-architecture.md](/private/tmp/incremental-plan-task3.7b_cor9m/reviews/product-architecture.md): no material improvements; focused renewal covers the repair. **Substitute simplicity review; Ponytail not run**, because unauthorized. |
| Verification/evidence quality | [product-verification.md](/private/tmp/incremental-plan-task3.7b_cor9m/reviews/product-verification.md): final remaining-evidence disposition: no material improvements; all mandatory source-level evidence gaps closed, with the explicit native/host/ancestry/race limits preserved. |

The controller verified material claims against current sources and raw artifacts. No additional source repair is proposed. The final disposition has been recorded and reconciled. This administrative update does not change the seven-file candidate; no second broad source review or unchanged test rerun is needed.

### Observed defect, correction and limits

Six original C06/C07/C17 inspections changed disposable Git index stat-cache bytes while leaving staged names/modes/flags/blobs and other protected content unchanged. Those observations did **not** pass exact Git-metadata preservation. A two-sentence repair at the canonical reference now requires `git --no-optional-locks -c diff.autoRefreshIndex=false …` per inspection and forbids concealing effects through index restoration. Controlled native probes established the cause; a fresh corrected planner preserved all 33 protected files, including 21 Git files. Later continuation/closure preservation also passed. Original failures, exact before bytes and corrected evidence remain distinct; no failed run was rewritten into a pass.

Initial approval-review rejections blocked one product write, I2b preparation and the I2b verification-report write. No rejected mutation occurred. Read-only inspection established the actual user-selected scope, including the original user message for the report case; the same bounded approval-controlled writes then succeeded. There was no alternate write route. Initial shell-wrapper/helper deviations are retained in the evidence rather than claiming a flawless harness.

Native installation/loading, qualified invocation and automatic discovery remain unapproved and unverified. Actual Ponytail, a genuinely absent-tool host, successful committed-predecessor ancestry and a simultaneous filesystem race are also unverified. Source-metadata routing, the authorized substitute, an unborn dirty repository and controlled inter-turn editing do not prove those routes. No real-repository commit, staging, push, PR, installation, publication or old-plugin replacement was performed; refs were not refreshed. Preserve the old plugin and both historical/current evidence directories. Temporary evidence paths may expire; missing future evidence must be reported rather than reconstructed.

### Historical fresh-thread boundary before installation

The final independent evidence disposition and administrative record are complete. All currently authorized source-level Tasks 3–4 work is exhausted. A fresh thread in the **target** repository is appropriate before separately authorized native activation or real use; routine source-result preapproval does not grant installation permission.

Historical continuation, superseded by native acceptance below:

> Work in `/Users/CoveMB/Code/CoveMB/incremental-plan-plugin`. Read this record's final result and linked actual reports, target guidance and canonical design/plan. Recheck the exact source candidate and available evidence; preserve settled checks, current files and the legacy implementation-plugin. Source-level Tasks 3–4 have been evaluated; native installed-product acceptance remains open. Do not repeat unchanged evaluations or invent missing receipts. Before any installation/configuration mutation, obtain separate explicit authority for a concrete native activation test, with existing-state inventory and recovery. No commit, push, PR, publication, old-plugin replacement or actual Ponytail is authorized by this handoff. Report installed behavior only when actually observed in a fresh native context.

## Native acceptance and plan completion — 2026-10-13

The user subsequently approved the concrete local installation/native-test plan, required updating the CLI first, approved the restricted test setup and routine future approvals, and requested completion of remaining work. This authorizes the documentation/evidence closeout. It does not authorize commits, pushes, publication, legacy-plugin replacement or actual Ponytail, and does not make an unseen result human-reviewed. New material design choices still require user answers.

### Whole-plan reconciliation

| Task | Implemented outcome and applicable evidence |
| --- | --- |
| 1 — source conversion | One planning-only skill, source/coverage/increment structure, coherent review units and recap. The source-conversion result and Task 2's actual C01/C02/C19/C20 observations remain applicable. |
| 2 — gates, reviews, handoffs | Canonical Gate 2/Gate 3 policy, three independent scopes, authorized simplicity substitute and portable preparation-return handoffs. The accepted reviewed-handoffs result and retained reports establish this scope. |
| 3 — continuation and closure | Actual preparation returns, separately executed synthetic results, fresh continuation, uncommitted predecessors, revisions, conflict handling and final owner/evidence reconciliation. The final source result and three independent dispositions above remain applicable. |
| 4 — complete package | Settled structural receipts, the actual three-increment journey, reconciled C01–C20 matrix and three clean source scopes are retained. Approved native loading, explicit/implicit activation and the implementation-only negative case now supply the missing installed-product evidence. |

**Implementation conclusion:** all four tasks are delivered within approved source-development and local native-CLI scope. No unresolved material source finding or mandatory evidence gap remains in that scope. This does not claim every conditional host/tool route, desktop interaction or simultaneous race was empirically tested. Native C15 gains the actual observations below; other matrix limits remain unchanged.

### Native acceptance

The existing Volta-managed CLI was updated from `0.146.0` to `0.162.1`, verified against the public npm stable tag and [official changelog](https://learn.chatgpt.com/docs/changelog). Native installation added the new plugin to the existing personal marketplace and enabled `incremental-plan-plugin@local-personal-codex-plugins`, alongside the preserved legacy plugin. Existing account authentication was used; credential files were not copied into test artifacts or model context.

Tests exercised the frozen seven-file candidate manifest `08c97e235d539bbf9b6b6c0159bcf96b5660e4f0d3285012cccbe81171842386`. This closeout changes only README and administrative plan/result records. Manifest, skill, reference, templates and scenarios remain byte-identical. The three existing source reviews and behavioral results retain their exact original subjects and applicability; no repeated broad source review or unchanged behavioral run is needed.

| Case | Actual observation |
| --- | --- |
| N0 loading | Fresh native app-server returned enabled `incremental-plan-plugin:incremental-plan` from installed cache, without skill-load errors. Used `skills/list` with `forceReload: true`, with no model turn. |
| N1 explicit | Fresh thread `01a13794-15f7-72f3-8462-2d27e0c90fb0` received the qualified invocation, read installed skill/templates/reference, created only plan/handoff and exited 0. |
| N2 automatic | Fresh thread `01a13794-92a1-7332-9cd2-48f1851a03b5` received no plugin name, path or body in its request. It selected/read installed skill/resources, created only plan/handoff and exited 0. |
| N3 negative | Fresh thread `01a13794-9d2b-7cb1-a0a0-92b199ffbc69` received only a small code-change request. It did not activate/read the planner, changed only `greeting.py`, passed all four existing tests and exited 0. No planning artifacts. |

Both complete planning outputs were inspected against the source: one coherent feature with tests/usage, default results/order preserved, opt-in case-only matching, empty-query behavior in both modes, excluded persistence/network work, pending independent reviews and required Gate 2/Gate 3. Source/sentinel hashes were preserved. Neither planner implemented code, ran application tests or dispatched reviewers.

The behavioral runs used the same restricted per-invocation settings with memory injection/generation, hooks and unrelated connectors disabled. Ten non-model native probes established allowed fixture/skill reads and fixture writes, and denied memory, credentials, both source repositories, sibling-file reads/writes and networking. Every model invocation reused that exact verified permissions argument. The [official permissions documentation](https://learn.chatgpt.com/docs/permissions) and [configuration reference](https://learn.chatgpt.com/docs/config-file/config-reference) informed the setup. This proves the observed restricted context, not every ordinary host configuration.

Earlier unsuccessful attempts remain distinct: the ordinary-config explicit actor read persistent memory and was interrupted before creating artifacts; automatic approval review rejected the first discovery launch before execution over unrelated private-data access. After approval of the safer alternative, an explicit memory deny corrected a `:minimal` allowance found by the first probe. A config-only startup error was corrected before any replacement model ran. No failure was relabeled as a pass. Capture helpers were confined to local development evidence; no runner or enforcement machinery was added to the product.

### Durable evidence and preservation

Task 2/Task 3 evidence and essential native receipts are retained in the ordinary sibling directory `incremental-plan-plugin-evidence/2026-10-13-completion/`, outside the installable source tree. Inspection showed that the native installer copied the source tree, including `.git`, into its cache; Git ignore rules are therefore not treated as a packaging exclusion. Only concise results belong in repository documentation. Archives preserve member paths and bytes without following the collision-test symlink or extracting fixture Git directories. No Git initialization, branch or worktree operation was performed; the native cached metadata is not used as a development checkout.

| Local archive | SHA-256 | Verified regular files |
| --- | --- | --- |
| [task2-evidence.tar.gz](../../../../incremental-plan-plugin-evidence/2026-10-13-completion/task2-evidence.tar.gz) | `218c7846190711ff7e4928fe23e59fa048f192c79b168326a868395418af2d89` | 236 |
| [task3-evidence.tar.gz](../../../../incremental-plan-plugin-evidence/2026-10-13-completion/task3-evidence.tar.gz) | `35fb372d75563895792edceb5bdc2f6ec1d302398972c135e72e0f79fb3dc999` | 951 |
| [native-evidence.tar.gz](../../../../incremental-plan-plugin-evidence/2026-10-13-completion/native-evidence.tar.gz) | `ce10c33c6190bf19e421df6b1a25ba0aa3d44e8670596c30e03a25f0fb305ba1` | 60 |

The [archive index](../../../../incremental-plan-plugin-evidence/2026-10-13-completion/archive-index.json) records original roots, sizes and checks. Native evidence includes prompts, synthetic inputs/outputs, retained actions, exact settings, invocation/result/preservation receipts and unsuccessful-attempt dispositions. It excludes copied user configuration, credentials, npm caches and generated host schemas. Original native-session logs outside the task directories remain external provenance references; they were not copied wholesale. Historical absolute links retain their original meaning. Report any later missing external evidence precisely; do not reconstruct a pass.

The legacy plugin, its 359 recorded cache files, the legacy source's 333 recorded files and existing repository work were preserved. Only three existing repository documentation files change in this closeout; raw evidence stays outside the plugin source tree. Canonical design, guidance, ignore rules, accepted Task 1/Task 2 records and behavioral resources remain unchanged. Recovery is to disable only the new plugin, preserving its evidence/cache and all legacy entries; never overwrite concurrent configuration with an old backup. Uninstalling, deleting, publishing or replacing legacy work remains outside scope.

### Remaining limits and next use

Desktop UI activation, actual Ponytail invocation/repair, a genuinely absent-tool host, successful committed-predecessor ancestry and a simultaneous filesystem race remain unverified. The authorized substitute, native CLI observations, unborn dirty-repository tests and controlled inter-turn edits establish their stated narrower outcomes. These remain coverage limits, not silently completed checks.

A real user-source plan requires a selected source and destination; that is subsequent use of the implemented plugin. This task creates no extra desktop conversation or invented real-project requirements. A later fresh desktop invocation can add interface-specific evidence. No further implementation change is currently indicated.

A bounded independent documentation/evidence review by `completion_documentation_review` supported this Tasks 1–4 conclusion and verified the native receipts and archive identities. It found no additional material issue beyond the controller-identified archive-location/cached-metadata clarification applied above. This is review of the new completion claims, not a repeated review of unchanged product behavior.
