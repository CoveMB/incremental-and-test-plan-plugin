# Incremental and QA Plan Plugin — implementation plan

Created: 2026-10-16. Scope: planning and independent review only; implementation has not started. Review readiness and outstanding permissions are recorded below.

## Purpose and context

Deliver one first-version, Codex-only package named `incremental-and-qa-plan-plugin` with two skills:

- `incremental-plan`: convert an authoritative plan into coherent increments, incorporating a QA design by default; permit explicit exclusion of supplementary QA design.
- `qa-design`: design appropriate QA and its implementation work from a plan, the current project, or both, without requiring an incremental plan.

Both remain instruction-based planning workflows. They inspect sources and relevant code/tests/CI, write requested planning artifacts, preserve approval boundaries, and distinguish proposed verification from observed results. They do not implement applications, run application tests, mutate Git, install tools/plugins, use credentials, publish, schedule, or create/message execution tasks.

Primary source: [source.md](source.md), the exact current user request, without an added trailing newline. [Review inputs](review-inputs.md) record the earlier recommendations referenced by the request and the actual follow-up decisions. The user selected **one combined plugin** and **no backward compatibility: treat this as a first version**. QA-on is the requested default; the earlier opt-in and separate-package proposals are superseded.

Inspected baseline: repository root `/Users/CoveMB/Code/CoveMB/incremental-plan-plugin`, branch `main`, HEAD `bf0c2b19ab4e1e90170fae048824aec3f6da7356`, clean before these planning artifacts, inspected 2026-10-16. Comparison for future preparation: that baseline plus the exact executor candidate, including relevant staged, unstaged, untracked, deleted, and generated inputs. Local refs were not refreshed; remote freshness is unnecessary for this local planning assignment.

The selected implementation scope is package source, documentation, scenario definitions, deterministic validation, and separately authorized behavioral evaluation. Repository-directory/remote renaming, installation/cache/configuration changes, publication, compatibility aliases, migration layers, external application QA execution, and live-provider testing are excluded. The physical checkout path need not match the manifest name. Historical design/evidence documents keep their historical identities; they must not become claims about the new package's activation.

## Design and canonical ownership

Use two skills in the same package and ordinary Markdown artifacts. No execution engine, runtime scripts, custom state/approval system, mandatory integration, MCP server, hooks, new runtime dependency, fixed test pyramid, coverage quota, or numeric risk scoring is needed.

| Canonical source | Responsibility and planned change |
| --- | --- |
| `references/verification-design.md` (new) | Shared decision guidance: consequence/reversibility, test selection, independent expected outcomes, test sensitivity, evidence limits, integration and residual obligations. Both skills and the review policy link here rather than copying the rules. |
| `skills/incremental-plan/SKILL.md` | Increment procedure, QA-on/exclusion routing, source/QA reconciliation, coordinated planning outputs and continuation. |
| `skills/incremental-plan/references/gates-and-reviews.md` | Existing gates, permissions, independent reviewer scopes and result eligibility. Extend the verification brief and reuse these semantics for standalone QA plans; no new routine approval gate. |
| `skills/incremental-plan/assets/plan-template.md` and `handoff-template.md` | Increment/output structure, concise QA mode/design references, acceptance/recovery, combined-journey ownership, residual evidence, and self-contained executor obligations. |
| `skills/qa-design/SKILL.md` (new) | Source/project inspection and standalone QA-design procedure; bounded output permissions and discriminating routing. |
| `skills/qa-design/assets/qa-plan-template.md` (new) | One `qa-plan.md` containing evidence-aware QA design, actionable implementation work, readiness, and a copy-ready preparation handoff. |
| `.codex-plugin/plugin.json` | Final package identity `incremental-and-qa-plan-plugin`, first-version metadata `0.1.0`, accurate descriptions/UI prompts and existing skills-directory discovery. Keep the supported compatibility manifest format. |
| `README.md`, `AGENTS.md`, `tests/scenarios.md` | Active usage/package guidance, canonical-owner links and observable evaluation scenarios. Preserve unrelated guidance and historical evidence. |

Relative links must resolve within the shipped package. From either skill entrypoint, the shared guide is `../../references/verification-design.md`; the incremental gate reference links to it via `../../../references/verification-design.md`. Standalone QA links to the gate owner via `../incremental-plan/references/gates-and-reviews.md`. Generated handoffs reproduce applicable obligations in plain language; package-relative links alone are not sufficient for receiving executors.

### QA-design output contract

`qa-plan.md` is a readable planning document, not a machine schema or authority receipt. It records:

