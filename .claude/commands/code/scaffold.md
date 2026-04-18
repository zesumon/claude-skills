# Scaffold

Generate boilerplate code and project structure for new components, modules, or features.

## Usage

```
/scaffold <type> <name> [options]
```

## Arguments

- `type`: What to scaffold (component, module, service, api, cli, test)
- `name`: Name of the thing being scaffolded
- `options`: Additional context or requirements

## What This Does

Analyzes your existing codebase to understand patterns and conventions, then generates consistent boilerplate that matches your project style.

## Process

1. **Detect patterns** — Scan existing files to understand naming conventions, file structure, import styles, and coding patterns
2. **Identify dependencies** — Find common dependencies and how they're used
3. **Generate structure** — Create files and directories following project conventions
4. **Wire up** — Add necessary imports, exports, and registrations
5. **Create tests** — Generate corresponding test files if tests exist in the project

## Output

For each scaffolded item, provide:
- List of files created with their paths
- Brief explanation of what each file does
- Any manual steps needed to complete the setup
- Relevant commands to run (install deps, run tests, etc.)

## Examples

```
/scaffold service UserAuthService with JWT support and refresh tokens
/scaffold api /users CRUD endpoints with pagination
/scaffold component DataTable with sorting and filtering
/scaffold module payments using Stripe
```

## Notes

- Match the existing code style exactly — indentation, quotes, semicolons
- Use the same testing framework already in the project
- Follow existing patterns for error handling and logging
- Don't add dependencies that aren't already in the project unless explicitly asked
