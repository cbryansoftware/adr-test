# Align Databases with Single Services

* Status: Accepted
* Date: 2022-05-19

## Context and Problem Statement

BigChange currently relies on self-managed MSSQL server instances for relational database workloads, leading to high load and costly scaling. Shared schemas create tight coupling between systems and engineering friction. How can we address these challenges as we build new services and decompose the monolith?

## Considered Options

* Align databases with single services
* Continue operating with shared database schemas
* Allow services to access each other's data directly

## Decision Outcome

Chosen option: "Align databases with single services," because it enhances loose coupling, data encapsulation, and fault isolation, while allowing independent scaling and simplifying schema management.

### Positive Consequences

* Enhances loose coupling, data encapsulation, fault isolation, and resilience.
* Each service can scale its database independently based on its specific needs.
* Simplifies schema management and reduces cross-service data dependencies.
* Teams can develop and deploy services independently, speeding up the development cycle.
* Reduces load on existing MSSQL instances, addressing long-term headroom issues.
* Enhanced security by limiting data exposure.
* Greater flexibility in choosing technology stacks to fit each service's needs.

### Negative Consequences

* Increased number of database servers may lead to higher infrastructure costs.
* Operational complexity of running many independent database workloads.
* Potential performance overhead due to increased inter-service communication.