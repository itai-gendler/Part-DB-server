---
{
  "kind": "validation",
  "routes": {
    "route": "Public Web"
  },
  "steps": [
    {
      "text": "The caller requests import components through this contract.",
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
      "text": "The Product stops the requested import component operation at its actual refusal boundary.",
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

# Import parts — Public Web refusal

## Trigger

The caller requests import parts and reaches its closed entry or disabled-control result.

## Outcome

The requested import parts result is withheld; no accepted change or removal of the requested subject is produced.
