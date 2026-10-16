# Incremental Plan Plugin

A Codex-only, instruction-based skill for turning an authoritative implementation plan into coherent development increments a human can review comfortably.

## Current scope

The skill supports **creation, revision, evidence-based continuation and final scope reconciliation** from a local Markdown source or pasted text, with optional supporting documents. It writes a readable plan, requirement coverage, proposed increment cards, factual progress notes and a copy-ready planning handoff. The response includes a concise part/increment recap and outstanding gates.

Each increment advances one identifiable feature through a coherent piece, with its meaningful tests and required documentation or safeguards. Keep coupled contracts and callers together. An entire small feature may be one increment. File counts, line counts and target increment counts do not determine the boundaries.

New plans remain drafts until three distinct independent reports are reconciled. The skill can arrange authorized read-only review or provide manual review briefs; missing review never becomes a pass. Reviewed plans yield preparation handoffs with both routine gates. The executor performs implementation and verification externally. Continuation reads actual executor results and current checkout evidence, preserves accepted history and updates only authorized planning artifacts. A preparation return resumes the same increment at Gate 2; an eligible verified result may lead to the next increment. Final reconciliation checks every owning increment and keeps approved deferrals and separate certification/release obligations visible.

The planner does not implement products, run application tests, write Git state, use provider credentials, install, publish, schedule or create/message execution tasks. Gate 2 approves a concrete execution plan; Gate 3 approves its verified result. Planning alone grants neither. Source/repository gates and explicit scoped user decisions remain visible.

Evidence guidance favors usable existing references and minimal selected captures. The external executor estimates selected contents before potentially large copying, applies target-project warning thresholds with their units/scope, and reports a bounded estimate or honest unknown/rationale where no threshold exists. There is no universal plugin byte limit. Exclusions are selective: names such as dependencies or caches do not make unique inputs, persistent data or required failed environments disposable. Instructions do not enforce limits or intercept copying; deterministic enforcement belongs to target artifact-producing tools.

Every new plan schedules a final **Evidence retention and cleanup review** outside feature-increment counts. It records preservation and proposed dispositions separately from product acceptance and executor cleanup; no artifacts can yield no-cleanup-needed. Optional storage decisions do not block demonstrated scope, while missing mandatory proof and source-required cleanup remain obligations. The planner never deletes or compacts evidence, and acceptance supplies no cleanup permission. Concrete executor cleanup needs its own applicable explicit authority. Old plans continue without migration and receive the review when closure is requested.

## Try the checked-out source

In a disposable workspace, ask Codex to read `skills/incremental-plan/SKILL.md` from this checkout, then provide a request such as:

> Turn `docs/search-plan.md` into a draft incremental plan. Use `docs/search-contract.md` as supporting context. Save the plan and handoff under `docs/incremental-plans/search/`.

For pasted input, identify exactly which text is the source and its destination. The skill saves that text verbatim as `source.md`. Existing source files are preserved. Ambiguous primaries, occupied output paths and escaping symlinks require a decision before affected writes.

For an existing plan, supply the saved plan/handoff and linked executor evidence:

> Continue `docs/incremental-plans/search/plan.md` from the executor return. Reconcile current evidence and update its plan and handoff.

For a refinement, identify the authorized scope change and ask to revise the pending cards; accepted IDs/history remain intact. For closure, ask to reconcile the selected scope against every increment's evidence. Missing records, stale checks and unresolved decisions yield a specific return request, not assumed completion. An accepted uncommitted predecessor can qualify when identifiable, present and permitted by the target repository.

An implementation-only request should use the ordinary development workflow, without activating this planner. Loading a source file manually is a source-level exercise, not proof of installed skill discovery.

## Package and validation

The package contains `.codex-plugin/plugin.json`, one skill, one gate/review reference and two templates. It has no executable runtime, dependency installation, MCP server, hooks, or mandatory third-party skills. Independent review uses available authorized host facilities or supplied applicable reports, without a mandatory reviewer tool. Ponytail is optional and explicit-only; the architecture reviewer supplies the documented simplicity substitute when it is not run. A stricter target policy is surfaced for a decision. Local metadata uses the bundled scaffold's `Local developer` label, without asserting a public publisher identity or license.

For development checks, locate the bundled Plugin Creator and Skill Creator directories in the active host's skill inventory. With those directories substituted, run:

```sh
python3 -B <plugin-creator-directory>/scripts/validate_plugin.py <plugin-root>
python3 -B <skill-creator-directory>/scripts/quick_validate.py <plugin-root>/skills/incremental-plan
```

These are host development tools, not plugin dependencies. Follow the host's shell conventions. Do not install missing validator dependencies silently. Static validation checks package structure; it does not establish behavioral correctness, human reviewability or native usability.

[Behavioral scenarios](tests/scenarios.md) define source conversion, review and handoff exercises, with simulated decision cases labeled separately. Run fresh agents against synthetic inputs and inspect their actual actions and outputs. Store local run evidence outside the repository. The scenario document includes persisted preparation/result returns, dirty predecessor checks, interrupted writes and whole-chain reconciliation. Scenario definitions alone are not passing results; the development continuation record links observed coverage and remaining limits.

## Installation status and design

The complete planning capability is implemented. Local installation and native CLI acceptance were verified on 2026-10-13 with Codex CLI `0.162.1` on macOS arm64: fresh loading, explicit qualified invocation, automatic discovery and an implementation-only negative case passed. Behavioral cases used synthetic inputs with memory disabled and verified filesystem restrictions. Desktop UI activation and universal routing reliability remain unverified.

Those historical activation results do not validate the evidence-storage/retention amendment. Its E01–E08 definitions require observed fresh-agent evaluation; source-level synthetic observations remain distinct from installed usability, actual executor capture, real failed-environment recovery and uncontrolled filesystem races.

For explicit installed use, begin a planning request with `$incremental-plan-plugin:incremental-plan`, then identify the source and destination. Ordinary planning requests can also select it automatically. Implementation-only requests remain ordinary development work.

The [completion and native evidence record](docs/superpowers/plans/2026-10-13-continuation-gate-2.md#native-acceptance-and-plan-completion--2026-10-13) reconciles Tasks 1–4, retained independent reviews, tested identity, recovery and coverage limits. The existing implementation-plugin remains installed and enabled; it is not replaced or migrated. Another host requires its own supported installation route and authorization.

The [reviewed design](docs/superpowers/specs/2026-10-11-incremental-plan-plugin-design.md), [implementation plan](docs/superpowers/plans/2026-10-11-incremental-plan-plugin.md) and [continuation scope and evidence](docs/superpowers/plans/2026-10-13-continuation-gate-2.md) record development authority and evidence. They are not runtime dependencies of the skill.
