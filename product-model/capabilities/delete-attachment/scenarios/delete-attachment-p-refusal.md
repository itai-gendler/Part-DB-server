---
{
  "kind": "validation",
  "routes": {
    "route": "Public Web"
  },
  "steps": [
    {
      "text": "The caller requests delete file reference through this contract.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::public::public-part"
        }
      }
    },
    {
      "text": "The Product stops the requested delete attached-file reference operation at its actual refusal boundary.",
      "kind": "product",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::public::public-part"
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

# Delete attachment — Public Web refusal

## Trigger

The caller requests delete attachment and reaches its closed entry or disabled-control result.

## Outcome

The requested delete attachment result is withheld; no accepted change or removal of the requested subject is produced.
