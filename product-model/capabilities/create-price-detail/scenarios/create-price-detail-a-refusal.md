---
{
  "kind": "validation",
  "routes": {
    "route": "Authenticated Web"
  },
  "steps": [
    {
      "text": "The caller requests create price tier through this contract.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::authenticated::authenticated-part"
        }
      }
    },
    {
      "text": "The Product stops the requested create price tier operation at its actual refusal boundary.",
      "kind": "product",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::authenticated::authenticated-part"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Entity/PriceInformations/Pricedetail.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controller/PartController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Entity/PriceInformations/Orderdetail.php"
    }
  ]
}
---

# Create price detail — Authenticated Web refusal

## Trigger

The caller requests create price detail and reaches its closed entry or disabled-control result.

## Outcome

The requested create price detail result is withheld; no accepted change or removal of the requested subject is produced.
