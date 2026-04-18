# Refactor Code

Analyze and refactor the specified code for improved readability, maintainability, and performance.

## Usage

```
/code/refactor [file_or_selection] [--focus=readability|performance|structure]
```

## What This Does

1. **Analyzes** the target code for:
   - Code smells and anti-patterns
   - Duplicate logic that can be extracted
   - Overly complex functions (high cyclomatic complexity)
   - Poor naming conventions
   - Missing type hints or docstrings

2. **Refactors** by:
   - Extracting reusable functions/classes
   - Simplifying nested conditionals
   - Improving variable/function naming
   - Adding type hints where missing
   - Splitting large functions into smaller focused ones

3. **Validates** the refactor:
   - Ensures behavior is preserved
   - Runs existing tests if available
   - Highlights any edge cases to verify manually

## Arguments

- `file_or_selection`: Path to file or describe the code section to refactor
- `--focus`: Optional focus area (default: general)
  - `readability`: Prioritize clarity and naming
  - `performance`: Prioritize speed and efficiency
  - `structure`: Prioritize architecture and separation of concerns

## Output

Provides a diff-style view of changes with explanations for each modification.

$ARGUMENTS
