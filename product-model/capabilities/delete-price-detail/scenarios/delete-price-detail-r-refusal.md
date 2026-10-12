---
{
  "kind": "validation",
  "routes": {
    "route": "REST"
  },
  "steps": [
    {
      "text": "The caller requests delete price tier through this contract.",
      "kind": "actor",
      "actor": "api-client",
      "entities": [],
      "contexts": {
        "route": {
          "place": "rest-api"
        }
      }
    },
    {
      "text": "The Product stops the requested delete price tier operation at its actual refusal boundary.",
      "kind": "product",
      "actor": "api-client",
      "entities": [],
      "contexts": {
        "route": {
          "place": "rest-api"
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
    }
  ]
}
---

# Delete price detail — REST refusal

## Trigger

The caller requests delete price detail and reaches its closed entry or disabled-control result.

## Outcome

The requested delete price detail result is withheld; no accepted change or removal of the requested subject is produced.
