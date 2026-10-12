---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Entity/Attachments/AttachmentType.php"
    }
  ],
  "domain": "attachment-types",
  "relations": [
    {
      "entity": "attachment-type",
      "verb": "contains",
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
    },
    {
      "entity": "attachment",
      "verb": "classifies",
      "cardinality": "one-to-many"
    }
  ]
}
---

# Attachment type

A hierarchical attachment type record with its own classification information, attachments and parameters.

## Information kept

- **Name** — The structural record’s name.
- **Comment** — The record’s explanatory comment.
- **Not selectable** — Whether the record is excluded from ordinary selections.
- **Alternative names** — Additional names identifying the same record.
- **Preview attachment** — The selected preview from the record’s attachments.
- **Added at** — When this record was added.
- **Modified at** — When this record was last modified.
- **File filter** — The configured attachment file filter.
- **Allowed targets** — The subjects to which this attachment classification may apply.
- **Parent assignment** — The optional parent record of the same structural kind.
