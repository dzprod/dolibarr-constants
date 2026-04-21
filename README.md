# Dolibarr Constants — Community Reference

Comprehensive documentation of Dolibarr PHP constants, extracted from source
code and enriched by the community.

## What is this?

Dolibarr ERP has thousands of constants scattered across ~800 PHP files,
with no centralized documentation. This project fills that gap.

For each constant you'll find:
- Type (`string`, `int`, `bool`...)
- Default value
- Module it belongs to
- All occurrences in source code (file + line)
- Human description (wiki, IA-generated, or community-reviewed)

## Structure

```
constants/
  21.0.0.json   ← all constants for Dolibarr v21
  22.0.0.json
  23.0.0.json
versions.json   ← index of all available versions
```

## API

Every JSON file is directly consumable as a free API via GitHub raw:

```
# All constants for a given version
https://raw.githubusercontent.com/dzprod/dolibarr-constants/main/constants/21.0.0.json

# Index of available versions
https://raw.githubusercontent.com/dzprod/dolibarr-constants/main/versions.json
```


## How to contribute

See [CONTRIBUTING.md](CONTRIBUTING.md)

## How it was generated

- Phase 1 : PHP files fetched from Dolibarr GitHub (targeted directories)
- Phase 2 : AST parsing with [tree-sitter-php](https://github.com/tree-sitter/tree-sitter-php) — real AST, not regex
- Phase 3 : Descriptions enriched via Claude Haiku when absent from source code
- Commented-out constants are flagged `is_commented: true` and excluded from enrichment

## License

MIT