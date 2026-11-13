# Verification design

Use this guide to choose proportionate acceptance evidence and recovery limits. The [gate and review policy](../skills/incremental-plan/references/gates-and-reviews.md) owns approvals, reviewer independence, evidence applicability and retention; this guide adds no gate or execution permission.

## Consequences, reversibility and material questions

Identify material wrong behavior, who or what it affects, and whether recovery can repair the harm. A software rollback may restore code while leaving disclosed data, duplicate payments or lost records unresolved. Connect those consequences to the evidence and safeguards needed before the affected implementation or acceptance.

During preparation, before finalizing the concrete implementation design, assess whether authoritative requirements and accepted decisions sufficiently define the selected increment's observable behavior. For standalone QA, assess the selected verification work and the product expectations it needs. Examine relevant interactions among affected actors, access boundaries, workflows, state transitions and consequential failure or recovery conditions. Identify omissions, contradictions and unsupported assumptions that leave a material product decision unresolved, including behavior the source does not explicitly mention.

First check applicable requirements, decisions and contracts, and resolve factual uncertainty through bounded inspection. For unresolved product choices materially affecting behavior, security, compatibility, recovery or acceptance, name the decision, its owner, consequence and affected work; ask concise, contextual questions with meaningful alternatives when useful. Consolidate related questions, reuse existing answers and keep only dependent work blocked. Nonprejudicial drafting and independent eligible work may continue under existing authority; a labeled assumption cannot clear dependent implementation.

Do not invent product semantics, financial rules, recovery guarantees or specialist conclusions. Existing implementation behavior, customary UX and assumptions do not establish an unspecified requirement; code can support preserving behavior when authoritative requirements call for that preservation. Routine technical choices remain with the executor within the accepted contract. Preserve applicable security/privacy, accessibility, migration, runtime, human and expert obligations.

Limit discovery to the selected work and concrete dependencies needed for its acceptance or safe intermediate result. Do not introduce hypothetical features, require unrelated future decisions or split/defer coupled work to evade a missing decision. Stop when behavior and acceptance are sufficiently specified and no identified consequential product question remains unresolved; this is not an assurance that every possible omission has been found. Revisit affected reasoning when relevant evidence or scope changes. Preserve decisions, their actual source/reference and affected scope in existing plan and handoff fields.

Keep this assessment in existing acceptance/recovery fields. A spelling-only edit may need a content/diff check; it does not need a risk register, mutation framework or live environment. The consequence and unresolved contract determine the depth, with no universal score or technique quota.

## Challenge case selection before finalizing

Before freezing a plan/QA candidate, translate material source outcomes into distinguishable cases, not only coverage categories. Inspect consequential choices, boundaries, state transitions, rejection/no-op paths, interruption/recovery and interacting requirements where applicable. Showing an approval menu does not demonstrate cancellation or separate creation; a successful update does not prove that unchanged input avoids writes. Select observable assertions for materially different outcomes without requiring every possible path or combination.

Map those cases to existing checks or proposed verification with independent expectations, feature/global owners, timing and required evidence. Explain significant omissions, uncertainty and accepted deferrals in existing coverage/readiness fields, including consequence, owner and needed evidence or decision. An untested source-required outcome remains an affected readiness gap; do not silently recast it as an optional improvement or let a scenario budget erase it. Group cases only when their assertions still distinguish the relevant failures.

When human code inspection is limited or not expected, record that material assurance assumption and identify the behavioral, security and operational evidence the plan actually relies on. Tests must assert source-derived outcomes independently of reviewer confidence or agent agreement. This assumption waives no required independent review, expert assessment or release decision and supplies no guarantee of safe release.

## Independent expectations and test sensitivity

First derive material observable outcomes from the selected requirements, accepted examples and amendments, before relying on current implementation or existing assertion values. Record consequential unknowns rather than filling them from code. Then inspect implementation, interfaces, fixtures, tooling and actual assertions to find useful coverage, real execution boundaries and gaps. This staged approach permits code inspection; it does not require a permanently blind author.

