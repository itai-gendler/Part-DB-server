---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "part-lot"
    },
    {
      "type": "entity",
      "id": "storage-location"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Validator/Constraints/ValidPartLotValidator.php"
    }
  ]
}
---

# Lot and location ownership satisfy the declared consistency constraints

Reserved anonymous identity cannot own a lot or location under the declared validation. Required owner matching applies where both the Location and lot have owners; absence of an owner is not a fabricated match.
