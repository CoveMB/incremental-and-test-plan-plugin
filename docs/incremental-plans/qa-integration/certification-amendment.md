# Conditional certification planning — authorized amendment

Recorded: 2026-10-16. This supplements, and does not replace, the exact original [source](source.md) and [review inputs](review-inputs.md).

## Direct user requests

The user asked: “does it include if appropriate creating certifications like in egeria-scaffold's plans (review the plans i am refering to)” and then “would it be a good idea to add this into the plugin (when appropriate)?”

The current action request is: “update the plan then then iterate independent review until ready for implementation”. This authorizes the planning refinement and independent review. It does not authorize implementation, certification execution, creating actual execution tasks, or external actions.

## Refinement being planned

Assess whether the target's policy or a material assurance gap warrants a separate certification task/plan. When warranted, design a subject-specific certification card and prerequisite runbook, with evidence, dependencies, closure, renewal, owners and permissions. Preserve source-required certification even when supplementary QA design is excluded. Optional new certification proposals require the material user decision before becoming mandatory gates. Keep ordinary behavior tests with their feature increments; use no universal registry, state engine, Egeria-specific commands, or mandatory deployed checks.

For standalone QA, embed the conditional certification plan/runbook and preparation handoff in `qa-plan.md`. For incremental planning, map it to separate certification cards/dependencies when warranted, using the QA design as the shared detailed owner. This is document design, not task creation, registry mutation, execution or an assertion that anything is certified.

## Inspected supporting sources and their limits

Egeria Scaffold root: `/Users/CoveMB/Code/CoveMB/egeria-scaffold`. The following repository-owned sources were read on 2026-10-16:

- `docs/roadmaps/2026-08-04-nextjs-boilerplate-builder-best-reconciled-plan.md`, “Capability certification journeys” and “Capability implementation and certification task pair” (lines 1080–1110): separate subject-specific tasks, conditional deployed evidence, local/lifecycle checks, exact subject, causal assertions, prerequisite preparation, closure and renewal. Its every-capability rule, registry and CI commands are project-specific, not requirements for every plugin target.
- `docs/governance/review-and-contribution.md`, “Capability-certification planning” (lines 49–67): current step-by-step human prerequisites or evidenced no-setup conclusion; least privilege, credential names/scopes/storage without values, synthetic data, bounded costs/polling, cleanup/recovery, action owners and separate external-action authority.
- `docs/roadmaps/program-roadmap.md`, “Capability delivery task pair” (lines 89–93), and `docs/roadmaps/2026-09-16-remaining-program-delivery-plan.md`, evidence contracts (lines 68–73) and separate certification/subject obligations (lines 735–763): implementation acceptance and certification closure differ; shared scenarios do not establish unrelated subjects by association; renew affected evidence while retaining valid historical proof.

These sources supply a concrete design example. The plugin generalizes only the appropriate planning principles and follows each target's own certification policy; it neither imposes Egeria's domain model nor claims accredited, regulatory or legal certification. Where such assurance is required, identify the qualified authority and required process as an external obligation.

Live primary-source check: [NIST SSDF 1.1, final SP 800-218](https://csrc.nist.gov/pubs/sp/800/218/final), inspected 2026-10-16, supports integrating security practices into the target development lifecycle. It does not prescribe this plugin's separate certification-task workflow. Provider/tool prerequisites must be researched against current official documentation at concrete preparation, rather than freezing transient setup details here.

## Baseline reconciliation

Current local baseline: `main`, HEAD `68ad21a70b38c6cc77e5b549833074e6510ee687`, clean before this amendment. Earlier planning records referred to `bf0c2b19ab4e1e90170fae048824aec3f6da7356`. The intervening commit saved the planning artifacts and changed canonical planner instructions, templates, README and scenario definitions for evidence storage/retention. Preserve that work, including `docs/superpowers/plans/2026-10-16-evidence-storage-retention.md`; it is no longer untracked. No remote refresh is needed for this local revision.

The updated plan must preserve existing capture/retention rules and schedule the terminal Evidence retention and cleanup review outside feature increments. Certification-required cleanup and holding active certification evidence remain distinct from optional storage disposition. This is baseline coherence, not an expansion into implementing the retention plan.

Review scope: the amended substantive plan, current handoff and this input note, compared with the pre-amendment committed documents at `68ad21a`. Historical reports remain historical evidence; obtain fresh source-fidelity, architecture/simplicity and verification-design reports for the amended candidate. Renew only scopes affected by any material correction.
