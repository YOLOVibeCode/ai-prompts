---
inclusion: always
---

# Project Development Principles

## ⚠️ MANDATORY DEVELOPMENT PRINCIPLES - READ FIRST

### SIMPLICITY FIRST (CRITICAL)

**DO NOT OVERCOMPLICATE. Keep it simple, focused, and practical.**

- **KISS Principle**: Keep It Simple, Stupid
- **YAGNI**: You Aren't Gonna Need It - no premature abstractions
- **Avoid over-engineering** - resist architectural speculation
- **Prefer composition over inheritance**
- **No design patterns until absolutely necessary**
- **Always read a README.md or root directory markdown to refresh context memory**

### INTERFACE SEGREGATION PRINCIPLE (NON-NEGOTIABLE)

**NOTHING should be created unless it's through a properly segregated interface.**

- **ALL business logic MUST implement interfaces**
- **NO direct class instantiation** - only through interface contracts
- **Clients depend ONLY on methods they actually use**
- **Interfaces are behavioral contracts, NOT implementation blueprints**

### TEST-DRIVEN DEVELOPMENT (REQUIRED)

**ALL business logic MUST be validated through CLI test harnesses BEFORE implementation.**

- **100% CLI test coverage** for all core interfaces
- **Mock implementations** validate interface contracts first
- **CLI tests exercise full business workflows**
- **No concrete implementation without passing CLI tests**

### STRICT DEVELOPMENT WORKFLOW

```
1. Interface First    → Define interface contract
2. CLI Test          → Create CLI test harness
3. Mock Implementation → Validate interface with mocks
4. Concrete Implementation → Only after CLI tests pass
```

### NO GENERIC NAMING CONVENTIONS (REQUIRED)

**NO GENERIC NAMES Principle**: After generating code, scan all class, method, and variable names. If any name is too generic (like Helper, Processor, Task, Info, Data, etc.), replace it with a name that describes its exact role in the application domain.

Examples of generic names to avoid:
- Helper → SpecificDomainHelper (e.g., `PatientDataValidator`)
- Processor → SpecificProcessor (e.g., `AudioSignalProcessor`)
- Task → SpecificTask (e.g., `TherapySessionTask`)
- Info → SpecificInfo (e.g., `PatientMedicalInfo`)
- Data → SpecificData (e.g., `TherapySessionData`)