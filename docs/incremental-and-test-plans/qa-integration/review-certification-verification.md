# Certification amendment — independent verification-design review

Captured 2026-10-16 from `/root/certification_verification_review`, a fresh-context read-only assignment. The frozen candidate is the substantive prefix of [plan.md](plan.md) before its progress heading. Historical reviews were not supplied. Controller reconciliation: the positive continuation gap is supported by the Q19–Q22/C14/E06 definitions; corrected Q22 with an isolated fulfilled counterpart and concrete causal assertions. Source requirements, design rules, ownership, sequencing and permissions did not change. Targeted verification renewal confirmed the fix; no material findings remain. Both actual reports are retained below.

## Round 1 — actual reviewer report

Reviewer: `/root/certification_verification_review` — independent, read-only verification-quality review.

Inspected substantive plan SHA256 `7c202ab574360f65edf9d56c5cccbe41e3515d6c9c027d54427ed9ab9fca8e35`, handoff SHA256 `5636dcab64af5c858b305c32f927916167efc378962ee2d8bc6c04ab40e67970`, and amendment SHA256 `a55780e1a47e6d18f1233697c4fd821011de95d9a53eb1c2b1bc59a3da99c2a3`. Verified local `main` HEAD `68ad21a70b38c6cc77e5b549833074e6510ee687`; refs were not refreshed. Excluded administrative verdicts and previous reviews.

**One material finding:**

- **[P2] Add a fulfilled-certification continuation counterpart.** [Candidate lines 228–231](/private/tmp/incremental-qa-certification-review-20261016/candidate.md:228) exercise missing certification, pending setup, stale evidence and unresolved cleanup. Existing C14-certification and E06 likewise retain pending certification. None tests recognition of complete, applicable certification evidence and the target’s required direct decision. A planner that always leaves certification pending and blocks its dependent could satisfy these cases, despite the continuation and dependency/closure contract at candidate lines 64–69 and 171–178.

  **Smallest remedy:** extend Q19 or Q22 with an isolated counterpart supplying inspectable, exact-subject evidence for every target-required outcome, prerequisite correspondence and the required accessible decision. Assert that only the satisfied certification obligation closes and its otherwise eligible dependent can proceed; unrelated certification, release and action boundaries remain intact. Clearly label controller-seeded evidence and decisions as synthetic. This requires no provider execution or real registry mutation.

Otherwise, the proposed checks adequately distinguish conditional certification from universal machinery, mandatory target rules from optional proposals, exclusion from waiver, pending setup from evidenced no-setup, affected renewal from blanket reruns, and implementation acceptance from certification and storage disposition.

Sources inspected: raw request/review inputs/amendment; canonical planner, gate policy and both templates; README validation guidance; applicable C/E scenario definitions; and the amendment’s bounded Egeria certification/governance ranges.

No files were edited, tests or validators run, providers called, Git mutated, or tasks created. Missing Plugin Creator validation and separately authorized behavioral/native evaluations remain evidence gaps. This review assesses the proposed verification design; it establishes no implemented behavior, certification result, installed usability or approval.

## Round 2 — actual targeted renewal report

Reviewer: `/root/certification_verification_review` — targeted independent verification renewal.

Verified hashes:

- Revised plan: `9380f3e6345eabe9689973a5925e97a81099e5595dea518a79c218cfb5fd7853`
- Original plan: `7c202ab574360f65edf9d56c5cccbe41e3515d6c9c027d54427ed9ab9fca8e35`
- Unchanged handoff: `5636dcab64af5c858b305c32f927916167efc378962ee2d8bc6c04ab40e67970`
- Unchanged amendment: `a55780e1a47e6d18f1233697c4fd821011de95d9a53eb1c2b1bc59a3da99c2a3`

**Previous P2 finding resolved.** The substantive diff changes only Q22 and adds its paired fixture specification at [lines 231–233](/private/tmp/incremental-qa-certification-review-20261016/candidate-round2.md:231). The fulfilled counterpart now requires inspectable subject-bound causal assertions, prerequisite correspondence and an accessible synthetic direct decision. Its expected continuation rejects perpetual blocking while preserving unrelated certification/release obligations, execution authority and consumer-based retention. The missing-proof counterpart retains the necessary rejection behavior.

No material improvements recommended.

This renewal inspected the correction and its correspondence with the previously reviewed contract. No edits, tests, validators, model evaluations, provider calls, Git mutations or task actions occurred. Controller-seeded receipts remain synthetic evaluation inputs; this review establishes neither implemented behavior nor actual certification, native usability or approval.
