# Candidate Architectures

<!--
Purpose:
Capture architecture options and early solution shapes before they are validated as target or transition architecture.

Use this page for:
- high-level architecture ideas that need assessment
- competing target options
- possible transition approaches
- assumptions, risks, and open questions before board acceptance

Avoid:
- presenting candidates as approved target architecture
- duplicating the accepted target or transition architecture
- tracking implementation tasks
-->

Candidate architectures are useful when architecture thinking exists before assessment, board review, or evidence is complete.

A candidate is not the target architecture. It is assessment input. Once accepted, the selected option is promoted into [Target Architecture](/architecture/architecture-states/target-architecture) or [Transition Architectures](/architecture/architecture-states/transition-architectures). Rejected options can stay here as context or be summarized in [Architecture Decisions](/architecture/decisions).

## Candidate Register

| Candidate ID | Candidate | Scope | Main Assumptions | Benefits | Risks / Gaps | Status | Outcome / Route |
| --- | --- | --- | --- | --- | --- | --- | --- |
| CAND-001 | FairSpot hosted pilot on NAS behind Cloudflare. | Hosted demo / early customer evaluation. | NAS remains acceptable for the first private pilot; Cloudflare can provide WAF/TLS/public boundary; backup/restore evidence is sufficient for pilot scope. | Fastest path to customer-visible evidence without selecting a permanent cloud platform. | Production-grade operations, restore, monitoring, and security evidence remain gaps. | Assessment Input | Deployment profile, risk register, readiness evidence. |
| CAND-002 | DataHub as event-fed replicated read store. | Cross-service operational reads, HR views, reports, draw history, role-safe projections. | Service-owned writes remain authoritative; Dapr pub/sub and idempotent projections can keep tenant-scoped reads current enough. | Supports role-specific reads without coupling UI/reporting to private service stores. | Projection freshness, replay, schema evolution, privacy shape, and operational evidence still need validation. | Recommended | Target data architecture, work packages, delivery slices. |
| CAND-003 | Native app store distribution deferred. | Mobile app packaging and customer access. | Web/PWA or Expo-based pilot access is enough for early customer validation. | Avoids App Store / Google Play operational overhead before product-market validation. | Customer expectations may require managed store distribution later. | Draft | Mobile transition architecture or deferred scope decision. |

## Status Values

| Status | Meaning |
| --- | --- |
| Draft | Candidate is being shaped and is not ready for review. |
| Assessment Input | Candidate is ready to compare against alternatives or assessment evidence. |
| Recommended | Candidate is recommended but not yet accepted by the Architecture Board or accountable owner. |
| Promoted | Candidate has been accepted and moved into target or transition architecture. |
| Rejected | Candidate was considered and not selected. |
| Superseded | Candidate was replaced by another candidate. |

## Candidate Record

Use this lightweight shape when a candidate needs more than one row:

| Field | Description |
| --- | --- |
| Candidate ID | Stable ID, for example `CAND-001`. |
| Scope | Business functions, systems, data, integrations, operations, or governance scope covered. |
| Architecture Sketch | Short narrative or diagram link. |
| Assumptions | What must be true for this candidate to work. |
| Benefits | Why this candidate may be useful. |
| Risks / Gaps | Known concerns, missing evidence, or unresolved questions. |
| Impacted Artifacts | Requirements, target, transition, data, application, technology, security, migration, governance, views. |
| Status | Draft, Assessment Input, Recommended, Promoted, Rejected, or Superseded. |
| Outcome / Route | Target architecture, transition architecture, decision, gap, risk, waiver, change set, or no further action. |

## Promotion Rule

Do not update [Target Architecture](/architecture/architecture-states/target-architecture) or [Transition Architectures](/architecture/architecture-states/transition-architectures) just because a candidate exists.

Promote a candidate only when it is accepted or explicitly selected for review. At that point:

1. Record or update the durable decision in [Architecture Decisions](/architecture/decisions) if alternatives were considered.
2. Use an [Architecture Change Set](/architecture/governance/architecture-change-set) when the selected candidate changes requirements, gaps, target, transition, domain architecture, migration, governance, or diagrams.
3. Update [Architecture Version Register](/architecture/architecture-states/architecture-version-register) only if the accepted candidate changes a named baseline, target, or transition snapshot.
4. Leave rejected or superseded candidates here with a short outcome so the reasoning is not lost.
