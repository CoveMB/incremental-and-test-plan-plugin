# Source conversion — Gate 2 implementation plan

Date: 2026-10-12. Candidate: Task 1, source conversion. Status: Task 1 accepted at Gate 3 on 2026-10-12; Task 2 preparation is next.

For the implementer: after approval, implement this bounded scope natively, using `superpowers:executing-plans` when available. The reviewed design and implementation plan remain authoritative. This document builds the plugin; it does not invoke the proposed plugin to implement another product. Stop at Gate 3 after verification and independent implementation reviews.

## Outcome and coherent boundary

Implement Task 1 of the reviewed plan: convert one authoritative local or pasted source into a source-faithful **draft incremental plan**, with a concise recap and a clearly bounded planning handoff. Each card identifies one feature and its coherent contribution, preserves coupled behavior/tests/documentation/safeguards, and has one understandable acceptance story. An entire small feature may remain one card when splitting would worsen safety or review.

Metadata, instructions, the plan template, usage documentation and behavioral scenarios belong together because they establish and test this one source-conversion behavior. Do not split packaging, tests or necessary documentation into separate build increments. Do not bundle Task 2's complete review/handoff workflow or Task 3's continuation into this increment.

This is the intentionally incomplete, safe intermediate state described in Task 1's completion criterion. Generated drafts must retain outstanding plan reviews and decisions; they must not claim implementation readiness, accepted work, approval or completed verification. Unsupported continuation/revision/completion requests receive a truthful limitation without modifying existing plans. The README and discovery description must describe only the current capability. Native plugin activation remains unverified.

## Authorities and inspected baseline

Target: `/Users/CoveMB/Code/CoveMB/incremental-plan-plugin`.

Read these sources in full before implementing:

- `/Users/CoveMB/Code/CoveMB/implementation-plugin/docs/superpowers/specs/2026-10-11-incremental-plan-plugin-design.md` — SHA-256 `22d90101991efaf3045b6f8048e4b75afd238721c8488e4e860d14b99bac6207`.
- `/Users/CoveMB/Code/CoveMB/implementation-plugin/docs/superpowers/plans/2026-10-11-incremental-plan-plugin.md` — SHA-256 `3cb2cfe4d6f33bfb34dfe35b3080339ce463665bd16bb0a0f60e8eaf590c08ad`.

The specification owns behavior; its implementation plan owns the four-task sequence and acceptance matrix. Reuse its independent design review; no redesign is proposed here.

Current target facts:

- The directory already exists, is not a symlink and is a separate Git repository.
- Branch `main` is unborn: no commits, staged files or base revision. No `origin` URL is configured. No fetch is needed.
- Existing user files are untracked `.gitignore` and `AGENTS.md`. During inspection, the initial `AGENTS.md` forwarding to `AGENTS.txt` was replaced externally by the same substantive guidance directly in `AGENTS.md`; `AGENTS.txt` is now absent. Preserve that current layout; do not recreate the removed file.
- Current `.gitignore` SHA-256: `0ab55b4cc11c8f7b761159ebd61bbe558a06f4dda33d8777f2f4a02dd5a28633`.
- Current `AGENTS.md` SHA-256: `f82bf2c2013330f3d6e502942dabd2c86235f947923e231a63ba93a88fb5900f`.
- Follow target `AGENTS.md` and the user's supplied repository rules and `/Users/CoveMB/.codex/RTK.md`. Prefix shell commands with `rtk`; use `rtk proxy` for exact output.

The old implementation-plugin remains at local `main`, `18a77af3f1fea552401bcc2c9a3959dbcb97d684`, with three untracked planning documents: the two sources above and `docs/superpowers/plans/2026-09-16-successor-operation-envelope-repair.md`. Its tracked diff and index are clean. Preserve all of it; do not stage or copy the September plan. Local remote refs were not refreshed.

