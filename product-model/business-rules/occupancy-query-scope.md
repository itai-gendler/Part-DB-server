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

# Occupancy validation uses the reached identified-record queries

The lot validator’s occupancy restrictions use its reached queries for identified records. Single-Part, existing-Part and compatible-storage checks do not establish helper parity or race-free occupancy.
