---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "p": "Public Web",
    "a": "Authenticated Web"
  },
  "steps": [
    {
      "text": "The caller submits a positive build quantity with accepted positive allocations from known stock.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "p": {
          "place": "web::public::public-project-build"
        },
        "a": {
          "place": "web::authenticated::authenticated-project-build"
        }
      },
      "capability": "build-project"
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
        "p": {
          "place": "web::public::public-project-build"
        },
        "a": {
          "place": "web::authenticated::authenticated-project-build"
        }
      },
      "capability": "build-project"
    },
    {
      "text": "The Product reads the Project requirements, accepted allocations and selected known quantities.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "project",
          "effect": "reads",
          "facts": [
            "Name",
            "Order quantity",
            "Build Part assignment"
          ]
        },
        {
          "entity": "bom-entry",
          "effect": "reads",
          "facts": [
            "Quantity",
            "Part assignment"
          ]
        },
        {
          "entity": "part-lot",
          "effect": "reads",
          "facts": [
            "Amount",
            "Unknown amount",
            "Expiration date"
          ]
        }
      ],
      "contexts": {
        "p": {
          "place": "web::public::public-project-build"
        },
        "a": {
          "place": "web::authenticated::authenticated-project-build"
        }
      },
      "capability": "build-project"
    },
    {
      "text": "The Product withdraws accepted positive allocations and reaches the build path’s second flush.",
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
        "p": {
          "place": "web::public::public-project-build"
        },
        "a": {
          "place": "web::authenticated::authenticated-project-build"
        }
      },
      "capability": "build-project"
    },
    {
      "text": "The Product carries the caller back to the existing subject’s information page.",
      "kind": "product",
      "actor": "user",
      "entities": [],
      "contexts": {
        "p": {
          "place": "web::public::public-project-build"
        },
        "a": {
          "place": "web::authenticated::authenticated-project-build"
        }
      },
      "capability": "build-project"
    },
    {
      "text": "The caller requests the supported information of one existing selected record.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "p": {
          "place": "web::public::public-project"
        },
        "a": {
          "place": "web::authenticated::authenticated-project"
        }
      },
      "capability": "browse-projects"
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
        "p": {
          "place": "web::public::public-project"
        },
        "a": {
          "place": "web::authenticated::authenticated-project"
        }
      },
      "capability": "browse-projects"
    },
    {
      "text": "The Product discloses the selected Project information through this contract.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "project",
          "effect": "reads",
          "facts": [
            "Name",
            "Description",
            "Comment",
            "Status",
            "Parent assignment",
            "Build Part assignment",
            "Added at",
            "Modified at",
            "Not selectable",
            "Alternative names",
            "Preview attachment"
          ]
        }
      ],
      "contexts": {
        "p": {
          "place": "web::public::public-project"
        },
        "a": {
          "place": "web::authenticated::authenticated-project"
        }
      },
      "capability": "browse-projects"
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
    }
  ]
}
---

# Build and return to project achieved

## Trigger

The same caller follows the source-carried continuation: Accepted build → Project information after reached stock effects.

## Outcome

Accepted reached stock effects are followed by the carried Project disclosure.
