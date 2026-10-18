# Verification design

Use this guide to choose proportionate acceptance evidence and recovery limits. The [gate and review policy](../skills/incremental-plan/references/gates-and-reviews.md) owns approvals, reviewer independence, evidence applicability and retention; this guide adds no gate or execution permission.

## Consequences, reversibility and material questions

Identify material wrong behavior, who or what it affects, and whether recovery can repair the harm. A software rollback may restore code while leaving disclosed data, duplicate payments or lost records unresolved. Connect those consequences to the evidence and safeguards needed before the affected implementation or acceptance.

When approved sources leave consequential behavior unspecified, name the missing decision, its owner and the affected work; ask the user before implementing that choice. Do not invent financial rules, recovery guarantees or specialist conclusions. Preserve applicable security/privacy, accessibility, migration, runtime, human and expert obligations.

Keep this assessment in existing acceptance/recovery fields. A spelling-only edit may need a content/diff check; it does not need a risk register, mutation framework or live environment. The consequence and unresolved contract determine the depth, with no universal score or technique quota.

## Independent expectations and test sensitivity

Ground important expected results in approved requirements, trusted examples or a justified reference independent of the implementation under test. Name the basis and the material wrong behavior a check should detect. For example, when separate records with equal titles must survive a search, asserting their ordered IDs distinguishes preservation from a deduplicating implementation; checking only distinct titles does not.

Inspect actual assertions and relevant failure paths. A green summary or an expected value recomputed by the implementation's own algorithm can hide a shared wrong assumption. Legacy parity can establish preservation, but cannot establish correctness of an intentionally changed rule. Independent reviewers must challenge these assumptions too; separate actors can still repeat the same mistake.

Review reduced assertions, broader tolerances, skipped/removed cases and excessive mocking against the approved contract. Require a concrete justification for changed tests. A genuine authorized contract amendment may warrant changed expectations; retain its scope and decision rather than treating every test change as forbidden. Where a material sensitivity gap warrants it, propose a failing regression demonstration or targeted mutation and the incorrect behavior it exposes. Those techniques are conditional, and proposed demonstrations are not observed RED/GREEN evidence.

## Conditional checks and metric limits

Start with the target's useful existing tooling, assertions and evidence; identify what is missing before proposing more. Choose the smallest adequate checks for the behavior and its consequences: local deterministic checks for isolated logic, integration/contract or end-to-end evidence for connected boundaries, and security, property/fuzz, performance, visual/accessibility, exploratory, human, migration/recovery or operational checks when the particular risk warrants them. Preserve required specialist evidence; do not impose every technique on every change.

Name the necessary candidate, environment/data, expected outcome and evidence limits. Mocks cannot demonstrate an unexercised real boundary. Coverage and quality metrics can identify gaps but cannot prove correctness or replace meaningful assertions, independent review or the responsible human decision. Static package checks establish structure, not model behavior, runtime outcomes or installed usability. Planning a check authorizes no execution, installation, provider use or other separate action.

Trace required user-facing effects to the boundary that produces them. A formatter returning text does not establish source-required printed output, just as a computed value does not establish persistence or provider confirmation. If the selected project lacks that effect, retain it as a known implementation/evidence gap; do not recast an explicit source obligation as optional new scope requiring the user to request it again.

## Combined evidence and residual owners

For critical behavior spanning components or increments, assign an owning increment or global obligation, independently expected outcome, relevant combined candidate/environment and required evidence. Keep tests with the feature behavior they protect; component passes cannot establish a combined journey they never exercise. Reuse applicable evidence and renew only the affected proof under the gate policy.

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
