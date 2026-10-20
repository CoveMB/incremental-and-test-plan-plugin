# Using Incremental and Test Plans

[Back to the README](../README.md)

Use this guide after choosing a skill in the README. Examples assume the plugin
is installed. For a checkout, load the relevant `SKILL.md` and omit the
installed-skill prefix from your request. Replace example paths with your own.

## Give the planner a clear source

For incremental planning, identify the existing plan, any supporting documents,
and the destination. A specification or a list of requested changes is not yet
an implementation plan.

```text
$incremental-and-test-plans:incremental-plan
Turn docs/search-plan.md into a draft incremental plan.
Use docs/search-contract.md as supporting context.
Save the documents under docs/incremental-and-test-plans/search/.
```

You can paste an existing plan instead of selecting a file. Mark exactly which
text is the plan and name the destination. Incremental conversion saves the
pasted plan verbatim as `source.md`. An existing source file is left in place.
Standalone test design saves a pasted source only when you explicitly request it.

If several sources could be primary, a destination is occupied, or a symlink
would lead outside the authorized location, the planner asks for the decision
needed before writing there. For revisions, identify the documents it may update;
existing history and human annotations are preserved.

## Choose how QA fits

Supplementary QA design is included in a new incremental conversion. Checks and
coverage gaps are assigned to the feature increments that own them, or to a
named obligation spanning the plan. Detailed verification design lives in the
QA document; the incremental plan sets the implementation order.

| What you want | Add to your request |
| --- | --- |
| Use an existing QA plan | “Reuse docs/qa/search-qa.md as the current QA document.” |
| Omit supplementary QA design | “Exclude supplementary QA design.” |
| Omit the launcher from the response | “Omit the implementation orchestration prompt.” |

Excluding supplementary QA removes the extra design work and new QA document.
It preserves meaningful feature tests, required combined evidence, source-required
certification, independent reviews, and approval gates. Those obligations remain
in the plan and handoff. Switching an existing plan to excluded mode preserves
its QA document and history, while distinguishing mandatory obligations from
supplementary proposals that no longer govern the work.

For QA without incremental planning, use `test-design`. It examines relevant
contracts, test assertions and fixtures, configured checks, CI, and existing
results without executing them. The resulting `qa-plan.md` connects important
outcomes and failure cases to proposed checks, coverage gaps, implementation
work, and a preparation handoff. It creates neither a separate incremental plan
nor a separate handoff file.

Certification work is included when required by the project or otherwise
warranted. A proposed new mandatory gate needs your decision. A certification
plan describes prerequisites, setup, expected outcomes, evidence, and responsible
owners; it does not establish certification or release readiness.

## Review the plan and hand it off

Planning produces a draft, then reconciles three distinct independent reports:

| Review | What it checks |
| --- | --- |
| Source fidelity | Requirements, exclusions, constraints, and source-defined gates are preserved |
| Architecture and simplicity | Boundaries are coherent, intermediate results are safe, and unnecessary complexity is avoided |
| Verification quality | Checks have justified expected outcomes and can detect material failures |

For coordinated incremental planning, the plan, QA document, and handoff are
reviewed together. They do not need separate copies of the same review round.
Standalone QA uses those scopes for its one-document candidate. Missing reports
stay pending; an author's self-review is not independent review.

Once the required reviews and decisions are resolved, the handoff normally asks
an executor to inspect the actual project and prepare the first eligible
increment. The default approval sequence is:

1. The executor prepares a concrete plan with actual files, interfaces, checks,
   dependencies, and recovery limits.
2. You approve that plan at **Gate 2** before implementation.
3. The executor implements and verifies the authorized work, then reconciles
   three independent implementation reviews covering the same scopes above.
4. You approve the verified result at **Gate 3**.
5. The planner reconciles that result and identifies the next eligible step.

