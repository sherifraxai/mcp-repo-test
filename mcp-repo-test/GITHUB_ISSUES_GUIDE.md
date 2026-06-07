# GitHub Issues Tracking Guide

This guide establishes a disciplined workflow for tracking work using GitHub issues. All AI dev agents must follow these practices to ensure clear progress tracking and milestone alignment.

---

## 1. Creating Issues

### When to Create an Issue
- **Start of New Work**: Create an issue before beginning any new feature, bug fix, or refactoring task
- **Bug Reports**: Document bugs as issues immediately when discovered
- **Feature Requests**: Log all planned features as issues
- **Epics/Milestones**: Break down large work into multiple issues under a single epic

### Issue Structure

#### Title (Required)
- **Format**: `[TYPE] Brief descriptive title`
- **Types**: `[FEATURE]`, `[BUG]`, `[REFACTOR]`, `[DOCS]`, `[CHORE]`, `[HOTFIX]`
- **Example**: `[FEATURE] Add user authentication system`
- Keep to 60 characters or less

#### Description (Required)
Include the following sections:

```
## Description
Brief overview of what needs to be done.

## Acceptance Criteria
- [ ] Specific, testable requirement 1
- [ ] Specific, testable requirement 2
- [ ] Specific, testable requirement 3

## Technical Notes
Any relevant technical context, dependencies, or architectural decisions.

## Related Issues
- Closes #XXX (if this resolves another issue)
- Relates to #YYY (if related but not directly closing)

## Estimation
- Story Points: N/A or estimate if using
- Complexity: Low / Medium / High
```

### Labels (Required)
Assign **at least one** of the following:
- **Status**: `not-started`, `in-progress`, `blocked`, `review`, `done`
- **Priority**: `priority-critical`, `priority-high`, `priority-medium`, `priority-low`
- **Type**: `type-feature`, `type-bug`, `type-docs`, `type-refactor`, `type-chore`
- **Category**: Based on your project (e.g., `backend`, `frontend`, `devops`, `security`)

### Milestone Assignment (Recommended)
- Link issues to a milestone if they're part of a planned release or sprint
- Use milestone names like: `v1.0.0`, `Sprint-1`, `Q2-2026`

---

## 2. During Development

### Linking Issues to Work

#### Commit Messages
Reference the issue in every commit:
```
git commit -m "[ISSUE-#123] Implement user authentication

- Add JWT token generation
- Implement login endpoint
- Add session management

Closes #123"
```

**Format**: 
- Start with `[ISSUE-#XXX]` where XXX is the issue number
- Use `Closes #XXX` or `Fixes #XXX` to auto-link on PR merge
- End commit messages with issue reference

#### Pull Requests
When creating a PR:
1. **Title**: Link the issue - `[ISSUE-#123] Implement user authentication`
2. **Description**: Include:
   ```
   ## Related Issue
   Closes #123
   
   ## Changes Made
   - Change 1
   - Change 2
   
   ## Testing
   How was this tested?
   ```
3. **Link the issue**: Use GitHub's "Link issues" feature in the PR sidebar

### Issue Status Updates
As work progresses:
1. **Starting Work**: Add `in-progress` label
2. **Blocking Issues**: Add `blocked` label + comment explaining why
3. **Review Phase**: Add `review` label when PR is submitted
4. **Completion**: Remove `in-progress`, add `done`

### Comments on Issues
- Post updates on progress
- Flag blockers immediately
- Link related PRs and commits
- Document decisions made during implementation

---

## 3. Closing Issues

### Closing Conditions
An issue is ready to close when:
- All acceptance criteria are met
- Code is reviewed and approved
- Tests pass (if applicable)
- PR is merged to main branch

### Closing Process
1. **Automatic**: Use `Closes #XXX` in PR to auto-close on merge
2. **Manual**: If closing manually, leave a comment explaining why and when
3. **Add `done` label**: Mark as complete before closing
4. **Comment with Proof**: Link to the PR/commit that resolved it

---

## 4. Milestone Management

### Milestone Lifecycle

#### Creation
- Create milestones for releases, sprints, or quarterly goals
- Example: `v1.0.0 - MVP`, `Sprint-1-Q2-2026`, `Security-Hardening`

#### Issue Assignment
- Assign related issues to the milestone during creation
- Review milestone issues weekly

#### Progress Tracking
- Monitor % of issues closed vs. total
- GitHub auto-calculates: `X% complete (N open / M closed)`
- Use milestones page to identify blockers

#### Completion
- Milestone is complete when all issues are closed
- Post a summary comment with:
  - Date completed
  - Key achievements
  - Known issues carried forward to next milestone

---

## 5. Best Practices for AI Agents

### Before Starting Work
- [ ] Check if a GitHub issue exists for the task
- [ ] If not, create one with full context
- [ ] Assign labels and milestone
- [ ] Post a comment: "Starting work" with start time

### During Work
- [ ] Update issue status in labels (add `in-progress`)
- [ ] Post progress updates as significant checkpoints
- [ ] If blocked, immediately add `blocked` label and explain
- [ ] Link commits and PRs to the issue

### After Completing Work
- [ ] Ensure PR is linked to the issue
- [ ] Add `review` label when PR is created
- [ ] Add `done` label when PR is merged
- [ ] Close the issue with a summary comment

---

## 6. Issue Templates (Quick Reference)

### Feature Issue
```
## Description
[What feature are we building?]

## Acceptance Criteria
- [ ] [Specific requirement 1]
- [ ] [Specific requirement 2]

## Technical Notes
[Any architectural or design considerations]
```

### Bug Issue
```
## Description
[What's broken?]

## Steps to Reproduce
1. [Step 1]
2. [Step 2]

## Expected Behavior
[What should happen]

## Actual Behavior
[What actually happens]

## Acceptance Criteria
- [ ] Bug is fixed
- [ ] No regression in related areas
```

---

## 7. Enforcement Checklist

Every time an AI agent starts working on a task:

- [ ] Is there a GitHub issue for this work? If no → CREATE ONE
- [ ] Does the issue have a clear description with acceptance criteria?
- [ ] Are appropriate labels assigned?
- [ ] Is the issue linked to a milestone?
- [ ] When starting work → Add `in-progress` label + comment
- [ ] During work → Commit messages reference issue #
- [ ] PR created → Link to issue, add `review` label
- [ ] Work done → PR merged, add `done` label, close issue

---

## 8. Communication Guidelines

### Issue Comments Should Include
- **Status updates**: "Completed X, moving to Y"
- **Blockers**: "@mention relevant team, explain blocker"
- **Time estimates**: "Estimated 2 more hours"
- **External links**: Links to docs, discussions, related code
- **Questions**: Clear, specific questions for clarification

### Avoid
- Vague comments like "working on it" with no detail
- Leaving issues in `in-progress` without updates for >24 hours
- Closing issues without clear proof of completion

---

## Summary

| When | Action |
|------|--------|
| **New Work** | Create issue with full context + labels |
| **Starting** | Add `in-progress` label + comment |
| **Coding** | Reference issue in every commit |
| **Stuck** | Add `blocked` label + explain |
| **PR Ready** | Create PR, link issue, add `review` label |
| **Merged** | Add `done` label, close issue |

---

**Last Updated**: June 7, 2026
