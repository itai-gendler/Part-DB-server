---
{
  "kind": "validation",
  "routes": {
    "route": "REST"
  },
  "steps": [
    {
      "text": "The caller submits the failing input: A nonpositive price or quantity, missing parent or duplicate discount threshold is submitted.",
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
      "text": "The Product does not complete create price tier because a nonpositive price or quantity, missing parent or duplicate discount threshold is submitted.",
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Entity/PriceInformations/Orderdetail.php"
    }
  ]
}
---

# Create price detail — REST invalid input

## Trigger

A nonpositive price or quantity, missing parent or duplicate discount threshold is submitted.

## Outcome

A nonpositive price or quantity, missing parent or duplicate discount threshold is submitted. No successful create price detail result is asserted.