For each material case or coherent group, make setup/input, action, expected observable outcome or relation, supporting source and relevant wrong behavior reviewable in the existing verification fields. Use a justified invariant, permitted outcome set or reference when literal constants are inappropriate. When requirements interact, choose a discriminating combined example: for a search contract preserving every matching record in input order, give IDs `[a1,b,a2]` titles `['red oak','red pine','red oak']`, search `red`, and expect IDs `[a1,b,a2]`. This catches duplicate loss and title grouping; counts or title sets do not. Include source-required original-object identity; when empty-query behavior and index reuse are also required, check both empty and matching nonempty queries against the same reused index.

A green summary or an expectation recomputed by the implementation's algorithm can share its mistake. Label expectations derived only from existing behavior as **characterization**: useful for preserving a refactor, insufficient to decide a changed or unspecified rule. A second helper, reference implementation or reviewer is independent only to the extent that the disputed expectation has independent justification. Inspect actual assertions and failure paths after establishing that basis. Prefer readable parameterized cases or structured scenarios using existing facilities where helpful; do not force stateful journeys into tables or introduce a custom DSL.

For a material proposed change, distinguish its approved intended effects from behavior that must remain true, and name a plausible regression specific to that change. Where useful, plan a small check expected to pass on an identified baseline and fail on a faulty candidate for the preserved behavior. A difference is only a candidate defect until assessed against the approved contract, including any authorized amendment. If no usable baseline or comparable setup exists, use independent contract-derived checks and record the missing comparison. Proposed comparisons are not observed results.

