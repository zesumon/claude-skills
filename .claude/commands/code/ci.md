# CI/CD Pipeline Command

Analyze, configure, and troubleshoot CI/CD pipelines for the project.

## Usage

```
/code/ci [action] [target]
```

## Actions

- `analyze` - Review existing CI/CD configuration and suggest improvements
- `setup` - Generate CI/CD pipeline configuration for detected stack
- `debug` - Diagnose failing pipeline steps
- `optimize` - Reduce build times and improve pipeline efficiency
- `security` - Add security scanning steps to the pipeline

## What This Command Does

When invoked, Claude will:

1. **Detect the project stack** by examining package files, Dockerfiles, and existing configs
2. **Identify the CI platform** (GitHub Actions, GitLab CI, CircleCI, Jenkins, etc.)
3. **Perform the requested action**:

### For `analyze`:
- Review existing `.github/workflows/`, `.gitlab-ci.yml`, or equivalent
- Identify missing steps (tests, linting, security scans, deployment)
- Flag anti-patterns (hardcoded secrets, missing caching, redundant steps)
- Suggest parallelization opportunities

### For `setup`:
- Generate a complete pipeline config matched to the detected stack
- Include: lint → test → build → security scan → deploy stages
- Add dependency caching for faster builds
- Configure environment-specific deployments (staging/production)
- Set up branch protection rules recommendations

### For `debug`:
- Parse provided error logs or pipeline output
- Identify root cause of failures
- Suggest specific fixes with corrected config snippets

### For `optimize`:
- Add caching for package managers (npm, pip, cargo, etc.)
- Split long jobs into parallel steps
- Use matrix builds where appropriate
- Minimize Docker layer rebuilds

### For `security`:
- Add SAST scanning (CodeQL, Semgrep, Bandit)
- Add dependency vulnerability checks (Dependabot, Snyk, Safety)
- Add secrets scanning (truffleHog, gitleaks)
- Add container scanning if Docker is used

## Output Format

Provides:
- Complete, ready-to-use pipeline configuration files
- Inline comments explaining each step
- List of required secrets/environment variables to configure
- Estimated build time impact of changes

## Examples

```
/code/ci setup
/code/ci debug "Error: Process completed with exit code 1"
/code/ci optimize
/code/ci security
```
