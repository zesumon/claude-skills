# Dependency Management

Analyze and manage project dependencies, check for outdated packages, security vulnerabilities, and unused imports.

## Usage

```
/code:dependencies [action]
```

## Actions

- `audit` - Check for security vulnerabilities in dependencies
- `outdated` - List outdated packages with available updates
- `unused` - Find unused dependencies in the codebase
- `licenses` - Audit dependency licenses for compliance
- `graph` - Generate dependency graph visualization
- `update` - Safely update dependencies with compatibility checks

## What This Command Does

1. **Dependency Audit**
   - Scan all dependency files (package.json, requirements.txt, Gemfile, go.mod, etc.)
   - Check against known vulnerability databases (CVE, OSV, etc.)
   - Identify transitive/indirect dependency risks
   - Suggest patched versions or alternative packages

2. **Outdated Package Detection**
   - Compare installed versions against latest stable releases
   - Highlight breaking vs non-breaking updates
   - Group updates by severity (major, minor, patch)
   - Estimate update effort and risk

3. **Unused Dependency Cleanup**
   - Scan source files for actual import/require usage
   - Cross-reference with declared dependencies
   - Flag packages that can be safely removed
   - Detect dev dependencies accidentally in production

4. **License Compliance**
   - Identify licenses for all direct and transitive deps
   - Flag potentially incompatible licenses (GPL in proprietary, etc.)
   - Generate SBOM (Software Bill of Materials) summary

5. **Safe Update Strategy**
   - Run tests after each update to catch regressions
   - Suggest lockfile best practices
   - Recommend pinning strategies for stability

## Output Format

Provides:
- Prioritized list of issues (critical → low)
- Specific commands to fix each issue
- Risk assessment for each recommended change
- Summary table of dependency health

## Examples

```
/code:dependencies audit
/code:dependencies outdated
/code:dependencies unused
/code:dependencies licenses
```
