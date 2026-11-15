# Orchestration token savings implementation plan

> Use native sequential implementation of this bounded development change. The user authorized planning, independent plan review, implementation in PR #12, an independent MR review, and a subsequent independent implementation-quality review.

## Goal and baseline

Reduce repeated launcher instructions and separate waits for concurrently active work while preserving implementation quality, evidence, gates and authority. The instruction package remains version `0.1.0` with its two existing skills and twelve runtime files.

The verified starting PR head is `53e19b85b1cb0dbe96f84324184272f7568cb670` on `orchestration-routing-and-waits`, based on `931af075e862e20e5c5cef754c3a0d285e14a443`. GitHub and local refs matched on 2026-11-15. Use the existing clean PR worktree. The separate main checkout contains unrelated work.

## Design and ownership

The launcher identifies artifacts, authority, actors and the next action. The selected handoff provides complete portable procedures, including the correction allowance. Its accessibility and coverage remain prerequisites. The host compatibility reference owns capability selection. Existing coordination fields retain each assignment's identity, state and cursor where supported.

| Source | Bounded change |
| --- | --- |
| `skills/incremental-plan/assets/orchestration-prompt-template.md` | Consolidate the three owner, coordination and correction paragraphs. Keep a fresh owner on first assignment and reuse thereafter, sequential writers, scoped packets/default models, verified routes and relays, timely bounded waits, human-only yield, required correction resolution and affected verification. Direct the receiver to read the correction procedure before repairs and retain escalation on exhausted allowance. Keep all other lifecycle, authority, missing-handoff and closure safeguards. |
| `references/host-compatibility.md` | Permit one native wait over multiple already-active targets only when supported and authorized, respecting target limits and available per-target continuation/error semantics. Preserve fallback by role and operation. |
| `skills/incremental-plan/assets/handoff-template.md` | Export the grouped-wait procedure in the existing coordination section. Preserve each target's identity and latest valid cursor, inspect all returned results/errors, promptly handle actionable returns, and retain unresolved targets. Bound by the earliest relevant deadline and host limits. Use existing per-target routes when grouping is unavailable. Grouping confers no parallel dispatch or writer permission and no change to review order. |
| `tests/scenarios.md` | Extend existing C20 waiting and EX01 receiver coverage for grouped waits and launcher procedure access. Keep synthetic raw inputs separate from evaluator expectations. |
| `tests/live-evaluation.md` | Add the affected grouped-wait and shortened-launcher cases to existing unexecuted selections, preserving explicit live-run authorization and measurement limits. |
| `docs/usage.md` | Briefly describe conditional grouped waiting alongside existing coordination guidance, retaining the token-savings limitation. |

The gate policy already owns independent reviews, correction limits and evidence applicability. Inspect it for preservation without duplicating its procedure or changing its semantics. Keep the full portable procedure in the handoff so receiving tasks can operate without the plugin.

## Acceptance and failure cases

| Condition | Required outcome |
| --- | --- |
| Two or more authorized assignments are already active and the host supports a bounded multi-target wait | Use a supported group with each target's own cursor. Wait for an actionable return within host limits and the earliest deadline. Inspect every returned result/error, including simultaneous returns. |
| One target completes while another is running, fails lookup, or lacks a cursor | Reconcile the completed target's evidence, preserve the other's pending state and own cursor, and refresh only the uncertain target as needed. A group return establishes no group completion. |
| Single target, excess targets beyond a host limit, unsupported grouping, or mixed manual/native routes | Respect host capacity and preserve coverage of all active targets using supported routes. Manual relays remain actionable. A denied operation retains its hold. |
| Sequential reviews or a single implementation writer are required | Group only work already authorized to run concurrently. Complete available review assignments before repairs. If a required review cannot be dispatched, collect all dispatched reports before authorized repairs. Require every applicable required report before acceptance, renewing affected checks/reviews after repairs. |
| Complete, missing, inaccessible or older handoff | Complete exports retain the correction procedure and its read trigger. Missing procedure/access makes reconciliation the next bounded action before affected execution. Prompt-only mode authorizes no saved-artifact edits. |
| Correction allowance exhausted, changed candidate/consumer, or revoked authority | Escalate the smallest necessary decision, retain counts and required findings, renew affected checks/reviews, and honor the actual current grant. |
| QA on, supplementary QA excluded, standalone QA or unrelated request | Both incremental modes carry the same mandatory safeguards. Existing independent routing and output boundaries continue to apply. |

## Work sequence

- [x] Independently review this plan against the current canonical sources and user scope. Resolve verified material findings before implementation.
- [x] Update the scoped sources and scenario definitions as one coherent batch. Compare the complete generated-launcher body and both templates with the baseline, checking every retained obligation.
- [x] Run both existing Skill Creator validators and `git diff --check` using the commands in `docs/development.md`. Check parsed manifest/frontmatter identity, resource containment and Markdown anchors. Compare catalog count and description lengths with the baseline.
- [x] Use the documented twelve-file export recipe in disposable temporary storage. Inspect actual exported contents and run its missing-resource, forbidden-file and altered-byte controls. Keep temporary output outside tracked source.
- [x] Desk-check positive, negative, adjacent and ambiguous routes and the acceptance cases above. Record source word/byte counts as source measurements only.
- [x] Commit the bounded change and push to the existing PR branch. The user's instruction to implement in the MR authorizes this update. Verify remote candidate correspondence.
- [x] Obtain a fresh read-only independent review of the full MR against its base, with focused attention to this approved plan. Fix confirmed material in-scope issues and renew affected evidence if needed.
- [x] Then obtain a different fresh read-only independent review focused on preserved implementation quality across the full MR. Check raw-source inspection, concrete design, verification, correction accounting, independent review scopes, authority, compatibility and failure handling. Reconcile all findings before completion.
- [x] Update the existing PR description to describe its complete current behavior and actual verification. Retain the plan and concise review outcomes in this development record. Report the final commit, review results and limitations.

