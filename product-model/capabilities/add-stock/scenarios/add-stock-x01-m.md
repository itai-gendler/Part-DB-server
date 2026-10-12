---
{
  "kind": "edge",
  "routes": {
    "route": "MCP"
  },
  "steps": [
    {
      "text": "The caller requests addition to a stock lot whose quantity is unknown.",
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
      "text": "The Product reads the selected Part lot’s unknown-quantity flag and rejects the relative helper operation.",
      "kind": "product",
      "actor": "ai-agent",
      "entities": [
        {
          "entity": "part-lot",
          "effect": "reads",
          "facts": [
            "Unknown amount"
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

# Add stock — Unknown quantity prevents relative addition (MCP)

## Trigger

The caller requests addition to a stock lot whose quantity is unknown.

## Outcome

Relative adjustment fails for unknown quantity; no accepted saved quantity change is produced.
