# Baseline Architecture

FairSpot does not yet maintain a full enterprise baseline architecture. The baseline is current-state evidence: what is implemented, documented, deployable, or known to be missing.

## Current-State Evidence

| Area | Current State | Evidence | Confidence |
| --- | --- | --- | --- |
| Business | Parking-first fair allocation product with documented booking, Draw, cancellation, notification, audit, reporting, and configuration behavior. | [Business Layer](https://robertvejvoda.github.io/fairspot/#/business-layer), [Allocation Rules](https://robertvejvoda.github.io/fairspot/#/business-layer/allocation-rules), [Booking Request Lifecycle](https://robertvejvoda.github.io/fairspot/#/business-layer/booking-request-lifecycle) | High |
| Applications | Backend services, web, mobile, DataHub skeleton, and supporting infrastructure exist in the repository; implementation completeness varies by slice. | [Software Architecture](https://robertvejvoda.github.io/fairspot/#/technology-layer/software-architecture), [Implementation Tracker](https://robertvejvoda.github.io/fairspot/#/implementation-tracker) | Medium |
| Data | Service-owned persistence and event-fed read-model direction are documented; DataHub is the target for cross-service CQRS reads. | [DataHub](https://robertvejvoda.github.io/fairspot/#/application-layer/datahub), [Function Map Validation](https://robertvejvoda.github.io/fairspot/#/function-map-validation) | Medium |
| Technology | Dapr-first, provider-neutral runtime direction is documented with local/demo/client production profiles. | [Dapr-First Standards](https://robertvejvoda.github.io/fairspot/#/production/dapr-first-production-standards), [Production](https://robertvejvoda.github.io/fairspot/#/production) | High |
| Security | Security model, privacy, audit, and Cloudflare/WAF guidance are documented; validation before hosted pilot remains required. | [Security](https://robertvejvoda.github.io/fairspot/#/security), [Security Model](https://robertvejvoda.github.io/fairspot/#/security/security-model), [Gap Register](https://robertvejvoda.github.io/fairspot/#/security/gap-register) | Medium |

## Baseline Limits

- Existing current-state evidence is assembled from docs, implementation tracker, and PR history rather than one formal baseline model.
- Some implementation tracker entries are historical and may need review before customer-facing claims.
- Billing is intentionally deferred and should not be treated as part of the customer-ready target.
- Legacy layer pages are evidence sources, not the new target architecture folder structure.

## Related Views

| View | Use When | Example |
| --- | --- | --- |
| Baseline Architecture View | A reader needs a high-level current-state picture before comparing target, transition, or gap content. | [Baseline Architecture Overview](#example-baseline-architecture-overview) |
| Gap Closure View | A reader needs to see which baseline-to-target gaps must be closed. | [Gap Closure Map](/architecture/architecture-states/gap-analysis?id=example-gap-closure-map) |

## Example Baseline Architecture Overview

```plantuml
@startuml
!include <archimate/Archimate>
LAYOUT_TOP_DOWN()

Business_Actor(employee, "Employee")
Business_Process(manualRequest, "Parking Request Handling")
Application_Component(app, "Mobile / Web App")
Application_Component(booking, "Booking Component")
Application_DataObject(transientState, "Transient / Partially Proven State")
Application_Component(reporting, "Manual Reporting")
Technology_Node(runtime, "Prototype Runtime")
Technology_Node(localStore, "Local / Unproven Store")
Motivation_Assessment(gap, "Durability And Restore Evidence Gap")

Rel_Triggering(employee, manualRequest, "requests")
Rel_Serving(app, manualRequest, "supports")
Rel_Flow(app, booking, "request")
Rel_Access_rw(booking, transientState, "reads/writes")
Rel_Assignment(runtime, booking, "hosts")
Rel_Assignment(runtime, reporting, "hosts")
Rel_Flow(booking, localStore, "stores")
Rel_Association(gap, transientState, "limits confidence")

' Layering hint: business above application above technology.
employee -[hidden]down- app
manualRequest -[hidden]down- booking
booking -[hidden]down- runtime
transientState -[hidden]down- localStore
@enduml
```
