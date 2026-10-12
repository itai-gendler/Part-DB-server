---
{
  "kind": "edge",
  "routes": {
    "route": "MCP"
  },
  "steps": [
    {
      "text": "The caller requests nonrecursive maker-record removal where surviving children must be reparented.",
      "kind": "actor",
      "actor": "ai-agent",
      "entities": [],
      "contexts": {
        "route": {
          "place": "mcp"
        }
      }
    },
    {
      "text": "The Product checks the selected structural record’s supported direct-reference deletion boundary.",
      "kind": "product",
      "actor": "ai-agent",
      "entities": [
        {
          "entity": "manufacturer",
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
          "place": "mcp"
        }
      }
    },
    {
      "text": "The Product reparents surviving children to the removed record’s former parent and removes the selected record.",
      "kind": "product",
      "actor": "ai-agent",
      "entities": [
        {
          "entity": "manufacturer",
          "effect": "changes",
          "facts": [
            "Parent assignment",
            "Modified at"
          ],
          "as": "child"
        },
        {
          "entity": "manufacturer",
          "effect": "removes",
          "as": "selected"
        }
      ],
      "contexts": {
        "route": {
          "place": "mcp"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Entity/Parts/Manufacturer.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controller/AdminPages/ManufacturerController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controller/AdminPages/BaseAdminController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/State/Mcp/DeleteStructuralElementProcessor.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/State/Mcp/AbstractStructuralElementMutationProcessor.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/State/Mcp/McpToolErrorHandling.php"
    }
  ]
}
---

# Delete manufacturer — Corresponding explicit deletion path (MCP)

## Trigger

The caller requests nonrecursive maker-record removal where surviving children must be reparented.

## Outcome

The explicit MCP path refuses applicable direct component references and reparents children rather than deleting the subtree.

## Edge cases

- REST resource deletion does not inherit this explicit tree-deletion acceptance.
