# Performance Analysis & Optimization

Analyze and optimize performance bottlenecks in your code.

## Usage
```
/code/performance [file or component] [--profile] [--benchmark]
```

## What This Does

This command performs a comprehensive performance analysis:

1. **Profiling** - Identifies CPU and memory hotspots
2. **Complexity Analysis** - Reviews algorithmic complexity (Big O)
3. **Database Queries** - Detects N+1 problems and missing indexes
4. **Caching Opportunities** - Suggests where caching would help
5. **Async/Concurrency** - Finds blocking operations that could be async
6. **Bundle Size** (frontend) - Analyzes import costs and tree-shaking
7. **Memory Leaks** - Identifies potential memory leak patterns

## Analysis Steps

- Read the target file(s) and understand the execution flow
- Identify the most expensive operations (loops, I/O, queries)
- Check for redundant computations that could be memoized
- Look for synchronous blocking calls in async contexts
- Review data structures — are the right ones being used?
- Suggest concrete, measurable improvements with expected gains

## Output Format

Provide a prioritized list of findings:

### 🔴 Critical (fix immediately)
- Issues causing significant slowdowns

### 🟡 Medium (fix soon)
- Inefficiencies worth addressing

### 🟢 Minor (nice to have)
- Small wins and micro-optimizations

For each finding include:
- **Location**: file + line number
- **Problem**: what's slow and why
- **Fix**: concrete code change
- **Impact**: estimated improvement

## Examples

```
/code/performance src/api/users.py
/code/performance src/components/DataTable.tsx --benchmark
/code/performance . --profile
```

## Notes
- Always measure before and after optimizing
- Premature optimization is the root of all evil — focus on real bottlenecks
- Readability > micro-optimizations unless perf is critical
