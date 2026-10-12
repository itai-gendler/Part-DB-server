---
{
  "kind": "edge",
  "routes": {
    "route": "Authenticated Web"
  },
  "steps": [
    {
      "text": "The caller imports a file with both valid and invalid rows and disables abort-on-validation-error.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::authenticated::authenticated-part-import"
        }
      }
    },
    {
      "text": "The Product saves accepted Part records while reporting distinguished failures for other imported rows.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "part",
          "effect": "creates",
          "facts": [
            "Name",
            "Description",
            "Comment",
            "Tags",
            "Internal part number",
            "GTIN",
            "Manufacturer product number",
            "Manufacturer URL",
            "Manufacturing status",
            "Minimum desired amount",
            "Favorite",
            "Needs review",
            "Mass",
            "EDA information",
            "Provider reference",
            "Preview attachment",
            "Category assignment",
            "Footprint assignment",
            "Manufacturer assignment",
            "Unit assignment",
            "Custom state assignment",
            "Added at",
            "Modified at"
          ]
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::authenticated-part-import"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Entity/Parts/Part.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controller/PartController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controller/PartImportExportController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Services/ImportExportSystem/EntityImporter.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "templates/parts/import/parts_import.html.twig"
    }
  ]
}
---

# Import parts — Saved records and per-record errors may coexist (Authenticated Web)

## Trigger

The caller imports a file with both valid and invalid rows and disables abort-on-validation-error.

## Outcome

Saved imported records and per-record errors can coexist; all-or-nothing import is not guaranteed.
