---
{
  "kind": "validation",
  "routes": {
    "route": "Authenticated Web"
  },
  "steps": [
    {
      "text": "The caller submits the failing input: The supplied requirement violates quantity, mount-name, manual-price or owning-assembly record constraints.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::authenticated::authenticated-bom-entry"
        }
      }
    },
    {
      "text": "The Product retains the form’s validation errors for the supplied requirement violates quantity, mount-name, manual-price or owning-assembly record constraints. The submitted write is not accepted.",
      "kind": "product",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::authenticated::authenticated-bom-entry"
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

# Edit bom entry — Authenticated Web invalid input

## Trigger

The supplied requirement violates quantity, mount-name, manual-price or owning-project constraints.

## Outcome

The supplied requirement violates quantity, mount-name, manual-price or owning-project constraints. No successful edit bom entry result is asserted.
