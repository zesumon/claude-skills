# Accessibility Audit & Remediation

Analyze code for accessibility issues and implement WCAG compliance improvements.

## Usage
```
/code/accessibility [target] [--level AA|AAA] [--framework react|vue|angular|html]
```

## What This Does

Performs a comprehensive accessibility audit of your UI code and provides actionable fixes:

1. **WCAG Compliance Check** — Evaluates against WCAG 2.1 AA or AAA standards
2. **Semantic HTML** — Ensures proper use of landmarks, headings, and HTML5 elements
3. **ARIA Attributes** — Validates aria-label, aria-describedby, roles, and states
4. **Keyboard Navigation** — Checks focus management, tab order, and keyboard traps
5. **Color & Contrast** — Identifies contrast ratio violations
6. **Screen Reader Support** — Reviews alt text, form labels, and announcements
7. **Motion & Animation** — Checks for prefers-reduced-motion support
8. **Auto-fix Generation** — Produces corrected code snippets for each issue

## Process

### Phase 1: Static Analysis
- Parse component tree and identify interactive elements
- Check for missing or incorrect ARIA roles and properties
- Validate heading hierarchy (h1 → h2 → h3 order)
- Detect images missing alt attributes
- Find form inputs without associated labels

### Phase 2: Interaction Patterns
- Review focus indicators and `:focus-visible` styles
- Check modal/dialog focus trapping implementation
- Validate skip navigation links
- Assess custom widget keyboard patterns (combobox, listbox, tree)

### Phase 3: Output Report
For each issue found:
- **Severity**: Critical / Serious / Moderate / Minor
- **WCAG Criterion**: e.g., 1.1.1 Non-text Content
- **Location**: File, line number, component name
- **Issue Description**: Clear explanation of the problem
- **Remediation**: Exact code fix with before/after comparison
- **Testing Hint**: How to verify the fix with assistive technology

## Example Output

```
🔍 Accessibility Audit Results
================================
Files scanned: 12 | Issues found: 8 | Critical: 2 | Serious: 3

[CRITICAL] Missing alt text — src/components/Hero.jsx:14
  Criterion: 1.1.1 Non-text Content
  Fix: Add descriptive alt attribute to <img> element

[SERIOUS] Low contrast ratio (2.4:1) — src/styles/Button.css:22
  Criterion: 1.4.3 Contrast (Minimum)
  Required: 4.5:1 for normal text
  Fix: Change color from #999 to #767676 or darker
```

## Arguments

- `target` — File, directory, or component to audit (defaults to `src/`)
- `--level` — WCAG conformance level: `AA` (default) or `AAA`
- `--framework` — UI framework hint for context-aware analysis
- `--fix` — Automatically apply safe, non-breaking fixes
- `--report` — Generate a full HTML/JSON report file
