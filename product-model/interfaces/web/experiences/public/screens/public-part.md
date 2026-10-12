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
        "Custom state assignment"
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
      ],
      "collects": [
        "Description",
        "Comment",
        "Amount",
        "Unknown amount",
        "Needs refill",
        "Expiration date",
        "User barcode",
        "Last stocktake",
        "Location assignment",
        "Owner assignment"
      ]
    },
    {
      "entity": "parameter",
      "shows": [
        "Name",
        "Group",
        "Symbol",
        "Unit",
        "Text value",
        "Minimum value",
        "Typical value",
        "Maximum value",
        "EDA visibility",
        "EDA symbol visibility",
        "Subject assignment",
        "Added at",
        "Modified at"
      ],
      "collects": [
        "Name",
        "Group",
        "Symbol",
        "Unit",
        "Text value",
        "Minimum value",
        "Typical value",
        "Maximum value",
        "EDA visibility",
        "EDA symbol visibility"
      ]
    },
    {
      "entity": "order-detail",
      "shows": [
        "Supplier part number",
        "Supplier URL",
        "Obsolete",
        "EDA visibility",
        "Available amount",
        "Availability updated at",
        "Prices include VAT",
        "Part assignment",
        "Supplier assignment",
        "Added at",
        "Modified at"
      ],
      "collects": [
        "Supplier part number",
        "Supplier URL",
        "Obsolete",
        "EDA visibility",
        "Prices include VAT",
        "Supplier assignment"
      ]
    },
    {
      "entity": "price-detail",
      "shows": [
        "Price",
        "Price-related quantity",
        "Minimum discount quantity",
        "Manual input",
        "Currency assignment",
        "Order detail assignment",
        "Added at",
        "Modified at"
      ],
      "collects": [
        "Price",
        "Price-related quantity",
        "Minimum discount quantity",
        "Currency assignment"
      ]
    },
    {
      "entity": "part-association",
      "shows": [
        "Association type",
        "Other type description",
        "Comment",
        "Originating Part assignment",
        "Other Part assignment",
        "Added at",
        "Modified at"
      ],
      "collects": [
        "Association type",
        "Other type description",
        "Comment",
        "Other Part assignment"
      ]
    },
    {
      "entity": "attachment",
      "shows": [
        "Name",
        "Original filename",
        "Internal file reference",
        "External URL",
        "Show in table",
        "Subject assignment",
        "Type assignment",
        "Content classification",
        "Added at",
        "Modified at"
      ],
      "collects": [
        "Name",
        "Original filename",
        "External URL",
        "Show in table",
        "Type assignment"
      ]
    },
    {
      "entity": "activity-entry",
      "shows": [
        "Actor name",
        "Occurred at",
        "Event kind",
        "Severity",
        "Access method",
        "Target reference",
        "Event details",
        "Request correlation",
        "Transaction correlation"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controller/PartController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Form/Part/PartLotType.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Form/ParameterType.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Form/Part/OrderdetailType.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Form/Part/PricedetailType.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Form/Part/PartAssociationType.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Form/AttachmentFormType.php"
    }
  ]
}
---

# Public part

Component information and supported lot, parameter, purchasing, price, association, attachment and history information; accepted component and nested edits, adjustment quantities, dates and comments.
