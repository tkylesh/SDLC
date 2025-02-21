# Acceptance Criteria

## Overview

Acceptance criteria define the conditions that must be met for a user story to be considered complete. They serve as the foundation for testing and validation, ensuring that development meets business requirements.

## Purpose

- Define completion requirements
- Guide development efforts
- Form test basis
- Set clear expectations
- Enable objective validation

## Structure

### Format Options

1. **Given-When-Then**
```markdown
Given [initial context]
When [action occurs]
Then [expected outcome]
```

2. **Scenario-Based**
```markdown
Scenario: [description]
  Given [precondition]
  When [trigger]
  Then [expected result]
```

3. **Checklist Style**
```markdown
- System must [requirement]
- User should be able to [action]
- Interface will [behavior]
```

## Writing Guidelines

### Characteristics
1. **Specific**
   - Clear conditions
   - Measurable outcomes
   - Defined boundaries

2. **Testable**
   - Verifiable results
   - Objective criteria
   - Clear pass/fail

3. **Complete**
   - All scenarios
   - Edge cases
   - Error conditions

4. **Consistent**
   - Standard format
   - Clear language
   - Common terminology

## Common Patterns

### Functional Requirements
```markdown
1. User Authentication
   - System validates username/password
   - Locks account after 3 failures
   - Provides password reset option

2. Data Entry
   - All required fields marked
   - Input validation rules
   - Error message display
```

### Performance Requirements
```markdown
1. Response Time
   - Page load under 3 seconds
   - Search results under 1 second
   - Report generation under 30 seconds

2. Concurrent Users
   - Support 100 simultaneous users
   - Maintain response times
   - No degradation
```

### User Interface Requirements
```markdown
1. Layout
   - Responsive design
   - Consistent navigation
   - Accessible elements

2. Feedback
   - Success messages
   - Error notifications
   - Progress indicators
```

## Validation Process

### Review Steps
1. Technical feasibility
2. Business alignment
3. Completeness check
4. Clarity assessment

### Approval Process
1. Developer review
2. QA review
3. Business review
4. Final sign-off

## Best Practices

### Writing
1. Be specific
2. Use active voice
3. Avoid technical jargon
4. Include all scenarios

### Review
1. Verify completeness
2. Check testability
3. Confirm clarity
4. Validate with stakeholders

### Maintenance
1. Version control
2. Change tracking
3. Update as needed
4. Keep synchronized

## Examples

### Good Example
```markdown
Feature: Password Reset

Scenario: User requests password reset
Given the user is on the login page
When they click "Forgot Password"
And enter their email address
Then they receive a reset link
And the link expires in 24 hours

Acceptance Criteria:
1. Reset link sent within 1 minute
2. Link valid for exactly 24 hours
3. Old password invalid after reset
4. Password requirements enforced
5. Audit log entry created
```

### Poor Example
```markdown
The system should handle password resets
```

## Related Topics
- [Requirements Clarification](clarification.md)
- [User Story Development](user-stories.md)
- [Testing Strategy](../testing/strategy.md)

## Navigation
- [Back to Project Flow](../README.md)
- [Back to Main](../../../README.md)
