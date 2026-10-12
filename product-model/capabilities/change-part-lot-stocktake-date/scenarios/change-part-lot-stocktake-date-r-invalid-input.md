---
{
  "kind": "validation",
  "routes": {
    "route": "REST"
  },
  "steps": [
    {
      "text": "The caller submits the failing input: The direct date input cannot be interpreted as a valid date.",
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
      "text": "The Product does not complete change stock record stocktake date because the direct date input cannot be interpreted as a valid date.",
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
      "target": "src/Entity/Parts/PartLot.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controller/PartController.php"
    }
  ]
}
---

# Change part lot stocktake date — REST invalid input

## Trigger

The direct date input cannot be interpreted as a valid date.

## Outcome

The direct date input cannot be interpreted as a valid date. No successful change part lot stocktake date result is asserted.
