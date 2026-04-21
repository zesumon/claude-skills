# Lint & Code Style Command

Analyze and fix code style, formatting, and linting issues in the codebase.

## Usage

```
/code/lint [target] [--fix] [--strict]
```

## Arguments

- `target` (optional): File, directory, or glob pattern to lint. Defaults to current directory.
- `--fix`: Automatically fix fixable issues
- `--strict`: Enable stricter linting rules

## What This Does

1. **Detects linting tools** configured in the project (ESLint, Pylint, Flake8, Ruff, Prettier, Black, etc.)
2. **Runs linters** against the target files
3. **Reports issues** grouped by severity (error, warning, info)
4. **Auto-fixes** safe issues when `--fix` flag is provided
5. **Suggests configuration** improvements if no linting config is found

## Behavior

### Detection Priority
- Check for config files: `.eslintrc`, `pyproject.toml`, `.flake8`, `.prettierrc`, etc.
- Fall back to language-appropriate defaults if no config found
- Respect `.gitignore` and `.lintignore` patterns

### Output Format
```
File: src/components/Button.tsx
  Line 12:5  error    'unused' is defined but never used    no-unused-vars
  Line 24:1  warning  Line length exceeds 100 characters    max-len

File: src/utils/helpers.py  
  Line 8     error    E302 expected 2 blank lines           pycodestyle
  Line 15    warning  W291 trailing whitespace              pycodestyle

Summary: 2 errors, 2 warnings across 2 files
```

### Auto-fix Report
When `--fix` is used, report what was changed:
```
Fixed 3 issues in 2 files:
  - Removed trailing whitespace (2 files)
  - Added missing newline at EOF (1 file)
  
Remaining issues require manual attention:
  - 1 error in src/components/Button.tsx (unused variable)
```

## Language-Specific Tools

| Language | Primary Tool | Formatter |
|----------|-------------|----------|
| Python | Ruff / Flake8 / Pylint | Black / autopep8 |
| JavaScript/TypeScript | ESLint | Prettier |
| Go | golint / staticcheck | gofmt |
| Rust | clippy | rustfmt |
| CSS/SCSS | stylelint | Prettier |

## Configuration Suggestions

If no linting configuration is detected, suggest creating appropriate config files based on the project's language and framework.
