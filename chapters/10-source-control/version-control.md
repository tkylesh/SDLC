# Version Control

## Overview
This document outlines the Git version control practices and standards at Trexis Systems, ensuring consistent and efficient code management across all projects.

## Git Fundamentals

### Basic Concepts
```markdown
Concept     | Description
------------|-------------
Repository  | Project's complete history
Commit      | Snapshot of changes
Branch      | Independent line of development
Tag         | Named reference to commit
Remote      | Hosted repository copy
```

### Core Operations
```markdown
Operation   | Command              | Usage
------------|---------------------|-------
Clone       | git clone url       | Get repository copy
Add         | git add files       | Stage changes
Commit      | git commit -m msg   | Save changes
Push        | git push origin br  | Upload changes
Pull        | git pull origin br  | Download changes
```

## Repository Structure

### Standard Layout
```
repository/
├── .git/
├── src/
│   ├── main/
│   └── test/
├── docs/
├── config/
├── scripts/
├── .gitignore
├── README.md
└── LICENSE
```

### Configuration Files
```markdown
File          | Purpose
--------------|----------
.gitignore    | Excluded files
.gitattributes| File handling
.gitconfig    | Git settings
.gitmodules   | Submodules
```

## Commit Standards

### Commit Message Format
```markdown
<type>(<scope>): <subject>

<body>

<footer>

Types:
- feat: New feature
- fix: Bug fix
- docs: Documentation
- style: Formatting
- refactor: Code restructure
- test: Testing
- chore: Maintenance
```

### Best Practices
1. **Message Guidelines**
   - Clear and concise
   - Present tense
   - Descriptive
   - Reference issues

2. **Content Guidelines**
   - Single responsibility
   - Complete feature/fix
   - Tested changes
   - Clean code

## History Management

### Log Management
```markdown
Command                     | Purpose
---------------------------|----------
git log --oneline          | Brief history
git log --graph           | Visual history
git log --author=name     | Author history
git log --since=date      | Date range
```

### History Cleanup
```markdown
Operation        | Command              | Use Case
-----------------|---------------------|----------
Amend           | git commit --amend  | Fix last commit
Rebase          | git rebase -i HEAD~n| Cleanup history
Cherry-pick     | git cherry-pick hash| Copy commits
Reset           | git reset --option   | Undo changes
```

## Tagging Conventions

### Tag Structure
```markdown
v<major>.<minor>.<patch>[-<stage>]

Examples:
- v1.0.0        # Major release
- v1.1.0        # Minor release
- v1.1.1        # Patch release
- v2.0.0-beta.1 # Beta release
```

### Tag Management
```markdown
Operation    | Command                  | Purpose
-------------|-------------------------|----------
Create       | git tag -a v1.0.0 -m "" | New tag
List         | git tag -l "v1.0.*"     | Show tags
Push         | git push origin v1.0.0  | Share tag
Delete       | git tag -d v1.0.0       | Remove tag
```

## Best Practices

### Version Control
1. **Repository Management**
   - Regular backups
   - Clean structure
   - Clear documentation
   - Access control

2. **Commit Practices**
   - Atomic commits
   - Clear messages
   - Regular commits
   - Clean history

### Common Pitfalls
1. **Avoid**
   - Large commits
   - Poor messages
   - Binary files
   - Sensitive data

2. **Ensure**
   - Regular pushes
   - Clean history
   - Good structure
   - Clear documentation

## Templates

### Commit Template
```markdown
# <type>(<scope>): <subject>
# |<----  Using a Maximum Of 50 Characters  ---->|

# Explain why this change is being made
# |<----   Try To Limit Each Line to a Maximum Of 72 Characters   ---->|

# Provide links or keys to any relevant tickets, articles or other resources
# Example: Resolves: #123
# See: #456, #789

# --- COMMIT END ---
# Type can be
#    feat     (new feature)
#    fix      (bug fix)
#    docs     (changes to documentation)
#    style    (formatting, missing semi colons, etc; no code change)
#    refactor (refactoring production code)
#    test     (adding missing tests, refactoring tests; no production code change)
#    chore    (updating grunt tasks etc; no production code change)
# --------------------
# Remember to
#    Capitalize the subject line
#    Use the imperative mood in the subject line
#    Do not end the subject line with a period
#    Separate subject from body with a blank line
#    Use the body to explain what and why vs. how
#    Can use multiple lines with "-" for bullet points in body
# --------------------
```

## Related Topics
- [Branch Management](branch-management.md)
- [Merge Procedures](merge-procedures.md)
- [Repository Standards](repository-standards.md)

## Navigation
- [Back to Source Control](README.md)
- [Back to Main](../../README.md)
