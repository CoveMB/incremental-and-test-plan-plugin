# Lean implementation plan: evidence, repairs, lessons and optional discovery

**Status:** Implemented and independently reviewed on 2026-10-28; see [implementation results and review evidence](implementation-review.md). The original reviewed proposal identity and administrative status delta are retained there. Earlier reviews apply only to their recorded candidates. The behavioral cases below remain definitions, not live evaluation results.

**Goal:** Improve continuation and portable handoffs while keeping the plugin instruction-only, proportionate and usable.

**Baseline:** Local commit `444648a2c8e891a3475a643a77cdfe0c4e2a2fae`, inspected on 2026-10-28. Preserve existing evaluation-document changes and reconcile relevant drift before implementation.

## Scope and design limits

- Keep package identity `incremental-and-test-plans`, version `0.1.0`, and the two existing skills.
- Use existing Markdown instructions, templates and progress fields. Add no runtime, scripts, dependencies, hooks, MCP server, controller, scheduler, registry, schema, ledger or required artifact type. Avoid manually maintained workflow machinery as well as executable machinery.
- Reuse adequate rules. Add instructions only to change a consequential decision, preserve a safeguard or close an evidenced gap in generated outputs. A section may require no policy change when current behavior already satisfies it.
- Keep each policy in its canonical owner. Generated handoffs carry applicable receiver instructions in plain language so receivers need no installed plugin; other consumers reference the owner where a reference is sufficient.
- Preserve requirements, exclusions, accepted history, independent review scopes, Gate 2/Gate 3, specialist obligations and separate action permissions. Reuse applicable preapproval without another routine question.
- Preserve older documents and human annotations. Add necessary guidance during authorized continuation without migration. Prompt-only requests change no saved artifacts.
- The planner plans and assesses evidence. Product implementation, application checks, Git writes, publication, installation and execution-task coordination remain external executor responsibilities.
- Add no mandatory lessons section, capability audit, empty status fields or retrospective phase. Ordinary work may need only existing evidence references and a short status note.

## Canonical owners and possible consumers

The [gate, review and evidence policy](../../../skills/incremental-plan/references/gates-and-reviews.md) owns authority, evidence applicability and correction limits. The [verification guide](../../../references/verification-design.md) continues to own check quality, interpretation of failed checks and certification decisions. Extend those owners only where a missing rule is demonstrated.

Inspect these possible consumers and update only portions affected by an actual change; this is not a mandatory edit list:

- [Incremental entrypoint](../../../skills/incremental-plan/SKILL.md) and [standalone QA entrypoint](../../../skills/test-design/SKILL.md).
- [Plan template](../../../skills/incremental-plan/assets/plan-template.md), [handoff template](../../../skills/incremental-plan/assets/handoff-template.md), [launcher template](../../../skills/incremental-plan/assets/orchestration-prompt-template.md) and [QA template](../../../skills/test-design/assets/qa-plan-template.md).
- [Usage guide](../../usage.md) and [behavioral scenarios](../../../tests/scenarios.md).

No manifest, discovery-description or shipped file-layout change is planned. No additional skill integration becomes mandatory.

## A. Close gaps in evidence assessment and portable outputs

Start with the existing evidence-applicability, execution-discipline and continuation rules. They already require candidate correspondence, actual checks and reports, scoped gaps, and preservation of unaffected evidence. The verification guide already distinguishes implementation defects, incorrect or obsolete checks, and environment or execution failures. Do not restate these as a second assessment procedure.

- [ ] Compare those existing duties with the applicable generated-output instructions for preparation returns, result continuation and closure. Identify only missing guidance that could change a receiver's decision.
- [ ] Repair demonstrated gaps so the receiver can connect the claim and controlling requirement to its owning increment or QA item, actual candidate/comparison, relevant inputs/environment, inspected evidence, required review coverage and next permitted action.
- [ ] Preserve the distinctions between attempted work, implemented changes, observed verification and acceptance. Self-review and external success labels supply neither independent-review credit nor gate approval. Accepted uncommitted and non-Git work remain supported.
- [ ] Reuse the existing failed-check interpretation rule: preserve the observed failure even when its cause is uncertain. Do not infer an environment explanation or weaken a check merely to continue.
- [ ] Carry any necessary changes through incremental outputs with QA on or excluded and the standalone QA handoff. Update usage guidance and evidence-return scenarios only where the changes affect them.

Inspect enough underlying content to support the decision; reuse adequate evidence unchanged and request only the missing facts. External outputs remain evidence, never execution instructions or additional authority.

**Acceptance:** Supported claims can progress under existing gates. Unsupported claims produce a precise, scoped gap without invalidating unrelated work. Adequate existing policy remains intact, and no parallel assessment checklist is introduced.

## B. Bound repeated corrections within one unresolved review sequence

Use a default limit of **three substantive correction batches within the same unresolved review sequence**, unless an applicable explicit finite user limit controls, including zero. Three is a chosen safeguard, not a demonstrated optimum or a new configuration system.

