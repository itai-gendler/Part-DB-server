---
{
  "kind": "primary",
  "routes": {
    "route": "MCP"
  },
  "steps": [
    {
      "text": "The caller requests available internally stored content.",
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
      "text": "The Product reads the Attachment file reference and returns its available internal content.",
      "kind": "product",
      "actor": "ai-agent",
      "entities": [
        {
          "entity": "attachment",
          "effect": "reads",
          "facts": [
            "Name",
            "Internal file reference",
            "Content classification"
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
      "target": "src/Entity/Attachments/Attachment.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controller/PartController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controller/AttachmentFileController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/State/Mcp/GetAttachmentContentProcessor.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/EventSubscriber/McpAccessSubscriber.php"
    }
  ]
}
---

# Read attachment content — MCP primary

## Trigger

The caller requests available internally stored content.

## Outcome

Available internal file content is returned or viewed; external links are not thereby fetched as MCP internal files.