## Evidence and constraints

Current official skill guidance supports loading detailed instructions when needed. This informs the launcher/handoff split but does not establish behavior of generated outputs. [OpenAI skill documentation](https://learn.chatgpt.com/docs/build-skills)

The exposed Codex `wait_threads` schema checked on 2026-11-15 supports up to eight targets, a cursor per target, first completion/attention wakeup, compact timeout state and per-target errors. This establishes one available host capability. Export generic conditional guidance and recheck the actual receiving host, without hard-coding the eight-target limit into portable instructions.

Use native independent source reviewers under the user's explicit request. Behavioral generation/receiver runs require separate live-model authorization under repository policy, so this work records static desk-checks and unexecuted scenarios. Static evidence cannot establish runtime token savings or model compliance. Preserve failing/unavailable checks honestly, and compare efficiency only at equivalent completed scope and evidence coverage.

The earlier 212-to-140-word illustrative rewrite is a sizing example. Final wording follows coverage and review findings without a size target. No new runtime, dependency, controller, monitor, ledger, metadata change or model override is required. A rollback would be a scoped follow-up commit after inspecting current work, preserving other changes.

## Review and completion evidence

Independent plan review completed before implementation by a fresh read-only reviewer. The reviewed plan digest was `ca0024f867126fb28479f3ec52394eec67c6b73a46e83d8b6a41aae890bd98f5`. Verdict was “No material improvements recommended.” The controller checked the report against the planned scope and canonical sources.

Implementation and static desk-checks completed for the cases above. The default Python interpreter lacked PyYAML. Both existing Skill Creator validators passed with already-installed Python 3.14 and PyYAML, with no dependency installation. Diff hygiene passed. The documented export produced twelve matching staged, archived and extracted files. Parsed metadata, two entrypoints, unchanged discovery descriptions (351 and 290 characters), 162 resource links/anchors and all three package negative controls passed. An initial resource check treated the generated `handoff.md` sibling placeholder as a shipped file; the corrected checker distinguishes that exact documented placeholder and passed. Actual exported contents were inspected for local/private material and undeclared dependencies.

The complete launcher body decreased from 398 words / 3,009 bytes to 349 words / 2,644 bytes. The full launcher and handoff template pair increased from 10,327 words / 82,421 bytes to 10,398 words / 82,924 bytes because the grouped-wait procedure adds safeguards. These are source measurements. Runtime savings and live receiver behavior remain unmeasured.

The implementation was published as `d6481aad3a49d63f4926f2aaa87cf7c84e5a70bd`; the remote branch and PR head were verified against it. Two further fresh read-only reviewers independently inspected the complete eight-file MR against `931af075e862e20e5c5cef754c3a0d285e14a443`, in the requested order.

| Review stage | Candidate and result |
| --- | --- |
| Independent plan review | Pre-implementation plan digest above. No material improvements recommended. |
| Independent MR review | `d6481aa`, full MR and connected consumers. No material improvements recommended. |
| Subsequent implementation-quality review | `d6481aa`, full MR with focused design, evidence, verification, review independence, correction, authority and failure-path inspection. No material improvements recommended. |

Both implementation reviewers confirmed that all twelve runtime hashes matched the inspected source and extracted files. The controller reconciled their claims with the canonical correction, review and coordination procedures. No material findings required a repair. These reports establish source-level preservation within their reviewed scope.

The PR title and description were updated to reflect the complete current change and verification limits. GitGuardian passed on `d6481aa`. CodeRabbit returned neutral because its review was rate-limited and all analysis stages were skipped. Native independent source reviews above are the completed requested review evidence. Live evaluations and measured runtime savings remain outstanding evidence outside this authorized development scope.

Commit `4a1c817` changed only this development record. Its reviewed runtime and scenario candidate was the content of `d6481aa`.

## CodeRabbit follow-up corrections

A later CodeRabbit review identified the optional execution comparison conflicting with the generation/decision product-execution prohibition. Commit `2ef8bf9` defined the separately authorized synthetic execution profile and aligned grading. A targeted independent source review and all 55 runbook resource links/anchors passed. No live evaluation was run.

The next provider review identified an overbroad prerequisite introduced by the grouped-wait guidance and mirrored in this plan and EX01. The canonical policy permits authorized repairs once all dispatched reviewer reports return, while acceptance requires all applicable required reports. The handoff, this acceptance case and C20/EX01 controls now preserve that distinction, including an undispatched required review versus an in-flight reviewer. Earlier review reports and size measurements above describe their identified candidate. The targeted independent reviewer identified a conflicting sentence in the canonical three-review policy. The canonical owner and handoff now explicitly preserve the normal review sequence and allow this repair path only when a required assignment cannot be dispatched and all dispatched reports have returned. C20/EX01 also contrast a remaining review that can proceed. Renewed targeted independent review found no material improvements recommended and confirmed that its earlier canonical-policy finding was resolved. The current twelve-file export, byte correspondence, 162 resource links/anchors, metadata checks, three negative controls and diff hygiene passed. The launcher remains 349 words / 2,644 bytes; the corrected full template pair is 10,429 words / 83,161 bytes, an increase of 102 words over the original baseline. These are source measurements, with runtime behavior and savings unmeasured.
