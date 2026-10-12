---
{
  "entities": [
    {
      "entity": "part",
      "shows": [
        "Name",
        "Description",
        "Category assignment",
        "Footprint assignment",
        "Preview attachment"
      ]
    },
    {
      "entity": "part-lot",
      "shows": [
        "Amount",
        "Unknown amount",
        "Location assignment"
      ]
    },
    {
      "entity": "storage-location",
      "shows": [
        "Name",
        "Parent assignment",
        "Preview attachment"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controller/ScanController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "templates/label_system/scanner/_info_mode.html.twig"
    }
  ]
}
---

# Authenticated scanner

Decoded barcode input and any found inventory information; barcode and interpretation choices.
