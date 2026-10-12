---
{
  "kind": "validation",
  "routes": {
    "route": "REST"
  },
  "steps": [
    {
      "text": "The caller requests delete specification value through this contract.",
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
      "text": "The Product stops the requested delete named value operation at its actual refusal boundary.",
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
      "target": "src/Entity/Parameters/AbstractParameter.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controller/PartController.php"
    }
  ]
}
---

# Delete parameter — REST refusal

## Trigger

The caller requests delete parameter and reaches its closed entry or disabled-control result.

## Outcome

The requested delete parameter result is withheld; no accepted change or removal of the requested subject is produced.
