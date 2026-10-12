---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Entity/Parts/Part.php"
    }
  ],
  "relations": [
    {
      "entity": "part-lot",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "order-detail",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "part-association",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "part-association",
      "verb": "is referenced by",
      "cardinality": "one-to-many"
    },
    {
      "entity": "bom-entry",
      "verb": "appears in",
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

# Part

An electronic component identity with descriptive, classification, purchasing and EDA information. Stock comes from its lots rather than from an independent kept Part quantity.

## Information kept

- **Name** — The component name.
- **Description** — The component description.
- **Comment** — The component comment.
- **Tags** — The component’s stored tags.
- **Internal part number** — The inventory’s internal component identifier.
- **GTIN** — The global trade item number.
- **Manufacturer product number** — The manufacturer’s component identifier.
- **Manufacturer URL** — The component’s manufacturer URL.
- **Manufacturing status** — The source-declared manufacturing-status value.
- **Minimum desired amount** — The desired minimum stock quantity.
- **Favorite** — Whether the Part is marked as a favorite.
- **Needs review** — Whether the Part is marked for review.
- **Mass** — The component mass.
- **EDA information** — The Part’s EDA information and overrides.
- **Provider reference** — Provider key, external reference and update time.
- **Preview attachment** — The Part’s selected preview attachment.
- **Category assignment** — The assigned Category.
- **Footprint assignment** — The assigned Footprint.
- **Manufacturer assignment** — The assigned Manufacturer.
- **Unit assignment** — The assigned Measurement unit.
- **Custom state assignment** — The assigned Part custom state.
- **Added at** — When this record was added.
- **Modified at** — When this record was last modified.
- **Stock summary** — Derived stock information from the Part’s lots, including known quantities, unknown quantities and expiration-sensitive projections.
