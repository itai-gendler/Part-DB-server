---
{
  "kind": "edge",
  "routes": {
    "route": "Authenticated Web"
  },
  "steps": [
    {
      "text": "The caller submits a supported external file download that fails during form processing.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::authenticated::authenticated-part"
        }
      }
    },
    {
      "text": "The Product attempts the external download and reports its distinguished failure; an otherwise-empty failed file reference may be discarded.",
      "kind": "product",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::authenticated::authenticated-part"
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

# Create attachment — Download failure is reported; otherwise-empty failed Part Attachment may be discarded (Authenticated Web)

## Trigger

The caller submits a supported external file download that fails during form processing.

## Outcome

A failed, otherwise-empty new attachment can be discarded by the submit handler; a successful saved file or whole-form rollback is not asserted.
