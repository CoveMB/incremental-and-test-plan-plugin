# Increment commit checkpoints implementation plan

Status: implementation independently reviewed, corrected and statically verified for MR delivery. Live-model and native-host acceptance remain untested.

## Goal and scope

Make the existing conditional commit checkpoint visible in generated incremental plans and distinguish it from publication. Deliver one coherent instruction-package increment, keeping the planning skill read-only with respect to product execution and Git.

Baseline: freshly fetched `origin/main` at `a83a58bd5e1c5458692a8c8e4e057fd953859819` on 2026-11-04, matching clean local `main`. Implementation branch: `increment-commit-checkpoints`. Recheck the checkout and comparison before writes/publication; refresh main before MR delivery and reconcile any relevant drift without discarding work.

The user requested independent plan review and corrections, implementation on latest main, independent implementation review and repairs, a final owner review, then an open MR. Implement in this chat. This authorizes bounded commits/push and MR creation to the verified existing repository remote, but no merge, installation, live-model evaluation, provider request/reply, destructive cleanup or unrelated work.

## Required behavior

- Carry a conditional checkpoint after implementation, required verification, independent reports, material repairs with affected rechecks/reviews, and applicable Gate 3 acceptance or scoped bypass/delegated decision. Preserve every existing review scope and gate; checkpointing adds no acceptance gate or independent-review assignment.
- When Git commits are applicable and authorized, record the settled increment in a commit and retain its revision in existing candidate/evidence fields. Verify that the committed scope corresponds to the reviewed candidate; a hash alone is not verification. Preserve unrelated staged, unstaged and untracked work. Reconcile a content-changing hook or other candidate drift before claiming correspondence.
- Reuse an existing commit that already represents the settled increment. Do not create empty commits, enforce exactly one commit, forbid earlier authorized commits, or imply permission to amend, squash or rewrite history. Later reviewed repairs can use additional authorized commits.
- Treat local commit, push and MR authority separately. A commit-only grant permits the local checkpoint without publication. Gate bypass or generated planning text grants no Git authority. Preserve narrower grants, revocation and selected publication/stack rules.
- Preserve non-Git, Git-unborn and accepted-uncommitted workflows. Do not initialize Git or force commits. When target rules require committed ancestry, missing authority or correspondence remains a precise blocker for affected dependent work; otherwise use the existing accepted-candidate evidence rules. A failed checkpoint is not a completed commit.
- Keep checkpoint status distinct from acceptance and dependent eligibility. Do not add a global commit prerequisite or alter required CI/provider settlement for published increments. Apply on authorized creation/revision/continuation, retaining accepted history and prompt-only write boundaries.
- Preserve package identity/version, two entrypoints, discovery metadata/implicit invocation policy and the twelve-file runtime selection. Add no runtime, dependency, integration, ledger, new document type or mandatory standalone-QA workflow.

## Implementation

1. In `skills/incremental-plan/references/gates-and-reviews.md`, clarify the lifecycle's After result step and own the bounded checkpoint rule there, adjacent to existing lifecycle/authority policy. Refer to existing predecessor/evidence and publication obligations rather than duplicating them.
2. In `skills/incremental-plan/assets/plan-template.md`, expose the checkpoint through the existing Gates / review scope and candidate/evidence fields. Keep shared policy in its canonical owner; export enough resolved instructions that the generated plan does not depend on access to package-relative links. Add no new table or ledger.
3. In `skills/incremental-plan/assets/handoff-template.md`, align the existing publication section with the canonical rule. Export local checkpoint and separately authorized publication duties as self-contained executor instructions, preserving existing MR/native-stack, CI and provider sequencing.
4. In `docs/usage.md`, add a short explanation beside the existing approval sequence, linking the canonical policy. Keep the README, entrypoint, orchestration launcher, standalone QA and manifests unchanged unless an evidenced routing/consistency defect makes a directly related edit necessary.
5. In `tests/scenarios.md`, extend the existing C20 orchestration raw variants and evaluator-only expectations for the cases below. Use synthetic states, separate actors' raw inputs from grading expectations, and reuse existing uncommitted/authority fixtures. Do not change live-evaluation selections or run actors under this request.

## Acceptance and verification

