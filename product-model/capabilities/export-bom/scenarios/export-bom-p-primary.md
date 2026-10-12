---
{
  "kind": "primary",
  "routes": {
    "route": "Public Web"
  },
  "steps": [
    {
      "text": "The caller selects a supported representation with the required filters and sort order.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::public::public-project"
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
          "place": "web::public::public-project"
        }
      }
    },
    {
      "text": "The Product reads matching BOM entry rows in the requested order and returns the export.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "bom-entry",
          "effect": "reads",
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
        }
      ],
      "contexts": {
        "route": {
          "place": "web::public::public-project"
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

# Export bom — Public Web primary

## Trigger

The caller selects a supported representation with the required filters and sort order.

## Outcome

All matching sorted and filtered rows are exported, rather than only the displayed page.
