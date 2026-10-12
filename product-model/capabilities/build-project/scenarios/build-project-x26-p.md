---
{
  "kind": "primary",
  "routes": {
    "route": "Public Web"
  },
  "steps": [
    {
      "text": "The caller accepts a build with configured output, chooses a new output stock lot and supplies valid positive allocations.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::public::public-project-build"
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
          "place": "web::public::public-project-build"
        }
      }
    },
    {
      "text": "The Product reads the Project’s configured output and its accepted BOM allocation.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "project",
          "effect": "reads",
          "facts": [
            "Build Part assignment"
          ]
        },
        {
          "entity": "part-lot",
          "as": "source",
          "effect": "reads",
          "facts": [
            "Amount",
            "Unknown amount",
            "Part assignment"
          ]
        }
      ],
      "contexts": {
        "route": {
          "place": "web::public::public-project-build"
        }
      }
    },
    {
      "text": "The Product creates the requested new output Part lot with its build description and normal zero known-quantity defaults, reaching the first flush.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "part-lot",
          "as": "output",
          "effect": "creates",
          "facts": [
            "Description",
            "Comment",
            "Amount",
            "Unknown amount",
            "Needs refill",
            "Expiration date",
            "User barcode",
            "Last stocktake",
            "Part assignment",
            "Location assignment",
            "Owner assignment",
            "Added at",
            "Modified at"
          ]
        }
      ],
      "contexts": {
        "route": {
          "place": "web::public::public-project-build"
        }
      }
    },
    {
      "text": "The Product withdraws the accepted positive allocation from the source Part lot.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "part-lot",
          "as": "source",
          "effect": "changes",
          "facts": [
            "Amount",
            "Modified at"
          ]
        }
      ],
      "contexts": {
        "route": {
          "place": "web::public::public-project-build"
        }
      }
    },
    {
      "text": "The Product adds the completed-unit quantity to the output Part lot and reaches the second flush.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "part-lot",
          "as": "output",
          "effect": "changes",
          "facts": [
            "Amount",
            "Modified at"
          ]
        }
      ],
      "contexts": {
        "route": {
          "place": "web::public::public-project-build"
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
      "target": "src/Entity/Base/TimestampTrait.php"
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

# Build project — Configured output lot receives completed-unit quantity (Public Web)

## Trigger

The caller accepts a build with configured output, chooses a new output stock lot and supplies valid positive allocations.

## Outcome

The new output lot is persisted before allocation withdrawal, then receives the completed-unit quantity at the second flush. No completion counter is updated.

## Edge cases

- A selected existing known output lot is increased instead of creating a new one; the helper still refuses unknown quantity or a full output location.
- Separate flushes do not promise atomic rollback if a later helper fails.
