# <Plan title>

Status: <draft/review-pending, current continuation state, or reconciled selected scope>. Created: <date>; updated: <date>.

## Purpose and context

- Outcome: <what the source asks to achieve>.
- Non-goals and constraints: <source exclusions and applicable repository constraints>.
- Primary source: <path, revision/date, content digest and relevant locators>.
- Supporting sources: <paths and identities; explain their supporting role when needed>.
- Inspected baseline: <repository, branch/base or non-Git/unborn state, relevant existing/dirty work and date>.
- Assumptions and unresolved decisions: <material unknowns; do not resolve them by invention>.
- Shared evidence/capture context: <briefly state reusable durable references or no new capture expected; when relevant, selected owned roots/contents, expected size or unknown with rationale, target warning units/scope and retention exceptions/consumers. Reuse this context across cards; omit irrelevant inventories>.

## Parts and increments

Parts are navigation; dependencies below govern order. Reuse meaningful source topics and explain material regrouping.

| Part / topic | Purpose | Ordered increment IDs and titles |
| --- | --- | --- |
| <part> | <topic's contribution> | <IDs — short titles> |

## Source coverage

Map material requirements, exclusions, constraints and source gates. A global obligation is a valid owner when it applies across cards; do not create one row per sentence.

| Source ID / locator | Obligation | Owning increment(s) or global obligation | Uncertainty / disposition |
| --- | --- | --- | --- |
| <ID, section or lines> | <meaning-preserving summary> | <IDs or global> | <unknown or proposed coverage, not a claim of completion> |

## Increment cards

### <Stable ID — short title>

- **Outcome and scope:** <single feature, this piece's contribution and one acceptance story>.
- **Exclusions:** <what is outside this card>.
- **Prerequisites / predecessor:** <dependencies, existing work needed and whether acceptance is evidenced or still pending>.
- **Owning areas / interfaces:** <known owners and affected contracts; future exact details remain provisional>.
- **Human review focus:** <the bounded effect a reviewer needs to understand; explain only difficult splits>.
- **Safe intermediate state / compatibility:** <what works after this increment and what must remain compatible>.
- **Acceptance / verification:** <observable criteria and proposed meaningful checks, including the tests belonging with this behavior; distinguish planned from observed evidence. Refer to shared capture context and add only applicable differences>.
- **Recovery:** <how to preserve or restore a safe state within actual authority, without assuming permission for destructive/Git/external actions>.
- **Gates / review scope:** <Gate 2, Gate 3, relevant independent scopes and source/repository obligations; actual scoped bypasses only>.
- **Future impact:** <dependencies/interfaces/acceptance to reassess during preparation and after a later accepted result>.

## Progress and review readiness

| Increment | Factual status | Candidate / evidence | Approval or explicit bypass | Blocker / next action |
| --- | --- | --- | --- | --- |
| <ID> | <proposed or blocked; drafting is not execution> | <baseline and exact candidate; applicable checks/reports or named gaps; retain historical references> | <actual decision/reference or named bypass scope/conditions; historical acceptance is distinct from current applicability> | <specific remaining condition> |

Record actual independent evidence; author checks supply none. Default each scope to pending until its report applies to this candidate. Distinguish substantive reviewed content from later administrative status notes.

| Scope | Reviewer / report | Candidate inspected | Disposition / remaining evidence |
| --- | --- | --- | --- |
| Requirements/source fidelity | <actual identity/link or pending> | <reference> | <material findings and disposition> |
| Architecture/reviewability/simplicity | <actual identity/link or pending> | <reference> | <actual Ponytail or substitute label/reason; disposition> |
| Verification quality | <actual identity/link or pending> | <reference> | <proposed-check quality or actual result-evidence quality, matching the review scope> |

## Decisions and remaining obligations

Record dated material user decisions, source amendments and scoped gate exceptions with their actual reference, scope and conditions. Keep unknowns unresolved and historical accepted IDs/candidates intact. Explain affected readiness separately from historical acceptance; link still-applicable evidence instead of replacing it.

For material revisions, map replaced pending IDs to replacement cards and update coverage/dependencies/parts together. Identify changed obligations, approved rationale and affected review scope. Wording-only changes need no invented whole-plan review. Record whether the current return is preparation for the same increment or a result whose shipped impact has been reconciled.

## Final scope reconciliation

At creation include the terminal task below as planned; leave the outcome table unperformed until assessing closure. Reconcile each original/amended requirement, exclusion and gate through its owner. Bare status and the last card's acceptance are insufficient.

| Obligation / source locator | Owning increment(s) | Candidate and applicable result/review evidence | Achieved, approved amendment/deferral, or unresolved condition |
| --- | --- | --- | --- |
| <ID / locator> | <stable IDs or global owner> | <actual references or exact gap> | <bounded outcome; decision and remaining owner for amendments/deferrals> |

Selected scope demonstrated: <what the combined evidence establishes, or why completion is blocked>.
Separate acceptance/release obligations: <integration/certification/deployment evidence still required; omit if none>.

### Evidence retention and cleanup review

Task status: <planned at creation; later factual completed or blocked status with evidence gaps>. Schedule after the selected scope's relevant verification/reviews; outside feature-increment counts, with no new approval gate.

Identify plan-owned artifacts and owners; confirm required content/references remain available. Record concise keep/hold/cleanup-candidate/unknown dispositions with reasons, outstanding consumers and review events where needed. Include applicable location, measured/estimated/unknown size and retention exceptions from shared context. No new artifacts: record no-cleanup-needed when actually reviewed. Do not invent artifacts or completed outcomes at creation.

Executor cleanup follow-up: <only for concrete necessary work: exact selected paths, preserved evidence, explicit applicable action authority or missing decision, surviving-reference/outcome checks; otherwise omit>. Record proposed/pending/performed separately from review completion; blocked cleanup stays held for its named consumer/event. The planner never deletes or infers permission. Optional undecided storage disposition alone does not block demonstrated product scope; missing mandatory evidence or unmet source-mandated cleanup blocks affected completeness unless explicitly amended.

Next action: <specific evidence/review/decision request, same-increment preparation return, next eligible increment, or final reconciliation outcome>.
Current handoff: [handoff.md](handoff.md).
