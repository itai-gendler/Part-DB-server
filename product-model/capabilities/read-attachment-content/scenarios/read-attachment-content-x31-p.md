---
{
  "kind": "edge",
  "routes": {
    "route": "Public Web"
  },
  "steps": [
    {
      "text": "The caller requests existing internal content whose stored file is missing or unavailable.",
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
      "text": "The Product reads the Attachment internal reference and content classification before testing its available file.",
      "kind": "product",
      "actor": "user",
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
          "place": "web::public::public-attachment"
        }
      }
    },
    {
      "text": "The Product rejects the missing file.",
      "kind": "product",
      "actor": "user",
      "entities": [],
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controller/AttachmentFileController.php"
    }
  ]
}
---

# Read attachment content — Missing/unavailable internal content fails (Public Web)

## Trigger

The caller requests existing internal content whose stored file is missing or unavailable.

## Outcome

Missing or unavailable internal content produces the distinguished failure.
