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
      "text": "The caller supplies a supported requirement file with usable mapping and matching choices.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "p": {
          "place": "web::public::public-bom-import"
        },
        "a": {
          "place": "web::authenticated::authenticated-bom-import"
        }
      },
      "capability": "import-bom"
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
          "place": "web::public::public-bom-import"
        },
        "a": {
          "place": "web::authenticated::authenticated-bom-import"
        }
      },
      "capability": "import-bom"
    },
    {
      "text": "The Product parses and matches the accepted rows and saves their Project requirements.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "bom-entry",
          "effect": "creates",
          "facts": [
            "Name",
            "Comment",
            "Quantity",
            "Mount names",
            "Price",
            "Project assignment",
            "Part assignment",
            "Price Currency assignment",
            "Added at",
            "Modified at"
          ]
        },
        {
          "entity": "project",
          "effect": "reads",
          "facts": [
            "Name"
          ]
        }
      ],
      "contexts": {
        "p": {
          "place": "web::public::public-bom-import"
        },
        "a": {
          "place": "web::authenticated::authenticated-bom-import"
        }
      },
      "capability": "import-bom"
    },
    {
      "text": "The Product carries the caller into the editor containing the imported requirements.",
      "kind": "product",
      "actor": "user",
      "entities": [],
      "contexts": {
        "p": {
          "place": "web::public::public-bom-import"
        },
        "a": {
          "place": "web::authenticated::authenticated-bom-import"
        }
      },
      "capability": "import-bom"
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Entity/ProjectSystem/Project.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Entity/Base/TimestampTrait.php"
    }
  ]
}
---

# Import bom and edit project achieved

## Trigger

The same caller follows the source-carried continuation: Import/mapping → Project editor with imported entries.

## Outcome

Accepted imported requirements are followed by a valid edit of the carried Project.
