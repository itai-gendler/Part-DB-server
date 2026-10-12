---
{
  "entities": [
    {
      "entity": "label-profile",
      "shows": [
        "Name",
        "Options"
      ],
      "collects": [
        "Name",
        "Options"
      ]
    },
    {
      "entity": "part",
      "shows": [
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
        "Modified at",
        "Stock summary"
      ]
    },
    {
      "entity": "part-lot",
      "shows": [
        "Description",
        "Comment",
        "Amount",
        "Unknown amount",
        "Needs refill",
        "Expiration date",
        "User barcode",
        "Last stocktake",
        "Part assignment",
        "Location assignment",
        "Owner assignment",
        "Added at",
        "Modified at"
      ]
    },
    {
      "entity": "storage-location",
      "shows": [
        "Name",
        "Comment",
        "Not selectable",
        "Alternative names",
        "Preview attachment",
        "Added at",
        "Modified at",
        "Full",
        "Single Part only",
        "Existing Parts only",
        "Owner must match",
        "Owner assignment",
        "Storage type"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controller/LabelController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "templates/label_system/dialog.html.twig"
    }
  ]
}
---

# Authenticated label generation

Saved options where supplied, resolved target information and generated-result feedback; target selection, transient overrides and supported inline profile-save inputs.