1. Selected source(s), intended outcomes/journeys, exclusions, inspected baseline and relevant existing test/tooling/evidence inventory. Plan-only future interfaces and commands stay provisional. Existing tests are inspected for assertions and applicability; their mere presence is not passing evidence.
2. Material failures, their consequences, reversibility and evidence gaps. Clarify consequential ambiguity with the user rather than inventing business rules, expected answers, legal conclusions, or requirements.
3. A compact design table: source outcome/journey or risk; useful existing coverage/gap; proposed check with independently justified expected behavior; necessary environment/data and isolation; owner/timing and required result evidence. Omit irrelevant empty categories.
4. Bounded implementation work for missing evidence: owning code/test/CI areas, dependencies, fixtures, meaningful assertions, target-supported commands where actually established, and acceptance. Reuse current useful coverage, helpers, native capabilities and installed tools before recommending additions. Material tooling/cost/environment choices remain decisions; no installation is implied.
5. Important untested conditions, expert/human obligations, current review readiness, and the preparation-only next action. Preserve applicable source/target gates and the existing Gate 2/Gate 3 semantics. Integrated QA and increment artifacts form one review candidate; do not require duplicate sets of reviews merely because there are two documents.

Choose techniques according to the actual behavior and consequence: unit, integration, contract, end-to-end, regression, property-based, fuzz, targeted mutation, security, performance, accessibility, visual, exploratory, human acceptance, specialist, migration, recovery and operational checks. Given/When/Then or Gherkin is an optional way to express an acceptance story when useful; do not mandate a BDD framework. Coverage and quality metrics are supporting diagnostic signals, never proof of correctness or substitutes for assertions. Do not produce a row for every test technique or force expensive techniques on low-risk documentary work.

For important claims, establish the expected result from approved requirements, trusted examples or a justified reference independent of the implementation under test. Legacy parity may demonstrate preservation, but not correctness of a deliberately changed rule. Identify material wrong behavior the check should detect; plan a failing regression demonstration or targeted mutation only when warranted. Review weakened assertions, broadened tolerances, skipped tests, removed cases and excessive mocking against the approved contract. Separate agents and green suites can share assumptions; retain independent review and explicit uncertainty.

For critical behavior crossing increments, designate the combined journey's owning increment/global obligation, relevant combined candidate/environment and required evidence. Component passes cannot establish an unexercised integration property. A software rollback cannot be assumed to reverse data disclosure, financial effects or other irreversible consequences. When release is in scope, retain the actual responsible human decision, specialist evidence and operational/recovery obligations. Implementation acceptance is not release readiness, certification, or legal assurance.

### Combined flow and exclusion semantics

- **Creation:** QA design is on unless the user explicitly excludes it. Inspect the selected sources and relevant project context, create/reconcile `qa-plan.md`, and incorporate its in-scope checks/owners into the feature increments. The QA document proposes verification; it cannot silently amend product requirements or source-required gates.
- **Exclusion:** a natural-language instruction such as “exclude supplementary QA design” omits that extra design/document, not meaningful feature tests, review scopes, specialist evidence, source/target gates, or required integration verification. Record the exclusion concisely. Do not introduce a CLI parser or configuration flag solely for this choice.
- **Standalone:** `qa-design` writes one requested `qa-plan.md`, with optional verbatim `source.md` for pasted input and scoped review notes. It does not manufacture an incremental plan. Its implementation work and copy-ready handoff are sections of the same document.
- **Combined outputs:** the incremental workflow may write `plan.md`, `handoff.md`, `qa-plan.md`, optional verbatim `source.md`, and scoped review notes. These are a single authorized artifact set. Reuse a selected current QA document when its sources/candidate still apply; do not generate a duplicate plan to satisfy the default.
- **Continuation/refinement:** preserve accepted history and human annotations. Reconcile the recorded QA choice, source changes, actual evidence and affected pending work. A new request to change QA mode authorizes only the corresponding planning revision, not past-approval reconstruction, new product behavior or gate waivers. Missing mandatory proof remains missing even with supplementary design excluded.
- **Changing on to excluded:** do not delete an existing QA artifact or source-required obligations. Preserve historical content and clearly identify what remains applicable and what supplementary proposal is no longer governing. No compatibility adapter, legacy schema reader or migration mode is required.
- **Ambiguity/failure:** unclear source/target/outcome, stale or contradictory evidence, material design choices, destination collisions, escaping symlinks or conflicting concurrent edits block affected claims/writes. Keep a useful pending draft where safe; do not silently omit QA, fabricate a pass or overwrite another person's work.

## Parts and increments

| Part / topic | Purpose | Ordered increments |
| --- | --- | --- |
| Verification design | Strengthen evidence decisions and deliver reusable standalone QA planning | I1 — Evidence quality at existing gates; I2 — Standalone QA design |
| Combined planning | Include QA in coherent increments by default, with explicit exclusion | I3 — QA-on incremental planning |
| Package identity | Present the completed combined capability as a first-version package | I4 — Rename and validate the combined package |

Dependencies: I2 and I3 reuse I1's canonical rules; I3 consumes I2's QA document contract; I4 depends on I1–I3. Review size follows these distinct acceptance stories, not file counts. Each increment includes its necessary instructions, consumers, documentation, safeguards and evaluation definitions; QA execution is not postponed into a final catch-all card.

## Source coverage

