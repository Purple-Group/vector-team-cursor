# Testing Pyramid

> Testing strategy and AI test generation following the 60/30/10 pyramid.

---

## The Testing Philosophy

> **"Shifting left with testing, but it goes even deeper—you need to become a self-serviced AI pod team."**

---

## Testing Pyramid Overview

```
        /\
       /  \  E2E Tests (10%)
      /____\  Critical user journeys
     /      \
    / Inte-  \ Integration Tests (30%)
   / gration  \ API + Database
  /____________\
 /              \ Unit Tests (60%)
/  Unit Tests    \ Business logic
```

---

## Step 1: Define Your Testing Layers

Early in the project, create detailed testing documentation:

### 1. Unit Tests (60% of tests)

* **What**: Pure business logic, calculations, transformations
* **Tools**: xUnit (C#), Jasmine/Jest (TypeScript)
* **Mocking**: All dependencies mocked
* **Speed**: < 1ms per test

### 2. Integration Tests (30% of tests)

* **What**: API endpoints with real database
* **Tools**: WebApplicationFactory (C#), Playwright (E2E)
* **Mocking**: External APIs mocked, database real
* **Speed**: 100-500ms per test

### 3. E2E Tests (10% of tests)

* **What**: Critical user journeys
* **Tools**: Playwright
* **Mocking**: Nothing mocked
* **Speed**: 5-30s per test

---

## Step 2: AI-Generated Tests

### Prompt for Unit Tests

```
Task: Generate unit tests for AnalysisService

Context:
1. Review TEST_AUTOMATION_STRATEGY.md for our testing approach
2. Look at existing tests (e.g., TeamServiceTests.cs) for patterns
3. Review the service to understand all methods

Requirements:
- Test all public methods
- Cover happy path and error cases
- Mock all dependencies (IUnitOfWork, ICodacyClient, ILogger)
- Follow xUnit conventions
- Use Theory/InlineData for parameterized tests
- Assert on return values and mock interactions

Generate:
- Test class with proper setup (constructor, mocks)
- At least 3 test cases per public method
- Use descriptive test names (MethodName_Scenario_ExpectedResult)
```

### Prompt for Integration Tests

```
Task: Generate integration tests for TeamsController

Context:
1. Review how we use WebApplicationFactory
2. Look at existing integration tests
3. Review our API response pattern (success/error format)

Requirements:
- Test all CRUD endpoints
- Use in-memory database
- Test both success and error scenarios
- Verify HTTP status codes
- Verify response structure
- Clean up data between tests

Generate:
- Test class inheriting from our base integration test class
- Tests for GET, POST, PUT, DELETE
- Negative test cases (not found, validation errors)
```

### Prompt for E2E Tests

```
Task: Generate E2E test for team management flow

Context:
1. Review MANUAL_REGRESSION_TESTING.md for user flows
2. Look at existing Playwright tests
3. Understand our authentication flow

Requirements:
- Test complete flow: Login → Create Team → View Team → Edit Team → Delete Team
- Use Page Object Model
- Handle authentication state
- Take screenshots on failure
- Use descriptive test names

Generate:
- Page object for Teams page
- E2E test covering the full flow
- Proper assertions at each step
```

---

## Step 3: Test Coverage as Quality Gate

**Define minimum coverage thresholds**:

* Unit Tests: 80% code coverage for service layer
* Integration Tests: All controller endpoints covered
* E2E Tests: All critical user journeys covered

**Use AI to verify**:

```
Prompt: "Review our test coverage and identify gaps.

Context:
- We aim for 80% coverage on service layer
- All controller endpoints should have integration tests
- Critical flows defined in MANUAL_REGRESSION_TESTING.md need E2E tests

Analysis:
1. List untested public methods in services
2. List API endpoints without integration tests
3. List critical flows without E2E tests

Generate:
- Tests for identified gaps
```

---

## Testing as First-Class Citizen

**Principle**: AI generates code AND tests in the same session.

**Workflow**:

1. Prompt: "Implement feature X following our patterns"
2. AI generates implementation
3. Prompt: "Now generate unit tests for this feature"
4. AI generates tests
5. Prompt: "Now generate integration tests"
6. AI generates integration tests
7. Verify: All tests pass

**Why**: Catches issues immediately, enforces quality, documents behavior.

---

## Key Takeaways

1. **Define pyramid early** - Create TEST_AUTOMATION_STRATEGY.md before coding
2. **60/30/10 split** - Unit (60%), Integration (30%), E2E (10%)
3. **AI generates tests** - Use prompts to generate tests at all layers
4. **Coverage thresholds** - Set minimums (e.g., 80% for service layer)
5. **Tests with code** - Generate tests in same session as implementation

---

## Reference

- Framework Source: `docs/ai-pod/common/accelerated-delivery-framework.md` (lines 419-551)
- Testing Strategy: `docs/TEST_AUTOMATION_STRATEGY.md`
- Testing Patterns: `.cursor/skills/testing-patterns/SKILL.md`
