# Environment Setup

## Overview

Proper environment setup is crucial for development success. This document outlines the process of provisioning and configuring development environments at Trexis.

## Environment Types

### M Environments (Triple Environments)
Used for large projects impacting both website and AS400:

```markdown
1. Development (MxD1)
   - AS400: MxD1 library
   - Website: devx.alfapolicy.com
   - Database: DC-4SQLMOT0x

2. QA/SIT (MxQ1)
   - AS400: MxQ1 library
   - Website: qax.alfapolicy.com
   - Database: DC-4SQLMOT0x

3. Model Office (Mx)
   - AS400: Mx library
   - Website: motx.alfapolicy.com
   - Database: DC-4SQLMOT0x

Where x = 1 to 7
```

### AS/SIT Environments
For application support with web and AS400 components:

```markdown
- AS400: ASx library
- Website: asx.trexis.com
- Database: DC-4SQLSIT0x
Where x = 1 to 6
```

### QA Environments
For AS400-only application support:

```markdown
- Multiple QA libraries
- No web interaction
- Claims reserved (QA20, QA21)
```

## Environment Selection

### Criteria
1. Project type
2. Components needed
3. Timeline requirements
4. Resource availability

### Process
1. Check availability
2. Reserve environment
3. Update tracking
4. Notify team

## Setup Process

### 1. Infrastructure Setup
```markdown
1. Environment Selection
   - Check availability
   - Reserve environment
   - Update tracking

2. Access Configuration
   - User permissions
   - Network access
   - VPN setup
   - Security groups

3. Tool Configuration
   - Development tools
   - Build tools
   - Test frameworks
   - Monitoring tools
```

### 2. Source Control Setup
```markdown
1. Repository Access
   - Clone repositories
   - Branch setup
   - Permission config

2. Branch Strategy
   - Feature branches
   - Development branch
   - Release branches
```

### 3. Database Setup
```markdown
1. Database Access
   - Connection strings
   - User permissions
   - Initial data

2. Schema Management
   - Version control
   - Migration scripts
   - Backup strategy
```

## Environment Management

### Documentation
1. **Environment Details**
   - Access information
   - Configuration
   - Dependencies
   - Contacts

2. **Usage Guidelines**
   - Best practices
   - Restrictions
   - Shared resources
   - Maintenance windows

3. **Support Information**
   - Contact details
   - Escalation path
   - Common issues
   - Troubleshooting

### Maintenance
1. **Regular Tasks**
   - Updates
   - Backups
   - Cleanup
   - Monitoring

2. **Issue Resolution**
   - Problem tracking
   - Resolution process
   - Communication
   - Documentation

## Best Practices

### Environment Usage
1. Regular cleanup
2. Resource monitoring
3. Documentation updates
4. Security compliance

### Shared Resources
1. Coordination
2. Communication
3. Resource scheduling
4. Conflict resolution

### Security
1. Access control
2. Data protection
3. Audit logging
4. Compliance checks

## Environment Tracking

### Confluence Page
```markdown
Environment Status Page:
https://alfainsco.atlassian.net/wiki/spaces/SD/pages/3412540/Development+Environments

Update Instructions:
1. Position cursor
2. Click + for "add more content"
3. Select "Jira Issue/Filter"
4. Search and select issue
5. Use @ for developer names
6. Click Publish
```

### Required Updates
1. Jira issue assignment
2. Developer/tester names
3. Environment status
4. Timeline information

## Related Topics
- [Code Development](coding-standards.md)
- [Unit Testing](unit-testing.md)
- [Code Review](code-review.md)

## Navigation
- [Back to Project Flow](../README.md)
- [Back to Main](../../../README.md)
