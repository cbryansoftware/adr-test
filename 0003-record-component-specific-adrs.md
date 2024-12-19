# Capture Component Specific Decisions as ADRs Alongside the Code

* Status: Accepted
* Date: 2024-02-26

## Context and Problem Statement

While we have a mechanism for capturing cross-cutting architectural decisions, we lack a well-understood process for documenting component-specific decisions. These decisions often get lost or are inconsistently documented, leading to a lack of clarity and historical context.

## Considered Options

* Use ADRs to capture component-level decisions alongside the code
* Continue using wikis for component-specific decisions
* Centralize all ADRs, including component-specific ones, in a single repository

## Decision Outcome

Chosen option: "Use ADRs to capture component-level decisions alongside the code," because it improves discoverability and ensures decisions are documented where they are most relevant.

### Positive Consequences

* ADRs are easy to find, enhancing understanding of decisions that shaped the solution.
* Source control provides an audit trail of decisions over time.
* Reduces context switching for engineers by allowing ADRs to be viewed and written in their IDE.
* Facilitates collaboration with the architecture team and preserves context for interactions.
* Vital context is more accessible for new initiatives.

### Negative Consequences

* Centralized view of all ADRs becomes more challenging, though tooling can mitigate this.
* Source controlling ADRs is more laborious than using a wiki and less accessible for non-technical staff.
* Adds some noise to codebases, but the information is important and worth capturing.

## Links

* [ADR-001 Record Architecture Decisions using ADRs](./adr-001-record-architecture-decisions.md)
* [ADR-002 Capture Cross-Cutting Architecture Decisions](adr-002-cross-cutting-adrs.md)