| ID / source locator | Obligation | Owner |
| --- | --- | --- |
| R1 — latest request and direct package decision | One renamed package with both independent entrypoints | I2, I3, I4 |
| R2 — latest request, default/exclusion | QA-on incremental conversion; explicit exclusion retains existing tests/gates | I3 |
| R3 — earlier user request, two uses | Standalone QA design and actionable implementation work from plan/project/both | I2 |
| R4 — earlier gate recommendation 1 | Failure consequence/reversibility drives proportionate verification and material questions | I1, I2 |
| R5 — earlier gate recommendation 2 | Independent expected outcomes, sensitivity, test weakening, correlated assumptions | I1, I2 |
| R6 — earlier gate recommendation 3 | Combined-journey evidence, residual uncertainty/owners and release separation | I1, I3 |
| R7 — earlier QA-design recommendation, techniques/output | Conditional technique selection, existing tooling/coverage, environment/data, actionable work | I2 |
| R8 — earlier QA-integration recommendation | QA obligations stay with their feature; shared work/combined journeys have owners | I3 |
| R9 — direct compatibility answer | First version; no aliases, migration framework or old invocation compatibility | I4; global exclusion |
| R10 — latest request, review sequence | First independent article-coverage review, then independent source, architecture and verification scopes | This plan's review workflow below |
| R11 — repository guidance and earlier planning-only design | Source fidelity, safe writes, user gates, explicit action permissions, no runtime machinery | All increments and handoff |
| R12 — earlier four evaluation proposals | Shared wrong assumption; weakened test; unverified integration; irreversible harm and proportionality | I1; Q01–Q04 |
| R13 — article's test/metric examples, interpreted proportionately | Optional Gherkin acceptance examples, coverage/quality metrics as supporting signals; no universal thresholds | I2; Q05, Q06 |

## Increment cards

### I1 — Evidence quality at existing gates

**Outcome/scope:** existing incremental plans and reviews demand trustworthy, consequence-appropriate evidence without new routine gates or supplementary QA documents yet.

**Prerequisites:** recheck current canonical instructions, gate policy, templates, actual dirty scope and this plan. No accepted predecessor is assumed.

**Owning files:** create `references/verification-design.md`; modify the incremental gate reference, both incremental templates, relevant procedure links in `skills/incremental-plan/SKILL.md`, associated guidance in `README.md`, and Q01–Q04 scenario definitions in `tests/scenarios.md`.

**Implementation work:**

- Put shared risk/verification principles in the guide, with conditional decisions and examples rather than universal technique quotas.
- At preparation/Gate 2, require material consequences, recovery limits, and selected evidence or unresolved questions within existing fields.
- Extend the verification reviewer brief to inspect independent expected results, material failure sensitivity and justified test changes. Preserve source and architecture scopes, fresh-context independence, expert obligations and existing permission semantics.
- At Gate 3/closure, require demonstrated behavior, relevant untested conditions and outstanding owners; preserve separate release obligations. Carry these rules into the handoff so executors do not need the package installed.
- Add Q01–Q04 raw fixtures and evaluator-only expectations alongside the behavior they protect. No source-text assertion tests.

**Acceptance/verification:** Q01–Q04 distinguish evidence quality from green labels; low-risk work receives proportionate checks. Existing C03, C06, C07 and C14 review/bypass/evidence/closure semantics remain intact. Run focused package/link/frontmatter checks as relevant; authorized behavioral observations, not prose inspection, establish model behavior.

**Human review focus:** selected checks must address the actual failure and may neither replace required reviews nor invent new business rules. **Safe intermediate:** the current planner remains usable with stronger evidence guidance; no unimplemented QA entrypoint/default is advertised. **Recovery:** preserve prior content and propose bounded reversal of this increment's edits if necessary; Git/destructive operations need separate authority. **Future impact:** confirm I2's output and I3's mapping reference the shared owner. **Gates:** preparation-only first, then Gate 2 and Gate 3; no bypass supplied.

### I2 — Standalone QA design

**Outcome/scope:** a user can request QA design and an implementation plan for a supplied plan, a current project or both, independently of incremental conversion.

**Prerequisites:** applicable I1 evidence/acceptance and current source/checkout correspondence.

**Owning files:** create `skills/qa-design/SKILL.md` and `skills/qa-design/assets/qa-plan-template.md`; extend the shared guide only for concrete technique/output decisions, the existing gate policy for standalone-vs-combined candidate review, `AGENTS.md` for the added workflow/canonical owner, `README.md` for actual new capability, `.codex-plugin/plugin.json` descriptions to match shipped skills, and Q05–Q09/Q14 in `tests/scenarios.md`. Keep the old package identity until I4 and do not claim installation.

**Implementation work:**

