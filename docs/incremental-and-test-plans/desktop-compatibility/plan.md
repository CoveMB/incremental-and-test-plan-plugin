# Desktop Compatibility Implementation Plan

**Archive context (2026-11-04):** This is the reviewed desktop-only proposal from 2026-10-28. Its original text below records planning-time status and permissions, not current pending work. The later desktop and CLI implementation is present in commits `5266f7e` and `87bf9d5`, merged into upstream main at `abbef5a`. Current package guidance lives in the [development guide](../../development.md); native acceptance is defined separately in `tests/native-acceptance.md`. This reconciliation performs no native evaluation and establishes no desktop or CLI acceptance. Preserve the original proposal and review identities as historical evidence rather than restarting their tasks.

> **For agentic workers:** This is ordinary repository development planning. Use the established execution workflow with one sequential writer; no additional planning or execution plugin is a dependency. Read the scope, permissions, verification, and current review record before implementation.

**Status:** Implementation-ready after three independent plan reviews, 2026-10-28; no unresolved material findings. Implementation has not started and requires a separate instruction. Review evidence and candidate identities are recorded in [plan-review.md](plan-review.md).

**Goal:** Make the existing planning skills usable through OpenCode v2 Desktop and the standalone Antigravity IDE while preserving Codex support and existing planning behavior.

**Architecture:** Maintain one canonical pair of Markdown skills and their shared resources. Add a small shared host-compatibility reference, an Antigravity manifest, and desktop-specific setup instructions. Use native skill discovery and existing manual handoffs; introduce no executable extension, orchestration engine, or runtime dependency.

**Tech stack:** Existing Markdown instructions/templates, JSON manifests, native desktop skill loading, existing static validators, and separately authorized synthetic desktop evaluations.

**Spec:** The direct user requests in this chat: “carefully review current project and opencode v2 and antigravity documentations we want to make this plugin/skills/project compatible with OpenCode v2 and Antigravity”; subsequently “Assessment and proposal only but for desktop apps,” selecting the standalone Antigravity IDE; and now “make a implementation plan for this support and independently review and fix until ready for implementation.” The contract below makes the proposed support concrete. This request authorizes planning-document writes and independent plan reviews, not product implementation, installation, or live skill evaluations.

## Scope and evidence

Target OpenCode **v2 Desktop** and **standalone Antigravity IDE**, retaining Codex. Exclude OpenCode v1, Antigravity App/CLI-specific integration, marketplaces, remote catalogs, automatic installation/update, and an OpenCode desktop UI extension. A skill bundle need not appear as an executable OpenCode plugin in its Extensions panel.

Planning inspected local `main` at `444648a2c8e891a3475a643a77cdfe0c4e2a2fae`; remote refs were not refreshed. Protected existing work: modified `docs/development.md` and `tests/scenarios.md`, untracked `tests/live-evaluation.md`, and `docs/incremental-and-test-plans/continuation-evidence/`. Reinspect and coordinate overlapping files before implementation; do not restore these files to this baseline or resume that separate effort. This plan and its review record are development records and never ship in the runtime bundle.

Application bundle metadata observed during assessment: OpenCode `2.2.0`, Antigravity `2.28.0`. These identify installed applications, not tested compatibility or minimum supported releases. Recheck actual product/surface, version, connection/server context, permissions, and loaded candidate before native acceptance. Initial support claims must name the versions actually exercised; do not advertise all v2 releases or other operating systems from one macOS run.

Current source assessment: two valid skill entrypoints, ten declared runtime files, and 69 resolving package-resource links/anchors. One template link intentionally names generated `handoff.md`. Ten entrypoint references leave their individual skill folders. Copying each skill independently would lose sibling/shared resources. These are static observations, not installed-use results.

### Documentation basis

Official sources inspected on 2026-10-28; reuse only while applicable to the actual implementation/test environment. Generic documentation queries must contain no private source or personal paths.