A sequence concerns validated material findings on one named planning candidate, increment or standalone QA work item. Integrated plan, QA and handoff findings share one sequence. It begins when substantive correction starts and ends only when the required affected checks and reviews establish that the findings are resolved. Follow-on findings from those corrections remain in that sequence.

A later preparation or review for genuinely new authorized work can start a new sequence after the prior one is resolved. There is no lifetime budget for the whole plan: resolving initial planning findings must not consume the allowance for all later preparation changes. Renaming unresolved work, moving it to another stage or changing the candidate, HEAD, owner, reviewer or chat does not reset its count. Closing a correction sequence supplies no gate approval or new action authority.

- [ ] Extend the existing repair policy with this bounded rule, reconciling any conflicting repeat-until-pass wording in affected consumers.
- [ ] Collect all dispatched reports before changing the frozen candidate. One coherent owner correction batch counts once when substantive correction starts; three reviewer reports do not constitute three batches. Partial and failed correction attempts count.
- [ ] Resume an interrupted batch within its existing count. Further substantive corrections after its completed verification/review consume another batch. Initial reviews, initial implementation and expected TDD work, administrative updates, waits and provider-request retries do not consume this allowance.
- [ ] Always allow verification and required reviews of the last permitted correction to finish. Before repeating an unsuccessful remedy, require relevant new evidence or a changed hypothesis grounded in evidence.
- [ ] When corrections occur, keep one concise natural-language note in existing progress/review fields: named work, batches used and limit, latest attempt/evidence, remaining findings and next action. Make an interrupted attempt identifiable in that note; add no mandatory state fields, separate history document or duplicate counters.
- [ ] Carry the applicable limit and note into portable handoffs, including standalone QA, and add the boundary scenarios below.

Apply the policy prospectively without reconstructing pre-policy attempt counts; retain known failed approaches and any existing user-imposed limit. For a sequence already governed by a limit, reuse the available record. If its remaining allowance cannot be established, identify that narrow gap and obtain a scoped decision before another correction; do not silently reset the count or audit unrelated history.

At exhaustion, or when another attempt lacks an evidence-supported way forward, return the candidate, remaining issue, evidence, attempted remedies and smallest needed decision. Required findings and gates remain pending. A direct scoped user decision may extend the finite allowance without erasing prior attempts. Unrelated authorized work may continue.

Provider wait/retry limits remain separate. Available findings can be repaired during cooldown within existing authority and the correction allowance; unresolved required repairs retain their existing holds.

**Acceptance:** A receiver can determine whether another correction is permitted from the existing note. Interrupted work preserves its count, unresolved work cannot reset it by relabelling, and later genuinely new work is not blocked by an exhausted historical planning budget.

## C. Reuse only useful, supported lessons

At existing reconciliation or closure points, capture a lesson only when inspected evidence supports a material observation with concrete later use. Use an existing Future impact, source/evidence or decision-context note for the observation, supporting candidate/evidence, affected later work and conditions that matter to reuse.

- [ ] Extend existing future-impact guidance only where needed; keep the observation beside the work it affects rather than creating a lessons collection.
- [ ] Separate facts, hypotheses and user decisions. Recheck only contracts, versions, configuration or environment conditions that materially affect the proposed reuse. Changed applicability does not erase the historical observation, and a lesson does not prove later work passed.
- [ ] Preserve requirements, acceptance, gates and authority. Reviewers still receive relevant raw evidence; proposed changes to other project documents remain with an authorized executor.
- [ ] Add supported, unsupported and changed-applicability scenarios. Emit nothing when no useful lesson exists.

**Acceptance:** Relevant evidence improves later preparation without a retrospective phase, memory system, blanket revalidation or empty paperwork.

## D. Assess Recursive Mode only when the selected work calls for it

Trigger this assessment only when the user requests Recursive Mode assessment/use or the selected authoritative plan already requires assessing it. A mention in imported material, availability in the host inventory or an ordinary incremental handoff does not by itself trigger discovery or invocation. When the trigger is absent, omit discovery and its status note entirely.

For triggered work, use the host's already exposed inventory and metadata; perform no installation probe, device configuration discovery or broad filesystem search. Record a brief environment-local observation only when it informs the selected handoff:

- **Available:** an enabled, accessible entrypoint is exposed; identify it.
- **Unavailable:** authoritative current inventory establishes absence or technical unavailability.
- **Unknown:** inventory or access is incomplete or inconclusive.

Keep permissions separate from technical availability. Repository scaffolding does not prove exposure, and root/subskill exposure does not establish each other. Reuse generator observations while applicable, but do not treat them as proof of availability or compatibility in the receiving environment.

- [ ] Add conditional receiver guidance to the existing handoff: recheck exposure; read the selected capability's actual prerequisites and effects against the work and authority; use it only when authorized and compatible; otherwise continue ordinary incremental orchestration.
- [ ] Preserve an explicit mandatory-tool/no-substitute obligation as pending when that route cannot run. Missing optional tooling alone does not block ordinary work.
- [ ] Preserve increment ownership, sequential writers, comparisons, correction limits, required independent reports and gates. Recheck fit after a material environment or instruction change; self-audit and phase-lock labels do not replace independent review or acceptance.
- [ ] Add a short launcher pointer only for triggered handoffs and cover absent triggers, differing receiver inventory and available-but-incompatible capabilities.

