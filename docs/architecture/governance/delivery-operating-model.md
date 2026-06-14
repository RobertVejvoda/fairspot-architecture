# Delivery Operating Model

<!--
Purpose:
Define architecture expectations for the selected delivery model.

Use this page for:
- delivery-model governance expectations after sourcing is selected
- internal and external architecture responsibilities
- handover and run-readiness expectations
- policy, security, deployment, and support conformance

Avoid:
- replacing procurement contracts
- replacing delivery tracking
- duplicating team ceremonies, sprint plans, or staffing plans
-->

Delivery sourcing may be internal, external, or mixed. Candidate options can be maintained in [Delivery Sourcing Options](/architecture/implementation-migration/delivery-sourcing-options), and unresolved sourcing questions can be tracked in the [Architecture Governance Log](/architecture/governance/architecture-governance-log).

This page defines governance expectations that any selected option must satisfy before production acceptance. Option-specific details should be completed after the sourcing decision is recorded.

## Decision-Dependent Model

| Aspect | To Be Defined When Sourcing Is Selected |
| --- | --- |
| Delivery structure | Internal delivery, external fixed-scope/fixed-price delivery, internal-led mixed team, or another selected model. |
| External role | Delivery capacity, specialist advice, fixed-scope accountability, managed service, or no external role. |
| Internal role | Product direction, business context, architecture acceptance, deployment readiness, operations readiness, and long-term maintainability. |
| Team boundary | Delivery scope, decision rights, review responsibilities, and escalation route. |
| Handover model | Evidence that accountable staff can operate and evolve the accepted scope. |
| Acceptance model | Architecture conformance plus option-specific readiness and handover evidence. |

## Delivery Expectations

| Area | Expectation |
| --- | --- |
| Conformance | Use accepted principles, standards, controls, contracts, and deployment profiles. |
| Internal onboarding | Involve accountable staff in design, review, deployment rehearsal, incident scenarios, and handover. |
| Knowledge ownership | Name an accountable technical owner for each accepted capability. |
| Deployment model | Fit the accepted build, release, configuration, observability, backup, restore, and rollback model. |
| Policy adoption | Follow security, privacy, access, audit, change, release, and operational policies or record waivers. |
| Evidence | Link reviews, test results, deployment logs, runbooks, restore tests, access reviews, and operational sign-off. |
| Handover | Show that accountable staff can build, deploy, monitor, support, and change the capability. |
| Supplier transition | Record remaining operational, licensing, access, data, or knowledge dependency on external staff. |

## Acceptance Gate

Delivered scope should not be accepted for production use until:

- delivery sourcing option is selected and recorded where relevant;
- architecture conformance has been reviewed through [Architecture Contract](/architecture/governance/architecture-contract);
- accountable ownership is named and accepted;
- required standards, controls, and deployment profile are satisfied or waived;
- handover and operational readiness evidence are linked;
- residual supplier or capacity dependencies are recorded as gaps, risks, decisions, or waivers.
