---
{
  "availability": [
    {
      "place": "web::public"
    },
    {
      "place": "web::authenticated"
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

# Import parts

Import results and distinguished errors returned
