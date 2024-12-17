# ADR-004 Adopt Amazon RDS for New Relational DB Workloads

Date: 2022-05-19

## Status

Accepted

## Context

As decided by [ADR-004 Align Databases with Single Services](./ADR-004-align-databases-with-single-services.md), services should own their own database rather than operating arounda a single, contested shared schema. We need to select an appropriate means of hosting these database workloads to suit the needs of the business. 

## Decision

New workloads will use Amazon RDS as a managed service rather than self-managed database instances.

### Alternatives Considered

- Self-managed database instances
- Managed database services outside of AWS (eg. Vercel)

## Consequences

### Positive

- AWS is an existing, cost-effect partner that we understand well, allowing us to move quickly without procurement process
- Reduced operational overhead as AWS handles routine tasks such as provisioning, patching, backup, recovery, and scaling
- Simplified management of high availability with built-in support for Multi-AZ deployments and automated failover
- Easier scalability, allowing database instances to scale up or down based on demand
- Enhanced security features, including automated backups, encryption, and integration with AWS IAM
- Allows engineering teams to focus on application development rather than database management

### Negative

- Less control over database configuration and tuning, though we are unlikely to need this
- Potentially higher infrastructure costs compared to self-managed instances, though this is offset by reduced operational complexity and TCO is likely still lower