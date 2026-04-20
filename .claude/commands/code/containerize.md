# Containerize

Containerize the application with Docker and optionally set up Docker Compose for multi-service orchestration.

## Usage

```
/code/containerize [target] [options]
```

## Arguments

- `target` - Application or service to containerize (default: current project)
- `options` - Additional flags:
  - `--compose` - Generate docker-compose.yml for multi-service setup
  - `--multi-stage` - Use multi-stage builds for smaller images
  - `--dev` - Include development-specific configuration
  - `--prod` - Optimize for production deployment
  - `--scan` - Run security scan on generated Dockerfile

## What This Does

1. **Analyzes project structure** to detect:
   - Runtime environment (Node, Python, Go, Java, etc.)
   - Dependencies and package managers
   - Build steps required
   - Exposed ports and environment variables
   - Static assets and volumes needed

2. **Generates Dockerfile** with:
   - Appropriate base image (official, minimal variant)
   - Proper layer caching order (deps before source)
   - Non-root user for security
   - Health check instructions
   - Multi-stage builds when beneficial

3. **Creates .dockerignore** to exclude:
   - node_modules, __pycache__, .venv
   - .git directory
   - Test files and docs
   - Local config overrides

4. **Optionally generates docker-compose.yml** with:
   - Service definitions
   - Network configuration
   - Volume mounts
   - Environment variable handling via .env
   - Dependency ordering (depends_on)

5. **Validates the output** by:
   - Checking Dockerfile syntax
   - Verifying base image exists
   - Confirming all COPY sources exist

## Examples

```
/code/containerize
/code/containerize --compose --multi-stage
/code/containerize --prod --scan
/code/containerize ./services/api --dev
```

## Output

- `Dockerfile` (or `Dockerfile.dev` / `Dockerfile.prod`)
- `.dockerignore`
- `docker-compose.yml` (if `--compose` flag used)
- Build and run instructions in the response
- Notes on any assumptions made and how to override them
