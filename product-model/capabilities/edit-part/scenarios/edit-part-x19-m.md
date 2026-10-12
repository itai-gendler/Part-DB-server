---
{
  "kind": "validation",
  "routes": {
    "route": "MCP"
  },
  "steps": [
    {
      "text": "The caller supplies Amount for an existing nested stock lot in a component update.",
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
      "text": "The Product rejects an Amount supplied for an existing nested lot before applying that nested update.",
      "kind": "product",
      "actor": "ai-agent",
      "entities": [],
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
      "target": "src/State/Mcp/UpdatePartProcessor.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Mcp/DTO/UpdatePartInput.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/State/Mcp/McpToolErrorHandling.php"
    }
  ]
}
---

# Edit part — Supplying existing-lot Amount is rejected (MCP)

## Trigger

The caller supplies Amount for an existing nested stock lot in a component update.

## Outcome

MCP existing-lot quantity input is rejected and directs quantity work to the stock tools; new-lot quantity remains a distinct supported branch.
