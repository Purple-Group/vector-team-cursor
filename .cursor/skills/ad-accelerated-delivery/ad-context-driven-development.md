# Context-Driven Development

> The Context → Plan → Execute workflow ensures every feature follows established patterns.

---

## The Core Principle

> **"With every prompt I started with: get context of architecture patterns used and plan before we execute, forcing us to stick to the patterns we laid out."**

---

## The Master Prompt Template

```
# Task: [CLEAR DESCRIPTION]

## Phase 1: Context Gathering
1. Review Architectural Patterns
   - Read: DESIGN_PATTERNS.md
   - Read: PROJECT_STRUCTURE.md
   - Read: [Relevant architecture doc]

2. Review Existing Implementation
   - Find similar features in codebase
   - Understand current approach
   - Identify reusable patterns

3. Identify Requirements
   - Functional requirements
   - Non-functional requirements (performance, security)
   - Testing requirements (per TEST_AUTOMATION_STRATEGY.md)

## Phase 2: Planning
1. Design Overview
   - Which layers affected? (Controller, Service, Repository, Model, DTO)
   - New files needed?
   - Existing files to modify?

2. Pattern Alignment
   - How does this fit Repository Pattern?
   - How does this fit Unit of Work?
   - How does this fit DTO Pattern?
   - Any deviations? Why?

3. Implementation Steps
   - Step 1: [Database/Models]
   - Step 2: [Repository]
   - Step 3: [Service]
   - Step 4: [Controller/API]
   - Step 5: [Frontend if applicable]
   - Step 6: [Tests]

4. Risk Assessment
   - Breaking changes?
   - Migration needed?
   - Performance considerations?

## Phase 3: Implementation
[AI implements following the plan]

## Phase 4: Testing
1. Unit Tests
   - Test service layer logic
   - Mock dependencies
   - Cover happy path + error cases

2. Integration Tests
   - Test API endpoints
   - Use real database
   - Verify response format

3. E2E Tests (if critical flow)
   - Test complete user journey
   - Verify UI interaction

## Phase 5: Verification
- [ ] Files in correct locations per PROJECT_STRUCTURE.md
- [ ] Patterns match DESIGN_PATTERNS.md
- [ ] All tests pass
- [ ] No linter errors
- [ ] Documentation updated
- [ ] CHANGELOG.md updated (if applicable)

## Phase 6: Documentation
- Update README.md if needed
- Update ARCHITECTURE.md if architectural change
- Add inline code comments for complex logic
- Update API documentation (Swagger)
```

---

## ❌ BAD: Direct Implementation Request

```
Prompt: "Add a new endpoint to get teams"
```

**Problem**: AI will create code without considering existing patterns.

---

## ✅ GOOD: Context → Plan → Execute

```
Prompt: "I need to add an endpoint to get all teams.

Before implementing:
1. Review our DESIGN_PATTERNS.md to understand our patterns
2. Look at existing controllers to see our approach
3. Review how we structure services and repositories
4. Provide a plan that follows our established patterns

Once you have the plan, implement:
- Controller endpoint following our controller pattern
- Service method following our service layer pattern  
- Repository method if needed
- DTOs following our DTO pattern
- Include proper dependency injection"
```

**Result**: AI generates code consistent with your architecture.

---

## Context Is King

**Every significant prompt must include**:

1. Task description
2. Context gathering (read DESIGN_PATTERNS.md, etc.)
3. Planning phase
4. Implementation phase
5. Verification phase

**Template**:

```
Task: [What you need]

Context:
- Read: [relevant docs]
- Review: [existing code]
- Understand: [constraints]

Plan:
- Step 1: [design]
- Step 2: [implement]
- Step 3: [test]

Execute:
[AI implements]

Verify:
- Follows patterns: ✅
- Tests pass: ✅
- Lints pass: ✅
```

---

## Real Example: Team Management

```
I need to implement team management (CRUD operations).

Context:
- Review DESIGN_PATTERNS.md for our Repository and Unit of Work patterns
- Look at how we structured database entities (BaseEntity pattern)
- Review our DTO pattern for API contracts

Plan:
1. Database layer:
   - Create Team entity (extends BaseEntity)
   - Add DbSet to RepoRadarDbContext
   - Create migration

2. Repository layer:
   - Create ITeamRepository (extends IRepository<Team>)
   - Implement TeamRepository (extends Repository<Team>)
   - Add specialized methods (GetTeamWithRepositories)

3. Service layer:
   - Create ITeamService interface
   - Implement TeamService
   - Inject IUnitOfWork
   - Business logic and validation

4. API layer:
   - Create DTOs (TeamDto, CreateTeamDto, UpdateTeamDto)
   - Create TeamsController
   - Inject ITeamService
   - Standard REST endpoints (GET, POST, PUT, DELETE)

Execute following our dependency injection pattern.
```

---

## Key Takeaways

1. **Never skip context gathering** - Always read patterns first
2. **Plan before implementing** - Identify layers and files
3. **Verify pattern compliance** - Check against DESIGN_PATTERNS.md
4. **Include testing** - Generate tests per testing pyramid
5. **Update documentation** - Code + Tests + Docs = Done

---

## Reference

- Framework Source: `docs/ai-pod/common/accelerated-delivery-framework.md` (lines 302-417, 835-914)
- Master Template: Lines 839-914
- Example Workflow: Lines 916-1074
