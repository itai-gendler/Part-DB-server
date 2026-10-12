---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Entity/PriceInformations/Orderdetail.php"
    }
  ],
  "relations": [
    {
      "entity": "price-detail",
      "verb": "contains",
      "cardinality": "one-to-many"
    }
  ]
}
---

# Order detail

Purchasing information linking a Part to a Supplier and its price tiers.

## Information kept

- **Supplier part number** — The Supplier’s component identifier.
- **Supplier URL** — The component URL at the Supplier.
- **Obsolete** — Whether this purchasing record is obsolete.
- **EDA visibility** — Whether this purchasing information is exposed to EDA consumers.
- **Available amount** — The Supplier’s reported available quantity.
- **Availability updated at** — When Supplier availability was updated.
- **Prices include VAT** — Whether the purchasing prices include VAT.
- **Part assignment** — The Part being supplied.
- **Supplier assignment** — The supplying Supplier.
- **Added at** — When this record was added.
- **Modified at** — When this record was last modified.
