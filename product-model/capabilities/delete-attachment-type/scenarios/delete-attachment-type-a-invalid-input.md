---
{
  "kind": "validation",
  "routes": {
    "route": "Authenticated Web"
  },
  "steps": [
    {
      "text": "The caller submits the failing input: The selected reference is absent or the required Web confirmation is invalid; no accepted removal is performed.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::authenticated::authenticated-attachment-type"
        }
      }
    },
    {
      "text": "The Product does not remove the requested record when its confirmation or reference is invalid.",
      "kind": "product",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::authenticated::authenticated-attachment-type"
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
    }
  ]
}
---

# Delete attachment type — Authenticated Web invalid input

## Trigger

The selected reference is absent or the required Web confirmation is invalid; no accepted removal is performed.

## Outcome

The selected reference is absent or the required Web confirmation is invalid; no accepted removal is performed. No successful delete attachment type result is asserted.