- Define discriminating frontmatter (`name: qa-design`): QA/test strategy and implementation planning activate it; “write tests”, “run E2E”, and implementation-only requests do not become planning assignments. Explicit invocation to execute explains the planning boundary without executing or inventing sources.
- Establish the authoritative outcome/source and selected target. In project mode inspect relevant user journeys, architecture/contracts, actual test assertions, fixtures, test scripts, CI, existing evidence and external boundaries using read-only tools. Do not execute imports, tests, package scripts, providers or infrastructure to discover coverage. Missing behavior/requirements are questions, not facts inferred solely from code.
- Implement the QA-design output contract above. Select useful techniques and independently justified expectations; propose additions only for material gaps. Plan safe synthetic data, environmental assumptions and isolation; do not retain secrets/private data in artifacts.
- Research current official documentation when recommending specific tooling/interfaces, using generic search terms and recording applicability; reuse current valid evidence. No private-source search/transfer or tool installation. Plan-only targets keep unsettled file paths/commands provisional for executor preparation.
- Produce one actionable `qa-plan.md`, optional exact pasted source and scoped notes. Use the existing gate/review semantics; a draft is useful without pretending reviews exist. Include a copy-ready preparation handoff inside the QA plan. Guard paths, symlinks, collisions and concurrent edits like the existing planner.
- Add representative raw fixtures for plan-only, project-only, both inputs, missing requirements, useful existing coverage, low/high consequence, and negative routing. Exercise conditional technique selection rather than checking for technique names in output.

**Acceptance/verification:** Q05–Q09/Q14 demonstrate appropriate selection, honest evidence boundaries and standalone output. The document identifies implementable work with meaningful assertions/dependencies and a correct preparation-only next action. Validate the new skill with the existing Skill Creator validator and all shipped links. No product file/test/CI change is a permitted QA-skill action.

**Human review focus:** observed coverage vs proposed coverage; appropriate tools/techniques and justified omissions; actionable work without a generic testing wishlist. **Safe intermediate:** standalone QA works while incremental planning remains pre-I3 behavior; metadata describes only implemented capabilities. **Recovery:** preserve user inputs and existing output content; no automatic deletion/install rollback. **Future impact:** freeze the QA artifact meaning for I3, not a schema/version service. **Gates:** Gate 2/Gate 3 and required review/evaluation authorization remain explicit.

### I3 — QA-on incremental planning

**Outcome/scope:** incremental conversion normally includes the QA design in the same coherent feature plan; explicit exclusion omits only supplementary design.

**Prerequisites:** applicable I1/I2 results and a current QA document contract. No cross-plugin invocation or separate installation is needed.

**Owning files:** incremental entrypoint, gate reference only where orchestration semantics require it, both incremental templates, QA entrypoint/template for the integrated return, `README.md`, relevant `AGENTS.md` scope guidance and Q10–Q13/Q15–Q16 in `tests/scenarios.md`.

**Implementation work:**

- Route default creation through the packaged QA procedure and shared guide, within the same authorized request. Read only the resources relevant to this mode. This is ordinary instruction composition, not an API, new task, execution engine or mandatory subagent.
- Extend the permitted artifact set and destination checks to include `qa-plan.md`. Record QA mode and the selected QA candidate/source identities concisely in the plan/handoff; no custom persisted state or receipts.
- Map QA checks/implementation work to owning increments/global obligations and existing source coverage. Keep feature behavior and its tests/docs/safeguards together. Create a distinct shared-testing prerequisite only for concrete shared work with a safe useful intermediate result; do not defer all QA or invent scaffolding solely to shrink cards.
- Reconcile an existing selected QA design before reuse. Surface material behavior/gate/scope changes, unsupported expected answers or contradiction with the primary source. Generated QA text cannot approve its own scope expansion.
- Implement default, exclusion, mode-change, continuation and stale-evidence semantics above. Re-read all authorized affected artifacts before writing; preserve human/accepted content and report partial or conflicting updates honestly. An excluded mode must not delete retained QA history.
- Review the plan and QA artifact as one substantive candidate through the three existing scopes; carry the resulting readiness and missing conditions into the current handoff.
- Update scenario output contracts: QA-on permits the additional QA artifact; explicit exclusion permits the original artifact set. Preserve isolated legacy C-case coverage by adding an explicit exclusion where the old case is testing only original planning semantics, and separately exercise representative C01/C19/C20 journeys with QA-on. Do not silently count old results as new QA-on evidence.

**Acceptance/verification:** Q10–Q13/Q15–Q16 plus representative C01/C19/C20 show default inclusion, meaningful mapping, correct counts/recap, safe exclusion/reuse/continuation and no product execution. Q03's critical combined journey has an owner and expected result on the relevant combined candidate. Required tests/gates remain visible in excluded mode. Focused checks while editing, then complete relevant checks once on settled inputs.

**Human review focus:** useful QA is incorporated into acceptance stories without duplicated plans/review rounds, unsafe splits or silent requirement changes. **Safe intermediate:** both flows work inside the existing package before identity changes; the active docs and artifact permissions match. **Recovery:** preserve all planning content and use bounded inspectable corrections; no automatic deletion or Git repair. **Future impact:** I4's descriptions/examples/routing claims must match this actual flow. **Gates:** unchanged Gate 2/Gate 3 and applicable expert/source/target obligations.

