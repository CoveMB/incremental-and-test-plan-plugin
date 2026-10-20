# Incremental and Test Plans

Turn an existing development plan into reviewable increments, or work out what a
project needs to verify before its results can be trusted.

This Codex plugin provides two planning skills. They produce Markdown plans and
handoffs for later implementation. They do not change product code, run tests,
or create pull requests.

## Choose a skill

| Your task | Skill | What you get |
| --- | --- | --- |
| Break an existing plan into coherent increments | `incremental-plan` | An incremental plan, a current handoff, and QA design by default |
| Revise a saved incremental plan or continue it from implementation evidence | `incremental-plan` | Updated planning documents and the next eligible action |
| Find coverage gaps and plan verification for a project, a plan, or both | `test-design` | One QA plan with verification work and an embedded handoff |

If you only have goals or a specification, create an implementation plan through
your usual planning workflow first. Requests to write code, implement tests, or
run checks belong to an execution workflow.

## Get started

Use the plugin in a Codex workspace that can read your selected source and write
to your chosen documentation directory.

If your configured marketplace provides this package, open **Plugins** in the
desktop app or `/plugins` in Codex CLI, select **Incremental and Test Plans**, and
check its source before installing. Start a new chat or CLI session afterward.
See [OpenAI's plugin guide](https://learn.chatgpt.com/docs/plugins) for the current
installation flow. A repository clone alone does not install the plugin.

To try a checkout without installing it, ask Codex to read
`skills/incremental-plan/SKILL.md` or `skills/test-design/SKILL.md` from that
checkout and follow it for your request. Give the full checkout path when your
target project is elsewhere. This exercises the source instructions; it does
not test installed discovery.

### Convert an existing plan

With the plugin installed, send:

```text
$incremental-and-test-plans:incremental-plan
Turn docs/search-plan.md into coherent increments.
Save the planning documents under docs/incremental-and-test-plans/search/.
```

Replace the example paths with your source plan and an unused output directory.
The default result is:

| File | Purpose |
| --- | --- |
| `plan.md` | Increment boundaries, dependencies, acceptance criteria, and progress |
| `handoff.md` | The current bounded next step and the instructions needed to carry it out |
| `qa-plan.md` | Verification design, coverage gaps, and their owners |

The source stays unchanged. A selected existing QA document can be reused at its
authorized location. Each increment keeps a coherent piece of a feature together
with its tests and necessary documentation or safeguards. A small feature may
need only one increment.

### Design QA on its own

```text
$incremental-and-test-plans:test-design
Design QA for this project. Inspect its relevant contracts, assertions,
and CI configuration. Save docs/qa/qa-plan.md with verification work
and a preparation handoff. Do not execute tests.
```

You can supply a plan, a project, or both. Standalone test design writes one QA
document with its handoff inside it. If the project has not been inspected,
proposed commands and paths remain provisional.

## What happens after planning

New plans remain drafts until three independent reviews have been reconciled:
source fidelity, architecture and simplicity, and verification quality. When
reviews cannot be arranged within the available permissions and tools, the
output includes manual review briefs and identifies the missing reviews.

A reviewed plan normally hands off preparation to an executor. **Gate 2** is your
approval of the concrete implementation plan; **Gate 3** is your approval of the
verified result. Required reviews, evidence, and project-specific gates still
apply when a routine approval pause has been explicitly preapproved.

Incremental planning also returns a copy-ready **Implementation orchestration
prompt** when implementation remains. You can use it in a separate execution
chat. Generating the prompt starts no work; its first action reflects any
outstanding reviews or decisions.

The [usage guide](docs/usage.md) covers continuation, QA options, reviews,
preapproved orchestration, and common problems.

## Package and validation

The package is `incremental-and-test-plans`, version `0.1.0`. It contains
instructions, references, and templates, with no executable runtime, hooks, MCP
server, or required third-party plugin.

For source ownership, package contents, and validation commands, read the
[development guide](docs/development.md). Static checks establish package
structure; they do not establish planning quality, installed usability, or
execution outcomes.
