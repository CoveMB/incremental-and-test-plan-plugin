# Implementation orchestration prompt

Use this asset for eligible [incremental recaps](../SKILL.md#return-a-concise-recap). It composes a short launch request for a separate orchestrator; generation performs no execution and saves no extra artifact.

## Compose from current artifacts

1. Select the actual repository, plan, current handoff and applicable QA document. Derive the first bounded action from current evidence and verified direct decisions. Pending reviews, material decisions and predecessor proof come first; with no repository, make selection the first action. Preserve accepted history and select only dependency-eligible unfinished work.
2. Inspect the actual selected handoff for the portable duties below. The prompt supplies coordination and directs reads; the handoff supplies detailed procedures in plain language, without installed-plugin links or author-conversation dependencies. Give conditional procedures clear sections and read triggers before their related actions. Retain future safeguards there even when today's next action is a review or decision.
3. During authorized generation/continuation, fill necessary handoff gaps within the selected artifact scope and preserve existing history/human annotations. Do not migrate an old plan merely to adopt headings. For a prompt-only request, do not edit saved artifacts: name missing/conflicting instructions and make their authorized reconciliation the first action. An unavailable handoff likewise needs recovery or authorized preparation before affected execution; do not infer policy or expand the launcher into a replacement manual.
4. Use the short body below, resolving its fields and preserving its essential instructions. Omit only the QA clause when supplementary QA is excluded. Add model selection or decision references only for verified applicable direct user instructions, with their scope, conditions and amendments; defaults confer neither a model override nor preapproval. Missing provenance stays unresolved.
5. Return one fenced prompt as the last substantive recap section, labeled **Implementation orchestration prompt**. Omit it for explicit exclusion, standalone QA, unrelated routes or completed implementation scope; retain actual closure obligations in the recap/handoff. An unfinished blocked plan is not complete.

## Portable coverage check

The [gate policy](../references/gates-and-reviews.md) owns policy; the [handoff template](handoff-template.md#portable-execution-guidance) carries it into the selected target artifact. Verify actual output coverage, not template intent or a receiver's inferred answer:

| Location | Required content |
| --- | --- |
| Launch prompt | Actual artifacts and next bounded action; read-before-action and missing-authority safeguards; one orchestrator, persistent increment owners and sequential writers; required lifecycle/reviews/gates and dependency readiness; native coordination/existing progress and final reconciliation. |
| Handoff: startup and coordination | Actual authority/readiness and source references; title/count/update rules; bounded native waits/latest supported cursors; owner/reviewer identities, resumption and safe replacement; default model and concise child packets. |
| Handoff: preparation and result | Contract correspondence, meaningful checks/self-review, three distinct fresh-context reviews and applicable simplicity route; frozen candidate/repair authority; semantic naming; future impacts, evidence and retention/closure. |
| Handoff: publication and exceptions | Separately authorized Git/PR/native-stack work, current required CI, provider expectation and settlement before dependent preparation/dispatch, bounded timed retries and late feedback. These sections are read before the corresponding work, not repeated in the prompt. |

Check QA-on and excluded modes for the same mandatory safeguards and correct next action. The referenced handoff may carry all detail omitted from the prompt; a generic reference to absent, incomplete or inaccessible instructions does not establish readiness. Report such gaps with the bounded first action above. Check the prompt remains a launcher rather than repeating those procedures; no verbatim full-policy export or word quota is required.

## Prompt body

```text
Orchestrate [selected plan] in [selected repository], using [current handoff] and [selected QA document, when applicable]. Start with [actual next bounded action and unfinished increment].

Read the selected artifacts, controlling sources and applicable handoff procedures before the related action. Recheck current checkout, prerequisites, evidence and direct user authority; missing or conflicting instructions, material decisions and permissions remain blockers for affected work. Preserve existing work and accepted history.

Keep one orchestrator for dependencies, progress and final reconciliation, and one fresh implementation owner chat per eligible increment. Reuse that owner for preparation, implementation, checks, required independent review coordination, repairs and authorized PR/CI work. Keep writers and shared-checkout/stack mutations sequential. Give children concise scoped packets and use configured model defaults unless I explicitly select otherwise.

Follow the handoff's lifecycle, required independent review scopes and Gate 2/Gate 3 pauses unless a verified scoped decision bypasses that pause. Missing evidence or reviews remain pending. Before dependent preparation or dispatch, reconcile applicable result, approval, current CI and expected provider-review evidence. Git/publication and other external actions require their separate authority; leave authorized PRs open for my review.

Use native coordination and bounded waits, follow the handoff's naming/resumption procedures, and keep actual owner/reviewer references, evidence, blockers and next actions in existing progress fields. Add no controller, ledger, scheduler or per-check tasks. Report concrete capability blockers. Finish with requirement/evidence reconciliation, retention obligations, PR links when present and any remaining gaps; do not infer completion from status labels.
```
