---
{
  "kind": "validation",
  "routes": {
    "route": "REST"
  },
  "steps": [
    {
      "text": "The caller requests edit requirement row through this contract.",
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
      "text": "The Product stops the requested edit requirement operation at its actual refusal boundary.",
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

# Edit bom entry — REST refusal

## Trigger

The caller requests edit bom entry and reaches its closed entry or disabled-control result.

## Outcome

The requested edit bom entry result is withheld; no accepted change or removal of the requested subject is produced.
