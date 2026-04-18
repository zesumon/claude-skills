# Debug

Analyze and debug issues in the codebase.

## Usage

```
/code/debug [file or error description]
```

## What this does

1. **Identifies the root cause** of the bug or error
2. **Traces execution flow** to find where things go wrong
3. **Suggests fixes** with clear explanations
4. **Adds defensive checks** to prevent similar issues
5. **Recommends tests** to catch regressions

## Instructions

When debugging:

- Look at the full stack trace if provided
- Check recent git changes that might have introduced the bug
- Identify edge cases that aren't being handled
- Consider race conditions, null/undefined values, type mismatches
- Look for off-by-one errors, incorrect assumptions
- Check environment-specific issues (dev vs prod configs)

For each identified issue:
1. Explain what the bug is and why it happens
2. Show the problematic code
3. Provide the fixed version
4. Explain what changed and why

If multiple issues are found, prioritize by severity.

## Arguments

- `$ARGUMENTS` — file path, error message, or description of the unexpected behavior
