# Record Architecture Decisions using ADRs

* Status: Accepted
* Date: 2022-03-03

## Context and Problem Statement

We need to record decisions at BigChange that are "architecturally significant": those that affect the solution structure, non-functional characteristics, dependencies, interfaces, or construction techniques. How can we ensure these decisions are documented and accessible for future reference?

## Decision Drivers

* Need for a standardized documentation method
* Desire for lightweight and efficient documentation
* Requirement for accessibility to developers and stakeholders
* Need for historical context on decisions

## Considered Options

* Use Architecture Decision Records (ADRs) with a lightweight format
* Use a shared Excel document for decision tracking
* Use a comprehensive ADR format with exhaustive detail

## Decision Outcome

Chosen option: "Use Architecture Decision Records (ADRs) with a lightweight format," because it provides a standardized and widely adopted methodology that captures essential information without significant operational burden.

### Positive Consequences

* Decisions are documented using a standard and widely adopted methodology.
* Lightweight decisions capture just enough information about a decision without adding significant operational burden.
* Developers and stakeholders have clear sight of ADRs, even as team composition changes over time.
* The motivation behind previous decisions is visible for everyone, present and future.
* The "Documentation as Code" approach provides a decision audit trail and a mechanism for contribution that engineers inherently understand.

### Negative Consequences

* Documentation as code means more overhead when creating or amending decisions, and more lightweight approaches exist (e.g., a shared Excel document). This can be somewhat mitigated by providing a template for authoring new ADRs.
* Lightweight architecture decision records lack the exhaustive detail of some other ADR formats.
* Source control makes it more difficult for non-developers to contribute to decisions. This can be mitigated via training and tools to simplify Git, such as GitHub Desktop.

## Links

* [Documenting Architecture Decisions](http://thinkrelevance.com/blog/2011/11/15/documenting-architecture-decisions) by Michael Nygard
* [Lightweight Architecture Decision Record](https://github.com/peter-evans/lightweight-architecture-decision-records)
* [Documentation as Code](https://www.gitbook.com/blog/what-is-docs-as-code)
