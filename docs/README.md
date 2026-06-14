# FairSpot Architecture Repository

This site is the standalone TOGAF 10-inspired architecture repository for FairSpot.

Use it to structure architecture content around stakeholder concerns, ADM phases, layered architecture views, decisions, governance, and implementation migration planning.

## Applied Template Version

This page tracks the architecture-repository-template structure that has been applied to FairSpot. FairSpot-specific baseline, target, and transition architecture versions are tracked in [Architecture Version Register](/architecture/architecture-states/architecture-version-register). FairSpot repository-structure changes are tracked in [Repository Changes](/architecture/repository-changes).

| Version | Date | Status | Summary | Migration Notes |
| --- | --- | --- | --- | --- |
| 2.5 | 2026-06-14 | Draft | Added solution context, requirement traceability, domain lifecycle, and operational readiness/resilience example views. | Use these views to connect scope, requirements, lifecycle states, and readiness evidence without duplicating backlog items or implementation logs. |
| 2.4 | 2026-06-14 | Draft | Added value stream, baseline, candidate, and target architecture example sketches with page-level purpose guidance. | Keep architecture sketches at state, outcome, and tradeoff level; split implementation detail into GitHub issues only after it is traceable to architecture requirements, gaps, decisions, or work packages. |
| 2.3 | 2026-06-14 | Draft | Simplified governance and migration structure by removing delivery sourcing and delivery operating model artifacts. | Keep supplier, staffing, and operating-model choices outside the architecture template unless they create architecture-significant constraints, risks, or decisions. |
| 2.2 | 2026-06-14 | Draft | Added implementation and migration diagram examples, including roadmap Gantt, work package dependency, transition state, and gap closure views. | Keep examples on the architecture pages that own the concern, and use the diagram register for lifecycle, source, export, and supported-version tracking. |
| 2.1 | 2026-06-14 | Draft | Added PlantUML ArchiMate-rendered FairSpot example implementations and related-view links from architecture pages. | Use examples as starters, replace sample terms with project terms, and track editable source plus exported image paths in the diagram register. |
| 2.0 | 2026-06-14 | Draft | Added the reusable governance model from the evolved architecture repository pattern. | Add plain-language onboarding, candidate architectures, governance log, architecture change sets, and increment checklist where useful. |
| 1.1 | 2026-06-03 | Draft | Simplified the default viewpoint catalog around stakeholder-question navigation and reduced starter diagram placeholders. | Treat the catalog as a lightweight navigation aid; add optional viewpoints only when a real stakeholder concern needs them. |
| 1.0 | 2026-06-03 | Draft | Added viewpoint taxonomy, diagram placeholders, and abstract view/diagram versioning rules. | Use the central Views and Diagrams section to govern diagram lifecycle, while architecture sections link their related views without duplicating the diagram register. |
| 0.9 | 2026-06-01 | Draft | Limited metadata tables to top-level Architecture Repository pages and the artifact register. | Track detailed child artifacts from the Artifact Register instead of repeating metadata on every page. |
| 0.8 | 2026-06-01 | Draft | Added standards catalog, glossary, constraints, risk register, and architecture contract. | Use these artifacts to make approved choices, shared language, solution limits, non-security risks, and delivery conformance explicit. |
| 0.7 | 2026-06-01 | Draft | Linked ADM checklist review gates to Architecture Review and Architecture Board governance. | Use the ADM checklist as the working readiness tool, Architecture Review as the review process, and Architecture Board as the decision owner. |
| 0.6 | 2026-05-31 | Draft | Replaced thin placeholder rows with representative sample rows across architecture artifacts. | FairSpot architecture maintainers should replace sample rows with project-specific content while preserving the traceability pattern. |
| 0.5 | 2026-05-31 | Draft | Added artifact metadata to major architecture artifacts, an Architecture Board page, and requirement-to-gap/work-package examples. | Keep decisions in the decision log, define board governance separately, and trace requirements to phase impacts, gaps, and work packages. |
| 0.4 | 2026-05-31 | Draft | Added cross-phase Requirements Management guidance with a generic example. | Requirements should be centrally tracked, then interpreted by each affected ADM phase with evidence and gaps. |
| 0.3 | 2026-05-31 | Draft | Changed artifact metadata examples to compact metadata tables without visible headers. | Prefer two-column metadata tables with bold field names and normal values. |
| 0.2 | 2026-05-31 | Draft | Added architecture states, artifact register, and TOGAF deliverable coverage mapping. | Map formal deliverables to existing pages before creating standalone deliverable documents. |
| 0.1 | 2026-05-31 | Draft | Initial TOGAF-style architecture repository skeleton. | First usable baseline. |

## Reader Paths

| Reader | Start here | Purpose |
| --- | --- | --- |
| New reader | [Architecture In Plain Words](/architecture/plain-language-introduction) | Understand the concepts and how to work with the repository. |
| Sponsor or product owner | [Architecture Vision](/architecture/architecture-vision) | Understand the target outcome and business context. |
| Architect | [Architecture Repository](/architecture/) and [ADM Map](/architecture/togaf-adm-map) | Navigate architecture artifacts and ADM coverage. |
| Business stakeholder | [Business Architecture](/architecture/business/) | Understand capabilities, value streams, actors, processes, and policies. |
| Technical stakeholder | [Information Systems](/architecture/information-systems/) and [Technology](/architecture/technology/) | Understand applications, data, integrations, runtime, and deployment. |
| Security reviewer | [Security Architecture](/architecture/security/) | Understand security, privacy, controls, and known gaps. |
| Delivery lead | [Implementation And Migration](/architecture/implementation-migration/) | Understand roadmap, work packages, increment checklist, and readiness. |
| Architecture governor | [Architecture States](/architecture/architecture-states/), [Governance Log](/architecture/governance/architecture-governance-log), and [Artifact Register](/architecture/artifact-register) | Understand active governance questions, baseline/target versions, artifact status, and gaps. |
| Implementation team | [Technology Standards](/architecture/technology/standards) and [Architecture Contract](/architecture/governance/architecture-contract) | Understand approved choices and conformance expectations. |

## How To Use This FairSpot Architecture Repository

- Keep each page focused on one architecture concern.
- Prefer links over duplication.
- Record durable decisions explicitly.
- Keep diagrams indexed from one place.
- Separate target architecture from implementation evidence.
- Use candidate architecture records before promoting unvalidated options to target or transition architecture.
- Use architecture change sets when a material change affects several artifacts.
- FairSpot/Parking diagram content is project content here, not sample-domain material.
- Keep template guidance only where it helps FairSpot architecture governance; replace generic guidance with FairSpot-specific rules over time.
