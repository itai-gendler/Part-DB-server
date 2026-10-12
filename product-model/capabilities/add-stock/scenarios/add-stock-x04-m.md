---
{
  "kind": "edge",
  "routes": {
    "route": "MCP"
  },
  "steps": [
    {
      "text": "The caller requests addition of 0.4 to a known integer-unit lot, with a supplied comment.",
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
      "text": "The Product interprets the Measurement unit as integer-valued and rounds a positive request of 0.4 to zero.",
      "kind": "product",
      "actor": "ai-agent",
      "entities": [
        {
          "entity": "measurement-unit",
          "effect": "reads",
          "facts": [
            "Integer amounts"
          ]
        },
        {
          "entity": "part-lot",
          "effect": "reads",
          "facts": [
            "Amount"
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
      "text": "The Product reaches the helper’s zero-effective addition and stock-event call without a second positivity check.",
      "kind": "product",
      "actor": "ai-agent",
      "entities": [
        {
          "entity": "part-lot",
          "effect": "changes",
          "facts": [
            "Amount"
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
      "target": "src/Entity/Parts/PartLot.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controller/PartController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Services/Parts/PartLotWithdrawAddHelper.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Security/Voter/PartLotVoter.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/State/Mcp/AbstractPartLotStockProcessor.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Form/Part/PartLotType.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/State/Mcp/McpToolErrorHandling.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/State/Mcp/AddPartStockProcessor.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Mcp/DTO/AddPartStockInput.php"
    }
  ]
}
---

# Add stock — Integer-unit rounding can turn a positive request into zero effective addition (MCP)

## Trigger

The caller requests addition of 0.4 to a known integer-unit lot, with a supplied comment.

## Outcome

The positive request can complete with zero effective added quantity after rounding.
