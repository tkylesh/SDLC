# Issue Relationships

## Overview

Understanding and maintaining proper relationships between different types of Jira issues is crucial for project organization and tracking. This document outlines the various types of relationships and best practices for managing them.

## Relationship Types

### Hierarchical Relationships

1. **Epic → Story**
   - Epics contain multiple stories
   - Stories implement epic features
   - Clear parent-child relationship

2. **Story → Task**
   - Stories break down into tasks
   - Tasks represent technical work
   - Direct implementation relationship

3. **Story → Sub-task**
   - Smaller units of work
   - Specific to parent story
   - Tracked separately

### Lateral Relationships

1. **Blocks/Blocked By**
   - Dependencies between issues
   - Prevents parallel work
   - Requires sequencing

2. **Related To**
   - Loose connections
   - Shared context
   - Information linking

3. **Duplicates/Duplicated By**
   - Identical issues
   - Consolidation needed
   - Version tracking

## Relationship Rules

### Must Have
- Every story links to an epic (if applicable)
- All tasks link to parent story
- Clear blocking relationships

### Should Have
- Related issue links
- Implementation dependencies
- Cross-reference links

### Nice to Have
- Context links
- Historical references
- Documentation links

## Best Practices

### Creating Relationships
1. Establish early
2. Document reasons
3. Keep updated
4. Review regularly

### Maintaining Relationships
1. Regular cleanup
2. Validate links
3. Update status
4. Remove obsolete

### Using Relationships
1. Track dependencies
2. Plan work
3. Measure progress
4. Report status

## Common Patterns

### Feature Development
```
Epic
  ├── User Story
  │     ├── Task
  │     ├── Task
  │     └── Sub-task
  └── User Story
        ├── Task
        └── Task
```

### Research Projects
```
Research Story
  ├── Related Story
  └── Blocking → Future Story
```

## Related Topics
- [Epics](epics.md)
- [User Stories](user-stories.md)
- [Tasks](tasks.md)
- [Research Stories](research-stories.md)

## Navigation
- [Back to Chapter](README.md)
- [Back to Main](../../README.md)
