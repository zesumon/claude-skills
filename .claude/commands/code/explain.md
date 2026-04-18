# Explain Code

Explain the provided code or file in clear, accessible terms.

## Usage

```
/code/explain [target]
```

## What This Does

Provides a thorough explanation of code including:
- High-level purpose and what problem it solves
- How it works step by step
- Key concepts, patterns, and algorithms used
- Dependencies and external interactions
- Edge cases and important assumptions
- Potential gotchas or non-obvious behavior

## Instructions

1. Read the target file or code snippet provided
2. Identify the language, framework, and context
3. Start with a 1-2 sentence summary of what the code does
4. Break down the logic section by section
5. Highlight any design patterns (e.g. factory, observer, singleton)
6. Call out any clever tricks or non-obvious implementations
7. Note any potential issues or areas of concern
8. Suggest docs or references if helpful

## Output Format

### Summary
One paragraph overview of what this code does and why it exists.

### Breakdown
Section-by-section walkthrough of the logic.

### Key Concepts
Bullet list of important patterns, algorithms, or techniques used.

### Gotchas
Anything that might trip someone up when reading or modifying this code.

## Arguments

- `target` — file path, function name, or pasted code block to explain
