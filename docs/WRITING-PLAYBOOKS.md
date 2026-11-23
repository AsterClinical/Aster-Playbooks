# Write your own Playbook

Start by copying an example from [`examples/`](../examples/). Use Notepad, VS Code, or another plain-text editor and save the file as **UTF-8** with the **`.asterplaybook`** extension.

## 1. Minimal Playbook

```json
{
  "format": "aster-playbook",
  "schema_version": 1,
  "title": "Synthetic example: visit documents",
  "description": "General document reminder; for demonstration only.",
  "author": "Aster Clinical contributors",
  "version": "1.0",
  "actions": [
    {
      "type": "advice.add_lines",
      "lines": [
        "Bring previous prescriptions and available reports to your next visit."
      ]
    }
  ]
}
```

`format`, `schema_version`, `title`, and `actions` are required. `description`, `author`, and `version` are optional. Aster processes Actions in the order listed.

## 2. The two supported Actions

**Add investigations** (catalogue keys are defined by the installed version of Aster):

```json
{
  "type": "investigations.add",
  "items": [
    { "catalogue_key": "cbc" },
    { "catalogue_key": "creatinine" },
    { "manual_name": "Synthetic manual test (example only)", "note": "Demonstration entry" }
  ]
}
```

Each investigation uses **either** `catalogue_key` **or** `manual_name`, never both. Optional details: `specimen`, `preparation`, `timing`, `note`. A catalogue key must be recognized by the installed Aster; the displayed name is obtained from Aster's own catalogue.

**Add advice lines:**

```json
{
  "type": "advice.add_lines",
  "lines": [
    "Bring your existing reports to the next visit.",
    "Contact your clinician if you have concerns before the scheduled review."
  ]
}
```

Aster appends advice without repeating matching lines. It never removes existing advice. It will not add the same investigation twice. A difference in investigation details requires explicit conflict resolution.

## 3. Format essentials

| Item | Limit or rule |
| --- | --- |
| Encoding | UTF-8 JSON, optional UTF-8 BOM |
| Size | At most 64 KB |
| `schema_version` | Exactly integer `1` for PLAYBOOK.1 |
| `title` | 1–120 characters |
| `description` | Up to 2,000 characters |
| `author` | Up to 120 characters |
| `version` | Up to 32 characters |
| `actions` | 1–20 Actions |
| Entries | Up to 40 per Action and 100 total |
| Advice lines | Up to 300 characters per line |

Unknown properties, unsupported Actions, duplicate JSON keys, invalid Unicode/control characters and malformed values are rejected. `description` may contain line breaks; ordinary fields should be single-line strings. Complex JSON is unnecessary: stay within five nesting levels.

### Common mistakes

- Saving as `.asterplaybook.txt` instead of `.asterplaybook`.
- Using an unknown `catalogue_key` or `type`.
- Adding unsupported Actions such as `medicines.add` or `shell.run`.
- Repeating an advice line or an investigation item in the same Playbook.
- Writing patient-specific findings, real patient names, identifiers, or prescriptive treatment regimens in a shared example.

## 4. Test before sharing

1. Check JSON syntax, for example: `python -m json.tool your-file.asterplaybook` (**syntax only**, not Aster schema validation).
2. Import into Aster Desktop and correct any validation error.
3. Preview on a **synthetic visit**. Check duplicate handling, preparation conflicts and the after-preview text.
4. Cancel once to confirm there are no changes. Only then consider applying and checking the resulting unsaved document.

Aster PLAYBOOK.1 handles only investigations and advice; other Actions will need a future schema version and application support.
