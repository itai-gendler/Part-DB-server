---
{
  "kind": "edge",
  "routes": {
    "route": "Authenticated Web"
  },
  "steps": [
    {
      "text": "The caller requests nonrecursive money-unit removal where surviving children must be reparented.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::authenticated::authenticated-currency"
        }
      }
    },
    {
      "text": "The Product checks the selected structural record’s supported direct-reference deletion boundary.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "currency",
          "effect": "reads",
          "facts": [
            "Name",
            "Parent assignment"
          ],
          "as": "selected"
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::authenticated-currency"
        }
      }
    },
    {
      "text": "The Product reparents surviving children to the removed record’s former parent and removes the selected record.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "currency",
          "effect": "changes",
          "facts": [
            "Parent assignment",
            "Modified at"
          ],
          "as": "child"
        },
        {
          "entity": "currency",
          "effect": "removes",
          "as": "selected"
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::authenticated-currency"
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

# Delete currency — Web tree-deletion path (Authenticated Web)

## Trigger

The caller requests nonrecursive money-unit removal where surviving children must be reparented.

## Outcome

An accepted nonrecursive removal reparents children; applicable direct references can prevent deletion. Web recursive deletion first checks the reached descendants; MCP has no recursive option.

## Edge cases

- REST resource deletion does not inherit this explicit tree-deletion acceptance.
