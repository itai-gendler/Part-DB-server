---
{
  "entities": [
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
      ],
      "collects": [
        "Favorite",
        "Needs review"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controller/PartController.php"
    }
  ]
}
---

# Authenticated part list

Matching component information, favorites, review flags, stock summaries and classification references; search, filter, sort, selection and table-action inputs.
