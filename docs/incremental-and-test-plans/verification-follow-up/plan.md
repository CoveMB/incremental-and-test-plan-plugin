# Verification Follow-up Implementation Plan

> **For agentic workers:** Use `superpowers:executing-plans` when available, with one sequential writer. This is a development/evaluation plan, not a runtime dependency or an invocation of the incremental-planning workflow.

**Status:** Proposed, 2026-10-18. Planning only. Assume the [previous repair plan](/Users/CoveMB/Code/CoveMB/incremental-and-test-plan-plugin/docs/incremental-and-test-plans/quality-repairs/plan.md) and its validation have been completed before this work starts. This document records no new passing result or execution authorization.

**Goal:** Close the remaining evidence gaps around portable completion duties and effective evaluation context, reusing completed repair evidence.

**Architecture:** Refine the existing receiver scenario and evaluation method, audit the completed batch, and run only a missing receiver check. Installed-use acceptance is a separately selected, conditional follow-up. No runtime instruction change or new test infrastructure is planned.

**Tech stack:** Existing Markdown scenarios, retained native traces/artifacts and supported host facilities. No new dependency, permanent runner or service.

**Spec:** The user's request to address the residual gaps after the earlier repairs. The [comparison](/private/tmp/skill-test-gap-comparison-8xffo80n/comparison.md) and [independent test-design assessment](/private/tmp/skill-test-gap-comparison-8xffo80n/qa-plan.md) support two refinements: future closure comprehension in R09 and observation of actual actor context/actions. This plan is self-contained if those temporary reports become unavailable.

## Scope and entry conditions

Treat the earlier F1/F2 source repairs, their twelve-case batch, held-out domain case, preservation checks and independent final review as predecessor work. Do not reimplement them or automatically rerun that batch. At execution entry, identify the actual completion record, settled candidate fingerprints, generated R03 QA/handoff, R09 request/response and raw run records. Confirm correspondence rather than infer completion from this assumption, HEAD or a status label. Missing records remain gaps; request only the missing evidence, without reopening valid approval or unaffected work.

Preserve all staged/unstaged/untracked work and the earlier plan/history. Recheck branch/status and current contents before edits; use exact source locators rather than frozen line numbers. Current concurrent changes are protected. This planning task does not certify their completion.

The only planned existing-file change is [tests/scenarios.md](/Users/CoveMB/Code/CoveMB/incremental-and-test-plan-plugin/tests/scenarios.md): its evaluation method, EX01 raw receiver request and evaluator-only expectations. Keep runtime files, metadata, package identity/version, output routes, gates and review policy unchanged. Keep run evidence outside tracked source. No commits, publication, installation, deletion, external review service or persistent configuration changes follow from this proposal.

## Task 1 — audit the completed batch's actual evidence

**Input:** The completed predecessor's raw records and identified candidate. **Output:** A concise audit/disposition in its existing authorized completion/evidence location, without rewriting historical observations.

- [ ] Compare each of the completed batch's records with its actual requested configuration and observed actions. Inspect model/CLI identity, actual skill/resource reads, native process and child-command exits, warnings/retries, before/after files and capture limits. Inspect content only as needed; retain raw retrieval references rather than copying packet trees.
- [ ] Distinguish requested settings, observable injected/discoverable metadata, actual extra policy reads, and unobservable context. Use permitted metadata; do not claim to have inspected hidden instructions. A disabled-plugin setting is not proof that other skill files were unavailable. Earlier case 06 demonstrated this by reading Superpowers skill files despite disabled configured-plugin entries.
- [ ] Record each result's usable claim: identified source behavior with the observed context; no observed extra reads, with remaining exposure unknowns; or influenced/incomplete evidence that cannot support the intended claim. Preserve failed starts and successful retry identities separately. A forbidden attempted action remains a failure even if blocked. Native exit zero does not erase child errors or missing results.
- [ ] Renew only evidence whose relevant inputs, missing capture or concrete confound prevent the required conclusion. Do not repeat a case merely because its record contains a recovered probe error or an honestly stated isolation limit. Attempt a cleaner affected run only after identifying a supported, concrete improvement; do not repeat the same confound, change global configuration, hide installed files or enable experimental bypasses.

