# Accelerated Delivery Framework - Cursor Components Guide

**Last Updated**: 2026-02-05  
**Purpose**: Comprehensive guide for using Accelerated Delivery Framework components in Cursor

---

## Table of Contents

1. [Introduction](#introduction)
2. [Component Overview](#component-overview)
3. [Workflow Guides](#workflow-guides)
4. [Agent Usage](#agent-usage)
5. [Best Practices](#best-practices)
6. [Examples](#examples)
7. [Reference](#reference)

---

## Introduction

### What is the Accelerated Delivery Framework?

The Accelerated Delivery Framework enables AI pod teams to achieve **10-17x velocity increases** through:

1. **Foundation First**: Proper project structure and architectural patterns before code
2. **Mental Models**: Clear building blocks defined before execution
3. **Pattern Adherence**: Every prompt starts with architectural context and planning
4. **Shift-Left Testing**: Testing pyramid defined early, AI-generated tests at all layers
5. **Self-Service Model**: Empowered decision-making and rapid unblocking

### How Cursor Components Enable the Framework

This framework is implemented as Cursor components:

- **Agents**: Specialized personas for specific roles
- **Skills**: Reusable knowledge modules
- **Rules**: Always-applied constraints
- **Commands**: Reusable workflows

All components use the `ad-` prefix (Accelerated Delivery).

### Quick Start

1. **Foundation Setup**: Run `ad-foundation-setup` command
2. **Feature Development**: Use `ad-feature-implementation` command
3. **Test Generation**: Use `ad-generate-tests` command
4. **Pattern Review**: Use `ad-pattern-review` command

---

## Component Overview

### Agents (`.cursor/agents/`)

Specialized personas that activate based on triggers:

#### `ad-foundation-architect.md`
- **When**: Project setup, architecture decisions
- **Does**: Validates foundation exists before code
- **Use**: Before starting any major work

#### `ad-pattern-adherence-agent.md`
- **When**: Feature implementation, code generation
- **Does**: Ensures code follows established patterns
- **Use**: During code generation and before completion

#### `ad-testing-strategist.md`
- **When**: Test generation requests, feature completion
- **Does**: Generates comprehensive test suites
- **Use**: After implementing features

#### `ad-self-service-pod-lead.md`
- **When**: Blockers, architecture questions, stuck situations
- **Does**: Enables rapid decision-making and unblocking
- **Use**: When stuck > 15 minutes or need decisions

### Skills (`.cursor/skills/ad-accelerated-delivery/`)

Reusable knowledge modules:

- `SKILL.md` - Main entry point
- `ad-context-driven-development.md` - Context→Plan→Execute workflow
- `ad-pattern-selection.md` - Pattern selection and documentation
- `ad-foundation-setup.md` - Foundation setup guide
- `ad-testing-pyramid.md` - Testing strategy and generation
- `ad-self-service-decision-making.md` - Decision frameworks
- `ad-pitfall-prevention.md` - Common pitfalls and prevention
- `ad-team-collaboration.md` - Team dynamics and collaboration
- `ad-success-metrics.md` - Success measurement and ROI

### Rules (`.cursor/rules/`)

Always-applied constraints:

#### `ad-accelerated-delivery.mdc`
- Foundation-first principle
- Context→Plan→Execute workflow
- Pattern adherence requirements
- Testing requirements
- Documentation requirements
- Pitfall prevention checks
- Team collaboration reminders

### Commands (`.cursor/commands/`)

Reusable workflows:

- `ad-foundation-setup.md` - Interactive foundation setup
- `ad-feature-implementation.md` - Feature development workflow
- `ad-generate-tests.md` - Test generation workflow
- `ad-pattern-review.md` - Pattern compliance review
- `ad-create-adr.md` - Architecture Decision Record creation

---

## Workflow Guides

### Foundation Setup: Using `ad-foundation-setup` Command

**When to use**: Starting a new project or when foundation docs are missing

**Steps**:
1. Run command: `ad-foundation-setup`
2. Command checks for existing foundation docs
3. Guides creation of missing docs:
   - DESIGN_PATTERNS.md
   - PROJECT_STRUCTURE.md
   - ARCHITECTURE.md
   - TEST_AUTOMATION_STRATEGY.md
   - README.md
4. Validates foundation completeness
5. Guides team alignment

**Output**: Complete foundation with all required documents

---

### Feature Development: Using `ad-feature-implementation` Command

**When to use**: Implementing any new feature

**Steps**:
1. Run command: `ad-feature-implementation`
2. **Context Gathering**: Reads patterns, reviews similar features
3. **Planning**: Identifies layers, files, pattern alignment
4. **Implementation**: Follows plan, creates code
5. **Testing**: Generates tests per pyramid
6. **Verification**: Checks pattern compliance
7. **Documentation**: Updates relevant docs

**Output**: Complete feature with code, tests, and documentation

---

### Test Generation: Using `ad-generate-tests` Command

**When to use**: After implementing features or when tests are missing

**Steps**:
1. Run command: `ad-generate-tests`
2. Identifies what needs testing
3. Reviews TEST_AUTOMATION_STRATEGY.md
4. Determines test type (unit/integration/E2E)
5. Generates tests following patterns
6. Verifies coverage thresholds

**Output**: Test files with appropriate coverage

---

### Pattern Review: Using `ad-pattern-review` Command

**When to use**: Before merging code or when validating compliance

**Steps**:
1. Run command: `ad-pattern-review`
2. Reads DESIGN_PATTERNS.md and PROJECT_STRUCTURE.md
3. Reviews code/files
4. Checks compliance against checklist
5. Reports violations and suggests fixes

**Output**: Compliance report with violations and fixes

---

### Decision Making: Using `ad-create-adr` Command

**When to use**: When making Type 2 (hard to reverse) decisions

**Steps**:
1. Run command: `ad-create-adr`
2. Identifies decision context
3. Gathers alternatives considered
4. Documents decision and rationale
5. Records consequences
6. Saves ADR document
7. Shares for review (Type 2) or documents (Type 1)

**Output**: Architecture Decision Record document

---

## Agent Usage

### `ad-foundation-architect`: Project Setup Scenarios

**Scenario 1**: Starting new project
- Agent validates foundation doesn't exist
- Guides through foundation setup
- Ensures all docs created before code

**Scenario 2**: Architecture question
- Agent reviews existing architecture
- Validates against patterns
- Provides recommendations

**Scenario 3**: Structure validation
- Agent checks folder structure
- Validates against PROJECT_STRUCTURE.md
- Reports violations

---

### `ad-pattern-adherence-agent`: Code Generation Scenarios

**Scenario 1**: Feature implementation
- Agent reads DESIGN_PATTERNS.md first
- Validates file locations
- Checks pattern compliance before completion

**Scenario 2**: Code review
- Agent reviews generated code
- Checks against patterns
- Reports violations with fixes

**Scenario 3**: Refactoring
- Agent validates refactored code
- Ensures patterns maintained
- Verifies no regressions

---

### `ad-testing-strategist`: Test Generation Scenarios

**Scenario 1**: New feature tests
- Agent determines test types needed
- Generates unit, integration, E2E tests
- Verifies coverage thresholds

**Scenario 2**: Coverage gaps
- Agent identifies untested code
- Generates tests for gaps
- Improves coverage

**Scenario 3**: Test patterns
- Agent reviews existing tests
- Generates tests following patterns
- Ensures consistency

---

### `ad-self-service-pod-lead`: Decision-Making Scenarios

**Scenario 1**: Technical blocker
- Agent applies "Immediate Call" rule
- Researches solutions
- Implements fix and documents

**Scenario 2**: Architecture decision
- Agent classifies decision type
- Researches alternatives
- Creates ADR if Type 2

**Scenario 3**: Stuck situation
- Agent recognizes stuck > 15 minutes
- Triggers 5-minute decision process
- Makes decision and moves forward

---

## Best Practices

### When to Use Which Component

| Task | Component | When |
|------|-----------|------|
| Starting project | `ad-foundation-setup` command | New project or missing foundation |
| Implementing feature | `ad-feature-implementation` command | Any new feature |
| Generating tests | `ad-generate-tests` command | After implementation or coverage gaps |
| Reviewing code | `ad-pattern-review` command | Before merge or validation |
| Making decisions | `ad-create-adr` command | Type 2 decisions |
| Architecture questions | `ad-foundation-architect` agent | Setup or architecture needs |
| Pattern validation | `ad-pattern-adherence-agent` agent | During code generation |
| Test generation | `ad-testing-strategist` agent | Test needs |
| Unblocking | `ad-self-service-pod-lead` agent | Stuck or decisions needed |

### Combining Components Effectively

**Foundation Setup Flow**:
1. Use `ad-foundation-setup` command
2. `ad-foundation-architect` agent validates
3. Foundation ready for development

**Feature Development Flow**:
1. Use `ad-feature-implementation` command
2. `ad-pattern-adherence-agent` validates patterns
3. `ad-testing-strategist` generates tests
4. `ad-pattern-review` command validates compliance

**Decision-Making Flow**:
1. `ad-self-service-pod-lead` agent identifies need
2. Use `ad-create-adr` command for Type 2
3. Document and move forward

### Common Workflows and Patterns

#### Workflow 1: New Feature
```
1. ad-foundation-architect validates foundation
2. ad-feature-implementation command
3. ad-testing-strategist generates tests
4. ad-pattern-review command validates
5. Complete
```

#### Workflow 2: Quick Fix
```
1. ad-pattern-adherence-agent validates
2. Implement fix
3. ad-pattern-review command validates
4. Complete
```

#### Workflow 3: Architecture Decision
```
1. ad-self-service-pod-lead identifies decision
2. ad-create-adr command (if Type 2)
3. Document and implement
4. Complete
```

### Troubleshooting Guide

**Issue**: Foundation docs missing
- **Solution**: Run `ad-foundation-setup` command
- **Agent**: `ad-foundation-architect` will guide

**Issue**: Code doesn't follow patterns
- **Solution**: Run `ad-pattern-review` command
- **Agent**: `ad-pattern-adherence-agent` will validate

**Issue**: Tests missing or insufficient
- **Solution**: Run `ad-generate-tests` command
- **Agent**: `ad-testing-strategist` will generate

**Issue**: Stuck on decision
- **Solution**: `ad-self-service-pod-lead` applies "Immediate Call" rule
- **Command**: Use `ad-create-adr` for Type 2 decisions

---

## Examples

### Example 1: Setting Up Foundation

**User**: "I need to set up the foundation for my project"

**Command**: `ad foundation setup`

**Process**:
1. Command checks for existing docs
2. Guides creation of DESIGN_PATTERNS.md
3. Guides creation of PROJECT_STRUCTURE.md
4. Guides creation of ARCHITECTURE.md with diagrams
5. Guides creation of TEST_AUTOMATION_STRATEGY.md
6. Validates completeness

**Result**: Complete foundation ready for development

---

### Example 2: Implementing a Feature

**User**: "I need to add user authentication"

**Command**: `ad feature implementation`

**Process**:
1. Context: Reads DESIGN_PATTERNS.md, reviews auth patterns
2. Plan: Identifies layers (Controller, Service, Repository, Model, DTO)
3. Implement: Creates code following patterns
4. Test: Generates unit, integration, E2E tests
5. Verify: Checks pattern compliance
6. Document: Updates ARCHITECTURE.md, README.md

**Result**: Complete feature with tests and documentation

---

### Example 3: Generating Tests

**User**: "Generate tests for UserService"

**Command**: `ad generate tests`

**Process**:
1. Reviews TEST_AUTOMATION_STRATEGY.md
2. Reviews existing test patterns
3. Determines: Unit tests needed (service layer)
4. Generates tests with mocks
5. Verifies coverage (80% threshold)

**Result**: Comprehensive unit test suite

---

### Example 4: Pattern Review

**User**: "Review my code for pattern compliance"

**Command**: `ad pattern review`

**Process**:
1. Reads DESIGN_PATTERNS.md
2. Reads PROJECT_STRUCTURE.md
3. Reviews code files
4. Checks compliance checklist
5. Reports violations with fixes

**Result**: Compliance report with actionable fixes

---

## Reference

### Component Quick Reference

| Component | Type | Location | Purpose |
|-----------|------|----------|---------|
| ad-foundation-architect | Agent | `.cursor/agents/` | Foundation validation |
| ad-pattern-adherence-agent | Agent | `.cursor/agents/` | Pattern compliance |
| ad-testing-strategist | Agent | `.cursor/agents/` | Test generation |
| ad-self-service-pod-lead | Agent | `.cursor/agents/` | Decision-making |
| ad-accelerated-delivery | Skill | `.cursor/skills/` | Framework knowledge |
| ad-accelerated-delivery | Rule | `.cursor/rules/` | Always-applied constraints |
| ad-foundation-setup | Command | `.cursor/commands/` | Foundation setup |
| ad-feature-implementation | Command | `.cursor/commands/` | Feature development |
| ad-generate-tests | Command | `.cursor/commands/` | Test generation |
| ad-pattern-review | Command | `.cursor/commands/` | Pattern review |
| ad-create-adr | Command | `.cursor/commands/` | ADR creation |

### Links to Framework Source

- **Framework Document**: `docs/ai-pod/common/accelerated-delivery-framework.md`
- **Design Patterns**: `docs/DESIGN_PATTERNS.md`
- **Project Structure**: `docs/PROJECT_STRUCTURE.md`
- **Architecture**: `docs/ARCHITECTURE.md`
- **Testing Strategy**: `docs/TEST_AUTOMATION_STRATEGY.md`

### Key Framework Sections

- **Phase 1**: Strategic Planning & Mental Models (lines 51-165)
- **Phase 2**: Foundation Setup (lines 167-299)
- **Phase 3**: Pattern-Driven Development (lines 302-417)
- **Phase 4**: AI-Augmented Testing (lines 419-551)
- **Phase 5**: Self-Serviced Pod Team Operations (lines 553-708)
- **Critical Success Factors**: Lines 710-832
- **Master Prompt Template**: Lines 839-914
- **Common Pitfalls**: Lines 1078-1157
- **Team Dynamics**: Lines 1161-1234
- **Measuring Success**: Lines 1237-1271

---

## Getting Started Checklist

- [ ] Run `ad foundation setup` command
- [ ] Review foundation docs with team
- [ ] Agree on patterns
- [ ] Try `ad feature implementation` on a small feature
- [ ] Use `ad generate tests` to create tests
- [ ] Use `ad pattern review` to validate
- [ ] Read this guide for best practices

---

**Ready to accelerate your delivery?**  
Start with the foundation. The rest follows naturally.

**Questions?**  
Review the framework source document for detailed explanations of every principle.

---

**Last Updated**: 2026-02-05  
**Framework Version**: Based on Accelerated Delivery Framework v1.0
