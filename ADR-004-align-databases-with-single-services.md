# ADR-004 Align Databases with Single Services

Date: 2022-05-19

## Status

Accepted

## Context

Currently, BigChange relies heavily on self-managed MSSQL server instances for relational database workloads. These instances are under significant load, and vertical scaling options are costly. The customer data held in these shared MSSQL schemas is used across multiple applications, creating a high degree of coupling between systems and significant engineering friction. 

As we build new services and decompose the monolith, we need a strategy to address these challenges.

## Decision

- Future relational database workloads will be aligned to one service only and be logically and physically separated from other schemas
- Each service will own its data and manage it independently. Direct access to a service's database by other services is **prohibited** (data hiding)
- Services will interact with each other through APIs. These APIs may be synchronous or asynchronous and will expose only necessary data required for other services to perform their function
- When data needs to be shared between services using APIs, we will use DTOs to transfer only the necessary information to prevent over-exposure of internal / sensitive data structures

### Alternatives Considered

- Continue operating with shared database schemas
- Allowing services to access each other's data directly

## Consequences

### Positive

- Enhances loose coupling, data encapsulation, fault isolation, and resilience
- Each service can scale its database independently based on its specific needs
- Simplifies schema management and reduces the risk of cross-service data dependencies
- Teams can develop and deploy services independently, speeding up the development cycle
- Reduces load on existing MSSQL instances, where long-term headroom is an issue
- Enhanced security by limiting data exposure
- Greater flexibility in choosing technology stacks to best fit needs of each service

### Negative

- Increased number of database servers may lead to higher infrastructure costs
- Operational complexity of running many, independant database workloads
- Potential performance overhead due to increased inter-service communication