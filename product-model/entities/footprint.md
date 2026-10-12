---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Entity/Parts/Footprint.php"
    }
  ],
  "domain": "footprints",
  "relations": [
    {
      "entity": "footprint",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "part",
      "verb": "describes",
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

# Footprint

A hierarchical footprint record with its own classification information, attachments and parameters.

## Information kept

- **Name** — The structural record’s name.
- **Comment** — The record’s explanatory comment.
- **Not selectable** — Whether the record is excluded from ordinary selections.
- **Alternative names** — Additional names identifying the same record.
- **Preview attachment** — The selected preview from the record’s attachments.
- **Added at** — When this record was added.
- **Modified at** — When this record was last modified.
- **EDA information** — The footprint’s EDA information.
- **3D attachment selection** — The selected attachment supplying its 3D model.
- **Parent assignment** — The optional parent record of the same structural kind.
