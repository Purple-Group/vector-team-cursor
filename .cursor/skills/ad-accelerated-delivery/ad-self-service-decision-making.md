# Self-Service Decision Making

> Decision frameworks and rapid unblocking strategies for pod teams.

---

## The Mindset Shift

> **"We enabled ourselves and had the confidence to carry responsibilities for the calls we made."**

Traditional teams escalate blockers. AI pod teams unblock themselves.

---

## Decision Framework

### Type 1 Decisions (Reversible)

**Definition**: Decisions that can be easily reversed or changed later.

**Examples**:
- Choosing a UI component library (can swap later)
- Selecting a logging framework
- Choosing a date formatting library

**Process**:
- Make immediately
- Document in commit message
- Share in Slack/chat
- Move forward

### Type 2 Decisions (Hard to Reverse)

**Definition**: Decisions that are difficult or expensive to reverse.

**Examples**:
- Database schema design (migrations are painful)
- Authentication architecture
- Core architectural patterns

**Process**:
- Create decision document (ADR)
- Async review with team
- 24-hour feedback window
- Decide and move forward

**Key**: Keep moving. Perfect is the enemy of shipped.

---

## The "Immediate Call" Rule

> **"When we got stuck, we would immediately make a call and move."**

**Definition of "Stuck"**: Spending > 15 minutes without progress.

**Process**:

1. **Identify**: Recognize you're stuck
2. **Huddle**: 5-minute team discussion
3. **Decide**: Make the best call with available information
4. **Document**: Write down the decision and rationale
5. **Move**: Implement and move forward
6. **Review**: Flag for async review if needed

**Example**:

```
Stuck: Should we use Azure AD B2B or Multiple App Registrations?

Huddle: (5 minutes)
- Review both approaches
- Consider UX, complexity, timeline
- Check documentation

Decision: Multiple App Registrations
- Better UX (no guest invites)
- Clearer tenant isolation
- Slightly more DevOps work (acceptable)

Document: Update MULTI_DOMAIN_AUTH_SUMMARY.md with decision

Move: Start implementation

Review: Share decision in Slack for async feedback
```

---

## Self-Service Capabilities

### 1. Architecture Decisions

**Traditional**: Schedule meeting with architect, wait for approval  
**AI Pod**:

```
Prompt: "We need to decide between Repository Pattern and Direct ORM access.

Context:
- Review DESIGN_PATTERNS.md for our current patterns
- Consider: testability, maintainability, team experience

Provide:
1. Pros/cons of each approach
2. Recommendation based on our project context
3. Migration path if we change patterns later

Make a decision and document it."
```

**Confidence**: Document the decision, move forward, review with team async.

### 2. Technical Blockers

**Traditional**: Post in Slack, wait for senior dev, context switch  
**AI Pod**:

```
Prompt: "We're getting a circular dependency error in our DI container.

Context:
- TeamService depends on IRepositoryService
- RepositoryService depends on ITeamService

Research:
1. Common solutions to circular dependencies in .NET DI
2. Review our architecture to see if this indicates a design issue
3. Recommend refactoring or workaround

Implement the fix."
```

**Confidence**: Fix it, document why, ship it.

### 3. DevOps & Infrastructure

**Traditional**: Create DevOps ticket, wait days/weeks  
**AI Pod**:

```
Prompt: "We need to add environment variables for Azure AD configuration.

Context:
- Review existing docker-compose.yml
- Review appsettings.json structure
- Review env.example

Provide:
1. Environment variables needed
2. docker-compose.yml updates
3. Documentation updates (README.md)
4. Security best practices

Implement the changes."
```

**Confidence**: Implement, test locally, document, done.

### 4. Testing Gaps

**Traditional**: QA finds bugs, create tickets, wait for sprint  
**AI Pod**:

```
Prompt: "E2E test failing: Login button not clickable.

Debug:
1. Review Playwright test code
2. Review application login flow
3. Common Playwright timing issues

Fix:
1. Update test with proper waits
2. Add assertions for element visibility
3. Re-run test to verify

Document the fix in test comments."
```

**Confidence**: Debug, fix, verify, commit.

---

## The Pod Team Structure

**Size**: 2-3 people  
**Skills**: Full-stack generalists (T-shaped)  
**Tools**: AI (Claude, GitHub Copilot, etc.), existing documentation  
**Empowerment**: Make decisions, implement, review with team

**Roles** (fluid):

* **Driver**: Actively prompting AI, implementing changes
* **Navigator**: Reviewing AI output, suggesting improvements
* **Reviewer**: Validating against patterns, testing

**Rotation**: Roles rotate every 30-60 minutes to maintain focus.

---

## Empowered Decision-Making

**Framework**:

* **Type 1 decisions** (reversible): Make immediately, document, move
* **Type 2 decisions** (hard to reverse): Discuss, document, decide, move

**Process**:

* Type 1: Document in commit message, share in Slack
* Type 2: Create decision document (ADR), async review, 24-hour feedback window, decide

**Key**: Keep moving. Perfect is the enemy of shipped.

---

## Key Takeaways

1. **Distinguish Type 1 vs Type 2** - Reversible vs hard to reverse
2. **Immediate Call rule** - 15 min stuck → 5-minute decision → move
3. **Self-service mindset** - Use AI to unblock, don't wait
4. **Document decisions** - Write down rationale for future reference
5. **Move forward** - Progress > Perfect decision

---

## Reference

- Framework Source: `docs/ai-pod/common/accelerated-delivery-framework.md` (lines 553-708, 814-831)
- Self-Service Operations: Lines 553-708
- Empowered Decision-Making: Lines 814-831