**Acceptance:** Every result used by this follow-up has a candidate, observed outcome, usable raw references and explicit context/action limits. Unobservable exposure stays unknown. A valid bounded observation need not be discarded to make an unsupported claim of complete isolation.

## Task 2 — verify portable future closure duties

**Input:** Actual R03 QA/handoff and R09 records from the completed predecessor. **Output:** One narrowly interpreted closure-comprehension result, reusing evidence wherever it already answers the question.

- [ ] Inspect the actual emitted QA handoff and its target references for applicable later completion requirements. Locate mandatory proof and independent reviews/gates, the terminal evidence-retention review, and separate cleanup authority. Source obligations determine applicability; add no new certification or release gate.
- [ ] Check whether the existing R09 request/response already exercises these duties. If it does, adjudicate that evidence without another model call. A concise answer about the immediate next action is not automatically defective for omitting an unasked future condition.
- [ ] Apply the scenario refinements previewed below. If future comprehension remains untested, use **one fresh read-only receiver** with the unchanged actual generated QA handoff, its selected raw target context and actual target references. Supply no plugin/template/policy text, evaluator answer, author conversation or manufactured review/approval. Ask the revised open question. Use configured model defaults and supported controls; record effective exposure rather than assert complete isolation.
- [ ] Evaluate the answer against the selected exported content. Distinguish absent instructions in the export, failure to recover present duties, unavailable evidence and environment contamination. An ambient policy read cannot supply missing export content or earn clean plugin-free credit. Preserve valid artifact-inspection evidence and disclose any remaining receiver limitation.

**Observable acceptance:** The receiver keeps the correct current stop; explains what applicable mandatory evidence/reviews/decisions remain before completion; treats the retention review as required planning/reconciliation rather than deletion already performed; and recognizes that a cleanup disposition or completed implementation does not grant destructive authority. It preserves accepted history and applicable proof while leaving actual gaps unresolved. Equivalent plain-language answers pass; keywords alone do not.

An actual missing-export defect warrants a bounded source-repair preview and affected checks; it does not authorize a speculative runtime rewrite. If the receiver result cannot be established with available supported controls, report that precise unresolved claim rather than invent a pass or silently expand the harness.

### Exact scenario changes for later approval

Retain all unmentioned scenario text. Reconcile concurrent edits before applying these previews; omit a change already implemented with the same meaning.

**A. Evaluation method:** After the paragraph beginning `Record the exact skill/template identities`, add:

> Record effective actor exposure separately from requested settings: model/version, injected or discoverable skill metadata when observable, actual extra skill/resource reads and remaining unknowns. Inspect native and child-command outcomes, warnings, retries and trace completeness. An exit zero or disabled-plugin setting alone proves neither successful actions nor isolation. Use only permitted observable metadata and keep unavailable context unknown.

**B. EX01 environment statement:** Replace:

> Its environment contains neither Superpowers nor this planning plugin, and it has no author conversation.

With:

> Do not provide this plugin, Superpowers, other skill-policy content or the author conversation to the receiver. Record effective ambient exposure and actual reads under the evaluation method; configuration alone does not establish isolation.

**C. EX01 first raw receiver request:** Replace:

```text
Read this handoff and selected target context. Describe the next permitted action, how to start or resume the work, and what to return after a check or an execution deviation. Do not execute, install, dispatch, change files or perform Git/external actions.
```

With:

```text
Read this handoff and selected target context. Describe the next permitted action, how to start or resume the work, and what to return after a check or an execution deviation. What would later be required before you could report the selected scope complete? Do not execute, install, dispatch, change files or perform Git/external actions.
```

**D. Evaluator-only EX01 expectations:** Append to the existing EX01 acceptance cell:

> For receivers asked about later completion, check applicable mandatory proof and review/gate conditions, the terminal evidence-retention review and separate cleanup authority against the actual exported content. Distinguish absent export content from an omitted answer; a concise current-action reply need not enumerate unasked future duties.

