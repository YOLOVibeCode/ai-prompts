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

### **INTERFACE SEGREGATION PRINCIPLE (NON-NEGOTIABLE)**

**NOTHING should be created unless it's through a properly segregated interface.**

- **ALL business logic MUST implement an interfaces**
- **NO direct class instantiation** - only through interface contracts
- **Clients depend ONLY on methods they actually use**
- **Interfaces are behavioral contracts, NOT implementation blueprints**

### **TEST-DRIVEN DEVELOPMENT (REQUIRED)**

**ALL business logic MUST be validated through CLI test harnesses BEFORE implementation.**

- **100% CLI test coverage** for all core interfaces
- **Mock implementations** validate interface contracts first
- **CLI tests exercise full business workflows**
- **No concrete implementation without passing CLI tests**

### **STRICT DEVELOPMENT WORKFLOW**

```
1. Interface First    → Define interface contract
2. CLI Test          → Create CLI test harness
3. Mock Implementation → Validate interface with mocks
4. Concrete Implementation → Only after CLI tests pass
```
