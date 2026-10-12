---
{
  "kind": "validation",
  "routes": {
    "route": "Public Web"
  },
  "steps": [
    {
      "text": "The caller requests read file reference content through this contract.",
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
      "text": "The Product stops the requested read attached-file reference content operation at its actual refusal boundary.",
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

# Read attachment content — Public Web refusal

## Trigger

The caller requests read attachment content and reaches its closed entry or disabled-control result.

## Outcome

The requested read attachment content result is withheld; no accepted change or removal of the requested subject is produced.