| Source | Decision supported and limit |
| --- | --- |
| [OpenCode v2 skills](https://opencode.ai/v2/docs/skills/) | `skills` is an array of source directories; `@skill-id` explicitly loads a skill. IDs derive from paths; resources are relative to the skill base. Configured relative skill paths resolve from the working directory. Duplicate IDs and skill/read permissions matter. |
| [OpenCode v2 configuration](https://opencode.ai/v2/docs/config/) and [desktop plugins](https://opencode.ai/v2/docs/plugins/#desktop) | Configuration belongs to the serving OpenCode environment. This package needs skill loading, not a GUI plugin. A remote server must not be assumed to see local Mac paths. |
| [OpenCode v2 agents](https://opencode.ai/v2/docs/agents/) | Native subagents have fresh contexts, subject to host permissions. Documentation alone does not prove every required owner/resumption/messaging operation works in a particular desktop session. |
| [Antigravity skills](https://antigravity.google/docs/skills) | IDE skills use workspace `.agents/skills/` or global `~/.gemini/config/skills/`; discovery and activation are separate. Do not copy App/CLI-only slash-command claims into IDE instructions. |
| [Antigravity plugins](https://antigravity.google/docs/plugins#standalone-ide-plugin-installation) | A root `plugin.json` and intact `skills/` bundle can be loaded from workspace `.agents/plugins/` or global `~/.gemini/config/plugins/`; inspect loaded components in Customizations. |
| [Antigravity manifest schema](https://antigravity.google/schemas/v1/plugin.json) | The live schema recognizes `$schema`, `name`, `version`, and `description`. The guide's embedded schema is less complete; validate the selected manifest against the retrieved official schema and actual target rather than copying Codex-only fields. |
| [Antigravity subagents](https://antigravity.google/docs/subagents) | Explicitly lists App and CLI, not standalone IDE. Native IDE orchestration remains unestablished; the baseline route uses manual independent review and handoff. Absence from this page is not proof that a future IDE cannot support it. |

## Global constraints and acceptance contract

- Preserve package identity `incremental-and-test-plans`, version `0.1.0`, skill names `incremental-plan` and `test-design`, descriptions, and implicit-invocation policy. Version publication/bumping is outside this work.
- Preserve existing-plan applicability, planning-only behavior, standalone QA's one-document boundary, supplementary QA defaults/exclusion/history, source preservation, and evidence-based continuation. No migration of accepted plans or historical results.
- Preserve Gate 2/Gate 3, scoped-preapproval provenance, three distinct independent review scopes/reports, material-decision stops, optional-review authority/fallback rules, and separate action permissions. Portability must neither waive obligations nor invent approvals.
- Keep one normative owner for policy. The host reference explains capabilities and naming; gate policy owns approval/review semantics; templates export applicable duties without requiring the recipient to install this package.
- Keep the full relative package layout. Do not duplicate/fork skills per host, flatten resources, hard-code personal paths, replace resources with unresolved plugin variables, or assume symlink behavior across hosts.
- Introduce no runtime scripts/dependencies, hooks, MCP server, custom agents, executable OpenCode plugin, scheduler, state service, installer, or automatic permission changes. Development verification uses existing utilities.
- Preserve user configuration and all concurrent work. Setup examples instruct users to merge the selected entry into existing configuration, never replace a whole config or relax broad permissions. Diagnose missing access without bypassing it.
- Local implementation and static verification require a later implementation instruction. Native installation/configuration changes and model evaluations each require their applicable explicit authorization. No commits, pushes, PRs/replies, publication, paid services, private-source transfers, or cleanup follow from approving this plan.

**Implementation-ready** means the plan is concrete and required independent plan reviews have no unresolved material findings. **Source-ready** means the implemented package passes deterministic/source checks. **Desktop-supported** additionally requires the actual native acceptance below. A missing native permission or failed trial leaves that host's compatibility unverified; it does not justify a support claim or invented pass.

## Review focus

| Material condition | Required outcome and owner |
| --- | --- |
| Individual skill copied without sibling/shared files | Task 2 packaging checks reject the incomplete bundle; users install/register the intact bundle. |
| Duplicate skill ID, stale installed copy, nested working directory, or remote server | Task 2 setup/troubleshooting and Task 3 discovery checks establish the selected candidate or report a precise conflict; no silent override. |
| IDE lacks native owner/reviewer coordination | Task 1 retains manual fresh-context reviews and user-mediated handoff; no same-author substitute or fabricated autonomous launcher. |
| Skill denied or required resource unreadable | Task 1 stops affected planning with a concrete missing resource/permission; Task 3 records the blocked action and absence of unauthorized writes. |
| Correct generation but wrong execution/approval inference | Task 3 checks actual actions and outputs, including explicit execution requests, prompt-only continuation, and an unadopted preapproval export. |

## File ownership

All paths below are repository-relative. Each planned edit serves this support feature; leave other content and historical evidence intact.

| File | Planned responsibility |
| --- | --- |
| `references/host-compatibility.md` (new) | Canonical host capability mapping: resource bases, host-specific invocation identity, manual coordination fallback, and honest evidence limits. No installation mutations or duplicate gate policy. |
| `skills/incremental-plan/SKILL.md`, `skills/test-design/SKILL.md` | Link the shared host reference when resolving host capabilities; preserve metadata and substantive planning boundaries. Resolve optional review identities from actual inventory rather than imposing a Codex-qualified spelling. |
| `skills/incremental-plan/references/gates-and-reviews.md` | Reference the host mapping for transport selection while retaining policy ownership, independent review obligations, and existing manual routes. |
| `skills/incremental-plan/assets/handoff-template.md`, `skills/incremental-plan/assets/orchestration-prompt-template.md`, `skills/test-design/assets/qa-plan-template.md` | Export self-contained capability-aware instructions and the actual next bounded action. Preserve lifecycle, scope, and authority. |
| `plugin.json` (new) | Antigravity metadata only; Codex's `.codex-plugin/plugin.json` stays unchanged. |
| `README.md`, `docs/usage.md`, `docs/development.md`, `AGENTS.md` | Desktop setup, supported/unverified capability distinctions, intact package selection/verification, and updated product scope. |
| `tests/scenarios.md`, `tests/live-evaluation.md` | Focused desktop cases and a separately selectable controller batch; preserve the existing unrelated evaluation program. Update active ten-file assumptions to the new selection without rewriting historical evidence. |

No planned changes to `references/verification-design.md`, `skills/incremental-plan/assets/plan-template.md`, or third-party notices. Inspect these consumers for conflicts, but do not edit them without a directly necessary compatibility reason. Keep all existing attribution.

## Task 1 — make host assumptions explicit without changing planning policy

**Consumes:** Current skills, gate policy, output templates, and the documented host capabilities above. **Produces:** One shared host reference and portable instructions; existing Codex behavior remains the baseline.

- [ ] Create `references/host-compatibility.md`. State that relative package links resolve from their owning file, not the user's project directory; all required siblings/resources must remain accessible. Missing required content is a named blocker, not permission to guess or fetch an arbitrary replacement.
- [ ] Define invocation identity by host: preserve documented Codex qualified names; use OpenCode's actual discovered `incremental-plan`/`test-design` IDs and `@` mentions; for IDE use “Use the incremental-plan skill…” or “Use the test-design skill…” after checking Customizations. Do not promise an IDE slash command until observed there. Optional review skills are selected by verified identity/purpose from the active inventory, retaining all existing availability, authorization, and substitute rules.
- [ ] Define two transport outcomes, not new approval modes. When supported and authorized native coordination is established, use it while preserving fresh independent contexts and sequential writers. Otherwise export manual owner/reviewer briefs: the user opens separate fresh chats or supplies qualified independent human reports and relays results. Retain actual owner/report references and unresolved scopes. No same-author review counts as independent.
- [ ] Update the gate policy and both entrypoints with precise references to that mapping. Never select native operations from a product name alone. The standalone IDE's baseline is manual; new observed capabilities can be used only within actual authorization and supported behavior.
- [ ] Adapt the orchestration and handoff templates together. A host with unavailable required chat creation/messaging/waiting gets an explicit manual next action, responsible human, destination, and return route; do not output an apparently executable autonomous instruction that can only fail later. Preserve one owner per increment and all gates/evidence, including proposed-until-adopted preapproval. Manual transport is not a gate bypass. If the user requires fully automatic coordination, retain that requirement as blocked rather than silently substituting manual operation.
- [ ] Export the relevant capability fallback in standalone QA's embedded handoff too. Keep startup, optional review, and resumption guidance meaningful when copied without the plugin. Chat-title limitations remain nonblocking naming limitations; missing independent-review or execution capabilities remain substantive limitations.
- [ ] Desk-check conversion with default/excluded QA, standalone QA, prompt-only continuation, and explicit execution requests against all three hosts. These are source checks, not model results. Confirm no new mode, artifact, review count, approval waiver, automatic install, or invocation-policy change.

## Task 2 — package and document native desktop discovery

**Depends on Task 1. Consumes:** Its shared contract and the intact source layout. **Produces:** A deterministic, inspectable desktop package definition and usable setup instructions; native support remains pending Task 3.

- [ ] Add root `plugin.json` with the official schema URL, `name: incremental-and-test-plans`, `version: 0.1.0`, and the current Codex manifest's description. Rely on standard `skills/` discovery; omit duplicate skills paths and Codex-only `interface` fields. Validate identity agreement and selected field types. Reinspect the live schema if implementation happens after material documentation/version drift.
- [ ] In README, provide a concise host-selection table and link to a new `Desktop setup` section in `docs/usage.md`. Preserve Codex setup and examples as Codex-specific. Label the other desktop routes as source-prepared/native-unverified until actual acceptance is recorded.
- [ ] Document OpenCode v2 Desktop setup using the intact bundle and a merged `skills` array entry in the serving environment's `opencode.json(c)`. Use an explicit replaced absolute path to `<bundle-root>/skills` in the example; explain working-directory resolution, duplicate IDs, remote-server path ownership, and access permissions. Do not register this bundle under executable `plugins` or promise an Extensions panel entry. Preserve pre-existing configuration entries and permission policy.
- [ ] Document Antigravity IDE installation of the entire bundle into either `.agents/plugins/incremental-and-test-plans/` in a selected workspace or `~/.gemini/config/plugins/incremental-and-test-plans/`. Recommend workspace scope for the first authorized trial. Inspect Customizations and the actual loaded skill/resource paths. Do not overwrite an occupied destination or deploy both copies during a trial; stop for an explicit update choice. Avoid App/CLI installation commands and unsupported reload promises; verify discovery in a fresh IDE conversation/window as appropriate to the actual version.
- [ ] Define the exact runtime selection in `docs/development.md`: the ten existing files plus root `plugin.json` and `references/host-compatibility.md`, twelve total. Keep the paths listed below. The source checkout can remain a development source, but it is not the distribution artifact.

```text
.codex-plugin/plugin.json
plugin.json
skills/incremental-plan/SKILL.md
skills/incremental-plan/assets/plan-template.md
skills/incremental-plan/assets/handoff-template.md
skills/incremental-plan/assets/orchestration-prompt-template.md
skills/incremental-plan/references/gates-and-reviews.md
skills/test-design/SKILL.md
skills/test-design/assets/qa-plan-template.md
references/verification-design.md
references/third-party-notices.md
references/host-compatibility.md
```

- [ ] Provide an allowlisted export recipe using existing host file/archive utilities and those exact files, with an unused destination outside source/installed paths. Require regular readable source files, reject escaping/symlinked selections, preserve relative paths, and refuse an occupied destination. Do not recursively copy the checkout or rely on `.gitignore`. Inspect the actual staged/extracted selection and source-byte correspondence before distribution. The recipe is development guidance, not a runtime or automatic installer.
- [ ] Update AGENTS product scope from Codex-only to the three selected hosts without broadening the planning-only behavior. Add ownership of the host reference/native manifest and preserve current verification/action boundaries. Update affected active package-count references in the controller runbook; do not alter its existing batch selection or historical ten-file evidence.
- [ ] Run the repository's documented static checks on settled inputs: both active Skill Creator validators; parsed manifest/frontmatter identity and unchanged description/policy checks; link/anchor resolution inside the twelve-file selection; actual selected-file privacy/dependency audit; and `rtk proxy git --no-optional-locks -c diff.autoRefreshIndex=false diff --check`. Locate the validator through the active host inventory; never install missing tooling silently.
- [ ] Verify a clean staged/extracted bundle independently from the source tree. Check exact allowed paths and byte correspondence separately. On disposable synthetic copies, removing `references/verification-design.md` must fail resource closure; adding a forbidden `docs/internal-note.md` must fail allowed-content validation even when present in both staging and archive; changing an extracted skill byte must fail correspondence. The valid bundle must pass. These are package-contract checks, not prose-matching tests or live agent runs.

## Task 3 — verify actual desktop use before claiming support

**Depends on Task 2. Consumes:** Frozen source and delivered package identities, synthetic fixtures, and explicit installation/configuration/live-evaluation authority. **Produces:** Host/version/candidate-bound results and honest support status. This task is planned, not currently authorized or performed.

Extend the existing scenario catalogue with the rows below and a separate desktop selection in the controller runbook. Reuse raw catalogue fixtures and existing Q05/Q10/Q11/Q14, C15, continuation, and PA cases where applicable; do not build a runner or duplicate the 34-call program. Keep evaluator expectations and this plan out of subject context. Use configured model defaults and record the actual resolved model or unknown. No broad benchmark or unrequested provider/CI/PR exercise.

| Case, run separately per target desktop | Observable acceptance |
| --- | --- |
| Native discovery and explicit entrypoints | The actual desktop exposes both intended skills from the delivered candidate. OpenCode `@` invocation and IDE name-based invocation load the corresponding body. Required sibling/shared reference reads come from that bundle. No stale/global collision is silently accepted. |
| Default conversion and explicit QA exclusion | Fresh synthetic source plan yields plan/handoff/QA by default; exclusion yields plan/handoff and retains required verification/gates. Preserve existing QA/history where the selected fixture has them. No product/test execution. |
| Standalone QA | A selected synthetic project produces only its requested QA document with embedded preparation handoff. No incremental plan, separate handoff, or execution. |
| Routing boundaries | In separate fresh requests, an existing-plan conversion and QA-design request select the appropriate skill; initial planning from goals and ordinary editing do not acquire incremental artifacts. “Implement these tests” does not route to QA planning; explicit use of test-design to execute explains its boundary without running tests. |
| Continuation and authority | In a fresh chat, reconcile actual saved synthetic outputs and supplied evidence, preserving human annotations/history. Missing required reports hold readiness; prompt-only continuation leaves files unchanged; an unadopted preapproval export supplies no execution or publication authority. |
| Capability fallback and optional review identity | With actual restricted/absent coordination, emit actionable manual briefs and preserve three independent scopes; do not call nonexistent tools or claim reviews ran. Verify optional-review lookup/fallback without installing or invoking unrelated tools. A fully automatic requirement stays blocked when unsupported. |
| Resource/access failure and candidate selection | In an isolated controlled setup, missing shared content or denied skill/resource access yields a specific blocker without unauthorized writes. Check conflicting/stale candidates and a nested project context; a wrong loaded identity fails even if output looks plausible. |
| Host-independent exported handoff | A separate fresh receiver sees only actual generated launcher/handoff/QA and selected synthetic target context, not the plugin. Ask the relevant next-action/authority question; verify usable manual/native routing, gates, review independence, and honest missing capabilities. Correct receiver inference cannot repair omitted producer instructions. |

Run each materially distinct variant in a fresh context, on the same frozen candidate. Shared scenario names do not collapse positive/negative or QA-on/excluded obligations into one pass. Before asking for live authorization, select the exact variants, derive the actual call count including receivers/capture probes, and state the proposed host/model route and limits. A broad case-family count is not that execution packet.

Use supported host isolation and capture controls. Establish candidate/fixture access, restricted writes, and inspectable action records; source directives alone do not prove enforcement. Do not start actors if private/evaluator input isolation or necessary action capture cannot be established. Record that host as blocked/unverified, not passing. Retain exact prompts, supplied identities, actual outputs/tool actions, errors, before/after file evidence, and limitations outside shipped/tracked source. Preserve failed attempts; no unchanged reruns for a better grade.

Install/configure only the explicitly approved scoped targets. Preview the exact paths/config diff first, preserve existing settings and installed copies, and identify a user-approved recovery procedure before mutation. Any restoration/removal requires its actual action authority; do not delete user work or claim rollback from an unperformed procedure. Native trials may use only synthetic fixtures and the approved package; transmit no private development records.

Codex regression: run unchanged static metadata/resource checks and, under separately authorized native/model testing, a focused explicit conversion, standalone QA, and capability/handoff case on the changed package. Reuse applicable old evidence only when its relevant instructions/environment match. Do not reinstall Codex or claim native regression coverage from source-read trials.

## Review, repair, and completion

For this plan, obtain three distinct read-only independent reports on the same substantive candidate: requirements/source fidelity, architecture/simplicity/desktop compatibility, and verification/evidence quality. Reviewers receive direct scope, canonical sources, and official links; no author conversation or other reviewers' verdicts. They may inspect sources but cannot write, run live subjects, invoke optional workflows, or delegate. Collect all dispatched reports before edits; validate findings, fix material in-scope issues, renew affected scopes, and retain applicable unaffected reports in [plan-review.md](plan-review.md).

For implementation, the owner self-checks the complete changed package/docs/scenarios and obtains independent requirements, architecture, and verification reviews before result acceptance. Keep reviewers read-only and repair verified material findings within actual authority. Reuse still-applicable reports; do not add generic review layers or treat this plan review as implementation review. No review pass grants installation, publication, or a human approval that has not occurred.

The implementation handoff must report: changed files and reason; exact source/delivered candidate; static commands/results and package controls; actual desktop/version/model/surface results or specific unrun/blocked scope; review findings/dispositions; protected-work preservation; and outstanding human decisions/actions. Check final documentation against the final delivered candidate after the last relevant change. Mark support only for demonstrated scope. Preserve existing accepted history, native failures, and required evidence; terminal evidence-retention review proposes disposition but performs no cleanup.

No material design question is intentionally deferred to the implementer. The selected design is native skill discovery with manual coordination fallback and additive Codex preservation. If current versions contradict the documented foundation or a required capability cannot be supported without changing that scope, stop affected implementation and return the concrete alternatives for the user's decision.
