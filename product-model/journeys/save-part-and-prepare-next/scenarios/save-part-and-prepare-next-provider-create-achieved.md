---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "p": "Public Web",
    "a": "Authenticated Web"
  },
  "steps": [
    {
      "text": "The caller chooses an external provider reference and accepts valid prepared component information.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "p": {
          "place": "web::public::public-part"
        },
        "a": {
          "place": "web::authenticated::authenticated-part"
        }
      },
      "capability": "create-part-from-info-provider"
    },
    {
      "text": "The Product consults the resolved User permission configuration.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "user",
          "effect": "reads",
          "facts": [
            "Permission overrides"
          ]
        }
      ],
      "contexts": {
        "p": {
          "place": "web::public::public-part"
        },
        "a": {
          "place": "web::authenticated::authenticated-part"
        }
      },
      "capability": "create-part-from-info-provider"
    },
    {
      "text": "The Product consults the separately addressed provider activity configuration for the selected provider path.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "product-settings",
          "effect": "reads",
          "facts": [
            "Provider activity configuration"
          ]
        }
      ],
      "contexts": {
        "p": {
          "place": "web::public::public-part"
        },
        "a": {
          "place": "web::authenticated::authenticated-part"
        }
      },
      "capability": "create-part-from-info-provider"
    },
    {
      "text": "The Product retrieves external detail information and prepares the accepted component form.",
      "kind": "product",
      "actor": "user",
      "entities": [],
      "contexts": {
        "p": {
          "place": "web::public::public-part"
        },
        "a": {
          "place": "web::authenticated::authenticated-part"
        }
      },
      "capability": "create-part-from-info-provider"
    },
    {
      "text": "The Product saves the accepted Part information before the selected Save-and-new or clone continuation.",
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
          ],
          "as": "previous"
        }
      ],
      "contexts": {
        "p": {
          "place": "web::public::public-part"
        },
        "a": {
          "place": "web::authenticated::authenticated-part"
        }
      },
      "capability": "create-part-from-info-provider"
    },
    {
      "kind": "product",
      "actor": "user",
      "text": "The Product carries the caller into the next new-record preparation selected by Save-and-new or clone.",
      "entities": [],
      "contexts": {
        "p": {
          "place": "web::public::public-part"
        },
        "a": {
          "place": "web::authenticated::authenticated-part"
        }
      },
      "capability": "create-part-from-info-provider"
    },
    {
      "text": "The caller submits a component name and classification with a known stock lot of two units, a valid specification, purchasing information with one price tier and a directed component association.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "p": {
          "place": "web::public::public-part"
        },
        "a": {
          "place": "web::authenticated::authenticated-part"
        }
      },
      "capability": "create-part"
    },
    {
      "text": "The Product consults the resolved User permission configuration.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "user",
          "effect": "reads",
          "facts": [
            "Permission overrides"
          ]
        }
      ],
      "contexts": {
        "p": {
          "place": "web::public::public-part"
        },
        "a": {
          "place": "web::authenticated::authenticated-part"
        }
      },
      "capability": "create-part"
    },
    {
      "text": "The Product saves the new Part with its supplied Part lot, Parameter, Order detail, Price detail and Part association, retaining normal defaults for omitted fields. Its supplied Attachment reference is saved with it.",
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
          ],
          "as": "next"
        },
        {
          "entity": "part-lot",
          "effect": "creates",
          "facts": [
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
          "with": "next"
        },
        {
          "entity": "parameter",
          "effect": "creates",
          "facts": [
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
          "with": "next"
        },
        {
          "entity": "order-detail",
          "effect": "creates",
          "facts": [
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
          "with": "next"
        },
        {
          "entity": "part-association",
          "effect": "creates",
          "facts": [
            "Association type",
            "Other type description",
            "Comment",
            "Originating Part assignment",
            "Other Part assignment",
            "Added at",
            "Modified at"
          ],
          "with": "next"
        },
        {
          "entity": "attachment",
          "effect": "creates",
          "facts": [
            "Name",
            "Original filename",
            "Internal file reference",
            "External URL",
            "Show in table",
            "Subject assignment",
            "Type assignment",
            "Added at",
            "Modified at"
          ],
          "with": "next"
        },
        {
          "entity": "price-detail",
          "effect": "creates",
          "facts": [
            "Price",
            "Price-related quantity",
            "Minimum discount quantity",
            "Manual input",
            "Currency assignment",
            "Order detail assignment",
            "Added at",
            "Modified at"
          ],
          "with": "order-detail"
        }
      ],
      "contexts": {
        "p": {
          "place": "web::public::public-part"
        },
        "a": {
          "place": "web::authenticated::authenticated-part"
        }
      },
      "capability": "create-part"
    },
    {
      "text": "The Product carries the caller into the saved record’s editor.",
      "kind": "product",
      "actor": "user",
      "entities": [],
      "contexts": {
        "p": {
          "place": "web::public::public-part"
        },
        "a": {
          "place": "web::authenticated::authenticated-part"
        }
      },
      "capability": "create-part"
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
      "target": "src/Controller/InfoProviderController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Services/InfoProviderSystem/ProviderRegistry.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controller/PartController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/State/Mcp/CreatePartProcessor.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/State/Mcp/AbstractPartMutationProcessor.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Entity/PriceInformations/Orderdetail.php"
    }
  ]
}
---

# Save part and prepare next provider create achieved

## Trigger

The same caller explicitly chooses Save-and-new or clone after the first accepted operation.

## Outcome

The first accepted operation carries the same caller into preparation and accepted saving of a distinct next component.
