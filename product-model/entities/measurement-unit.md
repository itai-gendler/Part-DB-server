---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Entity/Parts/MeasurementUnit.php"
    }
  ],
  "domain": "measurement-units",
  "relations": [
    {
      "entity": "measurement-unit",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "part",
      "verb": "measures",
      "cardinality": "one-to-many"
    },
    {
      "entity": "storage-location",
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

# Measurement unit

A hierarchical measurement unit record with its own classification information, attachments and parameters.

## Information kept

- **Name** — The structural record’s name.
- **Comment** — The record’s explanatory comment.
- **Not selectable** — Whether the record is excluded from ordinary selections.
- **Alternative names** — Additional names identifying the same record.
- **Preview attachment** — The selected preview from the record’s attachments.
- **Added at** — When this record was added.
- **Modified at** — When this record was last modified.
- **Unit symbol** — The displayed unit symbol.
- **Integer amounts** — Whether quantities are interpreted as integers.
- **SI prefixes** — The supported SI-prefix configuration.
- **Parent assignment** — The optional parent record of the same structural kind.
