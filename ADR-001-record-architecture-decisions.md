# ADR-001 Record Architecture Decisions using ADRs

Date: 2022-03-03

## Status

Accepted

## Context

We need to record decisions BigChange that are "architecturally significant": those that affect the solution structure, non-functional characteristics, dependencies, interfaces, or construction techniques. We need to provide a means to maintain and contribute to these decisions, as well as the context on when and why a decision was made.

## Decision

- We will use Architecture Decision Records, as described by Michael Nygard in 
[documenting architecture decisions](http://thinkrelevance.com/blog/2011/11/15/documenting-architecture-decisions).
- Each decision should be stored in an invidual markdown document held in source control
- Markdown documents should be numerically sequenced and follow naming convention: `ADR-001-brief-outcome-of-adr.md`
- We will adopt the [lightweight architecture decision record](https://github.com/peter-evans/lightweight-architecture-decision-records) format

## Consequences

See Michael Nygard's article, linked above.

### Positive

- Decisions are documented using a standard & widely adopted methodology
- Lightweight decisions capture just enough information about a decision without adding significant operational burden
- Developers and stakeholders have clear sight of ADRs, even as team composition changes over time
- The motivation behind previous decisions is visible for everyone, present and future
- [Documentation as code](https://www.gitbook.com/blog/what-is-docs-as-code) approach provides a decision audit trail and a mechanism for contribution that engineers inherantly understand

### Negative

- Documentation as code means more overhead when creating or amending decisions and more lightweight approaches exist (eg. a shared excel document). Can be somewhat mitigated by providing a template for authoring new ADRs
- Lightweight architecture decision records lack the exhaustive detail of some other ADR formats
- Source control makes it more difficult for non-developers to contribute to decisions. Can be mitigated via training and tools to simplify git, such as [Github Desktop](https://desktop.github.com/download/)