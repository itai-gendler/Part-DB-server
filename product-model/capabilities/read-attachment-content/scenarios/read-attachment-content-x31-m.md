---
{
  "kind": "edge",
  "routes": {
    "route": "MCP"
  },
  "steps": [
    {
      "text": "The caller requests existing internal content whose stored file is missing or unavailable.",
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
      "text": "The Product reads the Attachment internal reference and content classification before testing its available file.",
      "kind": "product",
      "actor": "ai-agent",
      "entities": [
        {
          "entity": "attachment",
          "effect": "reads",
          "facts": [
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
    },
    {
      "text": "The Product rejects the missing file.",
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

# Read attachment content — Missing/unavailable internal content fails (MCP)

## Trigger

The caller requests existing internal content whose stored file is missing or unavailable.

## Outcome

Missing or unavailable internal content produces the distinguished failure.
