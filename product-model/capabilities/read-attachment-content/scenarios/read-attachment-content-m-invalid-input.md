---
{
  "kind": "validation",
  "routes": {
    "route": "MCP"
  },
  "steps": [
    {
      "text": "The caller submits the failing input: The reference is invalid or has no usable internal content source.",
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
      "text": "The Product does not complete read file reference content because the reference is invalid or has no usable internal content source.",
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
    }
  ]
}
---

# Read attachment content — MCP invalid input

## Trigger

The reference is invalid or has no usable internal content source.

## Outcome

The reference is invalid or has no usable internal content source. No successful read attachment content result is asserted.