When research materially supports a decision or expected result, apply the shared [research-dependent assessment](../skills/incremental-plan/references/gates-and-reviews.md#research-dependent-decisions). Carry the source basis, applicability, limitations and unresolved gaps into these existing verification fields; a cited finding alone is not an acceptance threshold.

Before changing expectations, broadening matchers/tolerances, updating snapshots, skipping/removing cases, changing mock behavior or accepting a green retry, assess the mismatch under the evidence rule below. Review the semantic effect of fixtures, comparison helpers, discovery, runners and CI error handling as well as assertion bodies. Do not discard a generated test merely because the current product fails it or copy actual output into its expected value without a source-based justification. Preserve useful diagnostics. A genuine test correction within the agreed contract needs no new approval; a material contract change retains its decision boundary and must link to the actual amendment. Correctness of the amended rule still needs meaningful assertions.

Challenge consequential checks with a plausible wrong result that could still pass. When detection is unestablished and material, select the smallest known-bad control, failing regression or targeted mutation, with a valid control or applicable equivalent evidence. The valid subject must pass and the faulty subject must fail for the intended reason; an unrelated crash establishes neither. Protect original artifacts and use disposable controls. For example, archive/folder byte equality detects stale archive content but misses a forbidden internal document copied into both; allowed contents need an independent contract-derived expectation. Prefer existing tooling and bounded controls over a new framework; retain untested sensitivity as a limitation.

For each executed check, compare its observed outcome and relevant diagnostics with the independently justified expectation. For a material mismatch, retain the smallest reproducing input, relevant baseline/candidate identities, expected and observed behavior, failure diagnostics and the supporting requirement; identify missing evidence. A mismatch requires evidence to distinguish an implementation defect, an incorrect or obsolete plan/check, and an environment or execution failure; the cause can remain unresolved or involve more than one. Preserve the actual result and its limits. Do not weaken an expectation, assume an environment explanation, or report success merely to continue. Corrections within approved scope retain their existing authority; changing a material contract or obtaining missing action permission requires the user's decision. Reuse still-applicable results and rerun only checks whose relevant inputs or evidence need renewal under the gate policy.

## Effective execution and faithful observations

When the test path or checking machinery is new, changed, unproven or material to acceptance, plan evidence for the whole checking path:

- The intended cases are discovered/selected and execute against the intended candidate, including relevant built artifacts and imports.
- Setup reaches the required behavior and assertions complete, including awaited asynchronous and exception paths. A negative case rejects the intended violation, not just an unrelated error.
- Comparators, snapshots and matchers preserve contract-relevant order, multiplicity, precision, fields and side effects. Sorting, rounding or filtering is legitimate only where the source makes that distinction irrelevant.
- Outcomes propagate to the runner and accepting workflow; a wrapper or CI setting must not hide a required failure.

A passing empty suite, an unreached assertion or a setup crash supplies no evidence for its claimed behavior. Reuse applicable execution evidence for unchanged checks; this condition does not demand fresh harness calibration for every low-risk test. Plans specify this evidence for an authorized executor and do not run the target themselves.

## Portable debugging

For a reported bug, unexpected failure or unexplained mismatch during authorized execution, investigate before correcting. Expected TDD RED for the intended missing behavior is not itself a debugging incident; setup or unrelated failures are not that RED. Reuse applicable diagnosis and scale further investigation to uncertainty and consequence. The planner exports this procedure; only the authorized executor performs it.

1. Preserve the expected and observed behavior, supporting requirement, relevant candidate/environment, diagnostics and smallest useful reproduction under the mismatch policy above. If reproduction is intermittent or unavailable, record that limit and gather bounded evidence rather than inventing a cause.
2. Inspect relevant changes and working examples; trace the failing value or behavior through its actual producer/consumer boundaries to the owning source. Use existing evidence first. Any additional diagnostic action must be permitted and proportionate: prefer synthetic inputs, minimal observations and redacted records over secrets, private payloads or broad environment dumps. Debugging grants no external or production access.
3. State a specific hypothesis and its evidence, then use the smallest discriminating experiment before layering fixes. Compare the result with the prediction; retain uncertainty or mixed causes. If unsuccessful remedies share an unverified premise, test that premise before relying on it again. Repeated failures warrant reassessment, not an automatic architecture verdict or redesign.
4. Apply the smallest adequate correction at the owning source within scope, using [test-driven implementation](#test-driven-implementation) or its justified alternate verification. Verify the original failure and relevant regressions; never weaken an assertion merely to pass. Contract changes and missing permissions retain their existing decision stops.

Return concise actual hypothesis/experiment/result, correction and verification evidence, candidate correspondence and remaining limits in existing progress/evidence fields. Preserve work, applicable proof and the existing [correction sequence](../skills/incremental-plan/references/gates-and-reviews.md#bounded-correction-sequences); changing tools or resuming does not reset it. Evidence-only diagnosis and expected TDD add no new counter; substantive repair remains subject to the existing allowance. An unresolved required failure remains pending even if optional tooling is unavailable.

This procedure is usable without Superpowers. The [optional debugging policy](../skills/incremental-plan/references/gates-and-reviews.md#optional-superpowers-debugging) selects a compatible aid; neither route authorizes denied diagnostics, destructive restarts or invented historical evidence.

## Test-driven implementation

For testable new or changed application behavior and bug fixes, use TDD by default within each coherent feature increment. The planner specifies the applicable method and expected evidence; only an authorized executor runs it. Use the target's useful existing tests and tools, with expectations justified independently of the implementation:

1. Select or add a small test for the next required behavior. Run it before the corresponding implementation and confirm it fails for the intended missing or incorrect behavior. Setup, infrastructure or unrelated failures do not establish that RED condition. If the behavior already passes, inspect whether any change is needed instead of manufacturing failure.
2. Implement the smallest coherent change that makes that test pass, then verify the result. Repeat for the remaining behavior; keep tests with their owning feature, not in a later testing increment.
3. Refactor where useful while keeping the relevant checks green. Run focused checks during changes and the full relevant verification on settled inputs. TDD does not replace combined-journey checks, independent reviews or required human/expert evidence.

For behavior-preserving refactoring, establish adequate passing coverage first and add characterization checks where needed; no artificial failing test is required for unchanged behavior. Documentation/metadata, exploratory and visual work use appropriate static, experimental or human evidence where test-first is unsuitable. Record a material exception's reason, alternative checks and remaining limits in existing acceptance/evidence fields. A missing test prerequisite remains a real preparation/evidence gap, not an automatic exception. Preserve stricter source/target requirements and direct scoped decisions about TDD.

Return concise actual RED/GREEN commands, relevant outcomes, intended failure and candidate correspondence, or the justified alternate verification route. Proposed tests and retrospective descriptions are not observed test-first evidence. On resumption or when code already exists, preserve the work and applicable proof, disclose missing historical RED evidence and verify the remaining behavior without deleting or rebuilding completed work to manufacture a sequence. Never weaken an assertion merely to obtain GREEN; use the mismatch assessment above.

This baseline applies with or without Superpowers. The [optional selection policy](../skills/incremental-plan/references/gates-and-reviews.md#optional-superpowers-tdd) chooses a compatible execution aid; it does not change required verification or grant execution authority.

## Conditional checks and metric limits

Start with the target's useful existing tooling, assertions and evidence; identify what is missing before proposing more. Choose the smallest adequate checks for the behavior and its consequences: local deterministic checks for isolated logic, integration/contract or end-to-end evidence for connected boundaries, and security, property/fuzz, performance, visual/accessibility, exploratory, human, migration/recovery or operational checks when the particular risk warrants them. Preserve required specialist evidence; do not impose every technique on every change.

Ground commands, imports/APIs, fixtures and dependencies in the actual repository and version-applicable documentation under the existing [stack revalidation](../skills/incremental-plan/references/gates-and-reviews.md#documentation-and-stack-revalidation) procedure. Plan-only commands/setup stay provisional; missing helpers or resources remain prerequisites to resolve, not invented executable checks or results.

When checks touch shared globals, environment variables, timers, random inputs, storage, threads or external resources, identify the relevant control and restoration. Prefer existing scoped fixtures and event/state-based waits over arbitrary delays; preserve meaningful real-boundary behavior when controlling time or concurrency. During authorized execution run affected tests together. Investigate ordering or repeat behavior when the change or observations justify it, without a blanket random-order framework or repetition quota. A later passing retry does not resolve an earlier unexplained failure. Skipping or quarantining required evidence leaves its gap visible under the existing decision rules.

Prefer observable public behavior and required effects over private method names, CSS classes, exact DOM structure or incidental style values. Preserve explicit visual/accessibility requirements and appropriate human checks. Combine redundant cases only if their distinct protection survives; some duplication can be clearer than another helper abstraction.

Name the necessary candidate, environment/data, expected outcome and evidence limits. For consequential cross-boundary claims, state which dependencies are real or simulated and what remains unverified. Keep useful fakes, adding a narrow real-boundary or contract check when the risk requires it; a mock cannot prove an unexercised boundary. Coverage and quality metrics identify gaps but do not prove correctness or replace meaningful assertions, independent review or responsible human decisions. A mutation score cannot establish a correct oracle, omitted functionality or production fidelity; inspect relevant exclusions, uncovered behavior, equivalent survivors and timeout/setup failures before interpreting it. Add no universal score threshold. Static package checks establish structure, not model behavior, runtime outcomes or installed usability. Planning a check authorizes no execution, installation, provider use or other separate action.

Trace required user-facing effects to the boundary that produces them. A formatter returning text does not establish source-required printed output, just as a computed value does not establish persistence or provider confirmation. If the selected project lacks that effect, retain it as a known implementation/evidence gap; do not recast an explicit source obligation as optional new scope requiring the user to request it again.

## Combined evidence and residual owners

For critical behavior spanning components or increments, assign an owning increment or global obligation, independently expected outcome, relevant combined candidate/environment and required evidence. Keep tests with the feature behavior they protect; component passes cannot establish a combined journey they never exercise. Reuse applicable evidence and renew only the affected proof under the gate policy.

Plan final correspondence checks on the actual delivered candidate, including built/packaged/extracted output when relevant. Completion claims, evidence references, usable links and genuine remaining limits must agree after the last relevant implementation, packaging or evidence update. Name this timing and its owner in existing verification fields; the [gate policy](../skills/incremental-plan/references/gates-and-reviews.md#execution-discipline-carried-by-a-handoff) governs review/acceptance sequencing and later evidence renewal.

At result review and closure, distinguish demonstrated behavior from important untested conditions and outstanding obligations, with owners and the evidence or decision still needed. Missing mandatory combined evidence remains a gap. When release is in scope, identify its responsible human decision-maker and applicable operational, specialist and recovery evidence. Implementation-result acceptance alone establishes neither release readiness, separate certification nor legal assurance.

## Selecting checks for a QA plan

Use relevant rows, not a checklist quota. Inspect the target's actual tooling before recommending changes; a material tool/cost/environment choice needs the user. An early plan may describe pending setup or provisional commands without claiming execution readiness.

| Behavior or consequence | Useful evidence when warranted |
| --- | --- |
| Isolated deterministic logic | Source-derived examples, boundaries and meaningful failure assertions; property checks for a real invariant or fuzzing for a consequential input space. |
| Parsing, storage, protocols or component boundaries | Contract/integration checks for invalid inputs, persistence, ordering, errors and recovery; independent expected values rather than the implementation's own calculation. |
| User journey spanning components/providers | End-to-end or sandbox evidence of the actual causal journey, matching displayed/stored/provider outcomes; mocks cover only their exercised boundary. |
| Security/privacy or irreversible effects | Abuse/permission/data-handling and recovery checks plus appropriate expert/human review; rollback cannot retract disclosure, duplicate financial effects or lost records. |
| Performance/load | Source-derived workload, environment/data, thresholds and bounded measurements; do not invent universal targets. |
| Visual/accessibility/interaction | Relevant reference, viewport/input/error/keyboard and assistive behavior checks, with human/expert inspection where automation is insufficient. |
| Migration/operations | Compatibility, preserved data, interruption, rollback/recovery and operational evidence for the actual changed candidate/environment. |

Explain significant omissions in relation to the target. A local sum does not warrant provider setup; a spelling correction usually needs a content check. Coverage can guide inspection but does not prove duplicate preservation, real command integration or recovery. Keep ordinary test work with its owning feature and separate infrastructure only for evidenced shared needs.

## Conditional certification design

Assess target policy first, then any material assurance boundary beyond ordinary implementation checks. Policy-required certification retains its gate. Otherwise propose a separately reviewable item only when warranted; a new mandatory gate awaits the user's material decision. Do not create blanket per-feature certification, an approval engine or registry. A justified no-separate-certification sentence is adequate.

Warranted work follows its **actual implementation prerequisite**, not a similarly named card. Identify the exact subject/version, controlling contract/configuration/dependencies and environment, and correspondence to inspectable implementation evidence. Specify independent causal outcomes and meaningful failure, interruption, cleanup and safe recovery evidence, owners, required human/expert decision and closure authority. Shared journey evidence needs distinct assertions for each certified subject: a booking confirmation without webhook signature/replay checks certifies neither webhooks nor a changed booking contract.

At early design, name setup unknowns and owners honestly. Before a concrete certification handoff can be execution-ready, supply a usable runbook:

1. Dated current official setup for the chosen provider/tool/version, or inspectable evidence that no human setup is needed. Missing/conflicting documentation keeps affected setup pending.
2. Account/tier/resource owners and least-privilege roles; credential **metadata only** (names, scopes, lifetime, protected storage), never values; domains, callbacks and allowlists.
3. Synthetic data, candidate/configuration/environment identity and prerequisite preflight; bounded polling/timeouts, quotas/spend and retention limits with owners rather than invented universal numbers.
4. Ordered execution and observation steps tied to independent expected outcomes; separate action/approval checkpoints for actual provider, credential, data, expert/human and production effects.
5. Step-by-step test-resource cleanup, credential revocation and interrupted/failure recovery, with required final safe-state evidence and ownership. Source-required cleanup proof is part of acceptance, distinct from optional evidence storage.

The plan describes these actions; it performs none of them. Unknown setup is not readiness, and a proposed runbook is not observed proof. Existing target conventions suffice; do not introduce a new digest/status service.

After results, retain historically accepted outcomes and valid unaffected proof. Renew affected evidence when subject, contract, configuration, dependencies, environment, lifecycle or recovery changes; a changed name or green status alone establishes no correspondence. Closure requires actual applicable evidence and the target's real acceptance decision under the shared gate policy. Recognize satisfied obligations narrowly and permit only otherwise eligible dependent preparation; unrelated certification/release gates remain. Optional storage disposition alone does not reopen proven scope, while missing mandatory proof and required cleanup remain unresolved.
