---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Entity/PriceInformations/Pricedetail.php"
    }
  ]
}
---

# Price detail

A purchasing price tier with quantity thresholds and a Currency.

## Information kept

- **Price** — The tier’s price.
- **Price-related quantity** — The quantity to which this price applies.
- **Minimum discount quantity** — The minimum quantity for the tier.
- **Manual input** — Whether the tier was entered manually.
- **Currency assignment** — The price Currency.
- **Order detail assignment** — The Order detail to which this price tier belongs.
- **Added at** — When this record was added.
- **Modified at** — When this record was last modified.
