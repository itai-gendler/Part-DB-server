---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "part-lot"
    },
    {
      "type": "entity",
      "id": "measurement-unit"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Entity/Parts/PartLot.php"
    }
  ]
}
---

# Integer units determine getter and helper rounding

Integer-valued Measurement units determine getter and helper rounding. Positive relative requests are checked before rounding, so a positive request can have zero effective quantity. Direct writable fields do not acquire an uninspected normalization guarantee.
