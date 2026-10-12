---
{
  "kind": "validation",
  "routes": {
    "route": "Authenticated Web"
  },
  "steps": [
    {
      "text": "The caller submits the failing input: The requested attached-file reference does not resolve.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::authenticated::authenticated-attachment"
        }
      }
    },
    {
      "text": "The Product does not complete read file reference metadata because the requested attached-file reference does not resolve.",
      "kind": "product",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::authenticated::authenticated-attachment"
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

# Read attachment metadata — Authenticated Web invalid input

## Trigger

The requested attached-file reference does not resolve.

## Outcome

The requested attached-file reference does not resolve. No successful read attachment metadata result is asserted.
