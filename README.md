# Incremental and Test Plans

A planning skill package for turning an existing development plan into coherent,
reviewable increments and designing the tests and evidence those increments
need. You can also plan QA for a project without creating an incremental plan.

The two skills write Markdown plans and handoffs for later implementation.
They do not change product code, run tests, or create pull requests.

[Get started](#get-started-codex) · [Examples](#examples) · [Usage guide](docs/usage.md) ·
[Help](docs/usage.md#when-something-needs-attention)

## Choose a skill

| Skill | Use it to | Output |
| --- | --- | --- |
| `incremental-plan` | Convert an existing plan into increments, revise pending work, or reconcile implementation evidence and prepare the next handoff | `plan.md`, `handoff.md`, and QA design by default |
| `test-design` | Identify coverage gaps and plan verification from a plan, a project, or both | One `qa-plan.md` with an embedded preparation handoff |

An increment keeps one coherent piece of a feature together with its meaningful
tests, necessary documentation, and safeguards. A small feature may need only
one increment.

Incremental planning needs an existing plan. If you only have goals or a
specification, create the implementation plan through your usual planning
workflow first. Writing code, implementing tests, and running checks belong to
an execution workflow.

## Choose a host

| Host | Route and evidence |
| --- | --- |
| Codex desktop and CLI | Existing plugin/source route preserved; [CLI setup](docs/usage.md#codex-cli) includes terminal commands. Native use of this changed candidate remains unverified. |
| OpenCode v2 Desktop and CLI | Register the intact bundle's `skills/` directory in the serving environment. Source-prepared; native use unverified. |
| Standalone Antigravity IDE | Load the intact plugin bundle at workspace scope initially. Source-prepared; native use unverified. |
| Antigravity CLI | Install the intact local bundle through its CLI plugin manager. Source-prepared; native use unverified. |

See [Desktop setup](docs/usage.md#desktop-setup) for candidate checks, invocation
and manual coordination; [CLI setup](docs/usage.md#cli-setup) covers all three
selected CLIs. These additions do not establish native support for all releases,
other operating systems, headless automation, or Antigravity App.

## Get started (Codex)

Open the target project in Codex. It needs access to the selected source and
permission to write the planning documents to your chosen destination.

### Use an installed copy

If a configured marketplace provides **Incremental and Test Plans**, open
**Plugins** in the desktop app or `/plugins` in Codex CLI. Select the package,
check its source, and install it. Start a new chat or CLI session afterward,
then use the examples below.

See [OpenAI's plugin guide](https://learn.chatgpt.com/docs/plugins) for the current
installation flow. If the package is not available in your marketplace, you can
try the checked-out source below. Cloning the repository alone does not install
it.

### Try this checkout

Replace `<plugin-root>` with the absolute path to this checkout, and replace the
example source and destination paths with paths in your target project. Use an
unused output directory for a new plan. Then send this prompt to Codex:

```text
Read <plugin-root>/skills/incremental-plan/SKILL.md and follow it for this request:
Turn docs/search-plan.md into coherent increments.
Save the planning documents under docs/incremental-and-test-plans/search/.
```

For standalone QA, load `<plugin-root>/skills/test-design/SKILL.md` and use the
QA request below without its installed-skill prefix. Keep the checkout's
references and templates available. Loading source instructions does not verify
installed discovery.

## Examples

These examples use the installed Codex skills. Replace their paths with your own.
When loading source directly, omit the `$incremental-and-test-plans:…` prefix.

### Convert an existing plan

```text
$incremental-and-test-plans:incremental-plan
Turn docs/search-plan.md into coherent increments.
Save the planning documents under docs/incremental-and-test-plans/search/.
```

The source stays unchanged. By default, the output directory contains:

| File | What it contains |
| --- | --- |
| `plan.md` | Increment boundaries, dependencies, acceptance criteria, and progress |
| `handoff.md` | The next bounded action and the instructions needed to carry it out |
| `qa-plan.md` | Verification design, coverage gaps, and their owners |

To reuse an existing QA document, identify it and its authorized location in
your request. To omit supplementary QA design, add “Exclude supplementary QA
design.” Meaningful feature tests, required evidence and certification, reviews,
and gates still apply. See [QA options](docs/usage.md#choose-how-qa-fits).

### Design QA on its own

```text
$incremental-and-test-plans:test-design
Design QA for this project. Inspect its relevant contracts, assertions,
and CI configuration. Save docs/qa/qa-plan.md with verification work
and a preparation handoff. Do not execute tests.
```

Supply a plan, a project, or both. The handoff is embedded in the QA document;
there is no separate incremental plan or handoff file. Proposed commands and
paths remain provisional when the project has not been inspected.

### Continue after implementation

```text
$incremental-and-test-plans:incremental-plan
Continue docs/incremental-and-test-plans/search/plan.md from the executor return.
Reconcile the linked evidence and update its plan, handoff, and current QA plan.
```

Provide the actual executor return and its evidence links. A preparation return
resumes the same increment; a verified result can make dependent work eligible.
See [continuation and revision](docs/usage.md#continue-or-revise-a-saved-plan)
for the required evidence and approval conditions.

## Review and implementation

New plans remain drafts until three distinct independent reports are reconciled:
source fidelity, architecture and simplicity, and verification quality. If the
available permissions or tools cannot provide those reviews, the planner
supplies manual review briefs and records what is still pending.

A reviewed plan normally hands off preparation to an executor. **Gate 2** is your
approval of the concrete implementation plan; **Gate 3** is your approval of the
verified result. Explicit scoped preapproval can remove a routine pause, while
required preparation, reviews, evidence, and project-specific gates still apply.

When implementation remains, incremental planning also returns a copy-ready
**Implementation orchestration prompt** unless you ask to omit it. You can send
it to a separate execution chat. Generating the prompt starts no work, and its
first action reflects any pending reviews or decisions.

The [review and handoff guide](docs/usage.md#review-the-plan-and-hand-it-off)
explains the approval sequence, optional review tools, and preapproved
orchestration.

## Help and further reading

- [Usage guide](docs/usage.md): sources, QA options, continuation, and closure.
- [Troubleshooting](docs/usage.md#when-something-needs-attention): missing skills,
  pending reviews, provisional commands, and blocked continuation.
- [Development guide](docs/development.md): canonical sources, package contents,
  and contributor checks.

## Package and validation

The package is `incremental-and-test-plans`, version `0.1.0`. It contains
instructions, references, and templates, with no executable runtime, hooks, MCP
server, or required third-party plugin.

[Validation instructions](docs/development.md#static-checks) cover source
structure and consistency. Static checks do not establish planning quality,
installed usability, or execution outcomes.
