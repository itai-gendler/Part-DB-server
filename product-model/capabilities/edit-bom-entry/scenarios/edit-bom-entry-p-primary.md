---
{
  "kind": "primary",
  "routes": {
    "route": "Public Web"
  },
  "steps": [
    {
      "text": "The caller submits valid replacement values for Name, Comment, Quantity, Mount names on the selected record.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::public::public-bom-entry"
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
          "place": "web::public::public-bom-entry"
        }
      }
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
        "route": {
          "place": "web::public::public-bom-entry"
        }
      }
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
      "target": "src/Entity/Base/TimestampTrait.php"
    }
  ]
}
---

# Edit bom entry — Public Web primary

## Trigger

The caller submits valid replacement values for Name, Comment, Quantity, Mount names on the selected record.

## Outcome

Entry saved
