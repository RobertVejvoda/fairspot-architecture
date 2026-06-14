# Architecture Governance Log

<!--
Purpose:
Track active board-level architecture questions before they are resolved or routed.

Use this page for:
- architecture questions requiring board or accountable-owner input
- acceptance blockers
- decisions needing evidence before final routing
- questions that may become decisions, gaps, risks, waivers, change sets, or delivery work

Avoid:
- permanent decision history
- local open questions that belong in one artifact
- daily delivery task tracking
-->

The governance log is active intake only. Once an item is resolved, move the final record to the right artifact and remove or close the active log row.

## Governance Log

| ID | Question / Issue | Trigger | Owner | Evidence Needed | Target Review | Status | Route When Resolved |
| --- | --- | --- | --- | --- | --- | --- | --- |
| GOV-001 | Which hosted profile is acceptable for the first customer-facing FairSpot pilot? | Customer-ready deployability. | Robert / Codex | Cloudflare/WAF approach, NAS constraints, backup/restore evidence, smoke evidence, residual risks. | Before external pilot | Open | Deployment Profiles, Readiness, Risk Register, Decisions. |
| GOV-002 | Is DataHub the accepted name and responsibility boundary for replicated read models? | Reporting/PostgreSQL direction superseded. | Robert / Codex | Requirements, data ownership, event flow, projection recovery, privacy shape, delivery slice plan. | Before DataHub implementation baseline | Ready For Review | Decisions, Data Architecture, Integrations and Events, Work Packages. |
| GOV-003 | Which mobile distribution route is needed for first customer validation? | App Store / Google Play question. | Robert | Customer expectation, security, device management, cost, release frequency. | Before mobile pilot | Evidence Needed | Candidate Architectures, Roadmap, Risk Register. |

## Status Values

| Status | Meaning |
| --- | --- |
| Open | Question is active and needs owner/evidence. |
| Evidence Needed | More information is required before review. |
| Ready For Review | Owner believes the item can be decided or routed. |
| Routed | Outcome has been moved to the target artifact. |
| Closed | Item has no remaining architecture action. |

## Routing Rules

| Outcome | Record In |
| --- | --- |
| Durable choice | [Architecture Decisions](/architecture/decisions) |
| Missing capability or evidence | [Gap Analysis](/architecture/architecture-states/gap-analysis) |
| Uncertainty or exposure | [Risk Register](/architecture/architecture-states/risk-register) |
| Time-boxed exception | [Waivers](/architecture/governance/waivers) |
| Multi-artifact solution change | [Architecture Change Set](/architecture/governance/architecture-change-set) |
| Delivery implementation task | FairSpot GitHub issue, with links from the relevant architecture artifact |
| No architecture impact | Close the log item with a short rationale |
