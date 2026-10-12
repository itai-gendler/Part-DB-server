---
{
  "kind": "primary",
  "routes": {
    "route": "REST"
  },
  "steps": [
    {
      "text": "The caller submits a positive price, positive price-related quantity and a unique discount threshold on the selected purchasing record.",
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
      "text": "The Product saves the new Price detail with its supplied information and source-supported defaults.",
      "kind": "product",
      "actor": "api-client",
      "entities": [
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
      "text": "The Product updates the containing Order detail and Part modification dates.",
      "kind": "product",
      "actor": "api-client",
      "entities": [
        {
          "entity": "order-detail",
          "effect": "changes",
          "facts": [
            "Modified at"
          ]
        },
        {
          "entity": "part",
          "effect": "changes",
          "facts": [
            "Modified at"
          ]
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
      "target": "src/Entity/PriceInformations/Pricedetail.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controller/PartController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Entity/PriceInformations/Orderdetail.php"
    }
  ]
}
---

# Create price detail — REST primary

## Trigger

The caller submits a positive price, positive price-related quantity and a unique discount threshold on the selected purchasing record.

## Outcome

Price tier added
