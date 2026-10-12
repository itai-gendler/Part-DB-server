---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Entity/PriceInformations/Currency.php"
    }
  ],
  "domain": "currencies",
  "relations": [
    {
      "entity": "currency",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "price-detail",
      "verb": "prices",
      "cardinality": "one-to-many"
    },
    {
      "entity": "bom-entry",
      "verb": "prices",
      "cardinality": "one-to-many"
    },
    {
      "entity": "supplier",
      "verb": "supplies default currency",
      "cardinality": "one-to-many"
    },
    {
      "entity": "user",
      "verb": "supplies preferred currency",
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

# Currency

A hierarchical currency record with its own classification information, attachments and parameters.

## Information kept

- **Name** — The structural record’s name.
- **Comment** — The record’s explanatory comment.
- **Not selectable** — Whether the record is excluded from ordinary selections.
- **Alternative names** — Additional names identifying the same record.
- **Preview attachment** — The selected preview from the record’s attachments.
- **Added at** — When this record was added.
- **Modified at** — When this record was last modified.
- **ISO code** — The Currency’s ISO code.
- **Exchange rate** — The configured exchange rate.
- **Parent assignment** — The optional parent record of the same structural kind.
