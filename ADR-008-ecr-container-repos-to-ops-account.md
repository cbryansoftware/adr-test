# ADR-008 Consolidation of ECR Container Repositories into AWS Main Ops Account

Date: 2024-03-24

## Status

In Review

## Context

Currently, AWS Inspector flags security alerts from container repositories (ECR) across multiple AWS accounts. This fragmentation complicates the management and control of security alerts, making it difficult to efficiently address Common Vulnerabilities and Exposures (CVEs) in applications. We'd like to centralize storage, streamline security management, and reduce the number of alerts, thereby focusing efforts on mitigating security risks.

## Decision

Consolidate all ECR container repositories into the `aws-main-ops` account.

## Consequences

### Positive

- Centralization simplifies the management and response to security alerts, enabling a more efficient and effective approach to potential security threats
- Managing user access and permissions becomes easier, reducing the risk of unauthorized access
- Consolidation can lead to cost savings by minimizing the overhead associated with multiple accounts
- Reduces complexity by managing repositories within a single account, facilitating smoother operations

### Negative

- The consolidation process requires significant effort and careful planning to minimize disruption to ongoing operations.
- Centralizing ECRs could create a single point of failure, but this risk can be mitigated with robust security measures and backup strategies.
- While centralization simplifies access control, changes to permissions will affect all repositories. This is mitigated by assigning read-only permissions for service deployments and providing developers with a read-only role to review stored images in the `aws-main-ops` account if needed.