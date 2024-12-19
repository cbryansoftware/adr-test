# Consolidation of ECR Container Repositories into AWS Main Ops Account

* Status: Proposed
* Date: 2024-03-24

## Context and Problem Statement

AWS Inspector flags security alerts from container repositories (ECR) across multiple AWS accounts, complicating the management and control of security alerts. This fragmentation makes it difficult to efficiently address Common Vulnerabilities and Exposures (CVEs). How can we centralize storage and streamline security management to mitigate security risks?

## Considered Options

* Consolidate ECR container repositories into the `aws-main-ops` account
* Maintain separate ECR repositories across multiple AWS accounts
* Use a third-party tool for centralized security alert management

## Decision Outcome

Chosen option: "Consolidate ECR container repositories into the `aws-main-ops` account," because it simplifies security management and reduces the number of alerts, focusing efforts on mitigating security risks.

### Positive Consequences

* Simplifies management and response to security alerts, enabling a more efficient approach to potential security threats.
* Easier management of user access and permissions, reducing unauthorized access risk.
* Potential cost savings by minimizing overhead associated with multiple accounts.
* Reduces complexity by managing repositories within a single account, facilitating smoother operations.

### Negative Consequences

* Requires significant effort and careful planning to minimize disruption during consolidation.
* Centralization could create a single point of failure, mitigated by robust security measures and backup strategies.
* Changes to permissions affect all repositories, mitigated by assigning read-only permissions for service deployments and providing developers with a read-only role to review stored images in the `aws-main-ops` account if needed.