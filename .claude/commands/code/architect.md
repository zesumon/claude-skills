# Architect

Analyze the codebase and provide architectural recommendations, design patterns, and structural improvements.

## Usage

```
/code/architect [scope]
```

## What This Does

This command performs a deep architectural analysis of your codebase:

1. **Structure Analysis** - Reviews directory layout, module organization, and separation of concerns
2. **Dependency Mapping** - Identifies coupling, circular dependencies, and dependency flow
3. **Pattern Detection** - Recognizes existing design patterns and suggests improvements
4. **Scalability Assessment** - Evaluates how well the architecture scales with growth
5. **Recommendations** - Provides actionable refactoring suggestions with priorities

## Process

1. Scan the project structure and understand the tech stack
2. Map out component relationships and data flow
3. Identify architectural anti-patterns (god classes, tight coupling, etc.)
4. Evaluate adherence to SOLID principles
5. Suggest concrete improvements with trade-off analysis

## Output Format

### Current Architecture
- High-level overview of existing structure
- Key components and their responsibilities
- Data flow diagram (text-based)

### Issues Found
- Critical architectural problems
- Moderate concerns
- Minor improvements

### Recommendations
- Prioritized list of changes (High/Medium/Low)
- Estimated effort for each change
- Expected benefits

### Proposed Structure
- Suggested directory/module reorganization if needed
- New abstractions or interfaces to introduce

## Arguments

- `$ARGUMENTS` - Optional scope (e.g., `src/`, specific module name, or `full` for entire project)

If no scope provided, analyze the entire project.
