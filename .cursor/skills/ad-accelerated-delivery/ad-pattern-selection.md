# Pattern Selection

> How to choose and document architectural patterns that AI can follow.

---

## The Principle

**Don't invent. Select from proven patterns.**

Choose patterns that:
- ✅ Enable testability
- ✅ Improve maintainability
- ✅ Support separation of concerns
- ✅ Are well-documented and understood

---

## Step 1: Define Your Building Blocks

Before writing code, answer these questions:

### Architecture Questions

1. What is the high-level architecture? (e.g., API + SPA + Database)
2. What are the major components? (e.g., Authentication, Authorization, Business Logic, External Integrations)
3. How do components communicate? (REST, GraphQL, gRPC, Events)
4. Where are boundaries drawn? (Frontend/Backend, Modules, Domains)

### Technology Questions

1. What's the backend stack? (Language, Framework, ORM)
2. What's the frontend stack? (Framework, State Management, UI Library)
3. What's the infrastructure? (Docker, Kubernetes, Serverless)
4. What external services? (Auth provider, Secret management, Observability)

### Pattern Questions

1. How will you access data? (Repository pattern, Direct ORM, Query objects)
2. How will you manage transactions? (Unit of Work, Ambient transactions)
3. How will you transfer data? (DTOs, Domain models, GraphQL types)
4. How will you inject dependencies? (Built-in DI, 3rd-party container)

---

## Step 2: Select Proven Patterns

**Example: RepoRadar Patterns**

- **Repository Pattern**: Abstracts data access, enables testing
- **Unit of Work**: Manages transactions across multiple repositories
- **DTO Pattern**: Separates API contracts from domain models
- **Dependency Injection**: Loose coupling, testability
- **Service Layer**: Encapsulates business logic

**Document WHY each pattern was selected**:

- Repository: Needed to mock data access for unit tests
- Unit of Work: Multiple entities modified per request (teams + repositories)
- DTOs: Frontend models differ from database models
- DI: Microsoft best practice, built-in support
- Service Layer: Complex business logic (tech debt scoring)

---

## Step 3: Document Your Patterns

Create **DESIGN_PATTERNS.md** that explains:

1. **What** each pattern is
2. **Why** you're using it
3. **How** it's implemented in your project
4. **Examples** from your actual codebase

**This becomes your AI's instruction manual.**

### Example Structure

```markdown
# Design Patterns Guide

## 1. Repository Pattern

### What is it?
[Explanation]

### Why use it?
✅ Testability
✅ Maintainability
✅ Separation of concerns

### How we use it
[Code example from your project]

### When to use this pattern
[Guidelines]
```

**Critical**: Include real code examples from your project, not generic samples.

---

## Step 4: Create Project Structure

Design your folder structure to reflect your architecture.

### ❌ Bad Structure (No clear architecture)

```
src/
├── files/
├── stuff/
├── utils/
└── code.cs
```

### ✅ Good Structure (Architecture-aligned)

```
RepoRadar.API/
├── Controllers/          # HTTP layer
├── Services/            # Business logic
│   ├── Interfaces/
│   └── Implementations/
├── Repositories/        # Data access
│   ├── Interfaces/
│   └── Implementations/
├── Models/              # Domain entities
├── DTOs/                # API contracts
├── Core/                # Cross-cutting (UnitOfWork)
├── Data/                # DbContext
└── Infrastructure/      # External APIs
```

**Principle**: A developer (or AI) should look at the folder structure and immediately understand the architecture.

---

## Pattern Adherence Checklist

After AI generates code, verify:

* ✅ Files in correct folders per PROJECT_STRUCTURE.md
* ✅ Patterns match DESIGN_PATTERNS.md
* ✅ Dependencies injected via constructor
* ✅ DTOs used for API contracts
* ✅ Repository methods async
* ✅ Service layer has business logic
* ✅ Controllers are thin (delegate to services)

---

## Key Takeaways

1. **Select, don't invent** - Use proven patterns
2. **Document why** - Explain rationale for each pattern choice
3. **Show examples** - Use real code from your project
4. **Structure reflects architecture** - Folder hierarchy should be self-explanatory
5. **Validate adherence** - Check code against patterns before completion

---

## Reference

- Framework Source: `docs/ai-pod/common/accelerated-delivery-framework.md` (lines 51-165, 198-299)
- Pattern Documentation: `docs/DESIGN_PATTERNS.md`
- Project Structure: `docs/PROJECT_STRUCTURE.md`
