---
{
  "kind": "primary",
  "routes": {
    "route": "Public Web"
  },
  "steps": [
    {
      "text": "The caller selects an existing attached-file reference.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::public::public-attachment"
        }
      }
    },
    {
      "text": "The Product consults the resolved User permission configuration.",
      "kind": "product",
      "actor": "user",
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
          "place": "web::public::public-attachment"
        }
      }
    },
    {
      "text": "The Product returns the selected Attachment metadata without claiming a REST binary-content endpoint.",
      "kind": "product",
      "actor": "user",
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
          "place": "web::public::public-attachment"
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

# Read attachment metadata — Public Web primary

## Trigger

The caller selects an existing attached-file reference.

## Outcome

Selected/nested metadata disclosed
