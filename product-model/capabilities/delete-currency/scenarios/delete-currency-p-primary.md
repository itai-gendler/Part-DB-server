---
{
  "kind": "primary",
  "routes": {
    "route": "Public Web"
  },
  "steps": [
    {
      "text": "The caller selects the existing money unit for removal with valid confirmation or reference input.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::public::public-currency"
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
          "place": "web::public::public-currency"
        }
      }
    },
    {
      "text": "The Product removes the selected Currency through this contract’s implemented path.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "currency",
          "effect": "removes"
        }
      ],
      "contexts": {
        "route": {
          "place": "web::public::public-currency"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Entity/PriceInformations/Currency.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controller/AdminPages/CurrencyController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controller/AdminPages/BaseAdminController.php"
    }
  ]
}
---

# Delete currency — Public Web primary

## Trigger

The caller selects the existing money unit for removal with valid confirmation or reference input.

## Outcome

The selected Currency is removed through the implemented deletion path.
