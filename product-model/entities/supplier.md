---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Entity/Parts/Supplier.php"
    }
  ],
  "domain": "suppliers",
  "relations": [
    {
      "entity": "supplier",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "order-detail",
      "verb": "supplies",
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

# Supplier

A hierarchical supplier record with its own classification information, attachments and parameters.

## Information kept

- **Name** — The structural record’s name.
- **Comment** — The record’s explanatory comment.
- **Not selectable** — Whether the record is excluded from ordinary selections.
- **Alternative names** — Additional names identifying the same record.
- **Preview attachment** — The selected preview from the record’s attachments.
- **Added at** — When this record was added.
- **Modified at** — When this record was last modified.
- **Address** — The company address.
- **Phone** — The company telephone number.
- **Fax** — The company fax number.
- **Email** — The company email address.
- **Website** — The company website.
- **Product URL template** — The URL template used for supplied component references.
- **Shipping costs** — The configured shipping costs.
- **Default currency** — The supplier’s default Currency.
- **Parent assignment** — The optional parent record of the same structural kind.