### I4 — Rename and validate the combined package

**Outcome/scope:** the complete source package presents itself as `incremental-and-qa-plan-plugin`, first version `0.1.0`, with both accurately documented entrypoints.

**Prerequisites:** applicable I1–I3 results; re-inspect manifest validation requirements and actual host support before concrete Gate 2 preparation.

**Owning files:** `.codex-plugin/plugin.json`, active naming/invocation/package sections of `README.md`, necessary current guidance in `AGENTS.md`, and Q17 in `tests/scenarios.md`. Audit current shipped instructions/resources for active old-name consumers. Preserve old design/implementation/evaluation documents as historical evidence, not compatibility infrastructure.

**Implementation work:**

- Set the manifest name exactly, preserve valid author/skills/interface metadata, and align descriptions, display name and prompts with incremental planning plus standalone QA design. Keep `incremental-plan` and `qa-design` as the two skill directory/frontmatter names.
- Document source examples for `$incremental-and-qa-plan-plugin:incremental-plan` and `$incremental-and-qa-plan-plugin:qa-design`, default QA-on and explicit exclusion. These are expected qualified invocation names until actually verified natively.
- Remove active claims that the old package's native acceptance proves the renamed package is installed/usable. Retain the dated historical evidence and describe new validation limits honestly. No alias, migration layer, new repository, directory/remote rename, old-plugin removal or configuration/cache editing.
- Update package inventory and canonical links. Verify all shipped referenced resources, both skill names/frontmatter and supported metadata using parsed package validation rather than source-string tests.
- Run the full relevant deterministic validation once on the settled source tree; reconcile all obligations against actual implementation evidence. Run authorized fresh-context behavioral evaluations against the final substantive candidate and retain applicability after the rename. If evaluation authorization is absent, report source validation and behavioral readiness separately; do not call unobserved behavior verified.
- Prepare, but do not execute, any separately requested native-install/activation work. New explicit/automatic routing, exclusion and negative execution cases require their own native evidence before installed-usability claims. Publication remains separate.

**Acceptance/verification:** Q17 and both validators establish source package integrity and no active stale names; Q05/Q10/Q11/Q14 are especially relevant final routing examples. Required behavioral evidence is actual observed output/action evidence. An unchanged tested tree is not rerun merely to collect another pass.

**Human review focus:** accurate identity/capability/evidence claims and first-version simplicity. **Safe intermediate:** identity changes only after both workflows are present; the installed old package and historical files remain untouched. **Recovery:** identify the exact source diff to reverse if authorized; no cache/config/repository mutation is implied. **Future impact:** native installation and release evidence remain external obligations. **Gates:** Gate 2/Gate 3; installation, live evaluations and publication have their own permissions.

## Verification design for this implementation

These are proposed checks, not passing results. `tests/scenarios.md` remains evaluator guidance, not an executable runner. Use fresh isolated actors and synthetic raw inputs; keep evaluator expectations and author/reviewer conclusions out of actor context. Capture candidate identities, prompts, actual actions/outputs, before/after files, result and limitations outside tracked source. Review dispatch authorized in this planning task does not authorize running these behavioral scenarios.

