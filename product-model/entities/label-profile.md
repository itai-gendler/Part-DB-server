---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Entity/LabelSystem/LabelProfile.php"
    }
  ],
  "domain": "label-profiles",
  "relations": [
    {
      "entity": "attachment",
      "verb": "has",
      "cardinality": "one-to-many"
    }
  ]
}
---

# Label profile

A saved label-option set with a name and selection information.

## Information kept

- **Name** — The profile name.
- **Comment** — The profile comment.
- **Options** — The saved label-generation options.
- **Show in dropdown** — Whether this profile is offered in profile selections.
- **Preview attachment** — The selected preview attachment.
- **Added at** — When this record was added.
- **Modified at** — When this record was last modified.
