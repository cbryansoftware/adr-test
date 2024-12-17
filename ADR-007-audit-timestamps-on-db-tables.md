# ADR-007 Mandatory Audit Timestamps for New Database Tables

Date: 2023-02-07

## Status

Accepted

## Context

The majority of our customer-aligned data lacks the standard timestamp information you'd typically expect to find in a database table's schema. While some tables contain a creation timestamp, very few contain a timestamp to indicate when a record was last updated. This makes it very difficult to build robust mechanism for tracking, analyzing, and understanding change in data over time. It often means that we cannot easily serve common data access patterns (eg. show me X records with recent activity) and queries cannot be written as efficiently as they could be.

## Decision

- All new tables must include a timestamp indicating the records initial creation timestamp
- All new tables should include a timestamp indicating the last modified timestamp, unless rows in that table are immutable
- Timestamp fields must be held as UTC without timezone
- For relational workloads, consider indexing these fields when queries aligned to typical use cases interact with them
- Consider adding these fields to existing tables with supporting refactor on-touch 

## Consequences

### Positive

- Improved tracking and auditing of data changes
- Enables more efficient retrieval of time-specific data for new workloads
- Supports better downstream processing for analytics workloads where trends and anomalies are more important
- Facilitates simpler data synchronization across systems
- Potential to rework existing queries to operate in a more efficient manner

### Negative

- Additional storage required to store new fields
- Potential slowdown in database performance if timestamps are not properly indexed, especially with frequent time-based queries
- Timestamps alone do not provide a complete row audit picture. Beyond the scope of this ADR, but consider capturing change in supportive audit aligned table(s) if this is important to your use case