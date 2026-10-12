---
{
  "kind": "primary",
  "routes": {
    "route": "REST"
  },
  "steps": [
    {
      "text": "The caller submits a component name and classification with a known stock lot of two units, a valid specification, purchasing information with one price tier and a directed component association.",
      "kind": "actor",
      "actor": "api-client",
      "entities": [],
      "contexts": {
        "route": {
          "place": "rest-api"
        }
      }
    },
    {
      "text": "The Product consults the resolved User permission configuration.",
      "kind": "product",
      "actor": "api-client",
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
        "route": {
          "place": "rest-api"
        }
      }
    },
    {
      "text": "The Product saves the new Part with its supplied Part lot, Parameter, Order detail, Price detail and Part association, retaining normal defaults for omitted fields. Its supplied Attachment reference is saved with it.",
      "kind": "product",
      "actor": "api-client",
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
          ]
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
          "with": "part"
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
          "with": "part"
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
          "with": "part"
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
          "with": "part"
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
          "with": "part"
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
        "route": {
          "place": "rest-api"
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

# Create part — REST primary

## Trigger

The caller submits a valid new component with a classification, a known stock lot of two units, one specification, one purchasing record with a price tier and one directed association. A valid external file reference is supplied as well.

## Outcome

Part and supported supplied nested records saved; Web includes clone preparation

## Edge cases

- Web clone preparation creates distinct identities and copies supported nested information; an explicitly chosen initial storage Location can produce a supplied new lot.
- MCP creation requires Category input and uses its supported fields; supported nested members belong to the enclosing new component.
