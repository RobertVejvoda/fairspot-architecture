# Architecture Change Set

<!--
Purpose:
Keep architecture-significant solution changes consistent across the repository.

Use this page for:
- top-down impact checks for material solution changes
- linking a solution change to affected architecture artifacts
- deciding whether a new architecture version is needed

Avoid:
- replacing delivery task tracking
- recording every documentation edit
- creating formal change bureaucracy for minor clarifications
-->

An architecture change set is the smallest controlled package of architecture updates needed to keep the solution consistent after a material change.

Use a change set when a solution change affects ownership, business process, requirements, data, integration, security, deployment, operations, transition sequencing, delivery model, or acceptance evidence.

Do not use a change set for spelling fixes, formatting fixes, or local wording improvements that do not change architecture meaning.

Change set status is architecture-review status, not delivery status. Delivery tasks, assignees, sprint state, and implementation progress remain in the FairSpot GitHub issues and PRs.

## Rule

Version the architecture snapshot, but govern solution change through an impact-checked change set.

When a material solution change is accepted, update the affected artifacts together and record the decision/evidence needed for traceability. If the accepted change alters a named baseline, target, or transition state, add or update the [Architecture Version Register](/architecture/architecture-states/architecture-version-register).

## Change Set Record

| Field | Description |
| --- | --- |
| Change Set ID | Stable ID, for example `ACS-001`. |
| Trigger | New requirement, assessment finding, decision, risk, supplier input, regulatory change, or implementation learning. |
| Affected Architecture Version | Current baseline, target, or transition version affected by the change. |
| Proposed Change | Short statement of what changes in the solution. |
| Decision | Link to [Decisions](/architecture/decisions) when the change creates or changes a durable architecture direction. |
| Status | Proposed, In Review, Accepted, Rejected, or Superseded. |
| Evidence | Links to assessment evidence, delivery issue, review notes, diagrams, tests, or acceptance evidence. |

## Impact Checklist

Before accepting a material solution change, check whether these artifacts need updates:

| Area | Check |
| --- | --- |
| Business | Value streams, capabilities, business processes, actors, and ownership still describe the changed solution. |
| Requirements | Central requirements, constraints, owners, consulted stakeholders, controls, and expected evidence remain valid. |
| Architecture States | Baseline, target, transition architectures, gaps, risks, and acceptance criteria reflect the change. |
| Information Systems | Application responsibilities, data ownership, read/write rules, integrations, events, APIs, and service catalog are consistent. |
| Technology | Runtime, deployment profile, standards, observability, and operational dependencies are still valid. |
| Security | Controls, privacy handling, access expectations, audit evidence, and security gaps are updated where impacted. |
| Migration | Work packages, roadmap, increment boundaries, readiness, and handover expectations still align. |
| Governance | Architecture review, contract expectations, waivers, and delivery operating model cover the changed scope. |
| Views | Diagrams and viewpoints still match the authoritative text or are marked superseded. |
| Versioning | Architecture version register is updated when the named baseline, target, or transition state changes. |

## Practical Flow

1. State the proposed solution change in one paragraph.
2. Decide whether it is architecture-significant.
3. Run the impact checklist and update only affected artifacts.
4. Record a decision if the change alters durable architecture direction.
5. Link delivery work to the FairSpot GitHub issues and PRs if implementation is needed.
6. Update the architecture version register if the change creates a new named snapshot.
7. Close related gaps only when evidence is linked or residual risk is accepted.
