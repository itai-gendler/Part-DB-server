---
{
  "kind": "edge",
  "routes": {
    "route": "Public Web"
  },
  "steps": [
    {
      "text": "The caller opens build feasibility for an assembly with no requirement rows.",
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
      "text": "The Product reads the Project with no requirements and displays a maximum build quantity of zero.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "project",
          "effect": "reads",
          "facts": [
            "Name",
            "Build Part assignment"
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

# Build project — Empty BOM maximum is zero; display alone is not a successful build (Public Web)

## Trigger

The caller opens build feasibility for an assembly with no requirement rows.

## Outcome

An empty BOM displays maximum zero; displaying this information alone does not constitute a successful build.
