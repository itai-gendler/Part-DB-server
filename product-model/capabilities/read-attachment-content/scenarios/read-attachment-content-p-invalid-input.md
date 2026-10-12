---
{
  "kind": "validation",
  "routes": {
    "route": "Public Web"
  },
  "steps": [
    {
      "text": "The caller submits the failing input: The reference is invalid or has no usable internal content source.",
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
      "text": "The Product does not complete read file reference content because the reference is invalid or has no usable internal content source.",
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

# Read attachment content — Public Web invalid input

## Trigger

The reference is invalid or has no usable internal content source.

## Outcome

The reference is invalid or has no usable internal content source. No successful read attachment content result is asserted.
