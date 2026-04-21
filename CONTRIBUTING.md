# Contributing to Dolibarr Constants

Thank you for helping document Dolibarr constants!

## Ways to contribute

### 1. Improve or add a description

The most useful contribution. If you know what a constant does:

1. Fork this repository
2. Open the relevant `constants/XX.0.0.json` file
3. Find the constant by name
4. Edit the `description` field with your explanation
5. Set `description_source` to `human_reviewed`
6. Submit a Pull Request

**Example:**
```json
"MAILING_LIMIT_SENDBYCLI": {
  "description": "Restricts the number of emails sent per session via the CLI script. A negative value disables CLI sending entirely.",
  "description_source": "human_reviewed"
}
```

### 2. Report an error

If a description is wrong or misleading:
- Open an [Issue](../../issues) with the constant name and the correction

### 3. Report a missing constant

If a constant is missing from the dataset:
- Open an [Issue](../../issues) with the constant name, the file and line where you found it

### 4. Flag a deprecated constant

If a constant no longer exists in a recent version:
- Open an [Issue](../../issues) or submit a PR setting `deprecated: true`

---

## JSON structure reference

Each constant follows this structure:

```json
"CONSTANT_NAME": {
  "name": "CONSTANT_NAME",
  "inferred_type": "string | int | bool | float | null",
  "default_value": "value or null",
  "module": "module name or null",
  "description": "Human readable description or null",
  "description_source": "wiki | ia_generated | human_reviewed | null",
  "occurrences": [
    {
      "usage_type": "define | getter | setter | conf_global",
      "file": "htdocs/path/to/file.php",
      "line": 42,
      "is_commented": false,
      "raw_context": "surrounding code lines"
    }
  ]
}
```

## Guidelines for descriptions

- Write in **English**
- Keep it **concise** (1-3 sentences)
- Mention **typical values** if relevant (e.g. `0=disabled, 1=enabled`)
- Mention the **Dolibarr version** if the constant was introduced or removed in a specific version
- Do **not** copy-paste from other sources without attribution

## Pull Request checklist

- [ ] JSON is valid (you can check with [jsonlint.com](https://jsonlint.com))
- [ ] Only `description` and `description_source` fields were modified
- [ ] `description_source` is set to `human_reviewed`
- [ ] One constant per PR is ideal, but batches are welcome

---

*This project is maintained by [DZProd](https://dzprod.net) and the Dolibarr community.*