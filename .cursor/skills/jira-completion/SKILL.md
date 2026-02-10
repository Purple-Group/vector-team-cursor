---
name: jira-completion
description: Add completion comments to JIRA tickets and transition status to Done. Use when marking tickets as complete, after PR merge, or when user requests to mark a JIRA ticket as done.
---

# JIRA Completion

Adds a completion comment to JIRA tickets and transitions them to "Done" status using Atlassian MCP tools.

## Quick Start

When user requests to mark a JIRA ticket as done:

1. Extract ticket key from context (branch name, conversation, or user input)
2. Get current ticket status and available transitions
3. Add completion comment using standard format
4. Transition ticket to "Done" status

## Workflow

### Step 1: Get Ticket Information

```javascript
const cloudId = "5de05e21-8394-4dd6-ba72-832fec1cf6d5";
const ticketKey = "DFG-155"; // Extract from context

// Get current ticket details
const issue = await mcp_atlassian_getJiraIssue(cloudId, ticketKey);
```

### Step 2: Get Available Transitions

```javascript
// Get available transitions from current status
const transitions = await mcp_atlassian_getTransitionsForJiraIssue(cloudId, ticketKey);
```

### Step 3: Find "Done" Transition

Look for transitions that lead to "Done" status. Common transition names:
- "Done"
- "Mark as Done"
- "Close Issue"
- "Resolve Issue"

Select the transition with `to.name` matching "Done" or similar.

### Step 4: Add Completion Comment

Use Markdown format (for API/MCP):

```markdown
## ✅ Implementation Complete

[Brief summary of what was accomplished]

### Summary:
- Key achievement 1
- Key achievement 2
- Key achievement 3

### Pull Request:
- [PR #X](https://github.com/.../pull/X) - Merged

### Status:
Task completed and ready for production.
```

**Add comment:**
```javascript
await mcp_atlassian_addCommentToJiraIssue(
  cloudId,
  ticketKey,
  commentBody // Markdown format
);
```

### Step 5: Transition to Done

```javascript
// Find transition ID for "Done"
const doneTransition = transitions.find(t => 
  t.to.name.toLowerCase().includes("done")
);

if (doneTransition) {
  await mcp_atlassian_transitionJiraIssue(
    cloudId,
    ticketKey,
    { id: doneTransition.id.toString() }
  );
}
```

## Comment Template

Use this template for completion comments:

```markdown
## ✅ Implementation Complete

[One-paragraph summary of the work completed]

### Summary:
- [Key deliverable 1]
- [Key deliverable 2]
- [Key deliverable 3]

### Pull Request:
- [PR #X](https://github.com/Purple-Group/donate-for-good-admin/pull/X) - [Status]

### Key Files:
- [File1.cs](link) - [Description]
- [File2.cs](link) - [Description]

### Status:
Task completed successfully and ready for production.
```

## Error Handling

### No "Done" Transition Available

If no transition to "Done" is available:
1. List available transitions to user
2. Suggest appropriate next step based on workflow
3. Do not force transition

### Transition Fails

If transition fails:
1. Check if ticket has required fields (sprint, fix version)
2. Inform user of missing requirements
3. Offer to add required fields first

## Examples

### Example 1: Simple Completion

**Input:** "Mark DFG-155 as done"

**Actions:**
1. Get ticket DFG-155
2. Add completion comment
3. Transition to Done

### Example 2: Completion with PR Link

**Input:** "DFG-155 is complete, PR #15 merged"

**Actions:**
1. Extract ticket key: DFG-155
2. Extract PR number: #15
3. Add comment with PR link
4. Transition to Done

## Notes

- **Cloud ID:** Always use `5de05e21-8394-4dd6-ba72-832fec1cf6d5` for Purple Group Atlassian instance
- **Comment Format:** Use Markdown for API/MCP calls (not Wiki Markup)
- **Transition Discovery:** Always check available transitions before attempting transition
- **Status Check:** Verify current status before transitioning to avoid errors
