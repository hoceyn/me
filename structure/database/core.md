Database Core

Core Principle

Database design must prioritize correctness, performance, clarity, and long-term maintainability.

Both relational and non-relational databases are acceptable when they fit the data model and performance requirements.

The database choice must follow the access pattern, not personal preference.

Performance Priority

Database structure must be designed around real read/write patterns.

Important reads must be fast.

If normalized relational design creates slow critical reads, do not corrupt the source model.

Use a performance layer instead:

* read models
* shortcut tables
* denormalized tables
* materialized views
* cache tables
* indexes
* search indexes
* document projections
* analytical databases

Relational Database

Use relational databases when the system needs:

* strong consistency
* clear relationships
* transactions
* financial records
* orders
* invoices
* users
* permissions
* structured reporting

Tables must have clear responsibility.

Relationships must be explicit.

Naming must describe the business concept, not the technical shortcut.

Non-relational Database

Use non-relational databases when the system needs:

* flexible documents
* metadata-heavy records
* high-volume event data
* logs
* analytics
* user behavior tracking
* semi-structured business data
* fast document-style access

Document structure must still be intentional.

Non-relational does not mean unstructured.

Naming

All database names must be readable, explicit, and related to their real concept.

This applies to:

* databases
* tables
* collections
* columns
* indexes
* foreign keys
* pivot tables
* JSON keys
* enum values

Avoid vague names:

* data
* item
* value
* temp
* misc
* info
* type
* status without context

Boolean and Status Fields

Boolean fields and status-like fields should start with _.

Examples:

* _active
* _verified
* _paid
* _published
* _deleted
* _status
* _payment_status
* _delivery_status
* _sync_status

This convention makes state fields visually recognizable.

Date and Time

Date-time fields must use datetime type unless there is a clear technical reason to use another type.

Preferred names:

* created_at
* updated_at
* deleted_at
* started_at
* finished_at
* expires_at
* paid_at
* published_at

Use date-only fields only when time is meaningless.

Indexing

Indexes must be designed intentionally based on query patterns.

Critical filters, joins, sorting fields, and lookup fields should be indexed.

Do not add indexes blindly.

Every important query should have an explainable indexing strategy.

Data Duplication

Data duplication is allowed when it improves performance or protects critical reads.

Duplication must be intentional and documented.

Duplicated data must have a clear source of truth.

Source of Truth

Every important data field must have one clear source of truth.

Derived data, cached data, and projected data must not replace the source model.

They exist only to improve access speed or reporting.

Query Safety

Avoid queries that can damage production performance.

Risky patterns:

* unbounded queries
* missing pagination
* large joins without indexes
* filtering on non-indexed high-volume fields
* sorting large datasets without strategy
* loading unnecessary columns
* repeated queries inside loops

Data Growth

Database design must consider future growth.

Large tables, logs, events, orders, messages, analytics, and tracking records must have a growth strategy.

Allowed strategies:

* partitioning
* archiving
* sharding when justified
* separate storage
* cold storage
* summary tables
* retention policies

Decision Rule

When choosing a database structure:

1. Preserve data correctness.
2. Optimize critical reads and writes.
3. Keep naming explicit and concept-based.
4. Choose relational or non-relational based on access pattern.
5. Use performance layers instead of corrupting the source model.
6. Make state fields visually recognizable with _.
7. Keep every derived structure tied to a clear source of truth.
