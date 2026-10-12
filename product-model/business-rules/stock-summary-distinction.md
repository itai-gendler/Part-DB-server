---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "part"
    },
    {
      "type": "entity",
      "id": "part-lot"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Entity/Parts/Part.php"
    }
  ]
}
---

# Stock summaries distinguish known, unknown and expiration-sensitive quantities

The stock projections distinguish known numeric quantities, unknown-quantity lots and expiration-sensitive totals. A Part stock summary is derived from its lots, not an independently edited kept Part quantity.
