---
{
  "kind": "edge",
  "routes": {
    "route": "MCP"
  },
  "steps": [
    {
      "text": "The caller supplies a specification collection with one changed existing member and one omitted existing member, leaving other collections absent.",
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
      "text": "The Product preserves omitted collections and reconciles a supplied nested member list against belonging identities.",
      "kind": "product",
      "actor": "ai-agent",
      "entities": [
        {
          "entity": "part",
          "effect": "reads",
          "facts": [
            "Name"
          ]
        },
        {
          "entity": "parameter",
          "effect": "changes",
          "facts": [
            "Text value",
            "Modified at"
          ],
          "as": "retained"
        }
      ],
      "contexts": {
        "route": {
          "place": "mcp"
        }
      }
    },
    {
      "text": "The Product removes an omitted member from the explicitly supplied collection.",
      "kind": "product",
      "actor": "ai-agent",
      "entities": [
        {
          "entity": "parameter",
          "effect": "removes",
          "as": "omitted"
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

# Edit part — Omission preserves collections; supplied/empty collections reconcile/remove (MCP)

## Trigger

The caller supplies a specification collection with one changed existing member and one omitted existing member, leaving other collections absent.

## Outcome

Omitted collections remain intact; supplied collections reconcile belonging identities, and an explicitly empty collection removes its members.

## Edge cases

- Lots, purchasing records, prices and associations follow their supported reconciliation branches; supplying existing-lot Amount remains rejected.
