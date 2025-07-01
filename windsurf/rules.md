# 🚨 WINDSURF PROJECT RULES - Place them in the root ./windsurf/rules.md

## ⚠️ **MANDATORY DEVELOPMENT PRINCIPLES - READ FIRST**

### **SIMPLICITY FIRST (CRITICAL)**

**DO NOT OVERCOMPLICATE. Keep it simple, focused, and practical.**

- **KISS Principle**: Keep It Simple, Stupid
- **YAGNI**: You Aren't Gonna Need It - no premature abstractions
- **Avoid over-engineering** - resist architectural speculation
- **Prefer composition over inheritance**
- **No design patterns until absolutely necessary**
- **Always read a README.md or and root directly markdown to refresh our context memory

### **EVENT-DRIVEN ARCHITECTURE (REQUIRED)**

**ALL components MUST communicate through a SIMPLIFIED event-driven pattern.**

**⚠️ SIMPLICITY WARNING: Do NOT overcomplicate the event architecture. Start simple and evolve only when necessary.**

- **Loose Coupling**: Components communicate only through events, never direct references
- **Event Bus Pattern**: Central event dispatcher for all cross-component communication
- **Domain Events**: Events represent meaningful business occurrences
- **Start with basic pub/sub** - resist complex patterns until proven necessary
- **Event Sourcing** (ONLY when appropriate): Store events as source of truth - NOT by default
- **CQRS** (ONLY when beneficial): Separate read/write models - avoid unless complexity demands it

#### **Event-Driven Toolkit Recommendation**
Before implementing custom event infrastructure, **ASK THE USER** if they want to use established, battle-tested event-driven toolkits:

**Popular Options:**
- **EventEmitter3** (Node.js) - Lightweight, fast event emitter
- **RxJS** - Reactive programming with observables
- **MediatR** (.NET) - In-process messaging patterns
- **EventBus** (various languages) - Simple pub/sub implementations
- **Apache Kafka** / **Redis** (for distributed systems)

**Decision Criteria:**
- Is the toolkit actively maintained?
- Does it have comprehensive test coverage?
- Does it follow established event-driven patterns?
- Is the learning curve justified by project complexity?

### **INTERFACE SEGREGATION PRINCIPLE (NON-NEGOTIABLE)**

**NOTHING should be created unless it's through a properly segregated interface.**

- **ALL business logic MUST implement interfaces**
- **NO direct class instantiation** - only through interface contracts
- **Clients depend ONLY on methods they actually use**
- **Interfaces are behavioral contracts, NOT implementation blueprints**
- **Event handlers MUST implement event interface contracts**

### **TEST-DRIVEN DEVELOPMENT (REQUIRED)**

**ALL business logic MUST be validated through CLI test harnesses BEFORE implementation.**

- **100% CLI test coverage** for all core interfaces
- **Mock implementations** validate interface contracts first
- **CLI tests exercise full business workflows**
- **Event-driven flows MUST be testable via CLI**
- **Mock event dispatchers** for testing event flows
- **No concrete implementation without passing CLI tests**

### **STRICT DEVELOPMENT WORKFLOW**

```
1. Interface First         → Define interface contract (including event contracts)
2. Event Schema           → Define event payload structures
3. CLI Test              → Create CLI test harness with mock events
4. Mock Implementation   → Validate interfaces with mock event flows
5. Concrete Implementation → Only after CLI tests pass
```

### **EVENT-DRIVEN SPECIFIC RULES**

**🚨 KEEP IT SIMPLE: Resist over-engineering the event system. Most applications need basic pub/sub, not complex event architectures.**

- **Event Naming**: Use past-tense verbs (e.g., `UserRegistered`, `OrderCompleted`)
- **Event Immutability**: Events should be immutable once created
- **Start with in-memory events** - move to persistent/distributed only when scaling demands it
- **Event Versioning**: Plan for event schema evolution (but don't over-engineer v1)
- **Error Handling**: Failed event processing should not crash the system
- **Idempotency**: Event handlers should be idempotent when possible
- **Avoid event chains** - if Event A always triggers Event B, consider if they should be one event

### **NO GENERIC NAMING CONVENTIONS (REQUIRED)**

- **NO GENERIC NAMES Principle**: After generating the code, scan all class, method, and variable names. If any name is too generic (like Helper, Processor, Task, Info, Data, etc.), replace it with a name that describes its exact role in the application domain.
- **Event-Specific**: Avoid generic event names like `DataChanged` or `UpdateEvent`
