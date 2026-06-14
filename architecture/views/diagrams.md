# Diagrams

This index keeps current diagrams discoverable, displays important source evidence, and makes missing architecture views explicit.

The repository has two diagram classes:

- **Source evidence** - existing exports, ArchiMate models, draw.io files, BPMN files, and validation diagrams that explain prior design intent.
- **Authoritative target views** - refreshed diagrams that match the current architecture repository and can be used in customer or implementation review.

Until a target view is explicitly marked authoritative, the text architecture pages remain the source of truth where they differ from an old diagram.

## Source Evidence Inventory

| Evidence | Purpose | Source / Export | Refresh Disposition |
| --- | --- | --- | --- |
| Exchange map | Shows high-level business exchanges and capability relationships. | [Exchange Map image](/images/fps-exchange-map.png), [Legacy Architecture Evidence](https://robertvejvoda.github.io/fairspot/#/architecture-views) | Reuse as source evidence; refresh or annotate for customer-ready target scope and deferred Billing. |
| Function map | Shows function/service relationship and implementation alignment. | [Function Map image](/images/fps-function-map.png), [Function Map Validation](https://robertvejvoda.github.io/fairspot/#/function-map-validation) | Reuse as source evidence; supersede with target capability and application cooperation views. |
| Application architecture | Shows application/service structure. | [Application Architecture image](/images/fps-application-architecture.png) | Reuse as source evidence; replace with target application cooperation view. |
| Application Architecture 1 | Shows browser/mobile, gateway, IAM, services, Dapr, stores, observability, and staged target components. | [Application Architecture 1 image](/images/fps-application-arch-1.png), [Validation](https://robertvejvoda.github.io/fairspot/#/application-arch-1-validation) | Strong source evidence; refresh to include DataHub, Customer persistence gap, Reporting obsolescence, and hosted profile. |
| Application Architecture 2 | Additional target application view. | [Application Architecture 2 image](/images/fps-application-arch-2.png) | Source evidence only until reconciled with the current application architecture. |
| Data architecture | Shows target data architecture shape. | [Data Architecture image](/images/fps-data-architecture.png) | Source evidence; replace with DataHub/read-model ownership view. |
| Logical architecture | Shows logical runtime/deployment shape. | [Logical Architecture image](/images/fps-logical-architecture.png) | Source evidence; replace with runtime deployment and trust-boundary views. |
| Provider examples | Show older Azure/AWS variants. | [Azure Application Architecture](/images/fps-application-arch-azure.png), [Azure Logical Architecture](/images/fps-logical-architecture-azure.png), [AWS Logical Architecture](/images/fps-logical-architecture-aws.png) | Keep as environment examples only; not core target architecture unless a decision records provider selection. |
| Software architecture and packages | Shows software packages and service boundaries. | [Software Architecture](https://robertvejvoda.github.io/fairspot/#/technology-layer/software-architecture), package and service images under `images/` | Source evidence; service catalog and target diagrams are authoritative after refresh. |
| BPMN process evidence | Shows older process flows. | [Draw BPMN](/process/draw.bpmn), [Subscribe Tenant BPMN](/process/subscribe-tenant.bpmn), [Generate Invoice BPMN](/process/generate-invoice.bpmn) | Draw can inform target process/workflow views; Billing invoice process is deferred. |
| Model files | Contain editable model sources. | `archi/fps.archimate`, `fps.drawio`, `fps-composition.drawio`, `wireframes.drawio` | Source model files; update only when Robert refreshes or approves the target model. |

## Diagram Evidence Gallery

The diagrams below are displayed as source evidence so readers can inspect the earlier model quickly. They are useful for migration and review, but they are not automatically authoritative. If a diagram conflicts with current target text, the target architecture pages and gap register win.

### Exchange Map

![FairSpot exchange map](/images/fps-exchange-map.png)

| Field | Value |
| --- | --- |
| Current use | High-level explanation of FairSpot business/application exchanges and adjacent capabilities. |
| Adoption status | Source evidence. Useful for business architecture and capability discussions. |
| Known gap | Needs annotation for the customer-first parking scope, deferred Billing, DataHub target, and which exchanges are current versus future. |

### Function Map

![FairSpot function map](/images/fps-function-map.png)

| Field | Value |
| --- | --- |
| Current use | Explains target functions/services and how product capabilities map to implementation areas. |
| Adoption status | Partial. The capability/application split has been restated in Business Architecture and Application Architecture. |
| Known gap | Needs refresh so Reporting/PostgreSQL does not look like the target read-model store, and so DataHub, Customer persistence, resource maps, and role-specific workspaces are visible. |

### Application Architecture 1

![FairSpot application architecture 1](/images/fps-application-arch-1.png)

| Field | Value |
| --- | --- |
| Current use | Strong source evidence for browser/mobile clients, API boundary, identity, services, Dapr, state stores, observability, and staged target components. |
| Adoption status | Partial. The text target now clarifies Booking ownership, Configuration policy/resource maps, Customer durable state, DataHub read models, Audit, Notification, and deferred Reporting/Billing. |
| Known gap | Needs an authoritative application cooperation view that separates command owners, DataHub projections, Reporting catalog/presentation, and hosted-profile infrastructure. |

### Application Architecture 2

![FairSpot application architecture 2](/images/fps-application-arch-2.png)

| Field | Value |
| --- | --- |
| Current use | Additional application-level evidence for earlier target thinking. |
| Adoption status | Source evidence only. |
| Known gap | Must be reconciled with the current DataHub, Dapr workflow, hosted deployment, and Reporting cleanup decisions before it can be used as target architecture. |

### Data Architecture

![FairSpot data architecture](/images/fps-data-architecture.png)

| Field | Value |
| --- | --- |
| Current use | Explains earlier data ownership/read model direction. |
| Adoption status | Partial. The current target is service-owned writes plus DataHub as the event-fed replicated read store. |
| Known gap | Needs a target DataHub/read-model view showing event inbox, projection checkpoints, approved read APIs, projection health, privacy shape, and rebuild path. |

### Logical Architecture

![FairSpot logical architecture](/images/fps-logical-architecture.png)

| Field | Value |
| --- | --- |
| Current use | Source evidence for runtime/deployment boundaries. |
| Adoption status | Partial. Runtime Platform and Deployment Profiles now describe the Dapr-first hosted profile in text. |
| Known gap | Needs authoritative deployment and trust-boundary views for NAS, Cloudflare/WAF, Dapr sidecars/components, state stores, backups, observability, and public/private surfaces. |

### Software Architecture And Package Evidence

| Evidence | Link | Use | Status |
| --- | --- | --- | --- |
| Software architecture | [Image](/images/fps-software-architecture.png) | Explains earlier software package and service structure. | Source evidence until service catalog and target application cooperation view are authoritative. |
| Detailed software architecture | [Image](/images/fps-software-architecture-detailed.png) | Lower-level package detail. | Source evidence; useful for implementation orientation, not customer-facing target validation. |
| Booking service package | [Image](/images/fps-software-arch-booking.png) | Booking internal component evidence. | Source evidence. |
| Configuration service package | [Image](/images/fps-software-arch-configuration.png) | Configuration internal component evidence. | Source evidence. |
| Customer service package | [Image](/images/fps-software-arch-customer.png) | Customer internal component evidence. | Source evidence; must reflect durable persistence progress and remaining gaps. |
| Audit service package | [Image](/images/fps-software-arch-audit.png) | Audit internal component evidence. | Source evidence. |
| Profile service package | [Image](/images/fps-software-arch-profile.png) | Profile internal component evidence. | Source evidence. |
| Reporting service package | [Image](/images/fps-software-arch-reporting.png) | Earlier Reporting component evidence. | Obsolete unless reduced to report catalog/configuration/presentation over DataHub-approved views. |

### Process Model Evidence

| Process Evidence | Link | Use | Status |
| --- | --- | --- | --- |
| Draw BPMN | [BPMN file](/process/draw.bpmn) | Source for Draw process, allocation, and operational workflow refresh. | Partial; target Draw workflow view still needed. |
| Subscribe Tenant BPMN | [BPMN file](/process/subscribe-tenant.bpmn) | Source for tenant onboarding/readiness process. | Source evidence; useful for Customer and tenant readiness. |
| Generate Invoice BPMN | [BPMN file](/process/generate-invoice.bpmn) | Source for future Billing process. | Deferred with Billing scope. |

## Target View Catalog

| Target View | Viewpoint | Owning Artifact | Current Status | Source Evidence | Refresh Decision / TODO |
| --- | --- | --- | --- | --- | --- |
| Product outcome map | Motivation and outcome | [Architecture Vision](/architecture/architecture-vision) | Optional | [Strategy](https://robertvejvoda.github.io/fairspot/#/strategy), [Roadmap](https://robertvejvoda.github.io/fairspot/#/roadmap) | Text currently sufficient; add only if customer review needs a visual summary. |
| Process classification diagram | Process classification | [Business Processes](/architecture/business/business-processes) | Placeholder | [Business Processes](/architecture/business/business-processes), legacy business-layer process pages | Robert TODO: classify FairSpot processes as management, core, and support processes, with Billing and broad support portal marked deferred where applicable. |
| Business process diagram | Business process | [Business Processes](/architecture/business/business-processes) | Partial | [Draw BPMN](/process/draw.bpmn), [Booking Request Lifecycle](https://robertvejvoda.github.io/fairspot/#/business-layer/booking-request-lifecycle), [Allocation Rules](https://robertvejvoda.github.io/fairspot/#/business-layer/allocation-rules) | Consolidate request, Draw, allocation, cancellation/reallocation, same-day behavior, and HR/admin actions into current target process diagrams. |
| Organized process diagram | Organized process | [Business Processes](/architecture/business/business-processes), [Actors and Roles](/architecture/business/actors-roles) | Placeholder | [Business Processes](/architecture/business/business-processes), [Actors and Roles](/architecture/business/actors-roles), [RACI](/architecture/governance/raci) | Robert TODO: show which roles execute, approve, audit, or receive notifications for core processes. |
| Functional architecture diagram | Functional architecture | [Capabilities](/architecture/business/capabilities), [Application Architecture](/architecture/information-systems/application-architecture) | Partial | [Function Map image](/images/fps-function-map.png), [Function Map Validation](https://robertvejvoda.github.io/fairspot/#/function-map-validation), [Functional Architecture](https://robertvejvoda.github.io/fairspot/#/business-layer/functional-architecture) | Reuse as source evidence; refresh as target functional architecture and clarify where it bridges business functions and application responsibilities. |
| Organization model | Organization | [Actors and Roles](/architecture/business/actors-roles), [Governance](/architecture/governance/) | Placeholder | [Actors and Roles](/architecture/business/actors-roles), [RACI](/architecture/governance/raci) | Add only if customer review needs an organization/role responsibility model beyond text and RACI tables. |
| Product and service catalog | Product and service catalog | [Capabilities](/architecture/business/capabilities), [Architecture Vision](/architecture/architecture-vision) | Placeholder | [Product Overview](https://robertvejvoda.github.io/fairspot/#/Home), [Architecture Vision](/architecture/architecture-vision), [Commercialisation](https://robertvejvoda.github.io/fairspot/#/strategy-layer/commercialisation) | Robert TODO: define FairSpot free-core service, hosted evaluation service, deferred Billing, and future resource domains. |
| Product and service realization | Product and service realization | [Value Streams](/architecture/business/value-streams), [Application Architecture](/architecture/information-systems/application-architecture) | Placeholder | [Value Streams](/architecture/business/value-streams), [Application Architecture](/architecture/information-systems/application-architecture) | Show how employee booking, HR operations, tenant readiness, and hosted evaluation are realized by functions, applications, and technology. |
| Capability map | Capability | [Capabilities](/architecture/business/capabilities) | Placeholder | [Exchange Map image](/images/fps-exchange-map.png), [Function Map image](/images/fps-function-map.png) | Robert TODO: create target capability map with customer-first parking scope, deferred Billing, and future resource domains marked as future scope. |
| Value stream map | Value stream | [Value Streams](/architecture/business/value-streams) | Placeholder | [Exchange Map image](/images/fps-exchange-map.png), [Business Processes](/architecture/business/business-processes) | Robert TODO: show request, Draw, allocation, cancellation/reallocation, HR operations, admin policy/resource setup, and feedback. |
| Draw and cancellation process view | Business process | [Business Processes](/architecture/business/business-processes) | Partial | [Draw BPMN](/process/draw.bpmn), [Booking Request Lifecycle](https://robertvejvoda.github.io/fairspot/#/business-layer/booking-request-lifecycle), [Allocation Rules](https://robertvejvoda.github.io/fairspot/#/business-layer/allocation-rules) | Consolidate into target process view; keep same-day request behavior and employee/HR/admin responsibilities visible. |
| Role interaction view | Role and actor | [Actors and Roles](/architecture/business/actors-roles) | Placeholder | [Role Intent Roadmap](https://robertvejvoda.github.io/fairspot/#/business-layer/role-intent-roadmap), [My Spots UX](https://robertvejvoda.github.io/fairspot/#/business-layer/my-spots-ux) | Create only if role-specific UI/default-view behavior needs visual validation. |
| Information model | Information model | [Data Architecture](/architecture/information-systems/data-architecture) | Placeholder | [Data Architecture image](/images/fps-data-architecture.png), [Data Architecture](/architecture/information-systems/data-architecture) | Robert TODO: define business information concepts such as Tenant, Employee, Booking Request, Draw, Allocation, Vehicle, Resource Map, Policy, and Audit Reference. |
| Information lifecycle diagram | Information lifecycle | [Data Architecture](/architecture/information-systems/data-architecture), [Privacy Architecture](/architecture/security/privacy-architecture) | Placeholder | [Data Privacy](https://robertvejvoda.github.io/fairspot/#/security/data-privacy), [Backup And Restore](https://robertvejvoda.github.io/fairspot/#/production/backup-restore) | Show create/use/project/retain/erase/rebuild paths for employee, booking, tenant, audit, and DataHub projection data. |
| Application data model | Application data model | [Data Architecture](/architecture/information-systems/data-architecture), [Service Catalog](/architecture/information-systems/service-catalog) | Placeholder | [Data Architecture](/architecture/information-systems/data-architecture), service implementation models | Add when service-owned stores and DataHub projections need reviewable entity-level shape. |
| Application data dictionary | Application data dictionary | [Data Architecture](/architecture/information-systems/data-architecture), [API Contracts](/architecture/information-systems/api-contracts) | Placeholder | Generated API contracts, [Data Architecture](/architecture/information-systems/data-architecture) | Add when important data entities, classifications, owners, and API fields need a shared glossary beyond text. |
| Application data flows catalog | Application data flow | [Integrations and Events](/architecture/information-systems/integrations-events), [API Contracts](/architecture/information-systems/api-contracts), [Privacy Architecture](/architecture/security/privacy-architecture) | Placeholder | [Booking Event Contracts](https://robertvejvoda.github.io/fairspot/#/business-layer/booking-event-contracts), [DataHub](https://robertvejvoda.github.io/fairspot/#/application-layer/datahub) | Catalog API/event/read-model flows, source owners, consumers, privacy shape, and retention expectations. |
| Applications mapped over business process | Applications over business process | [Application Architecture](/architecture/information-systems/application-architecture), [Business Processes](/architecture/business/business-processes) | Placeholder | [Application Architecture 1 image](/images/fps-application-arch-1.png), business process pages | Show which apps/services support each request, Draw, cancellation, notification, HR operation, and tenant readiness step. |
| End-to-end application exchange diagram | End-to-end application exchange | [Integrations and Events](/architecture/information-systems/integrations-events) | Placeholder | [Application Architecture 1 image](/images/fps-application-arch-1.png), [Booking Event Contracts](https://robertvejvoda.github.io/fairspot/#/business-layer/booking-event-contracts) | Show full exchange path from mobile/web/API through services, Dapr, events, DataHub, notifications, and audit. |
| Application exchange diagram | Application exchange | [Integrations and Events](/architecture/information-systems/integrations-events), [API Contracts](/architecture/information-systems/api-contracts) | Placeholder | [Application Architecture image](/images/fps-application-architecture.png), generated contracts | Show application-to-application APIs/events and external boundaries. |
| Applications mapped over functional architecture | Applications over functional architecture | [Application Architecture](/architecture/information-systems/application-architecture), [Capabilities](/architecture/business/capabilities) | Placeholder | [Function Map image](/images/fps-function-map.png), [Application Architecture](/architecture/information-systems/application-architecture) | Show how FairSpot functions are realized by mobile/web apps, services, DataHub, and deferred Reporting/Billing boundaries. |
| Application use-case diagram | Application use-case | [Application Architecture](/architecture/information-systems/application-architecture), [Actors and Roles](/architecture/business/actors-roles) | Placeholder | Role intent and UX docs | Add if role-to-application capability access needs visual validation. |
| Application logical architecture diagram | Application logical architecture | [Application Architecture](/architecture/information-systems/application-architecture), [Service Catalog](/architecture/information-systems/service-catalog) | Partial | [Application Architecture 1 image](/images/fps-application-arch-1.png), [Software Architecture](https://robertvejvoda.github.io/fairspot/#/technology-layer/software-architecture) | Refresh as authoritative target view with Booking, Configuration, Customer, Notification, Audit, DataHub, frontend apps, Dapr, and deferred/obsolete Reporting boundary. |
| Physical application architecture diagram | Physical application architecture | [Runtime Platform](/architecture/technology/runtime-platform), [Deployment Profiles](/architecture/technology/deployment-profiles) | Placeholder | [Logical Architecture image](/images/fps-logical-architecture.png), deployment docs | Show deployable containers/processes, stores, sidecars, gateways, and environment-specific runtime mapping. |
| Application cooperation view | Application cooperation | [Application Architecture](/architecture/information-systems/application-architecture) | Partial | [Application Architecture 1 image](/images/fps-application-arch-1.png), [Application Architecture image](/images/fps-application-architecture.png), [Software Architecture](https://robertvejvoda.github.io/fairspot/#/technology-layer/software-architecture) | Robert TODO: refresh as authoritative target view with Booking, Configuration, Customer, Notification, Audit, DataHub, frontend apps, Dapr, and deferred/obsolete Reporting boundary. |
| Data ownership and read-model view | Data and read-model | [Data Architecture](/architecture/information-systems/data-architecture) | Placeholder | [Data Architecture image](/images/fps-data-architecture.png), [DataHub](https://robertvejvoda.github.io/fairspot/#/application-layer/datahub) | Robert TODO: confirm first DataHub projections; show write ownership, events, read APIs, report catalog, retention/privacy constraints, and Customer physical storage gap. |
| API and event context view | API and event context | [API Contracts](/architecture/information-systems/api-contracts), [Integrations and Events](/architecture/information-systems/integrations-events) | Placeholder | Booking API/event contract pages under `business-layer/` | Add when generated contract evidence or integration review needs a visual boundary. |
| Deployment diagram | Deployment | [Deployment Profiles](/architecture/technology/deployment-profiles), [Runtime Platform](/architecture/technology/runtime-platform) | Partial | [Logical Architecture image](/images/fps-logical-architecture.png), production runbooks | Robert TODO: create target hosted profile view for NAS, Cloudflare/WAF, containers, Dapr sidecars/components, state stores, backups, and smoke evidence. |
| Runtime deployment view | Deployment | [Deployment Profiles](/architecture/technology/deployment-profiles), [Runtime Platform](/architecture/technology/runtime-platform) | Partial | [Logical Architecture image](/images/fps-logical-architecture.png), production runbooks | Alias for the Deployment Diagram when the audience expects runtime terminology. |
| Draw workflow execution view | Workflow execution | [Runtime Platform](/architecture/technology/runtime-platform), [Business Processes](/architecture/business/business-processes) | Placeholder | [Draw Scheduling and Workflow](https://robertvejvoda.github.io/fairspot/#/production/draw-scheduling-and-workflow), [Draw BPMN](/process/draw.bpmn) | Robert TODO: show cron/manual trigger, single execution safety across replicas, Dapr Workflow actions, idempotency, progress read model, and next Draw schedule visibility. |
| Operations and observability view | Operations and observability | [Observability](/architecture/technology/observability) | Placeholder | [Monitoring](https://robertvejvoda.github.io/fairspot/#/production/monitoring), [Hosted Smoke Runbook](https://robertvejvoda.github.io/fairspot/#/production/hosted-smoke-runbook) | Add before hosted pilot hardening; include logs, metrics, traces, alerts, smoke tests, support diagnostics, and customer-service boundary. |
| Trust boundary view | Trust boundary | [Security Architecture](/architecture/security/security-architecture), [Controls](/architecture/security/controls) | Placeholder | [Security Model](https://robertvejvoda.github.io/fairspot/#/security/security-model), [Cloudflare WAF Profile](https://robertvejvoda.github.io/fairspot/#/security/cloudflare-waf-profile), [Logical Architecture image](/images/fps-logical-architecture.png) | Robert TODO: show browser/mobile, Cloudflare/WAF, API, services, Dapr mTLS, secrets, state stores, backups, and tenant data isolation. |
| Privacy and audit view | Privacy and audit | [Privacy Architecture](/architecture/security/privacy-architecture), [Controls](/architecture/security/controls) | Placeholder | [Data Privacy](https://robertvejvoda.github.io/fairspot/#/security/data-privacy), [Audit Capability](https://robertvejvoda.github.io/fairspot/#/business-layer/audit), [Audit Application](https://robertvejvoda.github.io/fairspot/#/application-layer/audit) | Robert TODO: show personal data, audit trail, notification duties, retention/erasure, role-safe DataHub reads, and support access limits. |
| Transition roadmap view | Transition roadmap | [Transition Architectures](/architecture/architecture-states/transition-architectures), [Gap Analysis](/architecture/architecture-states/gap-analysis) | Placeholder | [Roadmap](https://robertvejvoda.github.io/fairspot/#/roadmap), [Implementation Tracker](https://robertvejvoda.github.io/fairspot/#/implementation-tracker) | Robert TODO: show customer-ready work packages, named transition states, delivery gates, deferred Billing, and obsolete Reporting/PostgreSQL direction. |

## Diagram Refresh Order

| Priority | Diagram | Why It Comes Next | Blocks / Supports |
| --- | --- | --- | --- |
| 1 | Application cooperation view | It is needed to explain service boundaries after the DataHub decision and Reporting cleanup. | Implementation slicing, customer technical review. |
| 2 | Data ownership and read-model view | It makes Customer durable storage and DataHub projection gaps visible before implementation. | DataHub issues, privacy review, read API design. |
| 3 | Runtime deployment and trust boundary views | They support hosted NAS/Cloudflare/WAF security review and public-domain readiness. | Hosted pilot readiness, security review. |
| 4 | Draw workflow execution view | It explains scheduled/manual Draw, Dapr Workflow, idempotency, and UI progress. | Draw workflow implementation and HR/customer clarity. |
| 5 | Capability, value stream, and process views | They support customer-facing business review once the technical target is stable. | Customer validation, business architecture approval. |
| 6 | Privacy/audit and observability views | They explain customer-service, DPO, audit, and operational support responsibilities. | Hosted operations, support model, privacy readiness. |
| 7 | Transition roadmap view | It links gaps, work package groups, named architecture versions, and deferred scope. | Architecture roadmap and release planning. |

## Robert TODO Placeholders

- Robert TODO: provide or approve the authoritative application cooperation diagram for the customer-ready target.
- Robert TODO: update source diagrams where Billing/Payment are future scope, Customer durable storage is a gap, Reporting/PostgreSQL is obsolete, and DataHub owns read models.
- Robert TODO: decide whether the current Exchange Map and Function Map should remain target diagrams or receive status annotations.
- Robert TODO: provide/update ArchiMate diagrams after this repository migration stabilizes.

## Rules

- New authoritative diagrams should be indexed here.
- Source model files and exported images should both be discoverable.
- Diagrams should state which stakeholder concern they answer.
- Missing required diagrams stay listed as placeholders until replaced by authoritative diagrams.
- Diagrams must use the current target architecture terminology: Draw, DataHub, Customer durable storage, hosted NAS/Cloudflare profile, Dapr-first runtime, and deferred Billing.
- Provider-specific diagrams are examples unless a provider decision is recorded in [Versions and Decisions](https://robertvejvoda.github.io/fairspot/#/versions-and-decisions).