| Case | Expected instructions or disposition |
| --- | --- |
| Accepted Git increment with commit permission | Checkpoint the exact reviewed scope; retain revision/candidate correspondence |
| Commit permission without push/MR permission | Local commit only; publication remains unperformed |
| Pending review, material finding, failed check or missing result decision | Resolve the specific condition before the accepted-result checkpoint |
| Absent/revoked Git permission | Preserve work and authority boundary; no commit or inferred publication |
| Non-Git or permitted accepted-uncommitted predecessor | Inspectable candidate evidence; no initialization or forced commit |
| Target requires committed ancestry | Missing ancestry/authority blocks affected dependent work, not unrelated authorized work |
| Settled candidate already committed | Reuse the actual matching revision, with no empty duplicate commit |
| Unrelated staged/dirty work, or changed committed content | Preserve unrelated work; reconcile mismatches and renew affected evidence |
| Later provider finding or failed/interrupted commit | Retain actual status, repair/reconcile within authority, no fabricated completion or automatic history rewrite |
| QA-on, QA-excluded, old-plan continuation and prompt-only request | Consistent portable checkpoint duties, preserved history and existing write boundaries |

Run the commands and package-contract checks documented in `docs/development.md#static-checks`, with RTK command prefixes: both available Skill Creator validators, parsed manifests/frontmatter, resource/anchor closure, unchanged catalog/description lengths and whitespace. Use focused checks while editing and the full relevant checks once on the settled candidate; repeat only affected checks after changed inputs or new evidence.

Inspect the documented allowlisted export's actual staged/archive/extracted files for exact membership, byte correspondence, private/local material and undeclared dependencies. Exercise the documented missing-resource, forbidden-member and changed-extracted-byte controls on synthetic copies. Keep temporary evidence outside tracked source, with underlying exit status and usable paths. Do not add automated tests that merely match prose. Scenario definitions and desk review establish neither live-model behavior nor native activation.

The supporting Git sources inspected on 2026-11-04 are [logical commit boundaries](https://git-scm.com/docs/SubmittingPatches) and [staged-content commit semantics](https://git-scm.com/docs/git-commit). They support coherent commits and precise content inspection; repository authority/gate policy determines when actions are permitted.

## Review and delivery

Before implementation, freeze this plan with the current sources and obtain three distinct fresh-context read-only reports: requirements/source fidelity; architecture/simplicity/compatibility; verification quality. Collect all dispatched reports, validate findings, make material in-scope corrections, and renew only affected scopes before readiness.

After implementation and checks, perform the owner self-review before independent dispatch. Obtain the same three independent scopes against the complete frozen actual change; reviewers stay read-only. Resolve material findings, renew affected checks/reviews, then perform the user's requested final owner review. Do not substitute prior recommendation reviews or static checks for these reports.

Completion requires plan/result review reconciliation, no unresolved material findings, applicable deterministic/package evidence and final owner review. Then commit/push only the reviewed candidate and create one open MR against verified current main. Leave merging and live/native acceptance separate. Recovery uses bounded forward corrections; never reset, stash, discard or amend user work.

## Progress

- Three distinct fresh-context read-only plan reports covered requirements/source fidelity, architecture/simplicity/compatibility and verification quality against candidate SHA-256 `c68700a1b2900011762198bb02c2cdee2da9acb42279fa07a384dfb7332b8467`. All reported no material improvements recommended. The owner reconciled their source evidence; no plan correction was required.
- Implemented the canonical checkpoint, card visibility, portable local-commit/publication distinction, usage explanation and bounded C20 scenario variants with separate evaluator expectations. Existing entrypoint/launcher routing already reaches these owners; no metadata or standalone-QA changes were needed.
- Both documented Skill Creator validations and whitespace checks passed (exit 0). The package check passed (exit 0): unchanged two-entrypoint catalog and description lengths (351 and 290 characters), 134 runtime resource/anchor links, 21 documentation/scenario links, and the twelve-file staged/archive/extracted export. Three synthetic controls rejected a missing resource, a matching forbidden staging/archive member and changed extracted bytes. Temporary evidence is retained outside tracked source. These checks do not establish model behavior or native activation.
- Initial owner self-review examined the complete implementation against the required behavior, authority and prerequisite exceptions, generated-output portability, documentation, scenarios, package scope and unnecessary duplication. This preceded independent implementation review.
- Independent implementation source-fidelity and architecture reviews found no material issues on the frozen candidate. Verification review found one material scenario-contract conflict: a continuation case requested edits while its controlling restrictions prohibited them. Correction batch 1 separates an explicitly writable selected-plan/handoff subvariant from prompt-only continuation and aligns its raw permissions and evaluator expectations. Product/package instructions remained unchanged. Affected resource/anchor and whitespace checks passed (exit 0), and targeted verification re-review confirmed the finding resolved with no directly introduced material defect. Unaffected source/architecture reports and package evidence remain applicable.
- Final owner review followed all independent reports and the targeted re-review. The actual change was reconciled against every required behavior and acceptance case, source/consumer ownership, permission/history boundaries, package contents and evidence limits. No unresolved material findings remain. Main was fetched again and remained at the baseline above. Only this administrative status/progress record changed after the final reviewed candidate; tested runtime and scenario inputs remain identical.
