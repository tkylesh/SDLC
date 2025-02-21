# User Stories

## Definition

User stories represent well-defined, testable, deliverable functionality expressed in business terms and from the point-of-view of the business user.

## Story Format

```
As a [type of user],
I want to [perform some action],
So that [achieve some goal/value]
```

## Story States

1. **New**
   - Initial creation
   - Default status
   - Not yet prioritized

2. **Ready for Development**
   - Prioritized
   - Acceptance criteria defined
   - Dependencies identified

3. **In Progress**
   - Development started
   - Assigned to developer
   - Being actively worked on

4. **Ready for Review**
   - Development complete
   - Code review pending
   - Tests written

5. **Done**
   - Meets acceptance criteria
   - Passes all tests
   - Approved by stakeholders

## Required Components

### Core Elements
- Title
- Description
- Acceptance Criteria
- Priority Level
- Story Points/Estimate

### Optional Elements
- Attachments
- Links to related stories
- Technical notes
- Test cases

## Story Writing Guidelines

### DO
- Write from user's perspective
- Keep it simple
- Include acceptance criteria
- Make it testable

### DON'T
- Include technical details
- Make it too large
- Forget the business value
- Skip acceptance criteria

## Example Story

```markdown
Title: Save Search Results

As a policy administrator
I want to save my search results
So that I can refer back to them later

Acceptance Criteria:
1. Can save current search results
2. Can name saved searches
3. Can access saved searches
4. Can delete saved searches
5. Saved searches persist across sessions
```

## Related Topics
- [Epics](epics.md)
- [Tasks](tasks.md)
- [Issue Relationships](relationships.md)

## Navigation
- [Back to Chapter](README.md)
- [Back to Main](../../README.md)
