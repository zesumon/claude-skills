# Document Code

Generate comprehensive documentation for the specified code.

## Usage

```
/code/document [target]
```

## What This Does

Analyzes the target file or module and generates:
- Module/file-level docstrings
- Function and class docstrings
- Inline comments for complex logic
- Usage examples where appropriate
- Parameter and return type documentation

## Process

1. **Analyze** the target code structure
2. **Identify** undocumented or poorly documented elements
3. **Generate** appropriate docstrings following language conventions
4. **Add** inline comments for non-obvious logic
5. **Create** usage examples for public APIs

## Documentation Standards

- Python: Google-style or NumPy-style docstrings
- JavaScript/TypeScript: JSDoc format
- Follow existing project conventions if present
- Keep docs concise but complete

## Arguments

- `target`: File path, function name, or module to document (defaults to current file in context)

## Example

```
/code/document src/utils/parser.py
```

This will add or improve documentation throughout `parser.py` while preserving all existing logic.
