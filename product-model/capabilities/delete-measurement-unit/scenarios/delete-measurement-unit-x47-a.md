---
{
  "kind": "edge",
  "routes": {
    "route": "Authenticated Web"
  },
  "steps": [
    {
      "text": "The caller requests nonrecursive quantity-unit removal where surviving children must be reparented.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::authenticated::authenticated-measurement-unit"
        }
      }
    },
    {
      "text": "The Product checks the selected structural record’s supported direct-reference deletion boundary.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "measurement-unit",
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
          "place": "web::authenticated::authenticated-measurement-unit"
        }
      }
    },
    {
      "text": "The Product reparents surviving children to the removed record’s former parent and removes the selected record.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "measurement-unit",
          "effect": "changes",
          "facts": [
            "Parent assignment",
            "Modified at"
          ],
          "as": "child"
        },
        {
          "entity": "measurement-unit",
          "effect": "removes",
          "as": "selected"
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::authenticated-measurement-unit"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Entity/Parts/MeasurementUnit.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controller/AdminPages/MeasurementUnitController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controller/AdminPages/BaseAdminController.php"
    }
  ]
}
---

# Delete measurement unit — Web tree-deletion path (Authenticated Web)

## Trigger

The caller requests nonrecursive quantity-unit removal where surviving children must be reparented.

## Outcome

An accepted nonrecursive removal reparents children; applicable direct references can prevent deletion. Web recursive deletion first checks the reached descendants; MCP has no recursive option.

## Edge cases

- REST resource deletion does not inherit this explicit tree-deletion acceptance.
