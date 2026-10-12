---
{
  "kind": "primary",
  "routes": {
    "route": "MCP"
  },
  "steps": [
    {
      "text": "The caller requests the supported information of one existing selected record.",
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
      "text": "The Product checks that the MCP endpoint is enabled before entering the tool operation.",
      "kind": "product",
      "actor": "ai-agent",
      "entities": [
        {
          "entity": "product-settings",
          "effect": "reads",
          "facts": [
            "MCP enabled"
          ]
        }
      ],
      "contexts": {
        "route": {
          "place": "mcp"
        }
      }
    },
    {
      "text": "The Product consults the resolved User permission configuration.",
      "kind": "product",
      "actor": "ai-agent",
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
          "place": "mcp"
        }
      }
    },
    {
      "text": "The Product discloses the selected Footprint information through this contract.",
      "kind": "product",
      "actor": "ai-agent",
      "entities": [
        {
          "entity": "footprint",
          "effect": "reads",
          "facts": [
            "Name",
            "Comment",
            "Preview attachment",
            "Added at",
            "Modified at",
            "EDA information",
            "3D attachment selection",
            "Parent assignment"
          ]
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
      "target": "src/Entity/Parts/Footprint.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controller/AdminPages/FootprintController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controller/AdminPages/BaseAdminController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/State/Mcp/ListStructuralElementsProcessor.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Entity/Base/AbstractStructuralDBElement.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/EventSubscriber/McpAccessSubscriber.php"
    }
  ]
}
---

# Browse footprints — MCP detail primary

## Trigger

One existing subject is selected for its detail information.

## Outcome

Matching Footprint records are disclosed.
