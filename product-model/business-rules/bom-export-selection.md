---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "export-bom",
      "contexts": [
        {
          "place": "web::public"
        },
        {
          "place": "web::authenticated"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Services/ImportExportSystem/ProjectBomExporter.php"
    }
  ]
}
---

# BOM export includes all matching sorted and filtered rows

BOM export applies the selected sort/filter query to all matching rows, rather than just the displayed page.
