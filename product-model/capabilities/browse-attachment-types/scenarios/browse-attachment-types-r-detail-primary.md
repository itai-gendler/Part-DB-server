---
{
  "kind": "primary",
  "routes": {
    "route": "REST"
  },
  "steps": [
    {
      "text": "The caller requests the supported information of one existing selected record.",
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
      "text": "The Product discloses the selected Attachment type information through this contract.",
      "kind": "product",
      "actor": "api-client",
      "entities": [
        {
          "entity": "attachment-type",
          "effect": "reads",
          "facts": [
            "Name",
            "Comment",
            "Preview attachment",
            "Added at",
            "Modified at",
            "File filter",
            "Allowed targets",
            "Parent assignment"
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
      "target": "src/Entity/Attachments/AttachmentType.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controller/AdminPages/AttachmentTypeController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controller/AdminPages/BaseAdminController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Entity/Base/AbstractStructuralDBElement.php"
    }
  ]
}
---

# Browse attachment types — REST detail primary

## Trigger

One existing subject is selected for its detail information.

## Outcome

Matching Attachment type records are disclosed.
