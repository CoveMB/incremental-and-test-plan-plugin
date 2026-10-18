# Review inputs and authority

This is a scoped source note for reviewing the implementation plan. It is not an approval record or an execution instruction. The latest user request is preserved verbatim in [source.md](source.md). Repository guidance and current canonical package sources remain necessary context.

## Direct user decisions after that request

The controller asked:

> Should the new design be one renamed plugin containing both incremental-plan and qa-design, replacing the earlier separate-plugin idea?

The user answered:

> One combined plugin (Recommended)

The controller asked:

> For the package rename, should existing saved plans remain usable with documented migration to the new invocation name, or must the old invocation name also keep working?

The user answered:

> no need for backward compatibility the plugin as not yet been use let's keep simple as if it is first version

These decisions replace the earlier separate-plugin proposal and its migration options. The latest user request sets QA design to on by default with an optional exclusion. No implementation, commit, installation, publication, or live behavioral evaluation has been authorized by this planning request. Independent read-only plan reviews are explicitly requested.

## Earlier user request defining the two uses

> could we create a second plugin that review a plan or project and designs appropriate qa, end to end and other type of tests mentioned in this article that can then either be trigger in an already existing project to design appropriate QA design implementation plan or used by current skill that create incremental plan to also add the qa designed into ?

The two uses remain required; the separate-package proposal has been replaced by the combined-package decision above.

## Earlier assistant recommendations referenced by “all the changes”

The following excerpts are the recommendations the user asked to plan. They are source material for scope, not independent evidence that the recommendations are correct.

### Verification and existing gates

1. **Before Gate 2: connect verification to failure consequences.** Identify material failures, their consequences, and whether recovery can actually repair the harm. Use that assessment to select necessary runtime, security, migration, accessibility, or expert evidence. A rollback may restore software while leaving disclosed data or incorrect payments unresolved. Where the source leaves consequential behavior unspecified, surface a material question before approving the affected implementation. Keep this proportionate: a short explanation in existing acceptance/recovery fields is enough.
2. **Strengthen the verification reviewer’s brief: challenge the tests themselves.** Examine where expected answers come from: approved requirements, trusted examples, or a justified reference, not simply the implementation’s own calculations. Examine whether checks detect relevant incorrect behavior, using a failing regression demonstration or targeted mutation where warranted. Removed assertions, broader tolerances, skipped cases, or excessive mocking need justification against the approved behavior. Comparing against existing behavior can establish compatibility; it cannot establish the correctness of an intentionally changed rule. Separate agents also need to challenge shared assumptions; separation alone supplies no guarantee. Keep mutation testing and other expensive techniques conditional on a concrete verification weakness.
3. **At Gate 3 and closure: make combined behavior and residual uncertainty explicit.** Assign an owner and appropriate evidence to critical behavior spanning increments whenever separate component checks cannot demonstrate that behavior. Distinguish demonstrated behavior, important untested conditions, and outstanding obligations with an owner. Where release is in scope, identify the responsible human decision-maker and applicable operational evidence. Gate 3 remains implementation-result approval; release readiness needs its own applicable evidence.

Four proposed evaluations accompanied those recommendations:

| Supplied situation | Expected planner behavior |
| --- | --- |
| Implementation and tests share the same incorrect assumption | Challenge the expected result despite green tests. |
| A regression passes after its assertion is weakened | Require a contract-based justification. |
| Component tests pass, but a critical combined journey is unverified | Keep the integration evidence gap visible. |
| An irreversible operation has vague safeguards | Surface the missing decision/evidence; keep low-risk work proportionate. |

### QA design and integration

The proposed first version was planning-only, with one skill reviewing a supplied plan, an existing project, or both. Its job was to determine what evidence would make intended behavior trustworthy, then produce an actionable plan for creating that evidence.

| Use | Intended result |
| --- | --- |
| Existing project | Inspect requirements, important user journeys, architecture, existing tests and CI; produce a QA design and implementation plan for material gaps. |
| Proposed feature or project plan | Design appropriate verification before implementation, marking assumptions that need confirmation against actual code. |
| Alongside incremental-plan | Supply QA obligations incorporated into relevant feature increments and acceptance criteria. |

The proposed techniques were unit, integration, contract, end-to-end, regression, property-based, fuzz, targeted mutation, security, performance, accessibility, visual, exploratory, human acceptance, specialist, migration, recovery, and operational checks. They were available techniques rather than a checklist every project must implement. Existing useful coverage should be retained, and proposed tooling should fit the current stack.

Each proposed check should explain the behavior or risk addressed, expected result and independent basis, necessary environment/data, and evidence that would count as passing. The design should identify important gaps automation cannot resolve.

The proposed handoff was a shared Markdown deliverable. QA design owns verification design; incremental-plan owns sequencing, coherent increment boundaries, and its existing gates. Tests stay with the behavior they protect; shared infrastructure and combined journeys get explicit owners where needed. Material changes to product scope or acceptance remain user decisions. Both workflows should remain independently useful using instructions, references, and templates. The user has since selected a single package and QA-on by default, replacing the earlier opt-in recommendation.

## Supporting public sources

- [Mark Seemann, Releasing AI-generated software, 12 October 2026](https://blog.ploeh.dk/2026/10/12/releasing-ai-generated-software/). Review the article itself. Do not treat its reported experiments, speculative comparisons, or legal illustrations as established empirical or jurisdiction-specific legal findings.
- [OpenAI, Build skills](https://developers.openai.com/plugins/build/skills), inspected 16 October 2026. Relevant to skill packaging and activation/output evaluation.
- [OpenAI, Package your plugin](https://developers.openai.com/plugins/build/plugins), inspected 16 October 2026. Existing Codex compatibility manifests remain supported; a portable-manifest migration is not required for this bounded change.
- [NIST SSDF 1.1, PW.8](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-218.pdf), inspected 16 October 2026. Supports choosing suitable verification and separating its design from performed, documented results.

Public sources inform the design. They do not grant action permissions or override the user's requirements.
