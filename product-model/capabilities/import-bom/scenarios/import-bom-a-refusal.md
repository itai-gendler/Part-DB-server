---
{
  "kind": "validation",
  "routes": {
    "route": "Authenticated Web"
  },
  "steps": [
    {
      "text": "The caller requests import bom through this contract.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::authenticated::authenticated-bom-import"
        }
      }
    },
    {
      "text": "The Product stops the requested import bom operation at its actual refusal boundary.",
      "kind": "product",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::authenticated::authenticated-bom-import"
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

# Import bom — Authenticated Web refusal

## Trigger

The caller requests import bom and reaches its closed entry or disabled-control result.

## Outcome

The requested import bom result is withheld; no accepted change or removal of the requested subject is produced.
