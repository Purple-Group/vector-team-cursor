---
name: capture-skill
description: Capture learnings, patterns, or workflows from the current conversation into a new or existing skill. Use when the user wants to save what was learned, discovered, or built during a conversation as a reusable skill for future sessions.
---

# Capture Skill from Conversation

Extract knowledge, patterns, and workflows from conversations and persist as reusable skills.

## When to Use
- User says "capture this as a skill" or "save this for next time"
- Useful workflow/pattern/domain knowledge emerged
- Update existing skill with new learnings
- Non-obvious steps, gotchas, or best practices discovered

## Capture Process

### 1. Identify What to Capture
Review for: workflows, domain knowledge, gotchas/fixes, patterns, decision rationale. Summarize and confirm before proceeding.

### 2. Decide Destination
- **New or existing?** If new: name it (lowercase, hyphens, max 64 chars)
- **Location:** Personal (`~/.cursor/skills/`) or project (`.cursor/skills/`)

### 3. Draft Content
**New skill:**
- Descriptive name + specific description (WHAT + WHEN, third person)
- Concise actionable instructions
- Concrete examples from conversation
- Utility scripts/commands used

**Update existing:**
- Read existing SKILL.md
- Integrate new learnings without duplication
- Preserve structure and voice

### 4. Distillation Guidelines
**Do:** Extract final working approach, generalize (use placeholders), include "why" for non-obvious steps, add context agent wouldn't know, keep under 500 lines

**Don't:** Include conversation artifacts, repeat known info, include overly specific details, verbose explanations where code suffices

### 5. Write and Verify
Create/update file → Verify <500 lines → Check description has trigger terms → Confirm with user

## Example
```markdown
---
name: debug-k8s-deployments
description: Debug Kubernetes deployment failures. Use when pods are failing to start.
---

# Debug K8s Deployments

1. Check status: `kubectl get pods -n <namespace> | grep -v Running`
2. Get events: `kubectl describe pod <pod> -n <namespace>`
3. Check logs: `kubectl logs <pod> -n <namespace> --previous`

**CrashLoopBackOff:** Check entrypoint, env vars, OOMKilled → increase memory  
**ImagePullBackOff:** Verify tag exists, check imagePullSecrets
```

## Edge Cases
- **Multiple topics:** Ask which to capture or suggest separate skills
- **Too small:** Suggest Cursor rule (`.cursor/rules/`) instead
- **Major rewrite:** Confirm restructure vs new skill
