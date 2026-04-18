# Monitor

Analyze and set up monitoring, logging, and observability for the codebase.

## Usage

```
/code/monitor [target]
```

## What This Does

This command helps you implement comprehensive monitoring and observability:

1. **Log Analysis** - Review existing logging patterns and suggest improvements
2. **Metrics Identification** - Identify key metrics worth tracking
3. **Health Checks** - Implement health check endpoints or functions
4. **Error Tracking** - Set up structured error reporting
5. **Performance Monitoring** - Add timing and performance instrumentation
6. **Alerting Rules** - Suggest alerting thresholds and conditions

## Process

### Step 1: Audit Current State
- Scan for existing logging calls and patterns
- Check for any monitoring libraries already in use
- Identify gaps in observability coverage

### Step 2: Recommend Instrumentation
- Suggest appropriate logging levels (DEBUG, INFO, WARN, ERROR)
- Propose structured logging format (JSON where applicable)
- Identify critical code paths needing trace spans

### Step 3: Implement Improvements
- Add or improve log statements with context
- Instrument key functions with timing metrics
- Create health check endpoints if applicable
- Add correlation IDs for request tracing

### Step 4: Dashboard & Alerting Guidance
- Suggest metrics to visualize
- Recommend alert thresholds based on code logic
- Provide example queries for common monitoring tools

## Output

- Summary of current monitoring coverage
- List of changes made with explanations
- Recommended monitoring stack if none exists
- Example dashboard configuration snippets
- Runbook suggestions for common failure modes

## Examples

```
/code/monitor                    # Audit entire project
/code/monitor src/api/           # Focus on API layer
/code/monitor src/workers/job.py # Single file instrumentation
```

## Notes

- Prefers structured logging over plain string messages
- Avoids logging sensitive data (passwords, tokens, PII)
- Follows existing conventions in the codebase when present
- Suggests lightweight solutions before heavy APM tools
