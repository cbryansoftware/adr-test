# Adopt Amazon RDS for New Relational DB Workloads

* Status: Accepted
* Date: 2022-05-19

## Context and Problem Statement

Following the decision in [ADR-004 Align Databases with Single Services](./ADR-004-align-databases-with-single-services.md), each service should own its database. We need to choose an appropriate hosting solution for these databases that aligns with business needs.

## Considered Options

* Use Amazon RDS as a managed service
* Self-managed database instances
* Managed database services outside of AWS (e.g., Vercel)

## Decision Outcome

Chosen option: "Use Amazon RDS as a managed service," because it reduces operational overhead and aligns with our existing AWS partnership, allowing us to move quickly without a procurement process.

### Positive Consequences

* AWS is a cost-effective partner we understand well, enabling quick implementation.
* Reduced operational overhead with AWS handling routine tasks like provisioning, patching, backup, recovery, and scaling.
* Simplified management of high availability with built-in Multi-AZ deployments and automated failover.
* Easier scalability, allowing database instances to adjust based on demand.
* Enhanced security features, including automated backups, encryption, and integration with AWS IAM.
* Allows engineering teams to focus on application development rather than database management.

### Negative Consequences

* Less control over database configuration and tuning, though this is unlikely to be needed.
* Potentially higher infrastructure costs compared to self-managed instances, offset by reduced operational complexity and likely lower total cost of ownership (TCO).