---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "p": "Public Web",
    "a": "Authenticated Web"
  },
  "steps": [
    {
      "text": "The caller submits valid new-record information with a unique name or supported parent reference.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "p": {
          "place": "web::public::public-attachment-type"
        },
        "a": {
          "place": "web::authenticated::authenticated-attachment-type"
        }
      },
      "capability": "create-attachment-type"
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
        "p": {
          "place": "web::public::public-attachment-type"
        },
        "a": {
          "place": "web::authenticated::authenticated-attachment-type"
        }
      },
      "capability": "create-attachment-type"
    },
    {
      "text": "The Product saves the new Attachment type with its supplied information and source-supported defaults.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "attachment-type",
          "effect": "creates",
          "facts": [
            "Name",
            "Comment",
            "Not selectable",
            "Alternative names",
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
        "p": {
          "place": "web::public::public-attachment-type"
        },
        "a": {
          "place": "web::authenticated::authenticated-attachment-type"
        }
      },
      "capability": "create-attachment-type"
    },
    {
      "text": "The Product carries the caller into the saved record’s editor.",
      "kind": "product",
      "actor": "user",
      "entities": [],
      "contexts": {
        "p": {
          "place": "web::public::public-attachment-type"
        },
        "a": {
          "place": "web::authenticated::authenticated-attachment-type"
        }
      },
      "capability": "create-attachment-type"
    },
    {
      "text": "The caller supplies valid changes to the selected record’s supported information.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "p": {
          "place": "web::public::public-attachment-type"
        },
        "a": {
          "place": "web::authenticated::authenticated-attachment-type"
        }
      },
      "capability": "edit-attachment-type"
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
        "p": {
          "place": "web::public::public-attachment-type"
        },
        "a": {
          "place": "web::authenticated::authenticated-attachment-type"
        }
      },
      "capability": "edit-attachment-type"
    },
    {
      "text": "The Product saves the supplied Attachment type information through the implemented write.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "attachment-type",
          "effect": "changes",
          "facts": [
            "Name",
            "Comment",
            "Modified at"
          ]
        }
      ],
      "contexts": {
        "p": {
          "place": "web::public::public-attachment-type"
        },
        "a": {
          "place": "web::authenticated::authenticated-attachment-type"
        }
      },
      "capability": "edit-attachment-type"
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
      "target": "src/Entity/Base/TimestampTrait.php"
    }
  ]
}
---

# Create attachment type and edit achieved

## Trigger

The same caller follows the source-carried continuation: Create Type → Edit saved Type.

## Outcome

The saved or surviving record reaches its editor and the same caller’s subsequent valid edit is saved.
