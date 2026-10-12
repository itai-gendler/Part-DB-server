---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "attachment",
      "effect": "removes",
      "contexts": [
        {
          "place": "mcp"
        }
      ]
    },
    {
      "type": "entity",
      "id": "category",
      "effect": "changes",
      "contexts": [
        {
          "place": "mcp"
        }
      ]
    },
    {
      "type": "entity",
      "id": "category",
      "effect": "creates",
      "contexts": [
        {
          "place": "mcp"
        }
      ]
    },
    {
      "type": "entity",
      "id": "category",
      "effect": "removes",
      "contexts": [
        {
          "place": "mcp"
        }
      ]
    },
    {
      "type": "entity",
      "id": "footprint",
      "effect": "changes",
      "contexts": [
        {
          "place": "mcp"
        }
      ]
    },
    {
      "type": "entity",
      "id": "footprint",
      "effect": "creates",
      "contexts": [
        {
          "place": "mcp"
        }
      ]
    },
    {
      "type": "entity",
      "id": "footprint",
      "effect": "removes",
      "contexts": [
        {
          "place": "mcp"
        }
      ]
    },
    {
      "type": "entity",
      "id": "manufacturer",
      "effect": "changes",
      "contexts": [
        {
          "place": "mcp"
        }
      ]
    },
    {
      "type": "entity",
      "id": "manufacturer",
      "effect": "creates",
      "contexts": [
        {
          "place": "mcp"
        }
      ]
    },
    {
      "type": "entity",
      "id": "manufacturer",
      "effect": "removes",
      "contexts": [
        {
          "place": "mcp"
        }
      ]
    },
    {
      "type": "entity",
      "id": "order-detail",
      "effect": "changes",
      "contexts": [
        {
          "place": "mcp"
        }
      ]
    },
    {
      "type": "entity",
      "id": "order-detail",
      "effect": "creates",
      "contexts": [
        {
          "place": "mcp"
        }
      ]
    },
    {
      "type": "entity",
      "id": "order-detail",
      "effect": "removes",
      "contexts": [
        {
          "place": "mcp"
        }
      ]
    },
    {
      "type": "entity",
      "id": "parameter",
      "effect": "changes",
      "contexts": [
        {
          "place": "mcp"
        }
      ]
    },
    {
      "type": "entity",
      "id": "parameter",
      "effect": "creates",
      "contexts": [
        {
          "place": "mcp"
        }
      ]
    },
    {
      "type": "entity",
      "id": "parameter",
      "effect": "removes",
      "contexts": [
        {
          "place": "mcp"
        }
      ]
    },
    {
      "type": "entity",
      "id": "part",
      "effect": "changes",
      "contexts": [
        {
          "place": "mcp"
        }
      ]
    },
    {
      "type": "entity",
      "id": "part",
      "effect": "creates",
      "contexts": [
        {
          "place": "mcp"
        }
      ]
    },
    {
      "type": "entity",
      "id": "part",
      "effect": "removes",
      "contexts": [
        {
          "place": "mcp"
        }
      ]
    },
    {
      "type": "entity",
      "id": "part-association",
      "effect": "changes",
      "contexts": [
        {
          "place": "mcp"
        }
      ]
    },
    {
      "type": "entity",
      "id": "part-association",
      "effect": "creates",
      "contexts": [
        {
          "place": "mcp"
        }
      ]
    },
    {
      "type": "entity",
      "id": "part-association",
      "effect": "removes",
      "contexts": [
        {
          "place": "mcp"
        }
      ]
    },
    {
      "type": "entity",
      "id": "part-lot",
      "effect": "changes",
      "contexts": [
        {
          "place": "mcp"
        }
      ]
    },
    {
      "type": "entity",
      "id": "part-lot",
      "effect": "creates",
      "contexts": [
        {
          "place": "mcp"
        }
      ]
    },
    {
      "type": "entity",
      "id": "part-lot",
      "effect": "removes",
      "contexts": [
        {
          "place": "mcp"
        }
      ]
    },
    {
      "type": "entity",
      "id": "price-detail",
      "effect": "changes",
      "contexts": [
        {
          "place": "mcp"
        }
      ]
    },
    {
      "type": "entity",
      "id": "price-detail",
      "effect": "creates",
      "contexts": [
        {
          "place": "mcp"
        }
      ]
    },
    {
      "type": "entity",
      "id": "price-detail",
      "effect": "removes",
      "contexts": [
        {
          "place": "mcp"
        }
      ]
    },
    {
      "type": "entity",
      "id": "storage-location",
      "effect": "changes",
      "contexts": [
        {
          "place": "mcp"
        }
      ]
    },
    {
      "type": "entity",
      "id": "storage-location",
      "effect": "creates",
      "contexts": [
        {
          "place": "mcp"
        }
      ]
    },
    {
      "type": "entity",
      "id": "storage-location",
      "effect": "removes",
      "contexts": [
        {
          "place": "mcp"
        }
      ]
    },
    {
      "type": "entity",
      "id": "supplier",
      "effect": "changes",
      "contexts": [
        {
          "place": "mcp"
        }
      ]
    },
    {
      "type": "entity",
      "id": "supplier",
      "effect": "creates",
      "contexts": [
        {
          "place": "mcp"
        }
      ]
    },
    {
      "type": "entity",
      "id": "supplier",
      "effect": "removes",
      "contexts": [
        {
          "place": "mcp"
        }
      ]
    }
  ],
  "permits": [
    {
      "configuredBy": "user",
      "when": [
        {
          "entity": "product-settings",
          "fact": "MCP enabled",
          "is": true
        },
        {
          "entity": "product-settings",
          "fact": "MCP editing enabled",
          "is": true
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/EventSubscriber/McpAccessSubscriber.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Settings/AISettings/McpSettings.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/State/Mcp/AbstractPartLotStockProcessor.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/State/Mcp/AbstractPartMutationProcessor.php"
    }
  ]
}
---

# MCP inventory writes require the editing switch as well as the enabled endpoint

The initiating AI agent uses the authenticated User’s authority and applicable token ceilings. Explicit write processors check editing enablement before lookup or mutation. Internal configuration evaluation remains available to determine a refusal and is not selected as an inventory disclosure or write.
