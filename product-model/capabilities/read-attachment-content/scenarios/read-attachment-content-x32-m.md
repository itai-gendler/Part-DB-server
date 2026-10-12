---
{
  "kind": "edge",
  "routes": {
    "route": "MCP"
  },
  "steps": [
    {
      "text": "The caller requests existing internal content whose file size is greater than 10 MiB.",
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
      "text": "The Product refuses the existing file because its size exceeds ten MiB.",
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

# Read attachment content — Existing content larger than 10 MiB is refused (MCP)

## Trigger

The caller requests existing internal content whose file size is greater than 10 MiB.

## Outcome

MCP rejects content larger than ten MiB and directs retrieval to the browser path; this is not a kept content mutation.
