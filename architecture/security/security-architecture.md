# Security Architecture

FairSpot security centers on authenticated context, tenant isolation, least privilege, Dapr runtime hardening, privacy by default, and traceable business evidence.

| Security Area | Target Direction | Status | Source Evidence |
| --- | --- | --- | --- |
| Authentication | OIDC/SSO-first customer identity; local accounts are fallback/local only. | Partial | [Authentication](https://robertvejvoda.github.io/fairspot/#/security/authentication), [Identity](https://robertvejvoda.github.io/fairspot/#/business-layer/identity) |
| Authorization | Role-centered access for employee, HR/facility, tenant admin, system admin, auditor, support/operator, and system actors. | Partial | [Authorization](https://robertvejvoda.github.io/fairspot/#/security/authorization), [Roles](https://robertvejvoda.github.io/fairspot/#/business-layer/roles), [Actors and Roles](/architecture/business/actors-roles) |
| Tenant isolation | Tenant context derives from authenticated claims or trusted service context and controls API, storage, event, read-model, audit, and backup boundaries. | Partial | [Security Model](https://robertvejvoda.github.io/fairspot/#/security/security-model), [Tenant Storage Contract](https://robertvejvoda.github.io/fairspot/#/production/tenant-storage-contract) |
| Service-to-service security | Dapr service invocation with mTLS/Sentry where supported; user context forwarded only where downstream authorization requires it. | Placeholder | [Dapr-First Standards](https://robertvejvoda.github.io/fairspot/#/production/dapr-first-production-standards) |
| Dapr component hardening | Component scopes, secret scopes, API token/app token hardening, resiliency policies, and state encryption where supported. | Placeholder | [Dapr-First Standards](https://robertvejvoda.github.io/fairspot/#/production/dapr-first-production-standards) |
| Secrets | Runtime secrets come from profile-specific secret stores and are never committed, printed, exported casually, or embedded in component files. | Partial | [Environments](https://robertvejvoda.github.io/fairspot/#/security/environments), [Security Model](https://robertvejvoda.github.io/fairspot/#/security/security-model) |
| Public ingress | Hosted profiles use Cloudflare/WAF/rate limits/Access and block admin, internal, metrics, Dapr, Swagger/OpenAPI, database, broker, and observability surfaces. | Partial | [Cloudflare WAF Profile](https://robertvejvoda.github.io/fairspot/#/security/cloudflare-waf-profile), [Deployment Profiles](/architecture/technology/deployment-profiles) |
| Audit evidence | Business evidence is append-only where possible and pseudonymised where required. Audit is separate from technical telemetry. | Partial | [Audit](https://robertvejvoda.github.io/fairspot/#/security/audit), [Security Model](https://robertvejvoda.github.io/fairspot/#/security/security-model) |
| Observability safety | Logs, metrics, and traces support operations without secrets, raw personal data, full payloads, or business-audit replacement. | Partial | [Observability](/architecture/technology/observability), [Local Observability](https://robertvejvoda.github.io/fairspot/#/local-observability) |
| DataHub/read-model privacy | Projections preserve tenant scope, minimal data, role-safe views, and approved exports only. | Placeholder | [Data Architecture](/architecture/information-systems/data-architecture), [Data Privacy](https://robertvejvoda.github.io/fairspot/#/security/data-privacy) |
| Resource-map and policy preview safety | Facilities/admin previews and publication flows remain tenant-scoped, audited, advisory where previewed, and separate from allocation decisions. | Placeholder | [Information Systems](/architecture/information-systems/), [Business Policies](/architecture/business/policies) |
| Backup and restore security | Restore actions preserve tenant boundaries, secret handling, audit evidence, PII mapping rules, and restore-time re-erasure obligations. | Placeholder | [Backup And Restore](https://robertvejvoda.github.io/fairspot/#/production/backup-restore), [RTO/RPO Requirements](https://robertvejvoda.github.io/fairspot/#/production/rto-rpo-requirements) |

## Trust Boundary Rules

- End users access FairSpot through HTTPS and OIDC Authorization Code + PKCE where applicable.
- Public ingress terminates at the selected gateway/tunnel profile; internal services and Dapr sidecars remain private.
- Backend services validate JWTs/claims and must not trust request bodies, query strings, or caller-supplied headers for tenant/user identity.
- Service-owned stores use tenant-safe keys, collections, partitions, or schemas derived centrally from trusted context.
- Dapr secures runtime transport and component access, but does not replace application authorization or privacy filtering.
- Domain events omit secrets, stack traces, hidden lottery internals, raw names/emails/license plates, and unrelated employee data.
- Audit PII mapping is a restricted path with reason capture and its own audit trail.
- Backup and restore operations are privileged security events when they can expose Confidential or Secret data.
- Sponsor, HR, and facilities views can use DataHub projections only after the projection shape is role-safe and tenant-scoped.

## Required Trust Boundary Diagram

Placeholder: a security trust-boundary view should show browser/mobile clients, Cloudflare/Tunnel/WAF, API gateway, Keycloak/OIDC, services, Dapr sidecars, state stores, pub/sub broker, DataHub PostgreSQL, Audit PII mapping, observability backends, secret stores, backup/restore path, and operator-only access path.

## Related Views

| View | Use When | Example |
| --- | --- | --- |
| Security And Privacy View | A reader needs to see trust boundaries, personal-data boundaries, controls, and material risks. | [Security And Privacy Diagram](#example-security-and-privacy-diagram) |
| Deployment View | A reader needs to see runtime, ingress, network, and platform boundaries that affect security. | [Deployment Diagram](/architecture/technology/deployment-profiles?id=example-deployment-diagram) |

## Example Security And Privacy Diagram

```plantuml
@startuml
!include <archimate/Archimate>
LAYOUT_TOP_DOWN()

Technology_Device(user, "User Device")
Technology_Service(edge, "TLS + WAF + Auth")
Application_Component(api, "FairSpot API")
Motivation_Requirement(authz, "Role / Scope Authorization")
Application_DataObject(scopeData, "Booking / User Scope Data")
Application_DataObject(audit, "Audit Events")
Motivation_Constraint(retention, "Retention Policy")
Motivation_Assessment(risk, "Missing Projection Isolation Evidence")

Rel_Flow(user, edge, "flow")
Rel_Serving(edge, api, "serves")
Rel_Association(authz, api, "constrains")
Rel_Access_rw(api, scopeData, "accesses")
Rel_Access_w(api, audit, "creates")
Rel_Association(retention, scopeData, "constrains")
Rel_Association(risk, scopeData, "risk")

' Layering hint: requirements above application/data above technology.
authz -[hidden]down- api
retention -[hidden]down- scopeData
risk -[hidden]down- audit
api -[hidden]down- edge
scopeData -[hidden]down- user
@enduml
```
