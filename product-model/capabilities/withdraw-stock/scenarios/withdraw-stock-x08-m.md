---
{
  "kind": "edge",
  "routes": {
    "route": "MCP"
  },
  "steps": [
    {
      "text": "The caller requests withdrawal of a positive fractional quantity from an integer-unit lot with sufficient balance.",
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
      "text": "The Product applies the Measurement unit’s integer interpretation, rounding the requested 1.6 units to two.",
      "kind": "product",
      "actor": "ai-agent",
      "entities": [
        {
          "entity": "measurement-unit",
          "effect": "reads",
          "facts": [
            "Integer amounts"
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
      "text": "The Product stores the effective rounded quantity through this helper path.",
      "kind": "product",
      "actor": "ai-agent",
      "entities": [
        {
          "entity": "part-lot",
          "effect": "changes",
          "facts": [
            "Amount",
            "Modified at"
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
      "target": "src/State/Mcp/WithdrawPartStockProcessor.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Mcp/DTO/WithdrawPartStockInput.php"
    }
  ]
}
---

# Withdraw stock — Integer rounding determines effective withdrawal (MCP)

## Trigger

The caller requests withdrawal of a positive fractional quantity from an integer-unit lot with sufficient balance.

## Outcome

The saved effective withdrawal is two units.
