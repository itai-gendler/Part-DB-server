---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Entity/Parts/StorageLocation.php"
    }
  ],
  "domain": "storage-locations",
  "relations": [
    {
      "entity": "storage-location",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "part-lot",
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
    }
  ]
}
---

# Storage location

A hierarchical storage location record with its own classification information, attachments and parameters.

## Information kept

- **Name** — The structural record’s name.
- **Comment** — The record’s explanatory comment.
- **Not selectable** — Whether the record is excluded from ordinary selections.
- **Alternative names** — Additional names identifying the same record.
- **Preview attachment** — The selected preview from the record’s attachments.
- **Added at** — When this record was added.
- **Modified at** — When this record was last modified.
- **Full** — Whether the Location is marked full.
- **Single Part only** — Whether occupancy is restricted to one Part, potentially in multiple lots.
- **Existing Parts only** — Whether only already-stored Parts may be added.
- **Owner must match** — Whether lot and Location owners must match.
- **Owner assignment** — The optional User owning this Location.
- **Storage type** — The optional Measurement unit determining compatible storage.
- **Parent assignment** — The optional parent record of the same structural kind.
