---
{
  "kind": "edge",
  "routes": {
    "route": "Public Web"
  },
  "steps": [
    {
      "text": "The caller submits an otherwise valid build form whose populated allocation control is disabled.",
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
      "text": "The Product presents owner-sensitive disabled controls for the selected Part lot.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "part-lot",
          "effect": "reads",
          "facts": [
            "Owner assignment",
            "Amount"
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
      "text": "The Product withdraws the accepted initialized allocation from the selected Part lot.",
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

# Build with a disabled allocation control (Public Web)

## Trigger

The caller submits an otherwise valid build form whose populated allocation control is disabled.

## Outcome

The accepted initialized allocation is withdrawn; the disabled control does not erase its populated allocation.
