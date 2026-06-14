# Architecture Increment Checklist

<!--
Purpose:
Define how architecture-significant increments are identified, shaped, reviewed, and accepted for migration governance.

Use this page for:
- choosing candidate increments or vertical slices
- defining boundaries
- checking whether an increment is complete enough to deliver and operate
- preparing evidence before production or pilot traffic

Avoid:
- treating an increment as only a UI, API, database, or infrastructure task
- duplicating detailed delivery backlog items
- using legacy module, screen, or table boundaries as the default slicing model
-->

This checklist helps make each architecture increment a complete business or technical outcome that can be operated, controlled, and evidenced.

An increment is ready to enter delivery only when its outcome, ownership boundary, data responsibilities, integrations, controls, and acceptance evidence are explicit enough for Architecture Review. It is ready for production or pilot use only when evidence proves that it can be operated without hidden dependencies outside the approved design.

## What An Increment Is

An architecture increment is a coherent change that owns an outcome. It may be a vertical slice, platform foundation, integration capability, data/read-model capability, security capability, or migration step.

An increment is not:

- a technical layer by itself without an outcome;
- a wrapper around old behavior without ownership clarity;
- a copied legacy module boundary unless it also matches a stable outcome;
- a report or replicated data feed without ownership, freshness, and evidence rules;
- a workaround that bypasses controls, write ownership, or reconciliation.

## Boundary Rules

| Rule | Question | Expected Result | Status | Evidence / Notes |
| --- | --- | --- | --- | --- |
| Outcome | What customer, operational, financial, or regulatory outcome changes when this increment succeeds? | The increment has a named outcome and accountable owner. | Open | - |
| Trigger | What request, event, schedule, or user action starts the increment? | Entry points are explicit. | Open | - |
| Completion | What state proves the increment is complete? | Completion state and evidence are defined. | Open | - |
| Ownership | Which system or team owns the authoritative state and behavior? | Ownership is explicit for the relevant state. | Open | - |
| Data responsibility | Which data is owned, referenced, replicated, published, or synchronized? | Command data, read data, events, and integrations are separated. | Open | - |
| Controls | Which approvals, audit, security, privacy, and segregation controls apply? | Controls are built into the increment scope. | Open | - |
| Integration | Which upstream, downstream, and external interfaces are required? | Interfaces have contracts and failure handling. | Open | - |
| Operations | How is the increment monitored, supported, restored, and reconciled? | Operational evidence is part of acceptance. | Open | - |

## Status Model

| Status | Meaning |
| --- | --- |
| Open | The item is known but not yet answered or evidenced. |
| In Progress | Work is underway, but the item is not ready for acceptance. |
| Blocked | The item cannot progress without a decision, dependency, or risk acceptance. |
| Waived | The item is not satisfied, but a time-boxed waiver has been accepted. |
| Closed | The item is answered and linked evidence is accepted. |
| Not Applicable | The item does not apply, with rationale recorded. |

## Candidate Increment Record

| Field | Description | Status | Evidence / Notes |
| --- | --- | --- | --- |
| Increment name | Short outcome name, not only a technology name. | Open | - |
| Source requirement/process | Link to the source requirement, process, gap, or candidate architecture. | Open | - |
| Outcome | Outcome the increment owns from trigger to completion. | Open | - |
| Owner | Accountable owner for accepting the outcome. | Open | - |
| Current owner | Existing system, team, manual process, or mixed owner today. | Open | - |
| Target owner | Target system or team for the relevant transition state. | Open | - |
| Included scope | Process steps, APIs/UI, commands, events, data, controls, integrations, and operations included. | Open | - |
| Excluded scope | Related functions explicitly left elsewhere. | Open | - |
| Dependencies | Read dependencies, write dependencies, integrations, external services, or readiness prerequisites. | Open | - |
| Control evidence | Security, privacy, compliance, audit, and approval evidence. | Open | - |
| Operational evidence | Monitoring, alerting, runbook, support ownership, restore/replay/retry evidence. | Open | - |
| Acceptance scenarios | Scenarios proving the increment is ready for use. | Open | - |
| Open decisions | ADRs, waivers, risks, or unresolved boundary questions. | Open | - |

## Acceptance Gate

Before an increment can be accepted for production or pilot use, Architecture Review should confirm:

- outcome and ownership are unambiguous;
- required interfaces and contracts are accepted or covered by approved waivers;
- control evidence is available for the increment scope;
- operational evidence is available for monitoring, support, failure handling, and recovery;
- scenario tests prove the outcome from trigger to completion;
- residual gaps, risks, and waivers are recorded.
