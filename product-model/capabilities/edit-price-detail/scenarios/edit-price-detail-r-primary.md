---
{
  "kind": "primary",
  "routes": {
    "route": "REST"
  },
  "steps": [
    {
      "text": "The caller submits valid replacement values for Price, Price-related quantity, Minimum discount quantity on the selected record.",
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
      "text": "The Product saves the supplied Price detail information through the implemented write.",
      "kind": "product",
      "actor": "api-client",
      "entities": [
        {
          "entity": "price-detail",
          "effect": "changes",
          "facts": [
            "Price",
            "Price-related quantity",
            "Minimum discount quantity",
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
      "target": "src/Entity/Base/TimestampTrait.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Entity/PriceInformations/Orderdetail.php"
    }
  ]
}
---

# Edit price detail — REST primary

## Trigger

The caller submits valid replacement values for Price, Price-related quantity, Minimum discount quantity on the selected record.

## Outcome

Price tier saved
