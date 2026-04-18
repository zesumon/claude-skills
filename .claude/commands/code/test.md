# Generate Tests

Generate comprehensive tests for the specified code.

## Usage

```
/code:test [file or function]
```

## Instructions

Analyze the target code and generate tests following these steps:

1. **Identify what to test**
   - Public functions and methods
   - Edge cases and boundary conditions
   - Error handling paths
   - Integration points

2. **Test structure**
   - Use the project's existing test framework (pytest, unittest, jest, etc.)
   - Follow existing test file naming conventions
   - Group related tests in classes or describe blocks

3. **Coverage targets**
   - Happy path scenarios
   - Invalid inputs and error cases
   - Boundary values (empty, null, max/min)
   - Async behavior if applicable

4. **Output**
   - Place tests in the appropriate test directory
   - Mirror the source file structure
   - Include fixtures and mocks where needed
   - Add docstrings explaining what each test validates

## Example

```
/code:test src/auth/login.py
```

This will generate `tests/auth/test_login.py` with full coverage of the login module.
