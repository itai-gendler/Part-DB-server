---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "order-detail"
    },
    {
      "type": "entity",
      "id": "price-detail"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Entity/PriceInformations/Pricedetail.php"
    }
  ]
}
---

# Purchasing references and price tiers satisfy parent and quantity constraints

Order detail requires its parent Part and Supplier and satisfies its declared purchasing uniqueness. Price detail requires its Order detail, positive price and related quantities and unique discount thresholds; currency references and manual-input information are retained.