These definitions improve future cases but do not retroactively change old observed results. They remain outside actor inputs. Reusing an existing R03 output avoids regenerating plans merely to obtain another receiver check; new wording does not require rerunning every EX01 variant.

## Task 3 — reconcile the local follow-up

- [ ] Compare changes against a preserved entry baseline and confirm only necessary scenario edits and authorized evidence notes were made. Validate edited Markdown/link/whitespace contracts; use `rtk proxy git diff --check -- tests/scenarios.md` after the coherent change. Reuse predecessor runtime/package checks when their inputs remain unchanged; do not rerun validators solely for a scenario wording change.
- [ ] If new scenario edits or a new result were necessary, obtain at most one bounded fresh read-only final review of the actual scenario change and evidence interpretation. Provide raw inputs/exports/results, candidate identities and the predecessor's relevant records. No inherited author history, recursive fan-out or external transport. Reconcile material findings; renew only affected checks. If everything was already covered by unchanged applicable evidence, do not create another unchanged review cycle.
- [ ] Report separately: closure portability demonstrated or unresolved; effective context/actions audited with stated limits; valid predecessor evidence reused; any remaining defect or permission/tool blocker. Do not call an unresolved required outcome complete. No additional six-case preservation/lifecycle battery, multi-model matrix or real provider workflow is included without new material evidence.

The local follow-up is complete when applicable scenario refinements, actual closure evidence, context/action dispositions and required bounded review are reconciled. Perfect visibility into host context is not a completion criterion; honest limits and appropriately narrow claims are. A source-only receiver result establishes neither installed behavior nor universal reliability.

## Conditional follow-up — installed-use smoke checks

This is a separate adoption outcome, **not a prerequisite for the local work above**. Select it only when the repaired candidate is to be used through an installed CLI or desktop entrypoint, with explicit authority for any necessary installation and live evaluations. Choose the actual target surface before execution; this proposal makes no desktop acceptance claim.

1. Inspect the supported native route, selected marketplace/source and exact delivered runtime inventory against the settled candidate. Reuse an already matching installation; no reinstall merely for freshness. If installation changes are needed, prepare its concrete source/diff and supported recovery route for the applicable approval. Never edit caches directly. Refresh official tool instructions only when version/operation/applicability requires it.
2. In disposable synthetic workspaces, run a bounded five-case smoke set: explicit qualified invocation of each of the two skills; natural-language incremental conversion; natural-language standalone QA; and an implementation-only negative route. Give actors the installed entrypoints/catalog appropriate to each case, not direct repository source paths that bypass the installed route. The negative case requests a read-only route decision, not actual product implementation.
3. Inspect resources actually selected, output boundaries, source correspondence, attempted actions and resulting artifacts. Reuse the same context/action audit. Require coherent planning on positive routes and no unsolicited planning artifact or execution on the negative route. Model use needs its own actual result; discovery/file parity alone is insufficient.
4. Record qualified invocation, natural-language selection and any selected desktop observation independently. One smoke set proves only those observed examples. Missing installed results leave this adoption outcome pending without reopening completed local source work.

## Execution boundary and research basis

Implementing this plan later requires a bounded execution request, including any necessary fresh receiver/final reviewer; installation/adoption remains separately selected. The prior plan's approval is not automatically extended to new actions. Routine inspection, preservation and reuse are not reasons to ask again for an already applicable permission.

Current official [trace-grading guidance](https://developers.openai.com/api/docs/guides/trace-grading) supports examining decisions and tool actions to localize failures. This plan uses existing local capture facilities; it adds no dashboard, API service or grading framework. The [skill-evaluation guidance](https://developers.openai.com/blog/eval-skills) likewise supports checking actual traces/artifacts rather than relying on final prose alone.

Return one concise completion note with the settled predecessor identity, reused evidence, any new receiver result, context/action limitations, actual scenario diff/checks, review disposition and optional adoption status. Keep the completed prior plan and historical observations intact.
