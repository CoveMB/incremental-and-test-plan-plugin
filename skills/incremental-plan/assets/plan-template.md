# <Plan title>

Status: <draft/review-pending, current continuation state, or reconciled selected scope>. Created: <date>; updated: <date>.

## Purpose and context

- Outcome: <what the source asks to achieve>.
- Non-goals and constraints: <source exclusions and applicable repository constraints>.
- Primary source: <path, revision/date, content digest and relevant locators>.
- Supporting sources: <paths and identities; explain their supporting role when needed>.
- Inspected baseline: <repository, branch/base or non-Git/unborn state, relevant existing/dirty work and date>.
- Assumptions and unresolved decisions: <material unknowns; do not resolve them by invention>.

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
- **Acceptance / verification:** <observable criteria and proposed meaningful checks, including the tests belonging with this behavior; distinguish planned from observed evidence>.
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

Use when assessing closure; omit while unrelated to the current step. Reconcile each original/amended requirement, exclusion and gate through its owner. Bare status and the last card's acceptance are insufficient.

| Obligation / source locator | Owning increment(s) | Candidate and applicable result/review evidence | Achieved, approved amendment/deferral, or unresolved condition |
| --- | --- | --- | --- |
| <ID / locator> | <stable IDs or global owner> | <actual references or exact gap> | <bounded outcome; decision and remaining owner for amendments/deferrals> |

Selected scope demonstrated: <what the combined evidence establishes, or why completion is blocked>.
Separate acceptance/release obligations: <integration/certification/deployment evidence still required; omit if none>.

Next action: <specific evidence/review/decision request, same-increment preparation return, next eligible increment, or final reconciliation outcome>.
Current handoff: [handoff.md](handoff.md).
