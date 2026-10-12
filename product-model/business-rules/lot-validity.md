---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "part-lot"
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

# Lot quantities are nonnegative and their declared references and barcode are valid

A lot has a required Part and a nonnegative numeric quantity; supplied user barcodes are unique and declared metadata types are valid. Unknown quantity remains a separate flag.
