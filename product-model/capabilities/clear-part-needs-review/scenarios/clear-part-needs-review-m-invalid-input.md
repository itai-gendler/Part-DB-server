---
{
  "kind": "validation",
  "routes": {
    "route": "MCP"
  },
  "steps": [
    {
      "text": "The caller submits the failing input: The selected reference or enclosing mutation input is invalid; the requested flag change is not accepted.",
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
      "text": "The Product does not complete clear component needs review because the selected reference or enclosing mutation input is invalid; the requested flag change is not accepted.",
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
    }
  ]
}
---

# Clear part needs review — MCP invalid input

## Trigger

The selected reference or enclosing mutation input is invalid; the requested flag change is not accepted.

## Outcome

The selected reference or enclosing mutation input is invalid; the requested flag change is not accepted. No successful clear part needs review result is asserted.
