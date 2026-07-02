Structure Core

Definition

Structure means the entire project organization, not only folders or database tables.

It includes project boundaries, directories, modules, services, sub-services, libraries, third-party integrations, data models, databases, execution flow, deployment flow, operational flow, and long-term maintainability.

A file, class, table, service, or module must be placed where its concept belongs, not where implementation is easiest.

Core Principle

Either do not build it, or build it with premium-grade structural quality.

The highest priority is the highest practical engineering quality that remains economically justifiable for a premium product.

No shortcut is acceptable if it damages the long-term structure, production reliability, or business credibility of the project.

Premium Execution

Every project is assumed to be a premium-level production system.

Avoid:

* useless execution
* test-like production work
* high-risk shortcuts
* temporary structures without isolation
* undocumented launch behavior
* production-only experiments

A feature is not complete only because it works.

A feature is complete only when it is structurally correct, maintainable, deployable, recoverable, observable, and documented.

Structure Scalability

The system must not avoid proper separation because it creates more files, folders, services, or sub-services.

There is no artificial limit on directories, modules, services, sub-services, tables, or supporting data stores.

Each part must have a clear responsibility and justified place.

Data Structure

Data models must be designed based on correct domain logic.

If a correct engineered database structure becomes inefficient for important reads, do not damage the core model.

Add a dedicated optimization layer instead.

Allowed optimization layers:

* shortcut tables
* read models
* materialized views
* cache tables
* denormalized projections
* search indexes
* separate analytical databases
* separate read-optimized databases

Optimization must be added beside the correct structure, not instead of it.

Concept Awareness

The system must understand conceptual differences.

Examples:

* system services are not libraries
* libraries are not business services
* third-party integrations are not internal services
* infrastructure code is not domain logic
* shared utilities are not feature modules
* database structure is not API structure
* UI structure is not backend structure

Files must be placed according to their conceptual role.

Directory Responsibility

Every directory must represent a clear concept.

A directory is invalid if its purpose cannot be explained in one sentence.

Generic dumping grounds are discouraged:

* utils
* helpers
* common
* misc
* temp
* shared

They are allowed only when their internal rules are explicitly defined.

Service Boundary

A service or sub-service is valid only when it has a clear independent responsibility.

A service boundary must be based on concept, ownership, data flow, execution model, or scalability need.

Do not create services only to make the project look advanced.

Do not merge services only to make the project look simpler.

Third-Party Boundary

Third-party integrations must have their own clear boundary.

External providers must not leak into core business logic.

Provider-specific logic must be isolated behind internal contracts.

Replacing a third-party provider should not require rewriting core domain logic.

Deployment Philosophy

Deployment is part of the product, not the final step of development.

Every deployable system must have a documented launch and deployment process.

Documentation must allow another qualified engineer to deploy, verify, recover, and maintain the system without undocumented knowledge.

Deployment documentation should include, whenever applicable:

* infrastructure requirements
* installation process
* configuration
* secrets management
* dependencies
* startup sequence
* health verification
* rollback procedure
* backup and recovery
* upgrade procedure

Fast launch must come from preparation, documentation, and automation; not from skipping engineering steps.

Risk Policy

Engineering decisions must minimize long-term business risk.

Avoid decisions that introduce:

* undocumented behavior
* deployment uncertainty
* operational dependency on individuals
* irreversible migrations
* hidden technical debt
* production-only testing

If a safer architecture exists with reasonable implementation cost, it should be preferred.

Operational Independence

A production system should not depend on the original developer for normal operation.

Knowledge required for operating the system must be transferred into the project through documentation, automation, and predictable structure.

The project itself should remain the primary source of operational knowledge.

Refactor Rule

If the current structure cannot support the correct implementation, refactor the structure before adding the feature.

Do not force new logic into the wrong structure.

A wrong structure with working code is still structurally invalid.

Anti-Overengineering Lock

These rules must not be interpreted as a preference for overengineering.

The goal is not complexity.

The goal is correct premium-grade structure.

A simple structure is valid only when it is conceptually correct, production-safe, and future-safe.

A complex structure is valid only when the problem actually requires it.

Decision Rule

When choosing between two structures:

1. Choose the one with more correct domain separation.
2. Choose the one that keeps future changes cleaner.
3. Choose the one that prevents conceptual mixing.
4. Choose the one that preserves data correctness.
5. Choose the one that allows performance optimization without corrupting the model.
6. Choose the one with clearer ownership.
7. Choose the one with lower long-term business risk.
8. Choose the one with better premium-grade execution quality.
