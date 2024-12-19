# Mandatory Audit Timestamps for New Database Tables

* Status: Accepted
* Date: 2023-02-07

## Context and Problem Statement

Many of our customer-aligned data tables lack standard timestamp information, making it difficult to track, analyze, and understand data changes over time. This absence hinders efficient query writing and serving common data access patterns. How can we ensure new tables support robust data tracking and analysis?

## Considered Options

* Mandate audit timestamps for new database tables
* Continue without standardizing timestamp usage
* Implement optional timestamp usage based on developer discretion

## Decision Outcome

Chosen option: "Mandate audit timestamps for new database tables," because it improves data tracking, auditing, and query efficiency.

### Positive Consequences

* Improved tracking and auditing of data changes.
* Enables more efficient retrieval of time-specific data for new workloads.
* Supports better downstream processing for analytics workloads where trends and anomalies are important.
* Facilitates simpler data synchronization across systems.
* Potential to rework existing queries to operate more efficiently.

### Negative Consequences

* Additional storage required for new fields.
* Potential slowdown in database performance if timestamps are not properly indexed, especially with frequent time-based queries.
* Timestamps alone do not provide a complete row audit picture; consider supportive audit tables for comprehensive auditing.