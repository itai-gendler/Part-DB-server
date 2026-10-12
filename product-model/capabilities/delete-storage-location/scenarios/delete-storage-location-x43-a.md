---
{
  "kind": "edge",
  "routes": {
    "route": "Authenticated Web"
  },
  "steps": [
    {
      "text": "The caller requests nonrecursive storage-place removal where surviving children must be reparented.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::authenticated::authenticated-storage-location"
        }
      }
    },
    {
      "text": "The Product checks the selected structural record’s supported direct-reference deletion boundary.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "storage-location",
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
          "place": "web::authenticated::authenticated-storage-location"
        }
      }
    },
    {
      "text": "The Product reparents surviving children to the removed record’s former parent and removes the selected record.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "storage-location",
          "effect": "changes",
          "facts": [
            "Parent assignment",
            "Modified at"
          ],
          "as": "child"
        },
        {
          "entity": "storage-location",
          "effect": "removes",
          "as": "selected"
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::authenticated-storage-location"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Entity/Parts/StorageLocation.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controller/AdminPages/StorageLocationController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controller/AdminPages/BaseAdminController.php"
    }
  ]
}
---

# Delete storage location — Corresponding explicit deletion path (Authenticated Web)

## Trigger

The caller requests nonrecursive storage-place removal where surviving children must be reparented.

## Outcome

An accepted nonrecursive removal reparents children; applicable direct references can prevent deletion. Web recursive deletion first checks the reached descendants; MCP has no recursive option.

## Edge cases

- REST resource deletion does not inherit this explicit tree-deletion acceptance.
