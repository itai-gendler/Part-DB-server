---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Entity/Parts/Category.php"
    }
  ],
  "domain": "categories",
  "relations": [
    {
      "entity": "category",
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

# Category

A hierarchical category record with its own classification information, attachments and parameters.

## Information kept

- **Name** — The structural record’s name.
- **Comment** — The record’s explanatory comment.
- **Not selectable** — Whether the record is excluded from ordinary selections.
- **Alternative names** — Additional names identifying the same record.
- **Preview attachment** — The selected preview from the record’s attachments.
- **Added at** — When this record was added.
- **Modified at** — When this record was last modified.
- **Part name hint** — The hint offered for names of Parts in this Category.
- **Part name pattern** — The configured validation pattern for Part names.
- **Internal part number prefix** — The Category’s internal-number prefix.
- **Default description** — The default Part description.
- **Default comment** — The default Part comment.
- **Disabled Part features** — The configured footprint, manufacturer, automatic-datasheet and property-feature exclusions.
- **EDA information** — The Category’s EDA library and visibility information.
- **Parent assignment** — The optional parent record of the same structural kind.
