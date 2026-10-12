---
{
  "kind": "primary",
  "routes": {
    "route": "Authenticated Web"
  },
  "steps": [
    {
      "text": "The caller selects the existing purchasing record for removal with valid confirmation or reference input.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::authenticated::authenticated-part"
        }
      }
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
        "route": {
          "place": "web::authenticated::authenticated-part"
        }
      }
    },
    {
      "text": "The Product removes the selected Order detail through this contract’s implemented path.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "order-detail",
          "effect": "removes"
        },
        {
          "entity": "price-detail",
          "effect": "removes",
          "with": "order-detail"
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::authenticated-part"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Entity/PriceInformations/Orderdetail.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controller/PartController.php"
    }
  ]
}
---

# Delete order detail — Authenticated Web primary

## Trigger

The caller selects the existing purchasing record for removal with valid confirmation or reference input.

## Outcome

Purchasing record removed
