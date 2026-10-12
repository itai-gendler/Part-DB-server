---
{
  "kind": "edge",
  "routes": {
    "route": "Public Web"
  },
  "steps": [
    {
      "text": "The caller requests matching information when the selected query or subject has no matching results.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::public::public-project"
        }
      }
    },
    {
      "text": "The Product consults the resolved User permission configuration.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "user",
          "effect": "reads",
          "facts": [
            "Permission overrides"
          ]
        }
      ],
      "contexts": {
        "route": {
          "place": "web::public::public-project"
        }
      }
    },
    {
      "text": "The Product returns the contract’s empty result without claiming a found inventory instance was read.",
      "kind": "product",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::public::public-project"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Entity/ProjectSystem/Project.php"
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

# Browse projects — Public Web empty result

## Trigger

The relevant selection has no matching result.

## Outcome

No matching Project records are returned.
