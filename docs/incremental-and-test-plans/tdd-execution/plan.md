# Portable TDD and optional Superpowers implementation plan

Status: implementation complete, independently reviewed and verified for MR delivery. Live-model and native acceptance remain untested.

## Goal and scope

Make test-driven development the default for testable behavior changes in generated implementation handoffs, whether or not Superpowers is available. Prefer the compatible, permitted Superpowers TDD skill when exposed by the receiving host; otherwise continue with a complete local procedure. Planning remains planning-only.

Deliver one coherent instruction-package change. Keep coupled policy, templates, documentation and scenario definitions together. Do not add an execution engine, dependency, integration framework, new gate, ledger or skill. Preserve the two entrypoints, discovery metadata, package identity/version, authorization boundaries and independent review scopes.

Baseline: local `main` at `c3e07290b48bbc468606a290ea8e7773b1ef60a8`, clean and equal to freshly fetched `origin/main` on 2026-11-04. Implementation branch: `tdd-execution`. Recheck before edits and publication; preserve unrelated changes.

## Selected approach

The shared verification guide owns one TDD baseline, including applicability, exceptions and evidence. The gate policy owns executor selection of optional Superpowers and preservation of gates/permissions. Host compatibility owns discovery and invocation identity. Generated handoffs export sufficient plain-language instructions to work without access to either plugin.

Alternatives considered: requiring Superpowers conflicts with portability; using TDD only as a fallback makes the development standard depend on the installed tool; importing the entire Superpowers execution workflow changes orchestration and review semantics unnecessarily. Select only its TDD skill when compatible, within the shared baseline and controlling instructions.

