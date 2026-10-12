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
      "text": "The caller supplies valid changes to the selected record’s supported information.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "p": {
          "place": "web::public::public-bom-entry"
        },
        "a": {
          "place": "web::authenticated::authenticated-bom-entry"
        }
      },
      "capability": "edit-bom-entry"
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
          "place": "web::public::public-bom-entry"
        },
        "a": {
          "place": "web::authenticated::authenticated-bom-entry"
        }
      },
      "capability": "edit-bom-entry"
    },
    {
      "text": "The Product saves the supplied BOM entry information through the implemented write.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "bom-entry",
          "effect": "changes",
          "facts": [
            "Name",
            "Comment",
            "Quantity",
            "Mount names",
            "Modified at"
          ]
        }
      ],
      "contexts": {
        "p": {
          "place": "web::public::public-bom-entry"
        },
        "a": {
          "place": "web::authenticated::authenticated-bom-entry"
        }
      },
      "capability": "edit-bom-entry"
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

# Edit bom entry and return to project achieved

## Trigger

The same caller follows the source-carried continuation: Independently selected entry edit → Project information.

## Outcome

The saved requirement is followed by disclosure of its owning Project.