| Case | Raw situation to prepare | Observable evidence required | Owning increment |
| --- | --- | --- | --- |
| Q01 — shared wrong assumption | Source requires duplicate records; returned implementation/tests both deduplicate and are green | Planner/reviewer grounds expected results in the approved contract and identifies missing discriminating evidence | I1 |
| Q02 — weakened regression | A failing regression is made green by reducing assertions; include a separate justified contract-change variant | Unjustified weakening is challenged; a legitimate approved change is not automatically forbidden | I1 |
| Q03 — combined journey | Components have passing mocked tests but a source-required combined consumer journey is unexercised | Assign owner, expected outcome and combined-candidate evidence gap; no completion inference from component passes | I1, I3 |
| Q04 — consequences/proportionality | An irreversible data/financial effect has vague recovery; compare a trivial prose-only task | Surface the material missing safeguard/decision; no mandatory mutation framework or risk bureaucracy for the trivial case | I1 |
| Q05 — plan input | Bounded feature plan with clear outcomes, optional Given/When/Then examples, no code yet | Useful QA design and implementation work; independent expectations; conditional techniques and provisional implementation details | I2 |
| Q06 — project input and current coverage | Synthetic project with existing unit/integration checks, untested critical journey, metrics showing high coverage | Inspect actual assertions/tooling/CI; reuse useful coverage; select the material missing check without treating coverage as assurance | I2 |
| Q07 — conditional techniques | Small deterministic logic, malformed input boundary, real provider contract, load-sensitive path and visual/accessibility journey variants | Justified selection among property/fuzz/contract/performance/visual/accessibility/human checks; no automatic all-techniques suite or live calls | I2 |
| Q08 — missing/contradictory outcomes | Project code exists but source behavior is unclear or source and implementation disagree | Name affected questions/evidence; useful pending design where safe; no invented business rules or silent source replacement | I2 |
| Q09 — QA artifact boundaries | Pasted source, occupied output, escaping symlink, private sentinel, concurrent annotation and restricted write variants | Exact source preservation, permitted outputs only, no private data leakage, overwrite/delete or invented native race evidence | I2 |
| Q10 — default combined flow | Convert a source plan without mentioning QA | `plan.md`, `handoff.md`, `qa-plan.md` agree; QA has concrete owners/checks and tests stay with feature behavior; combined review remains pending until actual reports | I3 |
| Q11 — explicit exclusion | Same source with supplementary QA design excluded; source still mandates tests and an extra human gate | Omit new supplementary QA artifact; retain source-mandated tests/gate, meaningful acceptance, review scopes and honest evidence | I3 |
| Q12 — reuse/stale QA | Selected current QA design, then a source/candidate change affecting one requirement | Reuse valid evidence and resolve only affected mismatches; no duplicate QA plan or presumed blanket readiness | I3 |
| Q13 — continuation and scope growth | Actual saved generated artifacts with accepted history; new QA proposal changes a pending rule/gate | Preserve history, surface the material choice and same-increment preparation return; do not import approvals or expand product authority | I3 |
| Q14 — routing/execution negative | Direct/indirect QA-planning requests, “implement these tests”, “run E2E”, and explicit planning-skill execution requests | Correct planning selection; no execution or fabricated planning assignment; source routing evidence kept distinct from native activation | I2, I4 |
| Q15 — on to excluded | Existing QA-on plan plus human annotations; request exclusion | Preserve QA/history bytes unless an authorized edit is necessary; identify supplementary non-governing content and still-required obligations without deletion | I3 |
| Q16 — interrupted combined write | Partial plan/QA/handoff update or controlled native concurrent edit | Recover from facts and preserve human content; report unresolved conflict/partial state; no fabricated atomicity or race pass | I3 |
| Q17 — final package identity | Settled renamed source package and historical old-package receipts | Parsed manifest/frontmatter/link integrity; active docs use new identity, historical receipts do not imply new activation | I4 |

Reuse meaningful existing C03 source/architecture/verification traps, C06 gate/bypass limits, C07 changed evidence, C08 preservation, C11 preparation returns, C12 interruption, C14 closure, C15 routing, and C19/C20 coherence/recap cases where their tested inputs still apply. Test source-required certification and release obligations separately from achieved implementation. Never fabricate reports, approvals, RED/GREEN output or scenario results.

### Deterministic and native checks

Use the existing commands in `README.md#package-and-validation`, with host-discovered tool locations substituted; missing tools/dependencies are reported, not installed silently:

```sh
rtk proxy python3 -B <plugin-creator-directory>/scripts/validate_plugin.py <plugin-root>
rtk proxy python3 -B <skill-creator-directory>/scripts/quick_validate.py <plugin-root>/skills/incremental-plan
rtk proxy python3 -B <skill-creator-directory>/scripts/quick_validate.py <plugin-root>/skills/qa-design
```

Also inspect all shipped relative links and the actual diff for stale consumers, unnecessary complexity/duplication and private material. Use ordinary read-only host utilities, not a new runtime validator or tests matching instructional wording. Static checks establish package contracts only. Authorized fresh-context evaluation establishes observed source-level decisions/actions for named cases; native loading/invocation/discovery requires separate evidence on the target host. No evaluation or installation is run as part of authoring this plan.

## Decisions and completion criteria

Direct decisions available in this conversation: one combined plugin; exact new package name; QA-on with optional exclusion; no backward compatibility, first-version simplicity; planning plus multiple independent read-only reviews. No execution method, Gate 2/Gate 3 bypass, live-evaluation allowance, commit, installation or publication permission has been supplied.

This planning assignment is complete when the source-faithful plan and current handoff are saved, the independent article review is reconciled first, the three independent plan scopes are reconciled against the final substantive candidate, and real remaining limits/decisions are visible. It does not require implementing the package.

Future implementation completion must reconcile every R obligation with its owning increment's actual applicable checks/reviews and decisions, including authorized behavioral evidence where required. Source-only completion, behavior demonstrated for named cases, and native activation are separate claims. Mandatory missing evidence cannot be hidden by a routine gate bypass; separate release/certification obligations remain visible. No numeric score, number of reviewers, or green metric establishes overall safety.

## Concrete preparation for I1 — 2026-10-16

This supplemental preparation advances the first increment from a reviewed outline to a concrete candidate for Gate 2. The product design and I2–I4 scope above are unchanged. Implementation has not begun, and the user's instruction to iterate independent review supplies no Gate 2/Gate 3 bypass.

Baseline correspondence was rechecked: `main`, HEAD `bf0c2b19ab4e1e90170fae048824aec3f6da7356`; tracked product sources unchanged; this planning directory and the unrelated retention-plan document are untracked. Do not inspect or modify the unrelated plan during execution. I1 has no accepted predecessor requirement.

