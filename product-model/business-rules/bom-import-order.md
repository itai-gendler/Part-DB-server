---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "import-bom",
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
      "target": "src/Services/ImportExportSystem/BOMImporter.php"
    }
  ]
}
---

# BOM clearing can precede a later import failure

BOM import can clear and flush existing entries before later parsing/mapping fails. Accepted unmatched input can retain supported free-text requirements; atomic replacement is not guaranteed.
