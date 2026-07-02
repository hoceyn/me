# Database Core

## Philosophy

The database is the foundation of the system.

Every design decision must prioritize:

1. Data correctness
2. Performance
3. Long-term maintainability
4. Readability
5. Scalability

The database technology must be selected based on the nature of the problem, not personal preference.

---

# Database Selection

Both relational and non-relational databases are valid.

Choose the database according to the access pattern, consistency requirements, scalability requirements, and business needs.

Never force every problem into a single database technology.

Multiple database engines may coexist in one system if they provide a better overall architecture.

---

# Relational Databases

Prefer relational databases when the domain requires:

- transactions
- financial operations
- relationships
- referential integrity
- reporting
- consistency
- business rules

The schema should accurately model the business domain.

---

# Non-relational Databases

Prefer document databases when the domain contains:

- flexible metadata
- dynamic structures
- documents
- logs
- analytics
- event storage
- user-generated schemas

Document databases must remain intentionally structured.

Flexible does not mean uncontrolled.

---

# Performance

Performance is a first-class design goal.

Critical read operations should always remain fast.

Do not destroy a correct relational model simply to optimize reads.

Instead, introduce dedicated optimization layers.

Allowed optimization techniques include:

- read models
- shortcut tables
- cache tables
- denormalized projections
- materialized views
- search indexes
- analytical databases
- dedicated read databases

The source model must remain logically correct.

Optimization exists beside the source model, never instead of it.

---

# Naming

Naming must always describe the business concept.

Names must be explicit, readable, and predictable.

This applies to:

- databases
- schemas
- tables
- collections
- columns
- indexes
- constraints
- foreign keys
- JSON properties

Avoid meaningless names such as:

- data
- item
- value
- temp
- misc
- info
- obj

---

# State Fields

Boolean fields and state-related fields should begin with an underscore.

Examples:

_active
_enabled
_verified
_deleted
_locked
_paid
_visible
_status
_payment_status
_delivery_status
_sync_status

State fields should be immediately recognizable.

---

# Date & Time

All date-time values should use the DATETIME type unless another type has a clear technical advantage.

Preferred field names:

created_at
updated_at
deleted_at
published_at
expires_at
started_at
finished_at
paid_at

Store date-only values only when time has no business meaning.

---

# Index Strategy

Indexes must be intentional.

Create indexes based on actual query patterns.

Indexes should support:

- filtering
- sorting
- joins
- unique lookups
- high-frequency queries

Avoid unnecessary indexes.

Every index should have a reason.

---

# Data Duplication

Intentional duplication is acceptable when it significantly improves performance.

Duplicated data must:

- have one source of truth
- be synchronized
- be documented

Never duplicate data without a defined synchronization strategy.

---

# Growth Strategy

The database must be designed with future growth in mind.

Large datasets should have a clear scaling strategy.

Possible approaches include:

- partitioning
- archiving
- dedicated storage
- read replicas
- sharding (when justified)
- retention policies
- summary tables

---

# Query Design

Queries should minimize unnecessary work.

Avoid:

- SELECT *
- unnecessary joins
- N+1 queries
- full table scans on high-volume tables
- sorting without indexes
- filtering on non-indexed fields
- loading unused columns

Every expensive query should have a measurable justification.

---

# Decision Rule

When multiple database designs are technically valid:

1. Preserve data correctness.
2. Preserve business meaning.
3. Prefer the design with better long-term performance.
4. Optimize using dedicated performance layers instead of weakening the source model.
5. Keep naming explicit and business-oriented.
6. Make state fields immediately recognizable using the underscore convention.
7. Design for future growth from the beginning.
