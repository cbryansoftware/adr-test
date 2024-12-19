# Capture Cross-Cutting Architecture Decisions

* Status: Accepted
* Date: 2022-03-10

## Context and Problem Statement

Certain architecture decisions impact multiple components, layers, or services, such as security, logging, error handling, and performance optimization. How can we ensure these cross-cutting concerns are consistently documented and accessible?

## Considered Options

* Create dedicated ADRs for cross-cutting concerns
* Integrate cross-cutting concerns into component-specific ADRs
* Use a centralized document for all cross-cutting concerns

## Decision Outcome

Chosen option: "Create dedicated ADRs for cross-cutting concerns," because it ensures consistency and provides a centralized reference for system-wide practices.

### Positive Consequences

* Ensures consistency in addressing cross-cutting concerns across the system.
* Provides a centralized reference for developers and stakeholders.
* Facilitates easier onboarding with clear documentation on system-wide practices.
* Enhances communication and collaboration by making decisions visible to all relevant parties.

### Negative Consequences

* Introduces additional overhead in maintaining separate ADRs.
* Requires diligence to keep cross-cutting ADRs up-to-date.
* Potential for overlap or redundancy with component-specific ADRs if not managed carefully.

## Links

* [ADR-001 Record Architecture Decisions using ADRs](../arch/adr-001-record-architecture-decisions.md)