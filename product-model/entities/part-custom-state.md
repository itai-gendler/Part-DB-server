---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Entity/Parts/PartCustomState.php"
    }
  ],
  "domain": "part-custom-states",
  "relations": [
    {
      "entity": "part-custom-state",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "part",
      "verb": "classifies",
      "cardinality": "one-to-many"
    },
    {
      "entity": "parameter",
      "verb": "has",
      "cardinality": "one-to-many"
    },
    {
      "entity": "attachment",
      "verb": "has",
      "cardinality": "one-to-many"
    }
  ]
}
---

# Part custom state

A hierarchical part custom state record with its own classification information, attachments and parameters.

## Information kept

- **Name** — The structural record’s name.
- **Comment** — The record’s explanatory comment.
- **Not selectable** — Whether the record is excluded from ordinary selections.
- **Alternative names** — Additional names identifying the same record.
- **Preview attachment** — The selected preview from the record’s attachments.
- **Added at** — When this record was added.
- **Modified at** — When this record was last modified.
- **Color designation** — The state’s source-declared color designation.
- **Parent assignment** — The optional parent record of the same structural kind.
