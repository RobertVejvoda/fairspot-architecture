# Architecture Version Register

This register tracks named FairSpot architecture versions. It complements page-level artifact versions in the [Artifact Register](/architecture/artifact-register).

## Versioning Model

Use the smallest useful version boundary:

| Boundary | Use When | Example |
| --- | --- | --- |
| Requirement status/evidence update | A delivery issue or PR changes evidence for an existing requirement, but the architecture intent is unchanged. | `AR-004` moves from `Partial` to `Implemented` after employee outcome history is accepted. |
| Artifact version bump | A governed page changes materially. | Requirements page adds a new accepted requirement; Security Architecture adds a new control. |
| Architecture version entry | A coherent baseline, target, or transition architecture needs review, approval, or communication as a package. | `Customer-Ready Target v0.2` includes DataHub target, hosted pilot controls, and updated role-specific UX requirements. |

Do not add a named architecture version for every issue or PR. Issues provide delivery evidence; architecture versions describe reviewable architecture states.

| Architecture Version | Type | Status | Date | Scope | Related Artifacts | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| Current State v0.1 | Baseline | Draft | 2026-05-31 | Current-state evidence from docs, implementation tracker, and merged product work. | [Baseline Architecture](/architecture/architecture-states/baseline-architecture) | Lightweight baseline, not a full enterprise baseline architecture. |
| Customer-Ready Target v0.1 | Target | Draft | 2026-05-31 | Target architecture for customer-first deployability and client evaluation. | [Architecture Vision](/architecture/architecture-vision), [Stakeholders and Concerns](/architecture/stakeholders-and-concerns), [Requirements](/architecture/requirements), [Target Architecture](/architecture/architecture-states/target-architecture), [Gap Analysis](/architecture/architecture-states/gap-analysis) | Billing excluded; DataHub, Customer durable storage, hosted pilot evidence, and diagram refresh gaps remain visible. |

## Status Rules

| Status | Meaning |
| --- | --- |
| Draft | Version is being prepared. |
| In Review | Version is ready for formal review. |
| Approved | Version is accepted for its scope. |
| Baselined | Version is the active baseline or target for governance. |
| Superseded | Version has been replaced by a newer version. |