| Exact I1 file | Concrete change and review boundary |
| --- | --- |
| `references/verification-design.md` (create) | Four short sections: consequence/reversibility and material questions; independent expectations and justified test sensitivity; conditional technique/metric selection; combined evidence and residual owners. Preserve the already specified semantics, avoiding duplicated gate policy or an exhaustive test catalogue. |
| `skills/incremental-plan/SKILL.md` | Link the shared guide in “Craft the increments” when choosing acceptance/recovery and preserve the existing planning-only output permissions. Do not enable supplementary QA output or change routing in I1. |
| `skills/incremental-plan/references/gates-and-reviews.md` | Extend existing preparation/Gate 2, Gate 3/closure, and verification-review wording to demand the concrete evidence described in I1; link the shared guide. Keep existing approval, independent-review and specialist obligations. |
| `skills/incremental-plan/assets/plan-template.md` | Enrich existing acceptance/recovery fields with independent expected outcomes, material failure consequences and recovery limits. Give critical combined journeys an owner within current coverage/final-reconciliation fields. Add no schema, score or mandatory extra field hierarchy. |
| `skills/incremental-plan/assets/handoff-template.md` | Carry the applicable evidence questions and residual owners into the existing executor instructions/return evidence so the handoff works without the installed package. Preserve the two gates and separate action permissions. |
| `README.md` | Update only the package/reference inventory and the concise description of evidence quality actually delivered by I1; retain existing name and capability/activation limits. |
| `tests/scenarios.md` | Add the four raw inputs below and evaluator-only expectations, preserving the existing separation between actor inputs and expected answers. Keep original allowed outputs and original C-case fixtures for I1. |

The Q01–Q04 fixtures should use these discriminating values rather than merely mentioning techniques:

| Case | Concrete raw input / supplied evidence | Required distinction |
| --- | --- | --- |
| Q01 | Contract preserves records `[{id: 1, title: "Echo"}, {id: 2, title: "Echo"}]` for query `echo`; supplied candidate deduplicates, and its tests assert only distinct titles | Expected IDs are `[1, 2]`; a green supplied summary cannot establish the duplicate-preservation contract |
| Q02 | Same contract; original assertion `result_ids == [1, 2]` was weakened to `len(result_ids) >= 1`. Separate explicitly simulated amendment changes the contract to first record per distinct title | Challenge the weakening in the unchanged-contract case; permit a justified revised expectation only in the actual scoped-amendment variant, without manufacturing real approval |
| Q03 | Source requires the command to display both duplicate records and count `2`; supplied component results use mocks, with no command-to-search journey evidence | Name the missing combined check, expected IDs/count and owning increment; do not infer integration success from component summaries |
| Q04 | Source asks for a one-time financial effect across an interrupted retry, without specifying duplicate-prevention/recovery behavior; contrast a spelling-only document edit | Surface the consequential ambiguity and appropriate assurance/owner rather than inventing transaction rules; do not demand mutation tooling for the spelling-only case |

These are synthetic inputs/evidence variations to be authored, not performed tests or naturally observed failures. Any approval in a fixture is explicitly simulated and confined to that fixture. No application executes inside a planning actor.

Confirmed development-tool availability: `/Users/CoveMB/.codex/skills/.system/skill-creator/scripts/quick_validate.py` exists; its source was inspected, and PyYAML is available to `/opt/homebrew/opt/python@3.14/bin/python3.14`. After I1 edits, the available focused command is:

```sh
rtk proxy python3 -B /Users/CoveMB/.codex/skills/.system/skill-creator/scripts/quick_validate.py /Users/CoveMB/Code/CoveMB/incremental-plan-plugin/skills/incremental-plan
```

Also check that the new guide and all its consumers' relative links resolve, inspect the complete seven-file candidate against the baseline, and check preservation of unrelated files. These parsed/file-level checks are narrower than package or behavioral validation. The historical official Plugin Creator validator is absent; a targeted search of current skill/cache inventories found only other projects' validators, which are not substitutes. One searched application-resource path did not exist, so that search's exit status was `2`, not a complete application-bundle inventory. No validator or application test was executed during preparation, and no tool was installed. [Current official packaging guidance](https://developers.openai.com/plugins/build/plugins), checked 2026-10-16, still supports this repository's compatibility manifest; it does not establish a locally available validator.

This tool gap does not prevent authoring I1's instruction/resource changes, which do not alter the manifest. It remains an explicit package-acceptance evidence gap: rediscover the official validator on the execution host; if unavailable, do not claim a package-validation pass or silently waive a required check. Behavioral acceptance of Q01–Q04 and affected C-cases likewise needs separately authorized fresh-context evaluation after edits; its absence cannot become a model-behavior pass. Package/native readiness remains distinct from permission to begin implementation.

Recovery remains a bounded reviewable source diff, with no automatic Git or destructive operation. I2 consumes the same shared guide, I3 uses the same evidence ownership and handoff fields, and I4 retains the package-validation/native-evidence obligations. Preparation changes no future card, interface, sequence, product scope, or QA default; no material design decision has been introduced. A final independent readiness review must check this preparation and its limits before the handoff presents I1 for Gate 2.

