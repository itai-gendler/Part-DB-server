---
{
  "kind": "edge",
  "routes": {
    "route": "Authenticated Web"
  },
  "steps": [
    {
      "text": "The caller accepts a default build allocation that includes known expired stock.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::authenticated::authenticated-project-build"
        }
      }
    },
    {
      "text": "The Product reads expired known Part lot stock used by the default allocation path.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "part-lot",
          "effect": "reads",
          "facts": [
            "Amount",
            "Unknown amount",
            "Expiration date"
          ]
        },
        {
          "entity": "bom-entry",
          "effect": "reads",
          "facts": [
            "Quantity",
            "Part assignment"
          ]
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::authenticated-project-build"
        }
      }
    },
    {
      "text": "The Product applies accepted positive allocations from that path.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "part-lot",
          "effect": "changes",
          "facts": [
            "Amount",
            "Modified at"
          ]
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::authenticated-project-build"
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Form/ProjectSystem/ProjectBuildType.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Helpers/Projects/ProjectBuildRequest.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Validator/Constraints/ProjectSystem/ValidProjectBuildRequestValidator.php"
    }
  ]
}
---

# Build project — Default allocation may include expired known lots despite different feasibility totals (Authenticated Web)

## Trigger

The caller accepts a default build allocation that includes known expired stock.

## Outcome

Default allocation can include expired known stock even though displayed feasibility uses a different expiration-sensitive total.
