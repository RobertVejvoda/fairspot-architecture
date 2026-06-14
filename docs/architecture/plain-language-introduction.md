# Architecture In Plain Words

This repository is a shared place to explain and control architecture.

It is not a project plan, not a task board, and not a place to manage daily work. Use the FairSpot GitHub issues and PRs for implementation tasks. This repository answers different questions:

- What are we trying to achieve?
- What business needs must the solution satisfy?
- What options are still only ideas?
- What architecture has been accepted?
- What is still missing or risky?
- What decisions were made, and why?
- Which documents belong together in one reviewed architecture version?

## The Simple Mental Model

Think about the repository as a set of shelves.

| Shelf | Plain Meaning | Use It When |
| --- | --- | --- |
| Vision | Why we are doing this. | Someone asks why the architecture exists or what the overall direction is. |
| Business | What the business does and needs. | Requirements, priorities, or solution boundaries need a business source. |
| Requirements | What the architecture must support. | A new business, security, operational, or delivery need appears. |
| Candidate Architectures | Possible solution ideas. | You have a high-level architecture idea, but it is not validated yet. |
| Target Architecture | The selected future direction. | The option is accepted or ready for formal review as the future architecture. |
| Transition Architectures | Meaningful intermediate states. | You need to explain what exists before the final target is reached. |
| Gap Analysis | What is missing. | The current or proposed architecture does not yet satisfy a requirement or target. |
| Risk Register | What could go wrong. | A risk can affect architecture feasibility, acceptance, operation, handover, or retirement. |
| Decisions | What was decided. | The accountable owner chooses one direction over alternatives. |
| Governance Log | Active questions for governance. | A question needs board input before it can become a decision, gap, risk, waiver, or delivery work. |
| Change Set | Impact checklist for a material change. | A decision or requirement changes the solution and several artifacts may need updates. |
| Version Register | What belongs together. | You need to know which artifact versions were reviewed together as one architecture snapshot. |

## What Happens When Someone Has An Idea?

If someone has a high-level solution idea, do not put it directly into the target architecture.

Put it in [Candidate Architectures](/architecture/architecture-states/candidate-architectures)

That means:

- this is a useful idea;
- it may become target or transition architecture later;
- it is not approved yet;
- assumptions, benefits, risks, and open questions should be visible.

When the idea is accepted, it can move into [Target Architecture](/architecture/architecture-states/target-architecture) or [Transition Architectures](/architecture/architecture-states/transition-architectures).

## What Happens When A New Requirement Appears?

Start with [Requirements](/architecture/requirements).

Do not hide requirements inside application, data, technology, or security pages. Those pages explain how the requirement affects their area, but the requirement itself should be recorded once.

Then ask:

1. Does the current architecture already cover it?
2. If not, is there a gap?
3. Does it create a risk?
4. Does it require a board decision?
5. Does it require delivery work?
6. Does it change an accepted architecture version?

If the answer affects several areas, use [Architecture Change Set](/architecture/governance/architecture-change-set) as a checklist so the update is not made in one page while other pages stay inconsistent.

## What Happens When Governance Has A Question?

Use [Architecture Governance Log](/architecture/governance/architecture-governance-log) only while the question is active.

The log is not permanent history. Once the question is answered:

- a decision goes to [Decisions](/architecture/decisions);
- a gap goes to [Gap Analysis](/architecture/architecture-states/gap-analysis);
- a risk goes to [Risk Register](/architecture/architecture-states/risk-register);
- an exception goes to [Waivers](/architecture/governance/waivers);
- delivery work goes to the FairSpot GitHub issues and PRs;
- an item with no architecture impact is removed.

## How Versioning Works

Do not try to make every page the same version number.

An architecture version is a named snapshot, for example `Target State v0.5`. It says which artifact versions were reviewed together.

Individual artifacts have their own local versions. For example:

| Named Architecture Snapshot | Related Artifact Versions |
| --- | --- |
| Target State v0.5 | Requirements v0.2; Target Architecture v0.2; Application Architecture v0.2; Data Architecture v0.1; Technology Architecture v0.1; Decisions v0.3 |

This is normal. It means only some pages changed.

Use [Architecture Version Register](/architecture/architecture-states/architecture-version-register) to see what belongs together.

Use [Artifact Register](/architecture/artifact-register) to see the status and owner of each artifact.

## How Different Stakeholders Use This Repository

| If You Are | Use The Repository To | Start With | You Usually Contribute |
| --- | --- | --- | --- |
| Sponsor / Product Owner | Check direction, risk, cost, timing, and decisions needed. | Architecture Vision, Decisions, Risk Register, Version Register | Decision input, risk acceptance, priority trade-offs. |
| Business Owner | Confirm business process, operational impact, and transition acceptability. | Business Processes, Requirements, Transition Architectures | Process corrections, requirement ownership, acceptance concerns. |
| Security / Privacy Reviewer | Confirm obligations, controls, evidence, privacy, and accepted exceptions. | Requirements, Security Architecture, Privacy Architecture, Controls | Mandatory controls, evidence needs, risk/waiver input. |
| IT Operations / Platform | Confirm deployability, monitoring, restore, support, and troubleshooting. | Technology Architecture, Observability, Delivery Operating Model, Readiness | Run requirements, support gaps, handover evidence. |
| Data / Reporting Owner | Confirm data ownership, definitions, lineage, freshness, and reporting needs. | Data Architecture, Integrations and Events, API Contracts, Gap Analysis | Data rules, reporting needs, quality/freshness concerns. |
| Delivery Lead | Check feasibility, dependencies, sequencing, capacity risks, and delivery links. | Roadmap, Work Packages, Delivery Operating Model, Governance Log | Delivery feasibility, dependency risks, delivery references. |
| Architecture Board | Decide or defer architecture-significant questions and ensure outcomes are recorded. | Governance Log, Decisions, Change Set, Version Register | Decisions, acceptance, risk/waiver direction. |
| External Supplier / Assessor | Understand context, compare options, record assumptions, and provide evidence. | Candidate Architectures, Architecture Review, Gap Analysis, Risk Register | Assessment findings, option recommendations, risks, evidence. |

## The Most Important Rule

Use one source of truth for each thing:

- requirements in Requirements;
- decisions in Decisions;
- risks in Risk Register;
- gaps in Gap Analysis;
- active governance questions in Governance Log;
- candidate ideas in Candidate Architectures;
- accepted snapshots in Architecture Version Register;
- delivery tasks in the FairSpot GitHub issues and PRs.

If something changes the solution, update only the affected artifacts and use a change set to check consistency. Do not duplicate the same information everywhere.