Before Gate 2, preparation checks the relevant tool and dependency versions
against current official documentation, advisories, and compatibility requirements.
It records the sources and whether the plan remains valid, needs amendment, or
is blocked, then reconciles affected later work. Still-applicable evidence can
be reused; a newer release alone does not force an upgrade or stop. Specific
project freshness gates remain in force. The handoff carries these duties even
when supplementary QA is excluded; standalone QA carries them in its embedded
handoff. See [documentation and stack revalidation](../skills/incremental-plan/references/gates-and-reviews.md#documentation-and-stack-revalidation).

These are the defaults described by the
[gate and review policy](../skills/incremental-plan/references/gates-and-reviews.md).
Applicable scoped preapproval can remove a named pause; it does not remove
preparation, checks, independent reviews, or material decisions. Project-specific
and specialist gates remain in force.

### Use the orchestration prompt

For creation and authorized revision or continuation with unfinished increments,
the response ends with an **Implementation orchestration prompt**, unless you ask
to omit it. The prompt points to the actual saved documents and carries the
current next action. Detailed execution guidance stays in the portable handoff,
so the receiving chat does not need this plugin or the author's conversation.

Send the prompt to an execution chat when you want that work to begin. The
exported guidance assigns one orchestrator to progression across increments and
one implementation owner to each increment. Writers and shared-checkout or stack
changes stay sequential. Your configured model defaults are retained unless you
request a particular model.

Requesting only a prompt does not authorize edits to saved planning documents.
If their guidance is missing or contradictory, the prompt identifies
reconciliation as the first step instead of presenting the work as ready to run.
Standalone QA and completed implementation scope receive no start prompt;
remaining closure obligations are still reported.

### Opt into preapproved orchestration

Manual approval is the default. To prepare an export that delegates routine
approvals through an open merge/pull request stack, request:

```text
Use Preapproved orchestration for this plan; prepare the prompt to deliver
an open MR stack, with material design decisions left to me.
```

Review the generated authorization before adopting it. When you submit or adopt
it as a direct execution instruction, it delegates Gate 2 and Gate 3 decisions
and authorizes the named scope's planning reconciliation, owner and reviewer
coordination, implementation, tests, ordinary in-scope repairs, commits, pushes,
and MR creation or updates in the selected repository. Drafting or quoting the
prompt grants none of that execution authority. A gate-only bypass does not
also authorize publication.

The orchestrator records its decisions against the concrete candidates and
required evidence. Material choices about scope, behavior, architecture, public
contracts, compatibility, or consequential tradeoffs still come to you. Existing
narrower permissions and later revocations remain effective.

The mode does not authorize merging, deployment, destructive cleanup,
installation, new paid services, permission changes, provider requests or
replies, additional private-data transfers, or specialist/human certification.
Host restrictions still apply. Missing mandatory evidence remains a blocker.
The [preapproved orchestration policy](../skills/incremental-plan/references/gates-and-reviews.md#preapproved-orchestration)
defines the full scope.

### Optional review tools

The required independent review scopes do not depend on a particular plugin.
The planner may recommend Material Code Review when a concrete risk warrants
its additional process, with regular independent reviews as the fallback.

At implementation-result review, Ponytail review is selected by default only
when available, usable, and permitted, unless you exclude it. Plan review does
not select Ponytail by default. To exclude it for an increment, say:

```text
Exclude Ponytail review for this increment.
```

When Ponytail cannot be used, the architecture reviewer performs the permitted
simplicity substitute. A project that requires the named tool and forbids a
substitute still needs that obligation resolved. Findings from Ponytail require
distinct explicit repair authorization before fixes. See the
[optional-review policy](../skills/incremental-plan/references/gates-and-reviews.md#simplicity-and-optional-ponytail)
for invocation conditions and fallback requirements.

## Continue or revise a saved plan

Bring back the current plan, handoff, selected QA document, and links to the
executor's actual preparation or result evidence.

```text
$incremental-and-test-plans:incremental-plan
Continue docs/incremental-and-test-plans/search/plan.md from the executor return.
Reconcile the linked evidence and update its plan, handoff, and current QA plan.
```

A **preparation return** can reveal that boundaries or later cards need revision.
After reconciliation and affected reviews, it returns to the same increment at
Gate 2. A proposed implementation is not a completed increment.

A **result return** can make a dependent increment eligible once the required
checks, reviews, prerequisites, and applicable result approval or bypass are
established. The planner reads existing results and current checkout evidence;
it does not run the checks. Valid unaffected evidence is reused. Missing or
stale proof produces a specific request for what is needed.

For published increments, current required CI and expected provider review must
settle before dependent preparation. An optional provider's mere availability
creates no review obligation. The handoff carries any applicable waiting,
retry, and separate-permission conditions.

To revise scope, identify the authorized change and ask the planner to update
the affected pending increments. Accepted IDs, decisions, and dated history stay
intact. Existing plans can continue in their current location and format.

## Close the selected scope

```text
$incremental-and-test-plans:incremental-plan
Reconcile the final scope of docs/incremental-and-test-plans/search/plan.md
against every increment's evidence. Identify unmet obligations, approved
deferrals, and any separate certification or release work.
```

Closure checks the original requirements and authorized amendments against their
owning increments. The last increment passing does not prove the whole plan is
complete. Required evidence across components, unresolved obligations, and
separate release decisions remain visible.

The final **Evidence retention and cleanup review** records what to preserve,
what still has consumers, and any proposed cleanup. It sits outside the feature
increment count. The planner does not delete or compact evidence, and acceptance
does not authorize cleanup. Optional storage decisions do not block demonstrated
product scope; missing mandatory proof and source-required cleanup remain
obligations.

## When something needs attention

| Situation | Next step |
| --- | --- |
| The installed skills are missing | Check that the intended plugin is installed and enabled, then start a new chat or CLI session. Use the source-loading route in the README if installation is unavailable. |
| You have goals but no existing plan | Create the implementation plan first, or use standalone test design if you only need QA planning. |
| The planner asks which source or destination to use | Identify the primary plan and the exact documents it may create or update. |
| The result is marked review-pending | Supply applicable independent reports or use the manual review briefs. |
| An implementation return does not advance the plan | Address the named missing approval, review, check, or predecessor evidence. |
| A command or path is provisional | Have the executor confirm it against the actual project during preparation. |
| A new requirement conflicts with the saved plan | Resolve the material choice and request a scoped revision before affected implementation. |