## Progress and review readiness

Everything above this heading is the substantive plan candidate. Content from this heading onward records administrative progress/review reconciliation; changing only these records does not imply that substantive scope was re-reviewed. Review reports identify both the full file and the substantive prefix SHA-256 they inspected.

| Increment | Factual status | Candidate/evidence | Approval or bypass | Next action |
| --- | --- | --- | --- | --- |
| I1 | Concrete preparation independently reviewed; not implemented | I1 card, supplemental preparation and readiness report | None | Gate 2 approval of the concrete seven-file candidate |
| I2 | Proposed, not implemented | This saved plan; no implementation evidence | None | Wait for applicable I1 result |
| I3 | Proposed, not implemented | This saved plan; no implementation evidence | None | Wait for applicable I1/I2 results |
| I4 | Proposed, not implemented | This saved plan; no implementation evidence | None | Wait for applicable I1–I3 results |

| Review stage/scope | Actual reviewer/report | Candidate/disposition |
| --- | --- | --- |
| First: article coverage | `/root/article_coverage`; [report](review-article.md) | Same substantive candidate; no material omissions or overstatement found |
| Then: requirements/source fidelity | `/root/plan_source_review`; [report](review-source.md) | Same substantive candidate; no material improvements recommended |
| Then: architecture/reviewability/simplicity | `/root/plan_architecture_review`; [report](review-architecture.md) | Same substantive candidate; no material improvements recommended; built-in simplicity substitute, Ponytail not requested/run |
| Then: verification quality/test evidence | `/root/plan_verification_review`; [report](review-verification.md) | Same substantive candidate; no material improvements recommended; proposed-check design only |
| Iteration requested afterward: implementation readiness | `/root/implementation_readiness`; [report](review-readiness.md) | Current substantive candidate; ready for Gate 2, no material improvements recommended; unchanged original design evidence retained |

Review sequence: freeze the candidate; commission the fresh-context article reviewer read-only, reconcile supported omissions and renew affected review if materially changed; then commission three distinct fresh-context plan scopes against the settled candidate. Reviewers receive raw inputs, relevant repository context and exact candidate, not the author's verdict or other reports. No recursive delegation, product execution, mutation or external comments. Renew only affected reviews after a material correction. User-requested multiple scopes apply to this planning task; no repeated unchanged review rounds are requested.

Review reconciliation, 2026-10-16: the article reviewer completed first and its report was reconciled before the three plan scopes were dispatched. All four were fresh-context, distinct read-only assignments; later reviewers were not given the article verdict, author conclusions or each other's reports. The controller checked the cited coverage/ownership against the raw requirements and candidate. No substantive corrections were required; no unchanged scope was repeatedly reviewed. Actual report limitations remain visible.

Original reviewed full-file SHA-256: `32f2cb98fad38147f47e519081693b85a9f8516dc7d5b12e5412961d8b8e6f9a`. Original reviewed substantive-prefix SHA-256: `15d31dd8deb4f964c5e9e0e68cfe2550fc4d77b905fdba5756f3693b53c675d0`. At the end of those four reviews, only administrative review records and handoff readiness were updated. The later supplemental I1 preparation is a new bounded review scope; the original product-design sections remain unchanged. Primary-source SHA-256: `82399fff11614c16355df8a598bb060d8f0a37222969b307ac2447b4fc6e8ef8`; review-inputs SHA-256: `847983539b97ec74b388ff34b81ed14b1ff38500e9e27da01a4e0063303243f1`.

The user subsequently requested: “iterate independent review until ready for implementation.” This authorizes further independent readiness review and bounded planning corrections, not implementation or a gate bypass. Concrete I1 preparation was added and reviewed in a new fresh context, without supplying earlier verdicts. The reviewer independently confirmed the starting scope, acceptance protections and tooling limits, and found no material readiness defect. No repair or additional unchanged review cycle is warranted.

Current reviewed full-plan SHA-256: `918ab1075c451bd7ed5b66899be22c9150e4bfa800446e5e6a8c0d2bba1b93eb`. Current reviewed substantive-prefix SHA-256: `12297c96428d79716c3d6174656f9fa4b4fb579e6274a4f626d706622b39cdeb`. Only administrative readiness records and the handoff were updated afterward. The original product-design prefix and exact primary source remain unchanged.

Readiness: the implementation plan and concrete I1 starting scope are ready for Gate 2; implementation approval has not been given. I2–I4 retain their accepted-predecessor preparation boundaries. The missing official package validator remains a future package-acceptance evidence gap, not a passed check or a blocker to I1 instruction/resource editing. No package validators, application tests, behavioral scenarios or native activation were run. Unrelated work remains unmodified.

Next action: Gate 2 approval of the prepared I1 candidate using the [current handoff](handoff.md), retaining Gate 3 and separate evaluation/external-action permissions. Review iteration is complete unless relevant inputs change or a new material defect is evidenced.
