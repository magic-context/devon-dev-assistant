# Architecture Patterns

## Monolith

Single deployable unit containing all application logic.

**When to choose:**
- Starting a new project (almost always start here)
- Small team (1-10 developers)
- Simple domain or unclear service boundaries
- Speed of development matters more than independent scaling

**Tradeoffs:**
- ✅ Simple deployment, testing, and debugging
- ✅ No network latency between components
- ✅ Easy to refactor and restructure internally
- ❌ Scales as a unit (can't scale just the hot path)
- ❌ Deploy everything to change anything
- ❌ Can become unwieldy at very large scale

**Best practice:** Modular monolith — monolith deployment, but clean internal boundaries. Extract services later when you have evidence.

## Microservices

Application split into independently deployable services, each owning its domain.

**When to choose:**
- Large team needing independent deployment
- Clear domain boundaries (proven, not guessed)
- Different scaling requirements per component
- Polyglot requirements (different languages/DBs per service)

**Tradeoffs:**
- ✅ Independent deployment and scaling
- ✅ Team autonomy and ownership
- ✅ Technology flexibility per service
- ❌ Network complexity, latency, and failure modes
- ❌ Data consistency challenges (no shared DB)
- ❌ Operational overhead (monitoring, tracing, deployment)
- ❌ Debugging distributed issues is hard

**Don't microservice until:** You've proven the boundaries in a monolith and have the operational maturity to support distributed systems.

## Serverless

Functions-as-a-service — code runs in response to events, infrastructure managed by provider.

**When to choose:**
- Event-driven workloads (webhooks, file processing, scheduled tasks)
- Variable/unpredictable traffic
- Prototyping and MVPs
- When you want zero infrastructure management

**Tradeoffs:**
- ✅ Zero server management
- ✅ Scales automatically (including to zero)
- ✅ Pay only for execution time
- ❌ Cold starts (latency on first invocation)
- ❌ Vendor lock-in (AWS Lambda ≠ Google Cloud Functions)
- ❌ Harder to test and debug locally
- ❌ Not great for long-running processes

## Event-Driven

Components communicate through events (messages, streams) rather than direct calls.

**When to choose:**
- Decoupled systems that need to react to changes
- Audit/logging requirements (event sourcing)
- Multiple consumers need the same data
- Temporal decoupling (producer doesn't wait for consumer)

**Tradeoffs:**
- ✅ Loose coupling between components
- ✅ Natural audit trail
- ✅ Easy to add new consumers without changing producers
- ❌ Eventual consistency (not immediate)
- ❌ Event ordering and deduplication complexity
- ❌ Harder to trace request flow (distributed tracing needed)

## Common Patterns

### API Design
- **REST** — Resource-oriented, HTTP verbs, widely understood. Default choice.
- **GraphQL** — Client-driven queries. Good when clients have diverse data needs.
- **gRPC** — Binary protocol, strongly typed. Good for service-to-service communication.
- **WebSocket** — Real-time bidirectional. Good for live data (chat, dashboards).

### Data Access
- **Repository pattern** — Abstraction over data access. Easy to test, swap implementations.
- **CQRS** — Separate read and write models. Good for complex domains or different scaling needs.
- **Event sourcing** — Store events, not state. Perfect audit trail, complex to implement.

### Caching
- **Cache-aside** — App checks cache first, loads from DB on miss. Most common.
- **Write-through** — App writes to cache and DB simultaneously. Consistency at cost of latency.
- **TTL-based** — Set expiration. Simple, good for data that changes infrequently.

## Decision Framework

| Factor | Lean Toward | Lean Away |
|--------|------------|-----------|
| Small team, new project | Monolith | Microservices |
| Proven domain boundaries | Microservices | Monolith (if scaling issues) |
| Unpredictable traffic | Serverless | Fixed infrastructure |
| Real-time requirements | Event-driven + WebSocket | REST polling |
| Strong consistency needed | Monolith or synchronous calls | Eventually consistent patterns |
| Rapid prototyping | Serverless or simple monolith | Complex architectures |
