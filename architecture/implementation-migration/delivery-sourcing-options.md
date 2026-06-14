# Delivery Sourcing Options

<!--
Purpose:
Compare candidate delivery sourcing options before selecting an implementation operating model.

Use this page for:
- internal, external, and mixed delivery option comparison
- sourcing assumptions and trade-offs
- architecture-significant sourcing risks
- input to delivery operating model decisions

Avoid:
- replacing procurement evaluation
- recording supplier commercial details that belong elsewhere
- treating an option as selected before a decision is recorded
-->

Delivery sourcing options are candidate ways to deliver the target architecture. Keep this page option-focused until the accountable owner records a decision.

## Option Register

| Option ID | Option | Description | Benefits | Risks / Costs | Status | Decision Route |
| --- | --- | --- | --- | --- | --- | --- |
| DS-001 | Internal delivery | Existing internal team delivers and operates the scope. | Strong ownership and continuity. | Capacity, specialization, and schedule risk. | Candidate | Decision required before delivery operating model is finalized. |
| DS-002 | External fixed-scope delivery | External supplier delivers a defined scope for acceptance. | Predictable commercial boundary and capacity. | Handover, maintainability, hidden dependency, and change-control risk. | Candidate | Decision, architecture contract, and handover model required. |
| DS-003 | Internal-led mixed team | Internal team owns product and architecture, external specialists add capacity. | Balances ownership and capacity. | Requires active knowledge transfer and clear decision rights. | Candidate | Decision and delivery operating model required. |

## Comparison Criteria

| Criterion | Question |
| --- | --- |
| Ownership | Who owns architecture decisions, long-term maintainability, and operation? |
| Capacity | Does the option provide enough delivery capacity for the target date? |
| Expertise | Does the option provide specialist knowledge where needed? |
| Handover | Can accountable staff operate and evolve the delivered scope? |
| Security and access | How are external access, privileged operations, and audit controlled? |
| Cost and flexibility | How does the option handle scope change, unknowns, and support needs? |
| Evidence | What proof is required before production acceptance? |

When a sourcing option is selected, record the durable choice in [Architecture Decisions](/architecture/decisions) and update [Delivery Operating Model](/architecture/governance/delivery-operating-model).
