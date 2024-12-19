# Adopt PostgreSQL for New Relational Database Workloads

* Status: Accepted
* Date: 2022-05-19

## Context and Problem Statement

Following [ADR-004 Adopt Amazon RDS for New Relational DB Workloads](./ADR-004-align-databases-with-single-services.md), we need a cost-effective and flexible database engine. BigChange's reliance on MSSQL incurs licensing costs and limits flexibility. What database engine should we adopt for new services to address these issues?

## Considered Options

* PostgreSQL
* RDS MySQL
* RDS MSSQL

## Decision Outcome

Chosen option: "PostgreSQL," because it is free, open-source, and offers flexibility, eliminating licensing costs associated with MSSQL.

### Positive Consequences

* Eliminates licensing costs associated with MSSQL as PostgreSQL is free and open-source.
* Supports a wide range of data types and extensions, providing flexibility in application design.
* Strong community support and extensive documentation.
* Provides a simple upgrade path to Amazon RDS Aurora for additional scale and performance.
* Encourages adoption of modern database features and practices.

### Negative Consequences

* Less experience with PostgreSQL compared to MSSQL, though mitigated by using a managed service.
* Existing MSSQL workloads may require significant effort to migrate to PostgreSQL.