# Optimize Code

Analyze and optimize the specified code for performance, memory usage, and efficiency.

## Usage

```
/code/optimize [file_or_function] [focus_area?]
```

## Arguments

- `file_or_function` - File path or specific function/class to optimize
- `focus_area` (optional) - Specific optimization target: `speed`, `memory`, `readability`, or `all` (default: `all`)

## What This Does

1. **Profile the code** - Identify bottlenecks and inefficient patterns
2. **Analyze complexity** - Check time and space complexity of algorithms
3. **Find quick wins** - Spot obvious inefficiencies (unnecessary loops, redundant calls, etc.)
4. **Suggest improvements** - Provide concrete refactored code snippets
5. **Benchmark estimate** - Estimate performance impact of suggested changes

## Optimization Checklist

### Speed
- [ ] Replace nested loops with vectorized operations where possible
- [ ] Cache expensive computations (memoization, `functools.lru_cache`)
- [ ] Use generators instead of building full lists when iterating
- [ ] Prefer built-in functions over manual implementations
- [ ] Avoid repeated attribute lookups inside loops

### Memory
- [ ] Use generators/iterators instead of lists for large datasets
- [ ] Release references to large objects when no longer needed
- [ ] Use `__slots__` for classes with many instances
- [ ] Prefer in-place operations where semantics allow

### Readability
- [ ] Extract complex logic into well-named helper functions
- [ ] Replace magic numbers with named constants
- [ ] Simplify conditional chains
- [ ] Remove dead code and unused imports

## Output Format

Provide:
1. Summary of findings with severity (high/medium/low)
2. Specific code changes with before/after examples
3. Explanation of why each change helps
4. Any trade-offs to be aware of
