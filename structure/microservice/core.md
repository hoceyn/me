Microservice Core

Philosophy

Large systems should not perform every task themselves.

A system should delegate responsibilities whenever an independent service can execute them with lower operational cost, better isolation, or better scalability.

The primary system should remain focused on its core business responsibilities.

Build vs Buy

Microservices must not become a reason to reinvent existing solutions.

Before creating a new service, evaluate whether a mature and reliable solution already exists.

Prefer adopting proven solutions over rebuilding them unless there is a clear business or technical justification.

The objective is solving the problem, not owning every implementation.

Responsibility

Every microservice must have one clear responsibility.

A service should exist because it owns a business capability or an operational capability.

A microservice must not become a collection of unrelated features.

Operational Isolation

Operations capable of degrading the stability, responsiveness, or availability of the primary system should be isolated.

Isolation may be achieved through:

* asynchronous workers
* dedicated services
* independent microservices
* separate infrastructure

Choose the simplest isolation mechanism that satisfies the operational requirement.

Microservices are not the default solution.

Service Independence

Each microservice should be independently:

* deployable
* scalable
* maintainable
* observable
* recoverable

Whenever practical, failures inside a microservice should not interrupt the primary system.

Resource Protection

CPU-intensive, memory-intensive, IO-intensive, network-intensive, and long-running operations should not compete with the primary business flow.

The primary system should remain responsive even while background operations continue.

Communication

Microservices should communicate through stable contracts.

Implementation details must remain private.

Communication mechanisms may include:

* HTTP APIs
* message queues
* event buses
* RPC

The communication method should be chosen according to operational requirements, not preference.

Business Perspective

Think of the platform as a company operating multiple specialized machines.

Each machine performs the task it is best suited for.

The value comes from coordination between specialized systems, not from forcing one system to perform every task.

Decision Rule

Before introducing a new microservice, answer these questions:

* Does it have a single responsibility?
* Can it evolve independently?
* Does it improve operational isolation?
* Does it reduce long-term maintenance cost?
* Does it reduce business risk?
* Is it more appropriate than a worker, queue, or module?

If the answer is no, a microservice should not be introduced.

Anti-Overengineering Lock

Microservices are a tool for improving architecture.

They are not a measure of engineering maturity.

The smallest architecture that correctly satisfies the operational and business requirements should always be preferred.

Communication Preferences

The preferred communication model between services is HTTP-based communication over dedicated subdomains.

Preferred endpoint style:

* https://service.example.com
* https://api.example.com
* https://ai.example.com

rather than path-based routing.

Authentication credentials should be transmitted using standard HTTP request headers.

Preferred authentication model:

Authorization: Bearer <token>

Avoid transmitting authentication credentials through:

* query parameters
* URL paths
* request body (unless explicitly required by the protocol)

Services should expose stable, versionable APIs that remain independent of their internal implementation.

When multiple communication approaches are technically valid, prefer the one that follows these conventions unless there is a clear technical or business reason to do otherwise.
