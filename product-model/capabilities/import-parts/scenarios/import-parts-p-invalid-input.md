---
{
  "kind": "validation",
  "routes": {
    "route": "Public Web"
  },
  "steps": [
    {
      "text": "The caller submits the failing input: The supplied file cannot be used by the selected import format.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::public::public-part-import"
        }
      }
    },
    {
      "text": "The Product does not complete import components because the supplied file cannot be used by the selected import format.",
      "kind": "product",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::public::public-part-import"
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

# Import parts — Public Web invalid input

## Trigger

The supplied file cannot be used by the selected import format.

## Outcome

The supplied file cannot be used by the selected import format. No successful import parts result is asserted.
