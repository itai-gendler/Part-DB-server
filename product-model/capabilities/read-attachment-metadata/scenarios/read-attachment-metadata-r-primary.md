---
{
  "kind": "primary",
  "routes": {
    "route": "REST"
  },
  "steps": [
    {
      "text": "The caller selects an existing attached-file reference.",
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
      "text": "The Product returns the selected Attachment metadata without claiming a REST binary-content endpoint.",
      "kind": "product",
      "actor": "api-client",
      "entities": [
        {
          "entity": "attachment",
          "effect": "reads",
          "facts": [
            "Name",
            "Original filename",
            "Internal file reference",
            "External URL",
            "Show in table",
            "Subject assignment",
            "Type assignment",
            "Content classification",
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
    }
  ]
}
---

# Read attachment metadata — REST primary

## Trigger

The caller selects an existing attached-file reference.

## Outcome

Selected/nested metadata disclosed
