# Security Audit

Perform a comprehensive security audit of the specified code.

## Usage

```
/code/security [file_or_directory]
```

## What This Does

Analyzes code for common security vulnerabilities and provides actionable fixes.

## Security Checks

### Input Validation
- SQL injection vulnerabilities
- XSS (Cross-Site Scripting) risks
- Command injection possibilities
- Path traversal issues
- Unvalidated redirects

### Authentication & Authorization
- Hardcoded credentials or secrets
- Weak password policies
- Missing authentication checks
- Privilege escalation risks
- Insecure session management

### Data Exposure
- Sensitive data in logs
- Unencrypted sensitive fields
- Overly verbose error messages
- Exposed API keys or tokens
- PII handling issues

### Dependencies
- Known vulnerable packages
- Outdated dependencies with CVEs
- Unnecessary permissions

### Cryptography
- Weak hashing algorithms (MD5, SHA1)
- Insecure random number generation
- Hardcoded encryption keys
- Improper certificate validation

## Output Format

For each issue found:
- **Severity**: Critical / High / Medium / Low
- **Location**: File and line number
- **Description**: What the vulnerability is
- **Impact**: What an attacker could do
- **Fix**: Concrete code change to resolve it

## Instructions

Review the target `$ARGUMENTS` for all security issues listed above. Prioritize findings by severity. For each issue provide a specific, copy-pasteable fix. If no issues are found in a category, briefly confirm it was checked. End with a summary score and top 3 recommended actions.
