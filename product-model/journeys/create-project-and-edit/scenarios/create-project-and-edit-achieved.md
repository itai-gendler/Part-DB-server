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
      "text": "The caller submits valid new-record information with a unique name or supported parent reference.",
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
      "capability": "create-project"
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
      "capability": "create-project"
    },
    {
      "text": "The Product saves the new Project with its supplied information and source-supported defaults.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "project",
          "effect": "creates",
          "facts": [
            "Name",
            "Description",
            "Comment",
            "Order quantity",
            "Status",
            "Order only missing Parts",
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
      "capability": "create-project"
    },
    {
      "text": "The Product carries the caller into the saved record’s editor.",
      "kind": "product",
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
      "capability": "create-project"
    },
    {
      "text": "The caller supplies valid changes to the selected record’s supported information.",
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
      "capability": "edit-project"
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
      "capability": "edit-project"
    },
    {
      "text": "The Product saves the supplied Project information through the implemented write.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "project",
          "effect": "changes",
          "facts": [
            "Name",
            "Description",
            "Comment",
            "Order quantity",
            "Status",
            "Modified at"
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
      "capability": "edit-project"
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

# Create project and edit achieved

## Trigger

The same caller follows the source-carried continuation: Create Project → Edit saved Project.

## Outcome

The saved or surviving record reaches its editor and the same caller’s subsequent valid edit is saved.
