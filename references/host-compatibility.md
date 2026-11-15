# Host compatibility

This reference owns host capability and invocation mapping. The [gate policy](../skills/incremental-plan/references/gates-and-reviews.md) owns approvals, independent reviews and evidence; transport changes none of those obligations. The entrypoints remain planning-only.

## Resources and capability checks

Keep the complete package layout. Resolve each relative link from the file that owns it, using the loaded skill's actual base directory, never the target project's working directory. Read required sibling skills, templates and shared references from that same candidate. They are not automatically loaded merely because discovery listed a skill. If a required resource is missing, denied or from a conflicting candidate, name its expected path and the missing access/correspondence; stop affected drafting rather than guess or fetch an arbitrary replacement.

Check the actual host, surface, discovered identity, loaded paths and authorized tool inventory. A product name, a documented API, or a permission in a prompt does not establish usable native operations. Preserve existing permission policy; do not install, enable or reconfigure capabilities to bypass a blocker.

## Invocation identities

| Host/surface | Selected entrypoint |
| --- | --- |
| Codex desktop and CLI | Preserve `$incremental-and-test-plans:incremental-plan` and `$incremental-and-test-plans:test-design` when exposed by the active inventory. Source loading is separate from installed invocation. |
| OpenCode v2 Desktop and CLI | Check the discovered path-derived IDs, normally `incremental-plan` and `test-design` from the configured `skills/` directory. Use `@incremental-plan` or `@test-design` only when those are the actual selected IDs. Duplicate/stale candidates require resolution. |
| Standalone Antigravity IDE | Inspect Customizations for the active plugin and both skills. Request “Use the incremental-plan skill…” or “Use the test-design skill…” with the intended discovered identity. Do not assume App/CLI slash commands work in the IDE. |

Antigravity CLI is a separate surface: install the intact inspected local bundle
through `agy plugin install /absolute/path/to/bundle` only with installation
authority, then inspect `/plugin` (or `agy plugin list --json`) and the staged
candidate. CLI assets normally live under `~/.gemini/antigravity-cli/plugins/`;
IDE locations are not a CLI installation recipe. In the interactive CLI, select
the exposed skill slash command, normally `/incremental-plan` or `/test-design`,
confirming any actual namespace/collision through autocomplete and loaded paths.
CLI subagent availability does not establish a complete authorized coordination
route. Headless syntax and behavior must be verified for the selected version;
interactive slash-command documentation alone does not establish them.

For optional review methods, resolve the intended skill by identity and purpose in the active inventory. Codex may expose `ponytail:ponytail-review` or `material-code-review:material-code-review`; another host may expose a different namespace or ID. Record and use only its verified invocation form. An `@` prefix is not universal syntax. This mapping adds no invocation authority: preserve the gate policy's availability, direct exclusion, exact-request-only conflicts, mandatory-tool and substitute rules. Never substitute a broader audit or persistent implementation mode for a bounded review.

For optional Superpowers TDD, resolve the `test-driven-development` skill by identity and purpose in the receiving host's active inventory. Codex may expose `superpowers:test-driven-development`; use only the actual verified identity and accessible version, not a guessed universal prefix or the planner's installation path. Read the selected skill for fit under the [optional TDD policy](../skills/incremental-plan/references/gates-and-reviews.md#optional-superpowers-tdd). Missing, disabled, inaccessible or unknown exposure leaves the self-contained procedure usable; discovery alone proves neither invocation nor TDD compliance. Do not install or reconfigure a host to satisfy this optional route.

For optional Superpowers debugging, resolve `systematic-debugging` by identity and purpose in the receiver's active inventory when a debugging trigger occurs. Codex may expose `superpowers:systematic-debugging`; use only the actual verified identity, accessible version and required resources. Apply the [optional debugging policy](../skills/incremental-plan/references/gates-and-reviews.md#optional-superpowers-debugging), independently of TDD availability. The portable procedure remains usable without the optional skill or its supporting capabilities; preserve access restrictions and real authority/evidence blockers. Discovery alone establishes neither invocation nor debugging quality, and supplies no installation or reconfiguration permission.

## Coordination transport

Resolve transport per role and operation before exporting the next action, separately from approval mode. For the orchestrator, each implementation owner and each review assignment, verify the capabilities and permissions needed to assign work in the required context, identify and resume the same child, return decisions and reports, and wait for or inspect actionable results. Check which actor can use each operation. Subagent availability alone does not establish a complete route, and an active-turn wait does not establish a wakeup after yielding.

- **Native operations:** use the supported authorized route for each operation. Prefer fresh, bounded read-only subagents for independent review under the candidate owner, with reports returned through the parent channel. Keep those reviews native when a different role or operation needs a human relay. Keep one durable implementation owner per increment and sequential writers.
- **Manual operations:** give copy-ready briefs and returns. Name the responsible human, the specific fresh or existing destination, the exact packet and candidate to relay, and the recipient and route for the result. The human can open a fresh chat or obtain a qualified independent human report where needed and authorized. The standalone IDE uses the manual baseline for operations whose native route is unverified. Keep unavailable native operations out of the immediate action.

An uncontactable or unresumable child keeps its scope pending if no authorized route remains. Reuse the established owner, and never replace one whose active state is unknown. Keep absent independent reports pending; the author cannot supply independent credit. A denied operation stays stopped under its permission control. A fully automatic requirement remains blocked if any required operation cannot run that way; do not silently substitute a relay. Preserve all gates, provenance, scope and separate action permissions.

Unavailable title operations are a naming limitation, not an execution/review substitute. Use human-readable labels and actual references. Missing required independent review or execution capabilities are substantive blockers. Export these applicable duties in plain language so a receiver needs neither this package nor the author's conversation.

## Evidence limits

The source prepares native discovery for Codex desktop/CLI, OpenCode v2 Desktop/CLI and standalone Antigravity IDE/CLI. Source validation does not establish installed discovery, implicit routing, usable resource access, native coordination or desktop support. Record the exact host/surface/version, loaded candidate and actual exercised behavior before making those claims. Antigravity App support, executable OpenCode extensions and unexercised operating systems are outside this change. CLI preparation adds no native validation result or blanket version guarantee.

Documentation basis: [OpenCode v2 skills](https://opencode.ai/v2/docs/skills/), [configuration](https://opencode.ai/v2/docs/config/), [Antigravity skills](https://antigravity.google/docs/skills), [standalone IDE plugins](https://antigravity.google/docs/plugins#standalone-ide-plugin-installation) [subagent surface limits](https://antigravity.google/docs/subagents), [Antigravity CLI plugins](https://antigravity.google/docs/cli/plugins), [OpenCode v2 CLI](https://opencode.ai/v2/docs/cli/) and [Codex CLI plugins](https://learn.chatgpt.com/docs/plugins#plugin-browser-in-codex-cli), checked 2026-10-29. Actual installed behavior still requires native acceptance.