Research basis: the upstream [TDD skill](https://github.com/obra/superpowers/blob/main/skills/test-driven-development/SKILL.md) describes observed red/green/refactor, and [Martin Fowler's TDD account](https://martinfowler.com/bliki/TestDrivenDevelopment.html) explains the small repeating cycle. Current upstream documentation was retrieved on 2026-11-04; the locally exposed Superpowers 7.0.1 was inspected. Neither source establishes the version or behavior in a future receiver. Preserve existing adaptation provenance; identify any newly adapted source separately rather than relabeling the older adaptation.

## Required behavior

- For testable new or changed application behavior and bug fixes, select a meaningful source-derived test, observe it fail for the intended missing/incorrect behavior, implement the smallest coherent change, then refactor as useful with tests remaining green. Reuse adequate existing tests; if the expected behavior already passes, inspect whether any change is needed rather than manufacturing failure.
- Assertions and expected results remain independent of the implementation. Infrastructure, setup or unrelated failures do not prove the intended RED condition. Keep tests and implementation within the same feature increment; run focused checks during changes and full relevant checks on settled inputs.
- For behavior-preserving refactoring, establish adequate passing coverage and add characterization checks where needed. Documentation/metadata, exploratory and visual work use appropriate validation rather than artificial prose-matching tests. Record a material exception's reason and alternative evidence in existing fields; preserve stricter controlling requirements and material-decision stops.
- Record actual concise RED/GREEN commands, relevant outcomes and applicability, or the justified alternate verification route. A proposed test, green label or retrospective assertion is not observed test-first evidence. Preserve existing and accepted work; never delete or rebuild it to fabricate a TDD history.
- At authorized implementation preparation, the receiver checks its own exposed, accessible and permitted TDD skill and actual-version fit. A generator's observation is not receiver proof. Use the verified identity when compatible. Missing, disabled, inaccessible, excluded, unknown or incompatible optional tooling selects the local procedure without an installation request, extra approval or dependency hold. Record the actual reason without mislabeling restriction as absence.
- A tool exclusion is not a TDD exclusion. Follow direct scoped instructions about TDD itself. Optional-tool fallback cannot waive mandatory tests, evidence, reviews or permissions. If a controlling source explicitly mandates a named tool with no substitute, surface that separate conflict rather than inventing a waiver.
- Selecting the TDD skill does not select Superpowers orchestration, subagent workflows, installation, Git actions or destructive cleanup. Preserve user work and apply controlling instructions to any incompatible upstream directions. Tool failure after partial work requires factual reconciliation and safe continuation, not replay of completed work.
- New handoffs and authorized revisions carry the policy prospectively for unfinished work, preserving accepted history and applicable evidence. Older prompt-only requests identify missing handoff duties and use existing reconciliation rules without editing saved artifacts. No forced migration or invented historical RED evidence.

## Implementation steps and owners

1. Update `references/verification-design.md` with the TDD baseline, proportionate applicability and evidence. Update `skills/incremental-plan/references/gates-and-reviews.md` to reference that owner from the lifecycle, define optional selection/fallback and align the existing Superpowers attribution wording. Update `references/host-compatibility.md` with verified-identity selection without universal slash/at syntax or host-version assumptions.
2. Export the applicable baseline, optional route and evidence into `skills/incremental-plan/assets/handoff-template.md` and `skills/test-design/assets/qa-plan-template.md`. Add only the necessary selection/evidence prompts to `skills/incremental-plan/assets/plan-template.md`; keep `skills/incremental-plan/assets/orchestration-prompt-template.md` a short launcher with a targeted duty/read trigger. Reuse existing acceptance, preparation and evidence fields. Adjust entrypoint bodies only if existing routing cannot reach the affected owners; preserve frontmatter byte-for-byte.
3. Update `README.md` and `docs/usage.md` to explain the default, exceptions and fully usable fallback, including explicit tool exclusion. Update `references/third-party-notices.md` only for accurate adaptation/optional-invocation claims; preserve its existing source identity and MIT notice. Add development-guide details only if source ownership or validation instructions actually change. No new runtime files or package manifest changes are expected.
4. Extend the existing self-contained execution scenarios in `tests/scenarios.md`, reusing fixtures and all three output modes. Keep raw actor inputs separate from evaluator expectations. Update live/native runbook references only if needed to make the new cases discoverable; do not imply execution or native acceptance.

## Verification and acceptance

Before implementation, obtain three distinct read-only plan reports: source fidelity, architecture/simplicity, and verification quality. Reconcile every report before edits; correct verified material findings and renew affected scopes. After implementation, repeat those independent scopes on one frozen candidate, correct findings and renew affected checks/reviews, then perform the requested final owner review before publication. Reviews are not live-model behavior evaluations.

Static checks use `docs/development.md#static-checks`: both Skill Creator validators, parsed manifests/frontmatter and identity checks, package resource/link/anchor closure and `git diff --check`. Confirm exactly two skills and unchanged discovery descriptions/lengths, metadata and invocation policy. Inspect the complete diff for privacy, stale consumers and unnecessary changes. Use the documented allowlisted export and inspect actual staged/archive/extracted contents before publication; preserve the twelve-file closure, avoid private/local paths and undeclared dependencies, and use the existing package contract controls. Temporary validation evidence stays outside tracked source.

Desk-check these distinct cases against the final instructions and scenario definitions:

| Case | Required outcome |
| --- | --- |
| Compatible skill exposed at receiver | Select only the verified TDD skill within the local policy; no extra workflow or permission |
| Missing, disabled, inaccessible or unknown availability | Continue with self-contained TDD and the honest reason, without setup or a new hold |
| Explicit tool exclusion or incompatible instructions | Use local TDD; preserve exclusions, restrictions and existing work |
| Planner and receiver inventories differ | Receiver evidence governs; planning performs no implementation invocation |
| Failure after partial work; already-passing behavior; resumed older work | Reconcile and reuse valid work/evidence; no fabricated RED or destructive restart |
| Feature/bug versus refactoring, docs, visual/exploratory work | Apply the appropriate test-first or alternate verification route |
| Failed mandatory tests or missing required evidence | Keep the real gap pending despite optional-tool fallback |
| Explicit mandatory named-tool/no-substitute source | Retain and surface the conflicting requirement, without silently weakening it |
| Incremental QA-on, QA-excluded and standalone QA | Each handoff is sufficient for a fresh receiver; output boundaries and gates remain intact |
| Prompt-only and authorized continuation | Respect write scope, preserve history, and reconcile only unfinished affected work |

Live-model scenarios and native installation/invocation are not authorized by this development/review request and are not completion claims for this change. Report them as untested; static checks and independent reviews establish source/package evidence only. No runtime tests should merely match instruction prose.

## Completion and recovery

Completion requires reconciled plan and implementation reviews, resolved material findings, relevant deterministic checks, the final owner review and one open MR to the verified existing remote. No merge, deployment, installation, review replies or unrelated configuration changes are included. The user requested this sequence, including implementation and MR creation; do not introduce another routine approval pause for the same scope.

If correction is needed, repair only this candidate's affected instructions and consumers while preserving unrelated work. No reset, discard, stash or deletion of existing work. Keep implementation and test claims honest; unresolved material design questions return to the user before affected changes.

## Review and implementation record

- Plan reviews: three distinct fresh-context read-only reports on 2026-11-04 covered source fidelity, architecture/simplicity/compatibility, and verification quality/evidence. Each reported no material improvements recommended. The owner reconciled the reports against the current sources; no plan corrections were required.
- Implementation: canonical baseline and optional selection, both portable handoffs, selection/evidence template prompts, user documentation, adaptation provenance and TD01–TD04 scenario definitions are updated. Existing entrypoint routing already reaches the canonical owners; both entrypoints and manifests remain byte-for-byte unchanged. The live runbook links the new cases without changing its authorized-call accounting.
- Static verification: both Skill Creator validators passed (exit 0); exactly two entrypoints retain description lengths 351 and 290 characters and unchanged metadata. The repository-owned export verified all twelve staged/archive/extracted files. Three synthetic controls correctly rejected a missing resource, forbidden matching folder/archive content and altered extracted bytes. All 115 runtime relative resource links/anchors and new documentation anchors passed; extracted privacy inspection and whitespace checks passed. The initial link-check helper misclassified the template's generated `handoff.md` link as a shipped resource and exited 1; a targeted corrected classification passed (exit 0), reusing successful export/control evidence without product changes.
- Initial owner source check: requirements, affected consumers, optional fallback, work preservation and dependency/package boundaries checked before independent result review. Live-model/native evidence remains untested.
- Independent result reviews: three distinct fresh-context read-only reports on the frozen 13-file candidate covered source fidelity, architecture/simplicity/compatibility, and verification quality/package evidence. Each verified the assigned candidate correspondence and reported no material improvements recommended. The owner reconciled all reports; no material implementation corrections were required.
- Final owner review: completed after all independent reports. Rechecked the whole change against the requested behavior, exceptions, output modes, authorization, continuation, package/privacy boundaries and evidence limits. All thirteen reviewed files and twelve tested runtime files still matched their recorded identities before this administrative completion update. No material improvements recommended.
- MR delivery: commit and publish this bounded candidate to the verified existing repository, leaving the MR open for human review. No merge or installed/native acceptance is implied.
