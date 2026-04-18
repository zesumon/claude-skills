# Deploy

Analyze the codebase and generate a comprehensive deployment plan with step-by-step instructions.

## Usage

```
/deploy [target?] [environment?]
```

## Arguments

- `target` (optional): Deployment target (e.g., `aws`, `gcp`, `azure`, `vercel`, `docker`, `k8s`)
- `environment` (optional): Target environment (e.g., `staging`, `production`, `dev`)

## What This Does

1. **Analyzes project structure** to detect framework, language, and dependencies
2. **Reviews existing configs** (Dockerfile, docker-compose, CI/CD files, package.json scripts)
3. **Identifies missing pieces** needed for deployment
4. **Generates deployment artifacts** appropriate for the target
5. **Provides step-by-step instructions** tailored to the environment

## Output

For each deployment target, provide:

### Pre-deployment Checklist
- Environment variables required
- Secrets that need to be configured
- Dependencies and services (databases, caches, queues)
- Build requirements

### Deployment Artifacts
Generate or review:
- `Dockerfile` if containerization is needed
- `docker-compose.yml` for local/staging
- CI/CD pipeline config (GitHub Actions, GitLab CI, etc.)
- Infrastructure-as-code if applicable
- Environment-specific config files

### Deployment Steps
Provide numbered, copy-paste ready commands for:
1. Building the application
2. Running tests
3. Building container/artifact
4. Pushing to registry/storage
5. Deploying to target
6. Verifying deployment health

### Rollback Plan
- How to revert if deployment fails
- Health check endpoints to monitor

## Examples

```
/deploy docker staging
/deploy k8s production
/deploy vercel
```

If no target is specified, detect from existing project files and suggest the most appropriate deployment strategy.