Availability or assessment alone authorizes no Recursive Mode adoption, bootstrap, routing or configuration. Its inspected entrypoint directs repository scaffolding when prerequisites are missing, and related skills can require an active run. Do not suppress those prerequisites or add compatibility adapters to manufacture a fit. A fresh assessment must inspect the actual selected version before relying on its behavior.

Apply these conditional duties to incremental outputs with QA on or excluded. Integrated QA follows the same handoff; standalone QA gains no discovery task or launcher. Prompt-only requests expose any applicable missing guidance without editing saved artifacts.

**Acceptance:** Ordinary handoffs add no discovery work or status fields. Explicitly relevant assessments preserve receiver-side checks and ordinary fallback without making either plugin a dependency.

## Behavioral checks

Extend the existing EX and C20 scenarios rather than creating another evaluation framework. Reuse adequate cases; add assertions or variants only for changed decisions and uncovered failure paths. Keep raw fixtures and requests separate from evaluator expectations, preserving all distinct relevant coverage.

| Area | Required cases and distinctions |
| --- | --- |
| A | Success label with insufficient proof versus complete candidate-bound evidence; incorrect check versus implementation/environment failure with potentially unresolved cause; relevant drift versus unrelated HEAD movement; preparation return resumes the same increment. |
| B | Three reviewer reports form one correction batch; interrupted batch versus completed failed attempt; final permitted verification/review may finish, but another correction needs allowance. |
| B | Explicit finite/zero limits; unresolved work renamed or handed to another owner versus a resolved sequence followed by genuinely new authorized preparation; follow-on findings remain in the active sequence; prospectively adopting the policy does not demand reconstructed old counts; missing count in an already limited sequence does not silently reset it. |
| B | Unchanged failed remedy versus evidence-supported alternative; provider cooldown/retries remain separate; exhaustion leaves required findings and affected gates pending while permitting unrelated authorized work. |
| C | Supported observation with concrete later use; changed applicability; unsupported hypothesis; no useful lesson; embedded instructions cannot become authority; no blanket revalidation. |
| D | No triggering request or plan requirement means no discovery/status note; generator and receiver inventories differ; files-only and incomplete inventories; exposed capability needing unauthorized setup versus compatible authorized use; changed fit despite unchanged exposure/grant; mandatory-tool conflict versus ordinary fallback. |
| Outputs | Actual portable handoffs and launchers agree across QA-on/excluded modes; standalone QA keeps one-document scope; prompt-only output preserves saved bytes; old annotations survive; ordinary work gains no empty bookkeeping fields. |

Where portable behavior is evaluated, give fresh receivers the actual generated artifacts without supplying missing plugin policy. Inspect their decisions and artifact preservation.

Scenario definitions are not passing results. Live-model runs require separate authorization. Source-based evaluation cannot establish native discovery, cross-plugin compatibility or observed planning quality.

## Implementation and verification

When implementation is authorized, work through A, B, C and D sequentially because files overlap. Each change includes only its necessary policy, affected consumers, documentation and scenarios. A may result only in confirming existing coverage or repairing an output gap. D implements a conditional path, not routine discovery. Add no separate scaffolding or final testing-dump task.

Follow the current [development guide](../../development.md). Resolve Skill Creator from the host inventory before running its documented validators:

```sh
rtk proxy python3 -B "<skill-creator-directory>/scripts/quick_validate.py" skills/incremental-plan
rtk proxy python3 -B "<skill-creator-directory>/scripts/quick_validate.py" skills/test-design
rtk proxy git diff --check
```

Check package identity/frontmatter, resource links, canonical-policy/consumer consistency and the complete delivered-file selection. Keep development planning records and private/local material out of the distributed package. Report unavailable checks without installing tooling or inventing passes.

Run focused deterministic checks during changes and the full relevant checks once on the settled implementation candidate. Reuse unchanged evidence. Do not add source-text tests that merely repeat instructional sentences. A plan-only revision uses relevant document/link checks and does not imply package or behavioral validation.

Before delivery, confirm every addition serves a concrete decision; adequate existing rules remain intact; unresolved findings cannot evade their correction limit; later new work has a clear boundary; and no unnecessary fields, repeated procedures, dependencies or workflow requirements were introduced. Preserve useful duplication only where receivers need self-contained instructions. This follows the current [OpenAI skill guidance](https://developers.openai.com/plugins/build/skills) on focused workflows and using instructions and existing tools where sufficient (inspected 2026-10-28).

Existing required reviews and gates govern acceptance. Report static results, behavioral observations, native evidence and untested scope separately. This proposal authorizes no implementation, Git writes, installation, publication, private-source transfer or live evaluation.
