---
{
  "kind": "primary",
  "routes": {
    "route": "REST"
  },
  "steps": [
    {
      "text": "The caller submits a valid file-reference name, compatible type and valid external URL attached to the selected subject.",
      "kind": "actor",
      "actor": "api-client",
      "entities": [],
      "contexts": {
        "route": {
          "place": "rest-api"
        }
      }
    },
    {
      "text": "The Product consults the resolved User permission configuration.",
      "kind": "product",
      "actor": "api-client",
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
          "place": "rest-api"
        }
      }
    },
    {
      "text": "The Product saves the new Attachment with its supplied information and source-supported defaults.",
      "kind": "product",
      "actor": "api-client",
      "entities": [
        {
          "entity": "attachment",
          "effect": "creates",
          "facts": [
            "Name",
            "Original filename",
            "Internal file reference",
            "External URL",
            "Show in table",
            "Subject assignment",
            "Type assignment",
            "Added at",
            "Modified at"
          ]
        }
      ],
      "contexts": {
        "route": {
          "place": "rest-api"
        }
      }
    },
    {
      "text": "The Product updates the containing Part modification date.",
      "kind": "product",
      "actor": "api-client",
      "entities": [
        {
          "entity": "part",
          "effect": "changes",
          "facts": [
            "Modified at"
          ]
        }
      ],
      "contexts": {
        "route": {
          "place": "rest-api"
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
      "target": "src/Services/Attachments/AttachmentSubmitHandler.php"
    }
  ]
}
---

# Create attachment — REST primary

## Trigger

The caller submits a valid file-reference name, compatible type and valid external URL attached to the selected subject.

## Outcome

Supported reference/file added
