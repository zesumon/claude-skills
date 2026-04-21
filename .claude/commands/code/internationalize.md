# Internationalize (i18n)

Analyze and implement internationalization (i18n) and localization (l10n) for the codebase.

## Usage

```
/code/internationalize [target] [--locale <locale>] [--framework <framework>]
```

## Arguments

- `target` - File, directory, or component to internationalize (default: current directory)
- `--locale` - Target locale(s) to add support for (e.g., `fr`, `es`, `de`, `ja`)
- `--framework` - i18n framework to use (e.g., `react-i18next`, `vue-i18n`, `gettext`, `fluent`)
- `--extract` - Extract existing hardcoded strings into translation files
- `--audit` - Audit codebase for missing i18n coverage

## What This Command Does

1. **Audits** the codebase for hardcoded strings, dates, numbers, and currency values
2. **Extracts** translatable strings into locale resource files
3. **Refactors** source files to use i18n function calls
4. **Generates** translation file structure (JSON, PO, YAML, etc.)
5. **Handles** pluralization, interpolation, and locale-specific formatting
6. **Sets up** RTL (right-to-left) support if needed
7. **Validates** existing translation files for missing or unused keys

## Output

- Refactored source files using i18n APIs
- Translation resource files (e.g., `locales/en.json`, `locales/fr.json`)
- i18n configuration/setup file
- Summary report of extracted strings and coverage

## Examples

```
# Audit entire project for i18n coverage
/code/internationalize --audit

# Extract strings from a React component and set up react-i18next
/code/internationalize src/components/Header.tsx --framework react-i18next

# Add French and Spanish locale support
/code/internationalize src/ --locale fr --locale es --extract

# Internationalize a Python Flask app using Babel/gettext
/code/internationalize app/ --framework gettext --locale de
```

## Notes

- Preserves existing i18n setup if already configured
- Detects framework automatically if not specified
- Flags dynamic strings that may need special handling
- Suggests locale-aware formatting for dates, numbers, and currencies
- Checks for accessibility considerations (e.g., `lang` attribute in HTML)
