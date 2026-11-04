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

## Coordination transport

Choose one transport from observed capabilities and actual authority, separately from approval mode:

- **Native coordination:** only when the needed fresh-context assignment, owner identity/resumption, message/return and bounded wait/status operations are supported and authorized in this session. Use the host's actual tools and limits; retain one owner per increment, sequential writers and distinct independent reports. Do not infer the full route merely from subagent availability.
- **Manual coordination:** otherwise give copy-ready owner/reviewer briefs. The human opens separate fresh chats or obtains qualified independent human reports, relays the bounded assignment and returns each report to the named coordinator. Record actual owner/report references and unresolved scopes. The author cannot supply independent credit. The standalone IDE uses this baseline unless its required native capabilities have actually been established.

When exporting a handoff or launcher, select the usable route before presenting a next action. For manual transport, identify the responsible human, the specific fresh or existing owner/reviewer destination, what packet to paste, and where to return its result. Reuse the established owner on resumption; unknown active ownership blocks a duplicate writer. Native-only creation/messaging/wait instructions must be conditional, not the immediate manual action. Keep absent independent reports pending and preserve all gates, provenance, scope and separate action permissions. A fully automatic coordination requirement remains blocked if the host cannot meet it; do not silently relax it to manual operation.

Unavailable title operations are a naming limitation, not an execution/review substitute. Use human-readable labels and actual references. Missing required independent review or execution capabilities are substantive blockers. Export these applicable duties in plain language so a receiver needs neither this package nor the author's conversation.

## Evidence limits

The source prepares native discovery for Codex desktop/CLI, OpenCode v2 Desktop/CLI and standalone Antigravity IDE/CLI. Source validation does not establish installed discovery, implicit routing, usable resource access, native coordination or desktop support. Record the exact host/surface/version, loaded candidate and actual exercised behavior before making those claims. Antigravity App support, executable OpenCode extensions and unexercised operating systems are outside this change. CLI preparation adds no native validation result or blanket version guarantee.

Documentation basis: [OpenCode v2 skills](https://opencode.ai/v2/docs/skills/), [configuration](https://opencode.ai/v2/docs/config/), [Antigravity skills](https://antigravity.google/docs/skills), [standalone IDE plugins](https://antigravity.google/docs/plugins#standalone-ide-plugin-installation) [subagent surface limits](https://antigravity.google/docs/subagents), [Antigravity CLI plugins](https://antigravity.google/docs/cli/plugins), [OpenCode v2 CLI](https://opencode.ai/v2/docs/cli/) and [Codex CLI plugins](https://learn.chatgpt.com/docs/plugins#plugin-browser-in-codex-cli), checked 2026-10-29. Actual installed behavior still requires native acceptance.
