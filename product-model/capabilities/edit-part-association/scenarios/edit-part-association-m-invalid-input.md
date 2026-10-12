---
{
  "kind": "validation",
  "routes": {
    "route": "MCP"
  },
  "steps": [
    {
      "text": "The caller submits the failing input: The supplied association violates its self-reference, uniqueness or custom-description constraints.",
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
      "text": "The Product does not complete edit directed component link because the supplied association violates its self-reference, uniqueness or custom-description constraints.",
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
      "target": "src/Entity/Parts/PartAssociation.php"
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

# Edit part association — MCP invalid input

## Trigger

The supplied association violates its self-reference, uniqueness or custom-description constraints.

## Outcome

The supplied association violates its self-reference, uniqueness or custom-description constraints. No successful edit part association result is asserted.
