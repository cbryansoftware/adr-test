# ADR-003 Capture Component Specific Decisions as ADRs Alongside the Code

Date: 2024-02-26

## Status

Accepted

## Context

We use ADRs as a well-understood mechanism to capture [architecturally significant decisions](./adr-001-record-architecture-decisions.md). Cross-cutting ADRs that apply to all solutions - such as this one - are [held centrally](adr-002-cross-cutting-adrs.md) in source control.

This ADR attempts to define a practice for **documenting architectural decisions that are more granular in their scope** applying to a single component, such as the noteworthy decisions that are made that apply to a single solution, project or service.

Today, we don't have a well-understood mechanism for documenting this kind of decision. Decisions aligned to a particular component happen frequently but they do not comfortably sit alongside top-level ADRs. Some solutions do have ADRs buried in the wiki, but that is seldom used and easily forgotten, and typically the context for these kinds of decisions is simply lost.

## Decision

- We should use ADRs to capture local, component-level decisions in the [established way](./adr-001-record-architecture-decisions.md).
- Component-level ADRs should sit alongside that project's code in source control in an `/adrs` folder at the root repository level for ease of discoverability.
- For the monolithic BigChange repository, more specific ADRs should exist alongside the product/service they support in `/adrs` at the project subfolder level (and should be additive).
- Component-specific ADRs should use a prefix unique to the project, for example 'CRM-004'.

## Consequences

### Positive

- ADRs become easy to find, making it easy for contributors to understand the decisions that have shaped the solution in front of them. No more 'out of sight, out of mind'.
- Source control means an audit trail of decisions made over time. They cannot just be changed ad-hoc as per the wiki.
- Reduces context switching for engineers if they can view/write ADRs in their IDE.
- Easier collaboration with the architecture team. A solution-centric log can support and document interactions between those teams, where often that context is lost today.
- Vital context can more easily be learned as we spin up new initiatives (e.g., my new project is similar to X, why did they decide to do Y?).

### Negative

- A centralised view of every ADR made in the business becomes more difficult, though this can be minimised with better tooling for documentation.
- Source controlling ADRs is a little more laborious than just keying something into the wiki and more difficult for non-technical staff.
- Adds some noise to codebases, though this is minor and hosts important information worth capturing.