Comparison for review: all new files in the allowlist below, including untracked content, against this existing-file baseline. Ordinary `git diff` alone cannot show this candidate. Inspect the complete new files and inventory; do not invent a base commit or stage files to make them visible. Re-read current instructions, status and source identities before any write and reconcile concurrent changes first.

## Current official documentation and local tooling

Checked 2026-10-12:

- [OpenAI plugin packaging](https://developers.openai.com/plugins/build/plugins): portable root manifests are recommended for portable packages; `.codex-plugin/plugin.json` and the built-in creator remain supported. Retain the reviewed Codex-only layout; there is no compatibility requirement to reopen that decision.
- [OpenAI skill authoring](https://developers.openai.com/plugins/build/skills): instructions and resources can stand alone without an MCP server; put procedure in the skill and templates in assets. Test direct, indirect, incomplete and unrelated requests.
- [Current host skill guidance](https://learn.chatgpt.com/docs/build-skills): discovery depends on name/description; optional UI/dependency metadata is unnecessary here. Document no unverified qualified invocation as proven.
- [OpenAI skill evaluation](https://developers.openai.com/blog/eval-skills): assess observed actions and saved outputs. Use existing host fresh-agent tools and disposable artifacts; do not add an evaluation framework.

Inspected installed creator and validators, including their argument interfaces. Local Python is 3.14.6 with PyYAML 6.0.3 available. These are development tools, not plugin dependencies. The bundled validator requires `author.name` and interface fields beyond the minimal documentation example. Use the scaffold's supported `Local developer` author/developer label, without inventing a person, license, contact details or public URL.

The target is outside this thread's writable roots. After Gate 2 approval, request the platform's scoped write permission for the approved files as needed. No target write has been attempted during preparation.

## Exact allowed changes

Paths are relative to the target repository. All are new; any collision stops the affected write.

| Path | Change and acceptance responsibility |
| --- | --- |
| `.codex-plugin/plugin.json` | Valid Codex metadata, version `0.1.0`, name `incremental-plan-plugin`, `skills: "./skills/"`; describe draft source conversion. Use required scaffold interface fields with accurate Read/Write capabilities limited by the skill. |
| `skills/incremental-plan/SKILL.md` | Frontmatter name `incremental-plan`; narrow create-draft trigger and implementation-only exclusion. Own source selection, inspection, fidelity, coherence, write boundaries, uncertainty, recap and current limitations. |
| `skills/incremental-plan/assets/plan-template.md` | Field structure with concise explanations: purpose/non-goals, sources/identity/baseline, parts, requirement mapping, increment cards, factual progress, decisions and reconciliation. Unknown future evidence remains unknown. |
| `README.md` | Actual Task 1 behavior, ordinary source-level use, boundaries, validation, current limitations and remaining Tasks 2–4. Installation is a separately authorized later action. |
| `tests/scenarios.md` | Synthetic inputs, prompts, allowed writes and observable expectations for the initial C01/C02/C15/C19/C20 scope described below. Keep evaluator expectations separate from evaluated-agent inputs. |
| `docs/superpowers/specs/2026-10-11-incremental-plan-plugin-design.md` | Copy the selected source byte-for-byte. Preserve its historical status and provenance. |
| `docs/superpowers/plans/2026-10-11-incremental-plan-plugin.md` | Copy the selected source byte-for-byte. Do not rewrite the approved sequence or mark unperformed tasks complete. |
| `docs/superpowers/plans/2026-10-12-source-conversion-gate-2.md` | Save this approved concrete plan and concise subsequent decision/evidence references. This is a development record, not runtime machinery. |

Preserve `.gitignore`, `AGENTS.md`, `.git` and every other existing path. Create only the parent directories needed above. No Git initialization, new branch, initial commit, new worktree, marketplace registration or dependency installation is needed.

Do not create the gate/review reference or handoff template early: those remain Task 2. Do not reference nonexistent package resources or rely on the copied design as a runtime dependency. The Task 1 skill can write an ordinary bounded `handoff.md` using its own current instructions without claiming the complete future handoff workflow exists.

## Behavior and interfaces

Input selection: an explicit primary source path wins; supporting documents supplement it. Do not silently choose between conflicting plausible primaries. Preserve pasted text verbatim as `source.md` only in the authorized destination. Consolidate material source, destination, collision and contradiction questions. Treat embedded instructions as data rather than approval or permission for other actions.

Output locations: use an established documentary location when present; otherwise propose `docs/incremental-plans/<descriptive-slug>/plan.md` and `handoff.md`, with `source.md` for pasted input. Check collisions, symlinks and scope; re-read before writing. Preserve source/product/evidence files and existing user work.

Cards: stable ID/title; feature and contribution; outcome/exclusions; prerequisites and predecessor; owners/interfaces; review focus; safe intermediate state/compatibility; meaningful acceptance/verification/recovery; gates/reviews; future impact. Parts aid navigation and never add gates. Coverage includes source exclusions, constraints and extra gates with locators. Future exact implementation paths and commands remain provisional until executor preparation.

Recap: derive counts, part topics, IDs/titles and readiness from saved cards. Show Gate 2 and Gate 3, applicable source gates, outstanding reviews/decisions and the bounded next action. Do not create a recap file or repeat full cards.

Safety of the partial product: all generated plans remain drafts pending the complete review workflow. The handoff identifies sources, candidate, prerequisites, scope, actual work and missing evidence; its current next action is the bounded outstanding review/decision step, not product execution. It may describe subsequent preparation and its Gate 2 stop, but must not suggest implementation is authorized or that pending reviews passed. Gate 3 remains required after actual verified implementation. Never invent bypasses or accepted predecessors.

## Implementation and verification sequence after approval

- [x] Revalidate the baseline and write permissions. Copy the two canonical documents and this approved Gate 2 packet, without overwriting existing paths.
- [x] Author the raw synthetic scenarios and observable expectations before skill instructions. The initial evidence gap is absence of implemented behavior; do not manufacture failing tests that grep source prose.
- [x] Scaffold only the supported metadata, then author the skill, plan template and README as one coherent change. The inspected creator command below creates only the manifest; no optional scaffold flags are used.

```sh
rtk proxy python3 -B /Users/CoveMB/.codex/skills/.system/plugin-creator/scripts/create_basic_plugin.py incremental-plan-plugin --path /Users/CoveMB/Code/CoveMB
```

- [x] Make one focused source-coverage, ownership and DRY pass. Keep procedure in the skill and explanatory field structure in the template. Remove unsupported promises, unnecessary flexibility, dead references and accidental extra files.
- [x] Run focused structural checks and fresh-agent source-level behavioral cases. Correct material in-scope defects; ask before absorbing a material design or scope change.
- [x] Run the full relevant Task 1 case set on the settled candidate. Reuse unchanged valid evidence; do not repeat passing cases without changed inputs or a concrete concern.
- [x] Freeze a readable inventory and content identities for all candidate files, including untracked additions. Obtain the three required independent implementation review assignments below, reconcile findings and renew only affected evidence.
- [x] Presented the Gate 3 packet and obtained direct result approval. Task 2 implementation requires its own Gate 2 approval.

### Planned behavioral checks

Use native host subagents with fresh contexts, no recursive delegation, synthetic data and explicitly isolated disposable directories under `/private/tmp`. Gate 2 approval of this plan includes these bounded live-model evaluations. Do not use an external review service, API credential, private client plan or installed-plugin mutation. Agents receive the relevant source skill/resources and fixture prompt, not expected answers. Preserve prompts, actual output, action evidence and before/after file inventories in temporary evidence; inspect changes independently of agent claims.

| Case | Initial Task 1 exercise and success evidence |
| --- | --- |
| C01 | A synthetic local search/index/query plan plus supporting specification, explicit exclusion and source-defined acceptance gate. Preserve all source obligations and existing search behavior; use coherent dependencies and safe intermediates; write only planning artifacts; retain draft/review status and no implementation authority. |
| C02 | Pasted source is saved byte-for-byte. Separate conflicting-primary and occupied-destination cases ask the consolidated material question and leave existing bytes untouched. Include a symlink escape as a destination-preservation check. |
| C15 | Source-context explicit and indirect planning prompts select the create route. An adjacent implementation-only request does not take over the workflow or create planning artifacts. A planner-invoked request to execute product work does not edit product code. These are source-level routing/boundary observations, not native discovery proof. |
| C19 | A larger naturally grouped source contains distinct features, a small indivisible feature, coupled contract/caller work and required tests. Outputs separate independent outcomes and keep coupled behavior/tests/safeguards whole. No arbitrary increment count, file/line quota, unused interface or invented temporary adapter. Each card has an acceptance story assessable without future repair work. |
| C20 | For ordinary and larger drafts, recap counts/topics/IDs match saved cards, gates and pending review are explicit, next handoff is appropriate, and no duplicate recap artifact or approval stage appears. |

C19's actual executor preparation-return and C20's reviewed/revised-plan variants remain for Tasks 2–4, as the canonical matrix explicitly states. C15's installed explicit/automatic activation also remains open. Report these as partial case-family coverage, never a blanket pass of the full C01–C20 matrix. No product execution or full-chain continuation is part of this increment's evaluation.

Structural checks on the settled source candidate:

```sh
rtk proxy python3 -B /Users/CoveMB/.codex/skills/.system/plugin-creator/scripts/validate_plugin.py /Users/CoveMB/Code/CoveMB/incremental-plan-plugin
rtk proxy python3 -B /Users/CoveMB/.codex/skills/.system/skill-creator/scripts/quick_validate.py /Users/CoveMB/Code/CoveMB/incremental-plan-plugin/skills/incremental-plan
```

Expect `Plugin validation passed` and `Skill is valid!`, respectively. Also inspect package-relative resource resolution, exact skill-directory/frontmatter agreement, manifest paths, document-copy equality, the full added-file inventory and whitespace in new files. Preserve existing target bytes and the old repository's tracked/untracked bytes. Use ordinary one-off host checks; add no product runner or tests that merely match normative phrases.

### Independent reviews

After implementation, use three distinct read-only assignments independent of the author, as required by the selected design and the user's request. Sequential execution is sufficient; these are separate scopes on one candidate, not repeated broad final reviews. Each receives the raw canonical sources, this approved scope, target instructions, exact candidate inventory/content identities and applicable actual evidence; no inherited author conclusions, recursive delegation, edits or external messages.

1. Requirements/source fidelity: all Task 1 obligations, exclusions, partial-product boundaries and copied-source preservation.
2. Architecture/reviewability/simplicity: coherent single-feature cards, safe draft boundary, tightly coupled changes, self-contained package, recovery and absence of unnecessary machinery. Explicitly label **Substitute simplicity review; Ponytail not run — not authorized**.
3. Verification/test evidence: actual behavioral outputs/actions and assertions, forbidden-write checks, candidate applicability and honest native/full-matrix limitations.

Validate retained findings against the current artifacts. Ordinary in-scope corrections from these reviews are included. Any new material design question returns to the user; re-review only affected scopes after corrections. Missing independent capability or evidence remains pending and prevents a verified-result claim.

## Future impact, recovery and Gate 3 evidence

No change to the reviewed Task 2–4 responsibilities, sequence or architecture. Task 2 will add the canonical gate/review reference and reusable handoff template, replacing superseded interim explanations rather than layering conflicting rules. Task 3 adds continuation/revision/closure; Task 4 owns complete scenario and native activation acceptance. Task 1 outputs must use the designed fields so later tasks can consume them without a new schema or compatibility engine.

There is no installed user population, persisted execution state or migration in this scope. Existing files and the old plugin remain intact. Recovery is to stop using the uninstalled candidate and retain the evidence; removing new files, installation changes or resetting Git would need separate authorization. Do not delete artifacts automatically.

Gate 3 presentation must identify the exact uncommitted candidate, changed-file inventory, source-copy and preservation evidence, actual scenario outcomes and scope limits, validator outputs, all three reviewer dispositions, unresolved obligations and next eligible work. Native activation status must read **not tested; installation not authorized**. Validation does not prove native usability, planning quality in every setting or completion of the whole plugin.

Approval sought: Task 1 implementation and the exact local setup, synthetic behavioral evaluation and independent reviews above, followed by a Gate 3 stop. No commit, push, PR, installation, publication, old-plugin replacement, Ponytail invocation or bypass of either gate is included.

## Execution record

- 2026-10-12: the user directly replied “Approved” to this Gate 2 package. Approval covers Task 1, bounded synthetic evaluations and the three independent reviews; Gate 3 remains required. The displayed approval candidate is preserved in the preparation artifact with SHA-256 `8a73d1ef9ea9118a0b3a1c809fae172a2532bc9179e134bebe2905a55b5c5baf`.
- Revalidation: target `AGENTS.md` was shortened externally after preparation, with the same applicable product, authority and verification requirements. Current pre-implementation SHA-256: `33c6c822229bb368d7e3adb9fd97c6e99c17db231c2d34274b53c776c2d2c482`. Preserve it unchanged; the earlier hash is historical. Target remains unborn `main`; no Git setup is required.
- Implementation uses the approved native sequence. General execution-skill suggestions to create worktrees/ledgers, commit or continue later tasks are superseded by this bounded scope. No such machinery or Git action is included.

## Gate 3 result — 2026-10-12

The following packet records the presentation state; the subsequent acceptance is recorded below.

Task 1 source conversion is implemented and verified within the approved scope. **Awaiting direct user Gate 3 approval.** No Task 2 work has started. The two canonical documents remain byte-identical historical copies; their original task checklists are not rewritten.

The candidate contains exactly the eight additions in the allowlist above. The five product/scenario files deliver one coherent source-to-draft behavior: supported metadata, one instruction skill, its explanatory plan template, usage documentation and behavioral scenarios. There is no executable runtime, custom state machinery, gate/review reference or reusable handoff template in this increment. Existing target `.gitignore` and `AGENTS.md` are unchanged from the execution baseline. Target remains uncommitted, unstaged, unborn `main`; no remote is configured.

### Actual checks and outcomes

Both planned bundled validators exited successfully on the unchanged manifest/skill inputs. Original stdout was `Plugin validation passed: /Users/CoveMB/Code/CoveMB/incremental-plan-plugin` and `Skill is valid!`. Parsed and file-level checks confirmed package paths, skill naming, shipped resource links, exact allowed inventory, copied-source equality and clean whitespace. These structural checks do not establish model behavior or installed usability.

Nine isolated source-level cases were observed, plus one bounded read-only follow-up:

| Observation | Actual result |
| --- | --- |
| C01 local source with supporting specification | One part, two coherent increments; source requirements, exclusion, extra gate and pending reviews retained. |
| C02 pasted source | One part, one indivisible increment; existing behavior reused; the 417-byte source was preserved exactly, including its final newline. |
| C02 ambiguous primaries | Initial response requested source selection and wrote nothing. A separately recorded follow-up read both sources, explained matching/order conflicts and unresolved obligations, and chose neither. |
| C02 occupied destination | Existing human draft preserved; decision requested before writes. |
| C02 escaping symlink | Destination refused without following it to write outside scope; existing link and sentinel preserved. |
| C15 indirect planning request | Source-context route selected; one part, two increments and a bounded draft handoff produced after explicit path-specific permission. |
| C15 unrelated implementation request | No planner takeover or planning artifacts. |
| C15 planner-invoked execution request | Planning boundary explained; no product edits or application tests. |
| C19 larger source | Three parts, four increments; independent features separated, contract/caller work and whole small features retained with necessary tests and safeguards. |

C20 recap checks covered all four saved positive drafts: their counts, topics and IDs matched saved cards; pending reviews and applicable gates remained visible; no separate recap file appeared. All generated plans remain drafts, not approved implementation instructions.

The C15 write was rejected twice by automatic approval review; both attempts remain recorded as nonpasses. The user then directly authorized only its `plan.md` and `handoff.md` in the named fixture. The same write method succeeded after that approval. No workaround was used.

All 38 original fixture files/links retained their identities; exactly nine planning artifacts were added. All 333 tracked/nonignored old-repository files and its inventory matched the baseline. Both pre-existing target files matched their baseline. Original action receipts were independently inspected and showed reads plus authorized planning writes, with no application execution or external actions in the evaluated runs.

### Independent review dispositions

Three distinct read-only reviewers assessed the same candidate, with the requirements reviewer reconciling only the added conflict-comparison observation and completed C15 evidence:

- Requirements/source fidelity: **No material improvements recommended.** The initial C02 evidence gap was resolved by the bounded follow-up; initial evidence alone is described only as no-guess/no-write behavior.
- Architecture/reviewability/simplicity: **No material improvements recommended. Substitute simplicity review; Ponytail not run — not authorized.**
- Verification/test evidence: **No material improvements recommended.** Original validator/action receipts matched native records; outputs, write scope, preserved bytes and candidate applicability were checked independently.

No material product defect remains open in these scopes. One test-documentation addition records the C02 follow-up; no skill/template change or broad rerun was needed.

### Evidence identity and limits

Local evidence root: `/private/tmp/incremental-plan-task1.np1rXt/`. It contains raw prompts, fixture sources and outputs, responses (including rejected attempts), baseline and output hashes, original action/validator receipt extracts, and the three review reports. These temporary development artifacts are not plugin runtime files and are not published.

The reviewed eight-file inventory is `candidate-files.sha256`, SHA-256 `8835c9dc57af2676311aabf809eb7541bbb9ee729b04331bc302d138b8373661`. After those reviews, only this development record's status, checklist and result section were updated. The seven other candidate files remain at their reviewed identities. `final-candidate-files.sha256` records the resulting complete Gate 3 candidate; `final-preservation-checks.txt` records the final scoped comparison.

The reviewer independently matched all nine action-receipt sets and original validator output to native records. The host stores original fresh-agent assignment envelopes encrypted; fresh-context/rubric separation is controller-attested, not independently established from those envelopes. Raw prompt files and observed actions remain inspectable. No claim of blind experimental validation or universal planning quality is made.

Native activation: **not tested; installation not authorized**. This evidence covers the initial Task 1 portions of C01/C02/C15/C19/C20 only. Full gate/review execution, revision, continuation, interruption recovery, complete matrix acceptance and native discovery remain later tasks. No commit, push, PR, installation, publication, old-plugin replacement or Ponytail invocation occurred.

The pending decision is Gate 3 acceptance of this bounded result. The next eligible work after acceptance is preparation of a concrete Task 2 Gate 2 plan; acceptance alone does not authorize Task 2 implementation or any Git/external action.

## Gate 3 acceptance — 2026-10-12

The user directly replied “Approved” to the Gate 3 request for this Task 1 result. This accepts the eight-file candidate identified by `final-candidate-files.sha256` (inventory SHA-256 `17218fdba181d446061a6ba9e25eaa30e8fb1054feb6f3b5857d645431b75774`), including this record at SHA-256 `a9a8e9605336f5199f414288c17052f70f6e6b083155a0b54504905b26cc203b`. All eight candidate files and both original target files matched their recorded identities before this acceptance note was added.

Task 1 is an accepted, identifiable uncommitted predecessor. The next work is concrete Task 2 preparation; its implementation remains behind a new Gate 2 approval. This acceptance does not authorize commits, pushes, PRs, installation, publication, replacement of the old plugin or an actual Ponytail invocation. The recorded evidence limitations remain unchanged; no verification rerun is implied by this administrative update.
