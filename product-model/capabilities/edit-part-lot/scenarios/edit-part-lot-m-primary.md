---
{
  "kind": "primary",
  "routes": {
    "route": "MCP"
  },
  "steps": [
    {
      "text": "The caller submits valid replacement values for Description, Comment, Unknown amount, Needs refill, Expiration date, Location assignment, Owner assignment, account barcode on the selected record.",
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
      "text": "The Product saves the supplied Part lot information through the implemented write.",
      "kind": "product",
      "actor": "ai-agent",
      "entities": [
        {
          "entity": "part-lot",
          "effect": "changes",
          "facts": [
            "Description",
            "Comment",
            "Unknown amount",
            "Needs refill",
            "Expiration date",
            "Location assignment",
            "Owner assignment",
            "User barcode",
            "Modified at"
          ]
        },
        {
          "entity": "part",
          "effect": "reads",
          "facts": [
            "Name"
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
      "target": "src/State/Mcp/AbstractPartMutationProcessor.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Entity/Base/TimestampTrait.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/EventSubscriber/McpAccessSubscriber.php"
    }
  ]
}
---

# Edit part lot — MCP primary

## Trigger

The caller submits valid replacement values for Description, Comment, Unknown amount, Needs refill, Expiration date, Location assignment, Owner assignment, account barcode on the selected record.

## Outcome

Supported metadata saved
