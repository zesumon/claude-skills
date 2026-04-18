# Code Analysis

Analyze the codebase or specific files for quality, complexity, and potential issues.

## Usage

```
/code/analyze [target]
```

## Arguments

- `target` (optional): File, directory, or glob pattern to analyze. Defaults to the entire project.

## What This Does

Performs a comprehensive analysis of the target code including:

1. **Complexity Analysis**
   - Cyclomatic complexity of functions/methods
   - Deeply nested logic that should be refactored
   - Functions that are too long or do too much

2. **Code Quality**
   - Duplicate or near-duplicate code blocks
   - Dead code (unused variables, functions, imports)
   - Magic numbers and hardcoded values
   - Inconsistent naming conventions

3. **Dependency Analysis**
   - Circular dependencies
   - Overly coupled modules
   - Missing or outdated dependencies

4. **Security Concerns**
   - Hardcoded secrets or credentials
   - Unsafe input handling
   - Common vulnerability patterns (SQLi, XSS, etc.)

5. **Performance Hints**
   - Inefficient loops or data structures
   - Unnecessary re-computation
   - Missing caching opportunities

## Output Format

Provide a structured report with:
- Summary of findings grouped by severity (critical / warning / info)
- Specific file and line references for each issue
- Brief explanation of why each item is flagged
- Suggested next steps or quick wins

Keep the tone constructive. Highlight what is done well before diving into issues.
