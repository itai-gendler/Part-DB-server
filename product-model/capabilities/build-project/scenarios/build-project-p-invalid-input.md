---
{
  "kind": "validation",
  "routes": {
    "route": "Public Web"
  },
  "steps": [
    {
      "text": "The caller submits the failing input: The submitted build quantity or allocations fail the build request’s declared validation.",
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
      "text": "The Product does not complete build assembly record because the submitted build quantity or allocations fail the build request’s declared validation.",
      "kind": "product",
      "actor": "user",
      "entities": [],
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

# Build project — Public Web invalid input

## Trigger

The submitted build quantity or allocations fail the build request’s declared validation.

## Outcome

The submitted build quantity or allocations fail the build request’s declared validation. No successful build project result is asserted.
