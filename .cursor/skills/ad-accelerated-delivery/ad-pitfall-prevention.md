# Pitfall Prevention

> Common pitfalls detection and prevention strategies.

---

## The 7 Common Pitfalls

### Pitfall 1: Skipping the Foundation

**Symptom**: Fast start, slow progress after 2-3 features. Lots of refactoring.

**Cause**: No architectural patterns defined. AI generates inconsistent code.

**Fix**: Stop. Invest 1 day in foundation:

* Create DESIGN_PATTERNS.md
* Create PROJECT_STRUCTURE.md
* Create ARCHITECTURE.md
* Refactor existing code to match patterns
* THEN continue development

**Prevention**: Always check for foundation docs before major work. Use `ad-foundation-setup` command if missing.

---

### Pitfall 2: Not Providing Context

**Symptom**: AI generates code that doesn't match your architecture. Lots of manual fixing.

**Cause**: Prompts like "Add feature X" without architectural context.

**Fix**: Always use the Context → Plan → Execute workflow.

**Prevention**: Every prompt must include:
- Read DESIGN_PATTERNS.md
- Read PROJECT_STRUCTURE.md
- Review similar existing features
- Plan before implementing

---

### Pitfall 3: Accepting AI Output Blindly

**Symptom**: Code works but feels wrong. Hard to maintain.

**Cause**: Not validating AI output against patterns.

**Fix**: Create a PR checklist:

* [ ] Follows DESIGN_PATTERNS.md
* [ ] Files in correct location per PROJECT_STRUCTURE.md
* [ ] Tests included
* [ ] Documentation updated

**Prevention**: Always review AI-generated code for:
- Pattern compliance
- Security issues (SQL injection, XSS, auth bypasses)
- Performance problems (N+1 queries, memory leaks)
- Correctness (edge cases, error handling)

---

### Pitfall 4: No Testing Strategy

**Symptom**: Features work in isolation, break when combined. Manual testing takes forever.

**Cause**: No testing pyramid defined. AI doesn't know what tests to generate.

**Fix**: Create TEST_AUTOMATION_STRATEGY.md early. Include in every prompt.

**Prevention**: 
- Define testing pyramid (60% unit, 30% integration, 10% E2E)
- Reference TEST_AUTOMATION_STRATEGY.md in every test generation prompt
- Set coverage thresholds (e.g., 80% for service layer)

---

### Pitfall 5: Paralysis by Analysis

**Symptom**: Long discussions, no progress. Waiting for "perfect" decisions.

**Cause**: Not distinguishing Type 1 (reversible) from Type 2 (hard to reverse) decisions.

**Fix**: Implement the "Immediate Call" rule. 15 minutes stuck → 5-minute decision → move.

**Prevention**:
- Distinguish Type 1 (reversible) vs Type 2 (hard to reverse) decisions
- Apply "Immediate Call" rule when stuck > 15 minutes
- Document decision and move forward
- Review async if needed

---

### Pitfall 6: Documentation Debt

**Symptom**: Fast initial progress, confusion when revisiting code. New team members lost.

**Cause**: Skipping documentation updates.

**Fix**: Documentation is part of "done":

* Code ✅
* Tests ✅
* Documentation ✅

AI can generate docs quickly. No excuse.

**Prevention**:
- Include documentation in every feature completion checklist
- Update README.md, ARCHITECTURE.md, API docs with every feature
- Create feature summary docs for complex features
- Use AI to generate documentation quickly

---

### Pitfall 7: Not Reviewing AI Code

**Symptom**: Subtle bugs, security issues, performance problems.

**Cause**: Trusting AI output without review.

**Fix**: Always review:

* Security: SQL injection, XSS, auth bypasses
* Performance: N+1 queries, memory leaks
* Correctness: Edge cases, error handling

**Tool**: Pull requests approval to mitigate or catch.

**Prevention**:
- Always review AI-generated code before accepting
- Check security, performance, correctness
- Use code review checklist
- Run tests and linters

---

## Prevention Checklist

Before completing any task, verify:

- [ ] Foundation docs exist (DESIGN_PATTERNS.md, PROJECT_STRUCTURE.md, ARCHITECTURE.md)
- [ ] Context → Plan → Execute workflow followed
- [ ] Code validated against patterns
- [ ] Tests generated per TEST_AUTOMATION_STRATEGY.md
- [ ] Decision made (not stuck in analysis)
- [ ] Documentation updated
- [ ] Code reviewed for security, performance, correctness

---

## Key Takeaways

1. **Foundation first** - Always check for foundation docs
2. **Context required** - Every prompt needs architectural context
3. **Validate output** - Review AI code before accepting
4. **Testing strategy** - Define pyramid early
5. **Decide and move** - Apply "Immediate Call" rule
6. **Document always** - Code + Tests + Docs = Done
7. **Review code** - Check security, performance, correctness

---

## Reference

- Framework Source: `docs/ai-pod/common/accelerated-delivery-framework.md` (lines 1078-1157)
- Common Pitfalls: Lines 1078-1157
- Prevention Strategies: Integrated throughout framework
