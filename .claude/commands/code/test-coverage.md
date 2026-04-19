# Test Coverage Analysis

Analyze and improve test coverage for the codebase.

## Usage
```
/code:test-coverage [target] [threshold]
```

## Arguments
- `target` - File, directory, or module to analyze (default: entire project)
- `threshold` - Minimum coverage percentage to enforce (default: 80)

## What This Does

1. **Analyze Current Coverage**
   - Run existing test suite with coverage instrumentation
   - Identify uncovered lines, branches, and functions
   - Generate coverage report by file and module

2. **Identify Gaps**
   - Find untested public functions and methods
   - Highlight critical paths lacking coverage
   - Detect dead code vs genuinely untested code
   - Flag edge cases not covered (null inputs, error paths, boundaries)

3. **Generate Missing Tests**
   - Write unit tests for uncovered functions
   - Add edge case tests for partially covered code
   - Create integration tests for uncovered workflows
   - Follow existing test patterns and conventions in the project

4. **Coverage Report**
   - Show before/after coverage percentages
   - List files below threshold
   - Prioritize by risk (public API > internal helpers)

## Output Format

```
Coverage Summary:
  Before: XX%
  After:  XX% (projected)
  
Files below threshold (< $threshold%):
  - path/to/file.py: XX%
  
Generated tests saved to: tests/
```

## Notes
- Respects existing test framework (pytest, jest, mocha, etc.)
- Does not delete or modify existing tests
- Focuses on meaningful coverage, not just line count
