# Changelog Generator

Generate a structured changelog from git history, commits, or code changes.

## Usage

```
/code/changelog [options]
```

## Arguments

- `$ARGUMENTS` - Optional: version tag, date range, or scope (e.g., `v1.2.0`, `since:2024-01-01`, `scope:auth`)

## What This Does

Analyzes git commit history and code changes to produce a well-structured changelog following [Keep a Changelog](https://keepachangelog.com) conventions.

## Process

1. **Gather commits** — Parse git log between tags or date ranges
2. **Categorize changes** — Group into Added, Changed, Deprecated, Removed, Fixed, Security
3. **Extract context** — Pull PR references, issue links, and author info
4. **Format output** — Generate Markdown following semver and changelog best practices
5. **Suggest version bump** — Recommend patch/minor/major based on change types

## Output Format

```markdown
## [Unreleased]

### Added
- New feature descriptions

### Changed
- Breaking or behavioral changes

### Fixed
- Bug fixes with issue references

### Security
- Vulnerability patches
```

## Options

- `--from <tag>` — Start from a specific git tag
- `--to <tag>` — End at a specific git tag (default: HEAD)
- `--format conventional` — Parse conventional commits strictly
- `--append` — Append to existing CHANGELOG.md instead of printing
- `--dry-run` — Preview without writing to file

## Notes

- Works best with conventional commit messages (`feat:`, `fix:`, `chore:`, etc.)
- Falls back to heuristic parsing for non-conventional histories
- Skips merge commits and version bump commits automatically
- Groups co-authored commits under primary author
