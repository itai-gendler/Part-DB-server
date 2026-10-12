---
{
  "kind": "primary",
  "routes": {
    "route": "MCP"
  },
  "steps": [
    {
      "text": "The caller selects the existing component for removal with valid confirmation or reference input.",
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
      "text": "The Product checks the editing switch before the mutation processor resolves or changes the requested record.",
      "kind": "product",
      "actor": "ai-agent",
      "entities": [
        {
          "entity": "product-settings",
          "effect": "reads",
          "facts": [
            "MCP editing enabled"
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
      "text": "The Product removes the selected Part and its dependent Part lots, Parameters, Order details, Price details, Associations and Attachments.",
      "kind": "product",
      "actor": "ai-agent",
      "entities": [
        {
          "entity": "part",
          "effect": "removes"
        },
        {
          "entity": "part-lot",
          "effect": "removes",
          "with": "part"
        },
        {
          "entity": "parameter",
          "effect": "removes",
          "with": "part"
        },
        {
          "entity": "order-detail",
          "effect": "removes",
          "with": "part"
        },
        {
          "entity": "part-association",
          "effect": "removes",
          "with": "part"
        },
        {
          "entity": "attachment",
          "effect": "removes",
          "with": "part"
        },
        {
          "entity": "price-detail",
          "effect": "removes",
          "with": "order-detail"
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
      "target": "src/Entity/Parts/Part.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controller/PartController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/State/Mcp/AbstractPartMutationProcessor.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Entity/Parts/PartTraits/OrderTrait.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Entity/Parts/PartTraits/InstockTrait.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Entity/Parts/PartTraits/AssociationTrait.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Entity/PriceInformations/Orderdetail.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Entity/PriceInformations/Pricedetail.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/EventSubscriber/McpAccessSubscriber.php"
    }
  ]
}
---

# Delete part — MCP primary

## Trigger

The caller selects the existing component for removal with valid confirmation or reference input.

## Outcome

Selected Part removed
