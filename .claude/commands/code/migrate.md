# Migrate

Perform code migration analysis and execution for framework upgrades, API changes, or language version updates.

## Usage

```
/migrate [target] [options]
```

## Arguments

- `target` - Migration target (e.g., "python 3.12", "react 18", "fastapi 0.100")
- `options` - Additional flags like `--dry-run`, `--breaking-only`, `--auto-fix`

## What This Does

1. **Analyzes current codebase** for patterns that need migration
2. **Identifies breaking changes** between current and target version
3. **Generates migration plan** with prioritized steps
4. **Applies safe automatic fixes** where possible
5. **Flags manual intervention** points that need human review
6. **Updates dependencies** in requirements/package files
7. **Runs tests** after migration to verify correctness

## Migration Steps

### Phase 1: Discovery
- Scan all files for deprecated API usage
- Check dependency compatibility matrix
- Identify transitive dependency conflicts
- Estimate migration effort (low/medium/high)

### Phase 2: Planning
- Group changes by risk level
- Order changes to minimize breakage
- Identify rollback points

### Phase 3: Execution
- Apply mechanical/automated changes first
- Handle renamed imports and moved modules
- Update type annotations if applicable
- Modernize syntax where beneficial

### Phase 4: Validation
- Run existing test suite
- Check for runtime warnings
- Verify no regressions introduced

## Output Format

Provide a structured report:
- Summary of changes made
- Files modified (with diff)
- Items requiring manual review
- Recommended follow-up tasks

## Examples

```
/migrate python 3.12
/migrate django 5.0 --breaking-only
/migrate typescript 5.0 --dry-run
```
