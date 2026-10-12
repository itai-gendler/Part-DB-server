---
{
  "kind": "primary",
  "routes": {
    "route": "Public Web"
  },
  "steps": [
    {
      "text": "The caller supplies a supported requirement file with usable mapping and matching choices.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::public::public-bom-import"
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
          "place": "web::public::public-bom-import"
        }
      }
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
        "route": {
          "place": "web::public::public-bom-import"
        }
      }
    },
    {
      "text": "The Product carries the caller into the editor containing the imported requirements.",
      "kind": "product",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::public::public-bom-import"
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
    }
  ]
}
---

# Import bom — Public Web primary

## Trigger

The caller supplies a supported requirement file with usable mapping and matching choices.

## Outcome

Supported import/matching saved and editor reached
