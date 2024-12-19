# Record Architecture Decisions using ADRs

* Status: Accepted
* Date: 2022-03-03

## Context and Problem Statement

BigChange needs to record architecturally significant decisions affecting solution structure, non-functional characteristics, dependencies, interfaces, or construction techniques. We need a means to effectively document and maintain these decisions.

## Considered Options

* Use Architecture Decision Records (ADRs) 
* Use a shared Excel document for decision tracking
* Use a comprehensive ADR format with exhaustive detail

## Decision Outcome

Chosen option: "Use Architecture Decision Records (ADRs)" because it provides a standardized and widely adopted methodology that captures essential information without significant operational burden.

### Positive Consequences

* Standardized and widely adopted methodology.
* Captures essential information without significant operational burden.
* Provides clear visibility of ADRs to developers and stakeholders over time.
* Motivation behind decisions is visible for present and future reference.
* "Documentation as Code" approach offers a decision audit trail and a contribution mechanism familiar to engineers.

### Negative Consequences

* More overhead compared to simpler methods like Excel.
* Lacks exhaustive detail of some other ADR formats.
* Source control complexity for non-developers, mitigated by training and tools like GitHub Desktop.

## Links

* [Documenting Architecture Decisions](http://thinkrelevance.com/blog/2011/11/15/documenting-architecture-decisions) by Michael Nygard
* [Markdown Architectural Decision Records](https://adr.github.io/madr/)
* [Documentation as Code](https://www.gitbook.com/blog/what-is-docs-as-code)
* [GitHub Desktop](https://desktop.github.com/download/)