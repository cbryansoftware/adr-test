# ADR-005 Adopt PostgreSQL for New Relational Database Workloads

Date: 2022-05-19

## Status

Accepted

## Context

As decided by [ADR-004 Adopt Amazon RDS for New Relational DB Workloads](./ADR-004-align-databases-with-single-services.md), we will adopt Amazon RDS as a managed service for new relational database workloads.

BigChange's current reliance on MSSQL incurs licensing costs and limits flexibility. As we transition to new services, a more cost-effective and flexible database engine is needed.

## Decision

Teams will use PostgreSQL as the default relational database engine choice for future workloads, unless there is strong justification to choose differently.

### Alternatives Considered

- RDS MySQL
- RDS MSSQL

## Consequences

### Positive

- PostgreSQL is free and open-source, eliminating licensing costs associated with MSSQL.
- Supports a wide range of data types and extensions, allowing for greater flexibility in application design.
- Strong community support and extensive documentation.
- Provides a simple upgrade path to Amazon RDS Aurora for additional scale and performance.
- Encourages adoption of modern database features and practices.

### Negative

- Less experience with PostgreSQL compared to MSSQL, though mitigated by using a managed service.
- Existing MSSQL workloads may require significant effort to migrate to PostgreSQL.
