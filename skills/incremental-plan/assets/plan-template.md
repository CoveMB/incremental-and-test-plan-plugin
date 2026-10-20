# <Plan title>

Status: <draft/review-pending, current continuation state, or reconciled selected scope>. Created: <date>; updated: <date>.

## Purpose and context

- Outcome: <what the source asks to achieve>.
- Non-goals and constraints: <source exclusions and applicable repository constraints>.
- Implementation naming: <reproduce the shared [semantic-naming contract](../references/gates-and-reviews.md#semantic-naming) in plain language: domain/behavior names for every authored/generated surface, including documentation; delivery labels describe work, with exceptions specific to tracking/provenance references. Preserve source/history, legitimate domain names and compatibility; source-name conflicts or migrations await the applicable decision. Select concrete names during preparation before Gate 2 and check actual changed artifacts during architecture review>.
- Primary source: <path, revision/date, content digest and relevant locators>.
- Supporting sources: <paths and identities; explain their supporting role when needed. For [material research dependencies](../references/gates-and-reviews.md#research-dependent-decisions), record claim-to-source-to-decision/check correspondence, source version/date and locator, actual inspection or applicable reuse, limitations and disposition here or in the owning acceptance/review fields; omit an empty research assessment>.
- Inspected baseline: <repository, branch/base or non-Git/unborn state, relevant existing/dirty work and date>.
- QA mode and correspondence: <on by default for new conversion, or actual explicit supplementary exclusion; selected QA path and source/candidate identity when on. Reuse current selected QA rather than duplicate it; retain historical QA on exclusion and distinguish mandatory obligations from non-governing supplementary proposals>.
- Assumptions and unresolved decisions: <material unknowns; do not resolve them by invention>.
- Orchestration approval mode: <manual by default, or explicitly requested Preapproved orchestration for the selected plan/repository/increments; distinguish proposed export from an adopted human grant and preserve any narrower conditions. Mode selection is not plan/result approval>.
- Shared evidence/capture context: <briefly state reusable durable references or no new capture expected; when relevant, selected owned roots/contents, expected size or unknown with rationale, target warning units/scope and retention exceptions/consumers. Reuse this context across cards; omit irrelevant inventories>.

## Parts and increments

Parts are navigation; dependencies below govern order. Reuse meaningful source topics and explain material regrouping.

| Part / topic | Purpose | Ordered increment IDs and titles |
| --- | --- | --- |
| <part> | <topic's contribution> | <IDs — short titles> |

## Source coverage

Map material requirements, exclusions, constraints and source gates, including applicable QA checks/gaps and certification prerequisites. Link detailed QA design to its owning feature increments/global obligations rather than duplicating an implementation plan. With supplementary QA excluded, record required tests/certification subject/runbook/evidence/closure here and in the portable handoff. A global obligation is a valid owner when it applies across cards; do not create one row per sentence. Assign critical combined journeys an owning increment or global obligation, expected outcome and required evidence on the relevant combined candidate/environment.

| Source ID / locator | Obligation | Owning increment(s) or global obligation | Uncertainty / disposition |
| --- | --- | --- | --- |
| <ID, section or lines> | <meaning-preserving summary> | <IDs or global> | <unknown or proposed coverage, not a claim of completion> |

## Increment cards

### <Stable ID — short title>

- **Outcome and scope:** <single feature, this piece's contribution and one acceptance story>.
- **Exclusions:** <what is outside this card>.
- **Prerequisites / predecessor:** <dependencies, existing work needed and whether acceptance is evidenced or still pending>.
- **Owning areas / interfaces:** <known owners and affected contracts; future exact details remain provisional>.
- **QA ownership:** <applicable source/check/gap references and concrete owners; tests stay with the feature. For warranted separate certification, matching implementation prerequisite, subject/environment and target dependency/closure gate; proposed new mandatory gates remain decision-pending. Omit an empty field>.
- **Human review focus:** <the bounded effect a reviewer needs to understand; briefly explain non-obvious grouping or splitting under the [increment-boundary guidance](../SKILL.md#craft-the-increments)>.
- **Safe intermediate state / compatibility:** <what works after this increment and what must remain compatible>.
- **Acceptance / verification:** <observable criteria, independently justified expected outcomes and proposed checks that detect material wrong behavior, with necessary candidate/environment/data; include tests belonging with this behavior. Connect material failure consequences to the chosen evidence or unresolved question, proportionately. Identify material branches/transitions and combinations, selected discriminating checks or justified omissions with residual owners, warranted sensitivity evidence/controls and relevant human-inspection assumptions; reference detailed QA rows when on. Assign final delivered-artifact/document reconciliation after the last relevant update. Distinguish planned from observed evidence. Refer to shared capture context and add only applicable differences; no extra matrix or mandatory technique quota>.
- **Recovery:** <how to preserve or restore a safe state, what harm rollback cannot repair and unresolved safeguards/owners, within actual authority; do not invent consequential behavior or assume permission for destructive/Git/external actions>.
- **Gates / review scope:** <Gate 2, Gate 3, the shared policy's three distinct independent implementation reports for this increment and source/repository obligations; actual scoped bypasses only. Record stronger review coverage when the source requests fewer reviews, and any explicit cap/conflict or applicable direct amendment. Regular reviews are the default. Apply the shared policy's implementation-result Ponytail default: proposed/actual default, scoped exclusion, substitute or pending route and reason; explicit candidate/comparison, applicable authority and rerun condition. Propose the bounded read-only pass in the concrete Gate 2 packet; drafting it is not approval. No default Ponytail plan-stage pass. For a warranted optional material-code-review recommendation, include concrete rationale, future Git candidate/timing and scopes its report could cover; note possible unavailability and regular independent fallback with appropriate scopes, preserving every required review>.
- **Future impact:** <dependencies/interfaces/acceptance to reassess during preparation and after a later accepted result>.

## Progress and review readiness

| Increment | Factual status | Candidate / evidence | Approval, delegation or explicit bypass | Blocker / next action |
| --- | --- | --- | --- | --- |
| <ID> | <proposed or blocked; drafting is not execution> | <baseline and exact candidate; applicable checks/reports or named gaps; retain historical references> | <verified original human grant/decision reference, scope, gates/actions, conditions and amendments; for an actual delegated approval identify the orchestrator, candidate and evidence/rationale, never human review of an unseen result. Historical acceptance is distinct from current applicability> | <actual remaining condition after authority/evidence reconciliation> |

Record actual independent evidence; author checks supply none. Default each scope to pending until its report applies to this coordinated plan/QA/handoff candidate. One set of three scopes covers the artifact set; keep readiness and embedded/current handoffs aligned. Distinguish substantive reviewed content from later administrative status notes.

For material research dependencies, give the requirements and verification reviewers the relevant underlying sources and their respective duties under the shared policy. Record actual assessment and unresolved owners in these existing reports; citations or planned source reads are not completed review.

| Scope | Reviewer / report | Candidate inspected | Disposition / remaining evidence |
| --- | --- | --- | --- |
| Requirements/source fidelity | <actual identity/link or pending> | <reference> | <material findings and disposition> |
| Architecture/reviewability/simplicity | <actual identity/link or pending> | <stage and bounded candidate/comparison> | <actual Ponytail/default, scoped exclusion, substitute or pending reason; applicable authority, disposition and rerun condition. Plan-stage architecture assessment does not imply Ponytail ran; proposed reviews are not reports> |
| Verification quality | <actual identity/link or pending> | <reference> | <proposed-check quality or actual result-evidence quality, matching the review scope> |

## Decisions and remaining obligations

Apply the [authority reconciliation rule](../references/gates-and-reviews.md#owners-and-authority) before deriving current progress, gate dispositions and the next action. Record dated material user decisions, source amendments and scoped gate/action permissions with their original reference, scope, conditions and later amendments. Preserve superseded “no bypass” or “preparation only” statements as dated history; align current cards, this table and authorized QA/handoff outputs with surviving authority. Keep unknowns unresolved and historical accepted IDs/candidates intact. Explain affected readiness separately from historical acceptance; link still-applicable evidence instead of replacing it. Recording authority alone does not establish an implementation result or invalidate unchanged reviews.

For material revisions, map replaced pending IDs to replacement cards and update coverage/dependencies/parts together. Identify changed obligations, approved rationale and affected review scope. Wording-only changes need no invented whole-plan review. Record whether the current return is preparation for the same increment or a result whose shipped impact has been reconciled.

## Final scope reconciliation

At creation include the terminal task below as planned; leave the outcome table unperformed until assessing closure. Reconcile each original/amended requirement, exclusion and gate through its owner, including required combined evidence rather than inferring it from component passes. Check final artifact identities, completion claims, evidence links and retained limits after the last relevant update; renew only affected proof. Bare status and the last card's acceptance are insufficient.

| Obligation / source locator | Owning increment(s) | Candidate and applicable result/review evidence | Achieved, approved amendment/deferral, or unresolved condition |
| --- | --- | --- | --- |
| <ID / locator> | <stable IDs or global owner> | <actual references or exact gap> | <bounded outcome; decision and remaining owner for amendments/deferrals> |

Selected scope demonstrated: <what the applicable evidence establishes, important untested conditions and outstanding obligations with owners/needed evidence, or why completion is blocked>.
Separate acceptance/release obligations: <integration/certification/deployment evidence still required and its owners; when release is in scope, its responsible human decision-maker and operational/specialist evidence. Implementation acceptance alone does not establish release readiness; omit inapplicable categories>.

### Evidence retention and cleanup review

Task status: <planned at creation; later factual completed or blocked status with evidence gaps>. Schedule after the selected scope's relevant verification/reviews; outside feature-increment counts, with no new approval gate.

Identify plan-owned artifacts and owners; confirm required content/references remain available. Record concise keep/hold/cleanup-candidate/unknown dispositions with reasons, outstanding consumers and review events where needed. Include applicable location, measured/estimated/unknown size and retention exceptions from shared context. No new artifacts: record no-cleanup-needed when actually reviewed. Do not invent artifacts or completed outcomes at creation.

Executor cleanup follow-up: <only for concrete necessary work: exact selected paths, preserved evidence, explicit applicable action authority or missing decision, surviving-reference/outcome checks; otherwise omit>. Record proposed/pending/performed separately from review completion; blocked cleanup stays held for its named consumer/event. The planner never deletes or infers permission. Optional undecided storage disposition alone does not block demonstrated product scope; missing mandatory evidence or unmet source-mandated cleanup blocks affected completeness unless explicitly amended.

Next action: <specific evidence/review/decision request, same-increment preparation return, next eligible increment, or final reconciliation outcome>.
Current handoff: [handoff.md](handoff.md).
