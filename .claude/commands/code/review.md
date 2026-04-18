# Code Review

Perform a thorough code review of the specified files or recent changes.

## Usage

```
/code/review [files or scope]
```

## What This Does

Analyzes code for:
- **Bugs & Logic Errors**: Identify potential runtime errors, edge cases, and incorrect logic
- **Security Issues**: Flag common vulnerabilities (injection, XSS, insecure dependencies, etc.)
- **Performance**: Spot inefficiencies, unnecessary re-renders, N+1 queries, memory leaks
- **Code Style**: Consistency with existing patterns and conventions in the codebase
- **Maintainability**: Overly complex functions, missing error handling, unclear naming
- **Test Coverage**: Note untested paths or missing edge case tests

## Instructions

1. If `$ARGUMENTS` is provided, review those specific files or the described scope
2. Otherwise, review all files changed since the last commit (`git diff HEAD`)
3. For each issue found, provide:
   - **Severity**: `critical` / `warning` / `suggestion`
   - **Location**: file + line number
   - **Description**: what the issue is and why it matters
   - **Fix**: concrete suggestion or code snippet
4. Summarize findings at the end with a count per severity level
5. If no issues are found, say so clearly — don't invent problems

## Arguments

`$ARGUMENTS` — optional: file paths, glob patterns, or a description like "the auth module"
