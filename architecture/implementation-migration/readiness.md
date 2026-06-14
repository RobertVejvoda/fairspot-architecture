# Readiness

Readiness records the evidence required before FairSpot can be treated as customer-ready for hosted pilot or later production handoff.

## Readiness Checklist

| Area | Evidence Required | Status | Notes |
| --- | --- | --- | --- |
| Security | Authenticated tenant/user context, tenant isolation tests, WAF/ingress controls, secrets handling, privacy controls, and audit evidence. | Partial | Source: [Security Architecture](/architecture/security/), [Security Gap Register](/architecture/security/gap-register), [NAS Cloudflare Deployment](https://robertvejvoda.github.io/fairspot/#/production/nas-cloudflare-deployment-profile). |
| Operational | Health endpoints, logs, metrics, traces, backup/restore, smoke runbooks, maintenance expectations, and support boundaries. | Partial | Source: [Hosted Smoke Runbook](https://robertvejvoda.github.io/fairspot/#/production/hosted-smoke-runbook), [Backup And Restore](https://robertvejvoda.github.io/fairspot/#/production/backup-restore), [Monitoring](https://robertvejvoda.github.io/fairspot/#/production/monitoring). |
| Data | Service-owned durable stores, tenant-scoped keys, projection rebuild strategy, event inbox, and recovery evidence. | Partial | Customer persistence evidence exists; DataHub projections and several service stores remain gaps. |
| Hosted Profile | NAS/Cloudflare/WAF public profile, private service exposure, auth callback, reset/reseed, no internal exposure, and log review. | Open | Owner: [WP-002 Customer-Ready Hosted Pilot](/architecture/implementation-migration/work-packages?id=work-package-register). Must be validated before real customer data. |
| Mobile | Expo build, environment configuration, real device testing, auth/session behavior, and pilot distribution path. | Open | Owner: [WP-003 Role-Centered UX](/architecture/implementation-migration/work-packages?id=work-package-register). Source: [Mobile Device Testing](https://robertvejvoda.github.io/fairspot/#/production/mobile-device-testing). |

## Readiness Outcomes

| Outcome | Meaning |
| --- | --- |
| Ready | Evidence is linked and residual risks are accepted. |
| Ready With Gaps | Pilot may proceed only with explicit risk ownership and review date. |
| Not Ready | Required evidence is missing or a critical risk remains unaccepted. |

## Related Views

| View | Use When | Example |
| --- | --- | --- |
| Readiness And Resilience View | A reader needs to see the readiness evidence path for health, alerting, restore, audit, support, and residual risk. | [Operational Readiness And Resilience View](#example-operational-readiness-and-resilience-view) |
| Roadmap View | A reader needs to see when readiness gates are expected. | [Roadmap Gantt Chart](/architecture/implementation-migration/roadmap?id=example-roadmap-gantt-chart) |

## Example Operational Readiness And Resilience View

```plantuml
@startuml
!include <archimate/Archimate>
LAYOUT_TOP_DOWN()

Application_Component(fairspot, "FairSpot Runtime")
Technology_Service(health, "Health Checks")
Technology_Service(alerting, "Alerting")
Technology_Service(observability, "Logs / Metrics / Traces")
Technology_Service(backupRestore, "Backup / Restore")
Business_Process(incident, "Incident Response")
Business_Actor(operator, "Operator")
Application_DataObject(audit, "Audit Evidence")
Implementation_Deliverable(evidence, "Readiness Evidence")
Motivation_Requirement(state, "AR-002\nRestart-Safe State")
Motivation_Assessment(risk, "Accepted Residual Risk")

Rel_Serving(health, fairspot, "checks")
Rel_Serving(observability, fairspot, "observes")
Rel_Triggering(alerting, incident, "alerts")
Rel_Assignment(operator, incident, "owns")
Rel_Serving(backupRestore, fairspot, "recovers")
Rel_Access_w(fairspot, audit, "creates")
Rel_Realization(evidence, state, "proves")
Rel_Association(incident, evidence, "updates")
Rel_Association(risk, evidence, "if incomplete")

' Layering hint: business operation above application/evidence above technology.
operator -[hidden]down- fairspot
incident -[hidden]down- evidence
fairspot -[hidden]down- health
audit -[hidden]down- backupRestore
@enduml
```
