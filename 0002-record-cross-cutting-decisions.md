# ADR-002 Capture Cross-Cutting Architecture Decisions

Date: 2022-03-10

## Status

Accepted

## Context

In our architecture, certain decisions impact multiple components, layers, or services. These cross-cutting concerns include aspects like security, logging, error handling, and performance optimization. Documenting these decisions separately from component-specific ADRs ensures that they are consistently applied across the entire system and easily accessible to all relevant stakeholders.

This decision builds on the board adoption of ADRs, described in [ADR-001 Record Architecture Decisions using ADRs](../arch/adr-001-record-architecture-decisions.md)

## Decision

- We will create dedicated ADRs for cross-cutting concerns that affect multiple parts of the system.
- Each cross-cutting ADR will be stored in an individual markdown document in a dedicated repository.
- Cross-cutting ADRs will follow the same lightweight architecture decision record format to maintain consistency.

## Consequences

### Positive

- Ensures consistency in how cross-cutting concerns are addressed across different parts of the system.
- Provides a centralized reference for developers and stakeholders to understand how these concerns are managed.
- Facilitates easier onboarding of new team members by providing clear documentation on system-wide practices.
- Enhances communication and collaboration by making cross-cutting decisions visible to all relevant parties.

### Negative

- May introduce additional overhead in maintaining a separate set of ADRs for cross-cutting concerns.
- Requires diligence to ensure that cross-cutting ADRs are kept up-to-date as the system evolves.
- Potential for overlap or redundancy with component-specific ADRs if not carefully managed.
