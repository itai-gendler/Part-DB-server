---
{
  "kind": "validation",
  "routes": {
    "route": "REST"
  },
  "steps": [
    {
      "text": "The caller submits the failing input: A nonpositive quantity, missing component and name, duplicate mount name or prohibited build-component reference is submitted.",
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
      "text": "The Product does not complete create requirement row because a nonpositive quantity, missing component and name, duplicate mount name or prohibited build-component reference is submitted.",
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
      "target": "src/Entity/ProjectSystem/ProjectBOMEntry.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controller/ProjectController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Services/ProjectSystem/ProjectBuildHelper.php"
    }
  ]
}
---

# Create bom entry — REST invalid input

## Trigger

A nonpositive quantity, missing component and name, duplicate mount name or prohibited build-component reference is submitted.

## Outcome

A nonpositive quantity, missing component and name, duplicate mount name or prohibited build-component reference is submitted. No successful create bom entry result is asserted.
